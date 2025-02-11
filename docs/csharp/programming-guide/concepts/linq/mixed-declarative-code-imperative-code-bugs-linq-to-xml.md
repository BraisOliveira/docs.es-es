---
title: Errores en código declarativo-imperativo mixto (LINQ to XML) (C#)
ms.date: 07/20/2015
ms.assetid: fada62d0-0680-4e73-945a-2b00d7a507af
ms.openlocfilehash: 30760999a264c81e16104c0c9b112d442ce66121
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/19/2019
ms.locfileid: "69591626"
---
# <a name="mixed-declarative-codeimperative-code-bugs-linq-to-xml-c"></a>Errores en códigos declarativos/imperativos mixtos (LINQ to XML) (C#)
[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] incluye numerosos métodos que le permiten modificar directamente un árbol XML. Puede agregar elementos, eliminarlos, cambiar sus contenidos, agregar atributos, etc. Esta interfaz de programación se describe en [Modificar árboles XML (LINQ to XML) (C#)](./in-memory-xml-tree-modification-vs-functional-construction-linq-to-xml.md). Si está llevando a cabo una iteración por uno de los ejes, como puede ser <xref:System.Xml.Linq.XContainer.Elements%2A>, y está modificando el árbol XML a medida que recorre el eje, es posible que acabe encontrando errores extraños.  
  
 En ocasiones, a este problema se le conoce como "El problema de Halloween".  
  
## <a name="definition-of-the-problem"></a>Definición del problema  
 Cuando se escribe cierto código utilizando LINQ para iterar por una colección, se utiliza un código de estilo declarativo. Es un método que se aproxima más a definir *qué* es lo que quiere, en vez de especificar *cómo* quiere hacerlo. Si escribe un código que 1) obtenga el primer elemento, 2) lo compruebe con una cierta condición, 3) lo modifique y 4) lo coloque nuevamente en la lista, entonces se trata de un código imperativo. Le está indicando al ordenador *cómo* hacer lo que quiere.  
  
 Si se combinan ambos estilos de código en una misma operación, es cuando aparecen los problemas. Considere el siguiente caso:  
  
 Suponga que tiene una lista vinculada que contiene tres elementos (a, b y c):  
  
 `a -> b -> c`  
  
 Ahora, suponga que desea recorrer la lista vinculada y añadir tres nuevos elementos (a', b' y c'). Desea que la lista vinculada resultante tenga el siguiente aspecto:  
  
 `a -> a' -> b -> b' -> c -> c'`  
  
 De forma que escribe un código que recorre la lista y, que para cada elemento, añade uno nuevo justo después. Lo que ocurrirá es que el código encontrará primero el elemento `a` e insertará `a'` justo después. Ahora, el código pasará al siguiente nodo de la lista, que en este momento será `a'` Entonces agregará un nuevo elemento a la lista, `a''`.  
  
 ¿Cómo se puede resolver esto en un caso real? Una opción es realizar una copia de la lista vinculada original y crear una lista completamente nueva. O bien, si únicamente está escribiendo un código imperativo, puede encontrar el primer elemento, añadir el nuevo y, a continuación, avanzar dos elementos en la lista, pasando así por encima del elemento recién agregado.  
  
## <a name="adding-while-iterating"></a>Agregar a medida que se va iterando  
 Suponga, por ejemplo, que desea escribir un cierto código que, para cada elemento de un árbol, cree un elemento duplicado:  
  
```csharp  
XElement root = new XElement("Root",  
    new XElement("A", "1"),  
    new XElement("B", "2"),  
    new XElement("C", "3")  
);  
foreach (XElement e in root.Elements())  
    root.Add(new XElement(e.Name, (string)e));  
```  
  
 Este código entrará en un bucle infinito. La instrucción `foreach` lleva a cabo una iteración a lo largo del eje `Elements()`, agregando nuevos elementos al elemento `doc`. Al final, acaba realizando dicha iteración por los elementos que se acaban de agregar. Y, dado que coloca los nuevos objetos en cada una de las iteraciones del bucle, llegará un momento en el que consuma toda la memoria disponible.  
  
 Puede resolver este problema almacenando en memoria la colección mediante el operador de consulta estándar <xref:System.Linq.Enumerable.ToList%2A>, de la siguiente forma:  
  
```csharp  
XElement root = new XElement("Root",  
    new XElement("A", "1"),  
    new XElement("B", "2"),  
    new XElement("C", "3")  
);  
foreach (XElement e in root.Elements().ToList())  
    root.Add(new XElement(e.Name, (string)e));  
Console.WriteLine(root);  
```  
  
 Ahora el código funciona correctamente. El árbol XML resultante es como sigue:  
  
```xml  
<Root>  
  <A>1</A>  
  <B>2</B>  
  <C>3</C>  
  <A>1</A>  
  <B>2</B>  
  <C>3</C>  
</Root>  
```  
  
## <a name="deleting-while-iterating"></a>Eliminar a medida que se va iterando  
 Si desea eliminar todos los nodos que se encuentren en un cierto nivel, podría tener la tentación de escribir un código como el que sigue:  
  
```csharp  
XElement root = new XElement("Root",  
    new XElement("A", "1"),  
    new XElement("B", "2"),  
    new XElement("C", "3")  
);  
foreach (XElement e in root.Elements())  
    e.Remove();  
Console.WriteLine(root);  
```  
  
 Sin embargo, no realiza la tarea que deseaba. En esta situación, tras eliminar el primer elemento (A), éste se elimina del árbol XML contenido en la raíz, con lo que el código del método Elements encargado de la iteración no podrá encontrar el siguiente elemento.  
  
 Este código anterior genera el siguiente resultado:  
  
```xml  
<Root>  
  <B>2</B>  
  <C>3</C>  
</Root>  
```  
  
 De nuevo, la solución pasa por llamar a <xref:System.Linq.Enumerable.ToList%2A> para materializar la colección, de la siguiente forma:  
  
```csharp  
XElement root = new XElement("Root",  
    new XElement("A", "1"),  
    new XElement("B", "2"),  
    new XElement("C", "3")  
);  
foreach (XElement e in root.Elements().ToList())  
    e.Remove();  
Console.WriteLine(root);  
```  
  
 Esto genera el siguiente resultado:  
  
```xml  
<Root />  
```  
  
 Como alternativa, puede eliminar la iteración entera llamando a <xref:System.Xml.Linq.XElement.RemoveAll%2A> en el elemento primario:  
  
```csharp  
XElement root = new XElement("Root",  
    new XElement("A", "1"),  
    new XElement("B", "2"),  
    new XElement("C", "3")  
);  
root.RemoveAll();  
Console.WriteLine(root);  
```  
  
## <a name="why-cant-linq-automatically-handle-this"></a>¿Por qué LINQ no puede controlar este comportamiento?  
 Una posible aproximación sería trasladar todo a memoria en vez de realizar evaluaciones diferidas. No obstante, esto resultaría muy costoso en términos de rendimiento y de utilización de la memoria. De hecho, si LINQ y (LINQ to XML) utilizaran este método, no sería viable en situaciones reales.  
  
 Otra posible aproximación consiste en utilizar una cierta sintaxis transaccional en LINQ y hacer que el compilador intente analizar el código para determinar si es necesario materializar alguna colección en particular. Sin embargo, puede resultar extremadamente complejo analizar todo el código que pueda tener efectos secundarios. Observe el código siguiente:  
  
```csharp  
var z =  
    from e in root.Elements()  
    where TestSomeCondition(e)  
    select DoMyProjection(e);  
```  
  
 Un código de análisis así necesitaría analizar los métodos TestSomeCondition y DoMyProjection, así como todos los métodos a los que llaman, con el fin de determinar si existe código con efectos secundarios. Pero no bastaría con que el código de análisis buscara código que tuviera efectos secundarios. Solo debería seleccionar aquel código que tuviera efectos secundarios sobre los elementos secundarios de `root` en este caso en particular.  
  
 LINQ to XML no realiza ese tipo de análisis.  
  
 Es responsabilidad del programador evitar este tipo de problemas.  
  
## <a name="guidance"></a>Orientación  
 Primeramente, no mezcle código imperativo con código declarativo.  
  
 Incluso en el caso de que conozca con precisión la semántica de las colecciones y de los métodos que modifican el árbol XML y escriba un código que evite este tipo de problemas, éste deberá ser mantenido por otros desarrolladores en un futuro, y es posible que éstos no estén al tanto de esos problemas. Si mezcla estilos de programación declarativa e imperativa, el código resultará más complicado.  
  
 Si escribe código que materialice una colección de forma que se eviten todos estos problemas, incluya en él comentarios de forma que los programadores encargados de su mantenimiento puedan comprender la problemática.  
  
 En segundo lugar, si el rendimiento y otras consideraciones lo permiten, utilice únicamente código declarativo. No modifique el árbol XML existente. Genere uno nuevo.  
  
```csharp  
XElement root = new XElement("Root",  
    new XElement("A", "1"),  
    new XElement("B", "2"),  
    new XElement("C", "3")  
);  
XElement newRoot = new XElement("Root",  
    root.Elements(),  
    root.Elements()  
);  
Console.WriteLine(newRoot);  
```  
 