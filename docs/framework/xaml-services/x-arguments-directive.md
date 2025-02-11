---
title: x:Arguments (Directiva)
ms.date: 03/30/2017
helpviewer_keywords:
- x:Arguments directive [XAML Services]
- Arguments directive in XAML [XAML Services]
- XAML [XAML Services], x:Arguments directive
ms.assetid: 87cc10b0-b610-4025-b6b0-ab27ca27c92e
ms.openlocfilehash: 338286b417c78b7cceeb30188e888928a15607cd
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2019
ms.locfileid: "73458656"
---
# <a name="xarguments-directive"></a>x:Arguments (Directiva)
Empaqueta los argumentos de una declaración de elemento de objeto constructor sin parámetros en XAML o para una declaración de objeto Factory Method.  
  
## <a name="xaml-element-usage-nonparameterless-constructor"></a>Uso de elementos XAML (constructor sin parámetros)  
  
```xaml  
<object ...>  
  <x:Arguments>  
    oneOrMoreObjectElements  
  </x:Arguments>  
</object>  
```  
  
## <a name="xaml-element-usage-factory-method"></a>Uso de elementos XAML (Factory Method)  
  
```xaml  
<object x:FactoryMethod="methodName"...>  
  <x:Arguments>  
    oneOrMoreObjectElements  
  </x:Arguments>  
</object>  
```  
  
## <a name="xaml-values"></a>Valores XAML  
  
|||  
|-|-|  
|`oneOrMoreObjectElements`|Uno o más elementos de objeto que especifican los argumentos que se van a pasar al constructor o Factory Method sin parámetros de respaldo.<br /><br /> El uso típico es usar el texto de inicialización dentro de los elementos de objeto para especificar los valores de argumento reales. Vea la sección ejemplos.<br /><br /> El orden de los elementos es significativo. Los tipos XAML en orden deben coincidir con los tipos y el orden del tipo del constructor de respaldo o de Factory Method sobrecarga.|  
|`methodName`|Nombre del Factory Method que debe procesar cualquier argumento de `x:Arguments`.|  
  
## <a name="dependencies"></a>Dependencias  
 `x:FactoryMethod` puede modificar el ámbito y el comportamiento donde se aplica `x:Arguments`.  
  
 Si no se especifica ningún `x:FactoryMethod`, `x:Arguments` se aplica a las firmas alternativas (no predeterminadas) de los constructores de respaldo.  
  
 Si se especifica `x:FactoryMethod`, `x:Arguments` se aplica a una sobrecarga del método con nombre.  
  
## <a name="remarks"></a>Comentarios  
 XAML 2006 puede admitir la inicialización no predeterminada a través del texto de inicialización. Sin embargo, la aplicación práctica de una técnica de construcción de texto de inicialización es limitada. El texto de inicialización se trata como una sola cadena de texto; por lo tanto, solo agrega funcionalidad para la inicialización de un solo parámetro, a menos que se defina un convertidor de tipos para el comportamiento de construcción que puede analizar elementos de información personalizados y delimitadores personalizados de la cadena. Además, la cadena de texto a la lógica del objeto es potencialmente un convertidor de tipos predeterminado nativo del analizador XAML para controlar los primitivos que no sean una cadena true.  
  
 El uso de `x:Arguments` XAML no es el uso de elementos de propiedad en el sentido típico, porque el marcado de directivas no hace referencia al tipo del elemento de objeto contenedor. Es más similar a otras directivas como `x:Code` donde el elemento marca un intervalo en el que el marcado debe interpretarse como distinto del predeterminado para el contenido secundario. En este caso, el tipo XAML de cada elemento de objeto comunica información sobre los tipos de argumento, que los analizadores XAML usan para determinar qué constructor específico Factory Method firma a la que está intentando hacer referencia un uso `x:Arguments`.  
  
 `x:Arguments` para un elemento de objeto que se va a construir debe preceder a cualquier otro elemento de propiedad, contenido, texto interno o cadena de inicialización del elemento de objeto. Los elementos de objeto dentro de `x:Arguments` pueden incluir atributos y cadenas de inicialización, según lo permitido por ese tipo XAML y su constructor de respaldo o Factory Method. En el caso del objeto o de los argumentos, puede especificar tipos XAML personalizados o tipos XAML que, de otro modo, se encuentran fuera del espacio de nombres XAML predeterminado haciendo referencia a las asignaciones de prefijo establecidas.  
  
 Los procesadores XAML usan las siguientes directrices para determinar cómo se deben usar los argumentos especificados en `x:Arguments` para construir un objeto. Si se especifica `x:FactoryMethod`, la información se compara con la `x:FactoryMethod` especificada (tenga en cuenta que el valor de `x:FactoryMethod` es el nombre del método y el método con nombre puede tener sobrecargas. Si no se especifica `x:FactoryMethod`, la información se compara con el conjunto de todas las sobrecargas del constructor público del objeto. A continuación, la lógica de procesamiento de XAML compara el número de parámetros y selecciona la sobrecarga con aridad coincidente. Si hay más de una coincidencia, el procesador XAML debe comparar los tipos de los parámetros en función de los tipos XAML de los elementos de objeto proporcionados. Si todavía hay más de una coincidencia, el comportamiento del procesador XAML es indefinido. Si se especifica un `x:FactoryMethod` pero no se puede resolver el método, un procesador XAML debe producir una excepción.  
  
 Es técnicamente posible el uso de atributos XAML `<x:Arguments>string</x:Arguments>`. Sin embargo, esto no proporciona ninguna funcionalidad más allá de lo que se podía hacer de otro modo mediante el texto de inicialización y convertidores de tipos, y el uso de esta sintaxis no es la intención de diseño de las características de Factory Method de XAML 2009.  
  
## <a name="examples"></a>Ejemplos  
 En el ejemplo siguiente se muestra una firma de constructor sin parámetros, que es el uso de XAML de `x:Arguments` que tiene acceso a esa firma.  
  
```csharp  
public class Food {  
    private string _name;  
    private Int32 _calories;  
    public Food(string name, Int32 calories) {  
        _name=name;  
        _calories=calories;  
    }  
}  
```  
  
```xaml  
<my:Food>  
    <x:Arguments>  
        <x:String>Apple</x:String>  
        <x:Int32>150</x:Int32>  
    </x:Arguments>  
</my:Food>  
```  
  
 En el ejemplo siguiente se muestra un destino Factory Method firma, el uso de XAML de `x:Arguments` que tiene acceso a esa firma.  
  
```csharp  
public Food TryLookupFood(string name)  
{  
  switch (name) {  
    case "Apple": return new Food("Apple",150);  
    case "Chocolate": return new Food("Chocolate",200);  
    case "Cheese": return new Food("Cheese", 450);  
    default: {return new Food(name,0);  
  }  
}  
```  
  
```xaml  
<my:Food x:FactoryMethod="TryLookupFood">  
    <x:Arguments>  
        <x:String>Apple</x:String>  
    </x:Arguments>  
</my:Food>  
```  
  
## <a name="see-also"></a>Vea también

- [Definir tipos personalizados para usarlos con los servicios XAML de .NET Framework](defining-custom-types-for-use-with-net-framework-xaml-services.md)
- [Información general sobre XAML (WPF)](../../desktop-wpf/fundamentals/xaml.md)
