---
title: Programación orientada a objetos (C#)
ms.date: 07/20/2015
ms.assetid: 89574786-65ef-4335-88bc-fbacd094f183
ms.openlocfilehash: 121d2e43f6896179756067e661be6d7960a1ee64
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/01/2019
ms.locfileid: "73418041"
---
# <a name="object-oriented-programming-c"></a>Programación orientada a objetos (C#)

C# proporciona compatibilidad completa para la programación orientada a objetos incluida la encapsulación, la herencia y el polimorfismo.

La *encapsulación* significa que un grupo de propiedades, métodos y otros miembros relacionados se tratan como una sola unidad u objeto.

La *herencia* describe la posibilidad de crear nuevas clases basadas en una clase existente.

El *polimorfismo* significa que puede tener múltiples clases que se pueden usar de manera intercambiable, aunque cada clase implementa las mismas propiedades o los mismos métodos de maneras diferentes.

En esta sección se describen los conceptos siguientes:

- [Clases y objetos](#Classes)

  - [Miembros de clases](#Members)

    - [Propiedades y campos](#Properties)

    - [Métodos](#Methods)

    - [Constructores](#Constructors)

    - [Finalizadores](#Finalizers)

    - [Eventos](#Events)

    - [Clases anidadas](#NestedClasses)

  - [Modificadores y niveles de acceso](#AccessModifiers)

  - [Creación de instancias de las clases](#InstantiatingClasses)

  - [Clases y miembros estáticos](#Static)

  - [Tipos anónimos](#AnonymousTypes)

- [Herencia](#Inheritance)

  - [Reemplazar miembros](#Overriding)

- [Interfaces](#Interfaces)

- [Genéricos](#Generics)

- [Delegados](#Delegates)

## <a name="Classes"></a> Clases y objetos

Los términos *clase* y *objeto* se usan a veces indistintamente pero, en realidad, las clases describen el *tipo* de los objetos, mientras que los objetos son *instancias* de clases que se pueden usar. Así, la acción de crear un objeto se denomina *creación de instancias*. Con la analogía de plano, una clase es un plano y un objeto es un edificio construido a partir de ese plano.

Para definir una clase:

```csharp
class SampleClass
{
}
```

C# también proporciona una versión ligera de las clases denominadas *estructuras*, que resultan útiles cuando es necesario crear una matriz grande de objetos y no quiere usar demasiada memoria para ello.

Para definir una estructura:

```csharp
struct SampleStruct
{
}
```

Para obtener más información, consulte:

- [class](../../language-reference/keywords/class.md)

- [struct](../../language-reference/keywords/struct.md)

### <a name="Members"></a> Miembros de clases

Cada clase puede tener distintos *miembros de clase*, entre los que se incluyen las propiedades que describen los datos de clase, los métodos que definen el comportamiento de la clase y los eventos que proporcionan comunicación entre distintos objetos y clases.

#### <a name="Properties"></a> Propiedades y campos

Los campos y propiedades representan información que contiene un objeto. Los campos se parecen a las variables ya que se pueden leer y establecer directamente.

Para definir un campo:

```csharp
class SampleClass
{
    public string sampleField;
}
```

Las propiedades tienen procedimientos get y set, que proporcionan un mayor control sobre la forma en que se establecen o devuelven los valores.

C# le permite crear un campo privado para almacenar el valor de propiedad o usar las denominadas propiedades de implementación automática que crean este campo en segundo plano automáticamente y proporcionan la lógica básica para los procedimientos de propiedad.

Para definir una propiedad implementada automáticamente:

```csharp
class SampleClass
{
    public int SampleProperty { get; set; }
}
```

Si necesita realizar algunas operaciones adicionales para leer y escribir el valor de propiedad, defina un campo para almacenar el valor de propiedad y proporcione la lógica básica para almacenarlo y recuperar lo:

```csharp
class SampleClass
{
    private int _sample;
    public int Sample
    {
        // Return the value stored in a field.
        get { return _sample; }
        // Store the value in the field.
        set { _sample = value; }
    }
}
```

La mayoría de las propiedades tienen métodos o procedimientos tanto para establecer como para obtener el valor de propiedad. Sin embargo, se pueden crear propiedades de solo lectura o solo escritura para restringir su modificación o lectura. En C#, se puede omitir el método de propiedad `get` o `set`. En cambio, las propiedades implementadas automáticamente no pueden ser de solo lectura o de solo escritura.

Para obtener más información, consulte:

- [get](../../language-reference/keywords/get.md)

- [set](../../language-reference/keywords/set.md)

#### <a name="Methods"></a> Métodos

Un *método* es una acción que un objeto puede realizar.

Para definir un método de una clase:

```csharp
class SampleClass
{
    public int sampleMethod(string sampleParam)
    {
        // Insert code here
    }
}
```

Una clase puede tener varias implementaciones o *sobrecargas* del mismo método que se diferencian en el número de parámetros o de tipos de parámetro.

Para sobrecargar un método:

```csharp
public int sampleMethod(string sampleParam) {};
public int sampleMethod(int sampleParam) {}
```

En la mayoría de los casos, un método se declara dentro de una definición de clase. En cambio, C# también admite los *métodos de extensión*, que le permiten agregar métodos a una clase existente fuera de la definición de la clase actual.

Para obtener más información, consulte:

- [Métodos](../classes-and-structs/methods.md)

- [Métodos de extensión](../classes-and-structs/extension-methods.md)

#### <a name="Constructors"></a> Constructores

Los constructores son métodos de clase que se ejecutan automáticamente cuando se crea un objeto de un tipo determinado. Normalmente, los constructores inicializan los miembros de datos del nuevo objeto. Un constructor solo puede ejecutarse una vez cuando se crea una clase. Además, el código del constructor siempre se ejecuta antes que cualquier otro código en una clase. Sin embargo, puede crear varias sobrecargas del constructor de la misma forma que para cualquier otro método.

Para definir un constructor para una clase:

```csharp
public class SampleClass
{
    public SampleClass()
    {
        // Add code here
    }
}
```

Para obtener más información, consulte:

[Constructores](../classes-and-structs/constructors.md).

#### <a name="Finalizers"></a> Finalizadores

Los finalizadores se usan para destruir instancias de clases. En .NET Framework, el recolector de elementos no utilizados administra automáticamente la asignación y la liberación de memoria para los objetos administrados en la aplicación. En cambio, es posible que aún se necesiten finalizadores para limpiar cualquiera de los recursos no administrados creados por la aplicación. Solo puede haber un finalizador para una clase.

Para obtener más información sobre los finalizadores y la recolección de elementos no utilizados en .NET Framework, vea [Recolección de elementos no utilizados](../../../standard/garbage-collection/index.md).

#### <a name="Events"></a> Eventos

Cuando ocurre algo interesante, los eventos habilitan una clase u objeto para notificarlo a otras clases u objetos. La clase que envía (o genera) el evento recibe el nombre de *publicador* y las clases que reciben (o controlan) el evento se denominan *suscriptores*. Para obtener más información sobre los eventos y la forma en que se generan y controlan, vea [Eventos](../../../standard/events/index.md).

- Para declarar un evento en una clase, use la palabra clave [event](../../language-reference/keywords/event.md).

- Para generar un evento, invoque al delegado de eventos.

- Para suscribirse a un evento, use el operador `+=`; para anular la suscripción de un evento, use el operador `-=`.

#### <a name="NestedClasses"></a> Clases anidadas

Una clase definida dentro de otra se denomina *anidada*. De forma predeterminada, una clase anidada es privada.

```csharp
class Container
{
    class Nested
    {
        // Add code here.
    }
}
```

Para crear una instancia de la clase anidada, use el nombre de la clase contenedora seguido de un punto y seguido, a continuación, del nombre de la clase anidada:

```csharp
Container.Nested nestedInstance = new Container.Nested()
```

### <a name="AccessModifiers"></a> Modificadores y niveles de acceso

Todas las clases y miembros de clase pueden especificar el nivel de acceso que proporcionan a otras clases mediante los *modificadores de acceso*.

Están disponibles los siguientes modificadores de acceso:

|Modificador de C#|Definición|
|------------------|----------------|
|[public](../../language-reference/keywords/public.md)|Puede obtener acceso al tipo o miembro cualquier otro código del mismo ensamblado o de otro ensamblado que haga referencia a éste.|
|[private](../../language-reference/keywords/private.md)|Solamente puede obtener acceso al tipo o miembro el código de la misma clase.|
|[protected](../../language-reference/keywords/protected.md)|Solamente puede obtener acceso al tipo o miembro el código de la misma clase o de una clase derivada.|
|[internal](../../language-reference/keywords/internal.md)|Puede obtener acceso al tipo o miembro cualquier código del mismo ensamblado, pero no de un ensamblado distinto.|
|[protected internal](../../language-reference/keywords/protected-internal.md)|Puede obtener acceso al tipo o miembro cualquier código del mismo ensamblado o cualquier clase derivada de otro ensamblado.|
|[private protected](../../language-reference/keywords/private-protected.md)|Un código de la misma clase o de una clase derivada dentro del ensamblado de clase base puede acceder al tipo o miembro en cuestión.|

Para obtener más información, consulte [Modificadores de acceso](../classes-and-structs/access-modifiers.md).

### <a name="InstantiatingClasses"></a> Creación de instancias de las clases

Para crear un objeto, debe crear una o varias instancias de una clase.

```csharp
SampleClass sampleObject = new SampleClass();
```

Una vez creadas las instancias de una clase, puede asignar valores a las propiedades y los campos de la instancia, así como invocar métodos de clase.

```csharp
// Set a property value.
sampleObject.sampleProperty = "Sample String";
// Call a method.
sampleObject.sampleMethod();
```

Para asignar valores a las propiedades durante el proceso de creación de instancias de una clase, use los inicializadores de objeto:

```csharp
// Set a property value.
SampleClass sampleObject = new SampleClass
    { FirstProperty = "A", SecondProperty = "B" };
```

Para obtener más información, consulte:

- [new (operador)](../../language-reference/operators/new-operator.md)

- [Inicializadores de objeto y colección](../classes-and-structs/object-and-collection-initializers.md)

### <a name="Static"></a> Clases y miembros estáticos

Un miembro estático de la clase es una propiedad, un procedimiento o un campo que comparten todas las instancias de una clase.

Para definir un miembro estático:

```csharp
static class SampleClass
{
    public static string SampleString = "Sample String";
}
```

Para obtener acceso al miembro estático, use el nombre de la clase sin crear un objeto perteneciente a esta:

```csharp
Console.WriteLine(SampleClass.SampleString);
```

Las clases estáticas en C# solo tienen miembros estáticos y no se puede crear una instancia de ellas. Además, los miembros estáticos no pueden tener acceso a las propiedades, los campos o los métodos no estáticos.

Para obtener más información, vea: [static](../../language-reference/keywords/static.md).

### <a name="AnonymousTypes"></a> Tipos anónimos

Los tipos anónimos permiten crear objetos sin escribir una definición de clase para el tipo de datos. En su lugar, el compilador genera una clase. La clase no tiene ningún nombre que se pueda usar y contiene las propiedades especificadas al declarar el objeto.

Para crear una instancia de un tipo anónimo:

```csharp
// sampleObject is an instance of a simple anonymous type.
var sampleObject =
    new { FirstProperty = "A", SecondProperty = "B" };
```

Para obtener más información, consulte: [Tipos anónimos](../classes-and-structs/anonymous-types.md).

## <a name="Inheritance"></a> Herencia

La herencia permite crear una nueva clase que reutiliza, extiende y modifica el comportamiento que se define en otra clase. La clase cuyos miembros se heredan se denomina *clase base* y la clase que hereda esos miembros se denomina *clase derivada*. En cambio, todas las clases de C# heredan implícitamente de la clase <xref:System.Object> que admite la jerarquía de clases .NET y proporciona servicios de bajo nivel a todas las clases.

> [!NOTE]
> C# no admite la herencia múltiple. Es decir, solo puede especificar una clase base para una clase derivada.

Para heredar de una clase base:

```csharp
class DerivedClass:BaseClass {}
```

De forma predeterminada, todas las clases se pueden heredar. Sin embargo, puede especificar si una clase no se debe usar como clase base o bien crear una clase que solo se pueda usar como clase base.

Para especificar que una clase no se puede usar como clase base:

```csharp
public sealed class A { }
```

Para especificar que una clase se puede usar solo como clase base y no se pueden crear instancias de esta:

```csharp
public abstract class B { }
```

Para obtener más información, consulte:

- [sealed](../../language-reference/keywords/sealed.md)

- [abstract](../../language-reference/keywords/abstract.md)

### <a name="Overriding"></a> Reemplazar miembros

De forma predeterminada, una clase derivada hereda todos los miembros de su clase base. Si desea cambiar el comportamiento del miembro heredado, debe invalidarlo. Es decir, se puede definir una nueva implementación del método, la propiedad o el evento en la clase derivada.

Los siguientes modificadores se utilizan para controlar cómo se reemplazan propiedades y métodos:

|Modificador de C#|Definición|
|------------------|----------------|
|[virtual](../../language-reference/keywords/virtual.md)|Permite invalidar un miembro de una clase derivada.|
|[override](../../language-reference/keywords/override.md)|Invalida un miembro virtual (invalidable) definido en la clase base.|
|[abstract](../../language-reference/keywords/abstract.md)|Requiere que se invalide un miembro de clase en la clase derivada.|
|[new (modificador)](../../language-reference/keywords/new-modifier.md)|Oculta un miembro heredado de una clase base.|

## <a name="Interfaces"></a> Interfaces

Las interfaces, como las clases, definen un conjunto de propiedades, métodos y eventos. Pero de forma contraria a las clases, las interfaces no proporcionan implementación. Se implementan como clases y se definen como entidades separadas de las clases. Una interfaz representa un contrato, en el cual una clase que implementa una interfaz debe implementar cualquier aspecto de dicha interfaz exactamente como esté definido.

Para definir una interfaz:

```csharp
interface ISampleInterface
{
    void doSomething();
}
```

Para implementar una interfaz en una clase:

```csharp
class SampleClass : ISampleInterface
{
    void ISampleInterface.doSomething()
    {
        // Method implementation.
    }
}
```

Para obtener más información, consulte:

[Interfaces](../interfaces/index.md)

[interface](../../language-reference/keywords/interface.md)

## <a name="Generics"></a> Genéricos

Las clases, las estructuras, las interfaces y los métodos de .NET Framework pueden incluir *parámetros de tipo* que definen los tipos de objetos que estos pueden almacenar o usar. El ejemplo más común de elementos genéricos es una colección, donde se puede especificar el tipo de objetos que se va a almacenar en una colección.

Para definir una clase genérica:

```csharp
public class SampleGeneric<T>
{
    public T Field;
}
```

Para crear una instancia de una clase genérica:

```csharp
SampleGeneric<string> sampleObject = new SampleGeneric<string>();
sampleObject.Field = "Sample string";
```

Para obtener más información, consulte:

- [Genéricos](../../../standard/generics/index.md)

- [Genéricos](../generics/index.md)

## <a name="Delegates"></a> Delegados

Un *delegado* es un tipo que define una firma de método y que puede proporcionar una referencia a cualquier método con una firma compatible. Puede invocar (o llamar) al método a través del delegado. Los delegados se utilizan para pasar métodos como argumentos a otros métodos.

> [!NOTE]
> Los controladores de eventos no son más que métodos que se invocan a través de delegados. Para obtener más información sobre el uso de delegados en el control de eventos, vea [Eventos](../../../standard/events/index.md).

Para crear un delegado:

```csharp
public delegate void SampleDelegate(string str);
```

Para crear una referencia a un método que coincida con la firma especificada por el delegado:

```csharp
class SampleClass
{
    // Method that matches the SampleDelegate signature.
    public static void sampleMethod(string message)
    {
        // Add code here.
    }
    // Method that instantiates the delegate.
    void SampleDelegate()
    {
        SampleDelegate sd = sampleMethod;
        sd("Sample string");
    }
}
```

Para obtener más información, consulte:

- [Delegados](../delegates/index.md)

- [delegate](../../language-reference/builtin-types/reference-types.md)

## <a name="see-also"></a>Vea también

- [Guía de programación de C#](../index.md)
