---
title: Referencias a elementos declarados (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- declared elements [Visual Basic]
- references [Visual Basic], declared elements
- qualified names [Visual Basic]
ms.assetid: d6301709-f4cc-4b7a-b8ba-80898f14ab46
ms.openlocfilehash: de4d42803be48a87f4dfd37a92b1b22fa2d5c554
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2019
ms.locfileid: "72524555"
---
# <a name="references-to-declared-elements-visual-basic"></a>Referencias a elementos declarados (Visual Basic)
Cuando el código hace referencia a un elemento declarado, el compilador Visual Basic coincide con el nombre de la referencia a la declaración adecuada de ese nombre. Si se declara más de un elemento con el mismo nombre, puede controlar a qué elementos se va a hacer referencia *calificando* su nombre.  
  
 El compilador intenta buscar una referencia de nombre a una declaración de nombre con el *ámbito más restringido*. Esto significa que comienza con el código que hace la referencia y funciona de forma saliente a través de los niveles sucesivos de elementos contenedores.  
  
 En el ejemplo siguiente se muestran referencias a dos variables con el mismo nombre. En el ejemplo se declaran dos variables, cada una con nombre `totalCount`, en distintos niveles de ámbito en el `container` de módulos. Cuando el procedimiento `showCount` muestra `totalCount` sin calificación, el compilador de Visual Basic resuelve la referencia a la declaración con el ámbito más restringido, es decir, la declaración local dentro de `showCount`. Cuando califica `totalCount` con el módulo contenedor `container`, el compilador resuelve la referencia a la declaración con el ámbito más amplio.  
  
```vb  
' Assume these two modules are both in the same assembly.  
Module container  
    Public totalCount As Integer = 1  
    Public Sub showCount()  
        Dim totalCount As Integer = 6000  
        ' The following statement displays the local totalCount (6000).  
        MsgBox("Unqualified totalCount is " & CStr(totalCount))  
        ' The following statement displays the module's totalCount (1).  
        MsgBox("container.totalCount is " & CStr(container.totalCount))  
    End Sub  
End Module  
Module callingModule  
    Public Sub displayCount()  
        container.showCount()  
        ' The following statement displays the containing module's totalCount (1).  
        MsgBox("container.totalCount is " & CStr(container.totalCount))  
    End Sub  
End Module  
```  
  
## <a name="qualifying-an-element-name"></a>Calificar un nombre de elemento  
 Si desea invalidar este proceso de búsqueda y especificar un nombre declarado en un ámbito más amplio, debe *calificar* el nombre con el elemento contenedor del ámbito más amplio. En algunos casos, es posible que también tenga que calificar el elemento contenedor.  
  
 Calificar un nombre significa que lo antepone en la instrucción de origen con información que identifica dónde se define el elemento de destino. Esta información se denomina *cadena de calificación*. Puede incluir uno o varios espacios de nombres y un módulo, clase o estructura.  
  
 La cadena de calificación debe especificar de forma inequívoca el módulo, la clase o la estructura que contiene el elemento de destino. A su vez, el contenedor se puede ubicar en otro elemento contenedor, normalmente un espacio de nombres. Es posible que deba incluir varios elementos contenedores en la cadena de calificación.  
  
#### <a name="to-access-a-declared-element-by-qualifying-its-name"></a>Para tener acceso a un elemento declarado calificando su nombre  
  
1. Determine la ubicación en la que se ha definido el elemento. Esto puede incluir un espacio de nombres, o incluso una jerarquía de espacios de nombres. Dentro del espacio de nombres de nivel inferior, el elemento debe estar incluido en un módulo, una clase o una estructura.  
  
    ```vb  
    ' Assume the following hierarchy exists outside your code.  
    Namespace outerSpace  
        Namespace innerSpace  
            Module holdsTotals  
                Public Structure totals  
                    Public thisTotal As Integer  
                    Public Shared grandTotal As Long  
                End Structure  
            End Module  
        End Namespace  
    End Namespace  
    ```  
  
2. Determinar una ruta de acceso de calificación en función de la ubicación del elemento de destino. Comience con el espacio de nombres de nivel superior, continúe con el espacio de nombres de nivel más bajo y termine con el módulo, la clase o la estructura que contiene el elemento de destino. Cada elemento de la ruta de acceso debe contener el elemento que le sigue.  
  
     `outerSpace` → `innerSpace` → `holdsTotals` → `totals`  
  
3. Preparar la cadena de calificación para el elemento de destino. Coloque un punto (`.`) después de cada elemento de la ruta de acceso. La aplicación debe tener acceso a todos los elementos de la cadena de calificación.  
  
    ```vb  
    outerSpace.innerSpace.holdsTotals.totals.  
    ```  
  
4. Escriba la expresión o instrucción de asignación que hace referencia al elemento de destino de la manera normal.  
  
    ```vb  
    grandTotal = 9000  
    ```  
  
5. Anteponga el nombre del elemento de destino a la cadena de calificación. El nombre debe seguir inmediatamente al punto (`.`) que sigue al módulo, la clase o la estructura que contiene el elemento.  
  
    ```vb  
    ' Assume the following module is part of your code.  
    Module accessGrandTotal  
        Public Sub setGrandTotal()  
            outerSpace.innerSpace.holdsTotals.totals.grandTotal = 9000  
        End Sub  
    End Module  
    ```  
  
6. El compilador usa la cadena de calificación para encontrar una declaración clara y no ambigua a la que puede coincidir con la referencia del elemento de destino.  
  
 También podría tener que calificar una referencia de nombre si la aplicación tiene acceso a más de un elemento de programación con el mismo nombre. Por ejemplo, los espacios de nombres <xref:System.Windows.Forms> y <xref:System.Web.UI.WebControls> contienen una clase `Label` (<xref:System.Windows.Forms.Label?displayProperty=nameWithType> y <xref:System.Web.UI.WebControls.Label?displayProperty=nameWithType>). Si su aplicación usa ambos o si define su propia clase `Label`, debe distinguir los distintos objetos `Label`. Incluya el espacio de nombres o el alias de importación en la declaración de variable. En el ejemplo siguiente se usa el alias de importación.  
  
```vb  
' The following statement must precede all your declarations.  
Imports win = System.Windows.Forms, web = System.Web.UI.WebControls  
' The following statement references the Windows.Forms.Label class.  
Dim winLabel As New win.Label()  
```  
  
## <a name="members-of-other-containing-elements"></a>Miembros de otros elementos contenedores  
 Cuando se usa un miembro no compartido de otra clase o estructura, primero se debe calificar el nombre del miembro con una variable o expresión que apunte a una instancia de la clase o estructura. En el ejemplo siguiente, `demoClass` es una instancia de una clase denominada `class1`.  
  
```vb  
Dim demoClass As class1 = New class1()  
demoClass.someSub[(argumentlist)]  
```  
  
 No se puede usar el propio nombre de clase para calificar a un miembro que no se [comparte](../../../../visual-basic/language-reference/modifiers/shared.md). Primero debe crear una instancia en una variable de objeto (en este caso `demoClass`) y, a continuación, hacer referencia a ella mediante el nombre de la variable.  
  
 Si una clase o estructura tiene un miembro de `Shared`, puede calificar ese miembro con el nombre de la clase o la estructura o con una variable o expresión que apunte a una instancia.  
  
 Un módulo no tiene ninguna instancia independiente, y todos sus miembros se `Shared` de forma predeterminada. Por lo tanto, puede calificar un miembro de módulo con el nombre de módulo.  
  
 En el ejemplo siguiente se muestran referencias completas a los procedimientos de miembros de módulo. En el ejemplo se declaran dos procedimientos `Sub`, ambos denominados `perform`, en módulos diferentes de un proyecto. Cada una se puede especificar sin calificación dentro de su propio módulo, pero se debe calificar si se hace referencia a ella desde cualquier otra parte. Dado que la referencia final de `module3` no cumple `perform`, el compilador no puede resolver esa referencia.  
  
```vb  
' Assume these three modules are all in the same assembly.  
Module module1  
    Public Sub perform()  
        MsgBox("module1.perform() now returning")  
    End Sub  
End Module  
Module module2  
    Public Sub perform()  
        MsgBox("module2.perform() now returning")  
    End Sub  
    Public Sub doSomething()  
        ' The following statement calls perform in module2, the active module.  
        perform()  
        ' The following statement calls perform in module1.  
        module1.perform()  
    End Sub  
End Module  
Module module3  
    Public Sub callPerform()  
        ' The following statement calls perform in module1.  
        module1.perform()  
        ' The following statement makes an unresolvable name reference  
        ' and therefore generates a COMPILER ERROR.  
        perform() ' INVALID statement  
    End Sub  
End Module  
```  
  
## <a name="references-to-projects"></a>Referencias a proyectos  
 Para usar elementos [públicos](../../../../visual-basic/language-reference/modifiers/public.md) definidos en otro proyecto, primero debe establecer una *referencia* al ensamblado o la biblioteca de tipos del proyecto. Para establecer una referencia, haga clic en **Agregar referencia** en el menú **proyecto** o use la opción del compilador [de línea de comandos-Reference (Visual Basic)](../../../../visual-basic/reference/command-line-compiler/reference.md) .  
  
 Por ejemplo, puede utilizar el modelo de objetos XML del .NET Framework. Si establece una referencia al espacio de nombres <xref:System.Xml>, puede declarar y usar cualquiera de sus clases, como <xref:System.Xml.XmlDocument>. En el ejemplo siguiente se usa <xref:System.Xml.XmlDocument>.  
  
```vb  
' Assume this project has a reference to System.Xml  
' The following statement creates xDoc as an XML document object.  
Dim xDoc As System.Xml.XmlDocument  
```  
  
## <a name="importing-containing-elements"></a>Importar elementos contenedores  
 Puede usar la [instrucción Imports (espacio de nombres y tipo de .net)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) para *importar* los espacios de nombres que contienen los módulos o las clases que desea usar. Esto le permite hacer referencia a los elementos definidos en un espacio de nombres importado sin calificar totalmente sus nombres. En el ejemplo siguiente se vuelve a escribir el ejemplo anterior para importar el espacio de nombres <xref:System.Xml>.  
  
```vb  
' Assume this project has a reference to System.Xml  
' The following statement must precede all your declarations.  
Imports System.Xml  
' The following statement creates xDoc as an XML document object.  
Dim xDoc As XmlDocument  
```  
  
 Además, la instrucción `Imports` puede definir un *alias de importación* para cada espacio de nombres importado. Esto puede hacer que el código fuente sea más corto y más fácil de leer. En el ejemplo siguiente se vuelve a escribir el ejemplo anterior para utilizar `xD` como un alias para el espacio de nombres <xref:System.Xml>.  
  
```vb  
' Assume this project has a reference to System.Xml  
' The following statement must precede all your declarations.  
Imports xD = System.Xml  
' The following statement creates xDoc as an XML document object.  
Dim xDoc As xD.XmlDocument  
```  
  
 La instrucción `Imports` no hace que los elementos de otros proyectos estén disponibles para la aplicación. Es decir, no se ocupa del establecimiento de una referencia. La importación de un espacio de nombres solo quita el requisito de calificar los nombres definidos en ese espacio de nombres.  
  
 También puede usar la instrucción `Imports` para importar módulos, clases, estructuras y enumeraciones. Después, puede usar los miembros de estos elementos importados sin calificación. Sin embargo, siempre debe calificar miembros no compartidos de clases y estructuras con una variable o una expresión que se evalúe como una instancia de la clase o estructura.  
  
## <a name="naming-guidelines"></a>Instrucciones de nomenclatura  
 Cuando se definen dos o más elementos de programación con el mismo nombre, puede producirse una *ambigüedad de nombres* cuando el compilador intenta resolver una referencia a ese nombre. Si hay más de una definición en el ámbito, o si no hay ninguna definición en el ámbito, la referencia es irresoluble. Para obtener un ejemplo, vea "ejemplo de referencia completa" en esta página de ayuda.  
  
 Puede evitar la ambigüedad de nombres proporcionando a todos los elementos nombres únicos. Después, puede hacer referencia a cualquier elemento sin tener que calificar su nombre con un espacio de nombres, un módulo o una clase. También reduce las posibilidades de hacer referencia accidental al elemento equivocado.  
  
## <a name="shadowing"></a>Sombreado  
 Cuando dos elementos de programación comparten el mismo nombre, uno de ellos puede ocultar, o *sombrear*, el otro. Un elemento sombreado no está disponible como referencia; en su lugar, cuando el código usa el nombre del elemento con sombra, el compilador Visual Basic lo resuelve en el elemento de sombreado. Para obtener una explicación más detallada de los ejemplos, vea [sombrear en Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md).  
  
## <a name="see-also"></a>Vea también

- [Nombres de elementos declarados](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)
- [Características de los elementos declarados](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md)
- [Administrar propiedades de soluciones y proyectos](/visualstudio/ide/managing-project-and-solution-properties)
- [Variables](../../../../visual-basic/programming-guide/language-features/variables/index.md)
- [Imports (instrucción), espacio de nombres y tipo .NET](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)
- [New (operador)](../../../../visual-basic/language-reference/operators/new-operator.md)
- [Public](../../../../visual-basic/language-reference/modifiers/public.md)
