---
title: 'Tutorial: Implementar la herencia con objetos COM (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- inheritance [Visual Basic], COM reusability
- base classes [Visual Basic], COM reusability
- inheritance [Visual Basic], walkthroughs
- derived classes [Visual Basic], COM reusability
ms.assetid: f8e7263a-de13-48d1-b67c-ca1adf3544d9
ms.openlocfilehash: 7cbf71d7a2bbd1e94864e785894fdea41d522486
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/17/2019
ms.locfileid: "71053333"
---
# <a name="walkthrough-implementing-inheritance-with-com-objects-visual-basic"></a>Tutorial: Implementar la herencia con objetos COM (Visual Basic)

Puede derivar Visual Basic clases de `Public` clases de objetos com, incluso las creadas en versiones anteriores de Visual Basic. Las propiedades y los métodos de las clases heredadas de objetos COM se pueden invalidar o sobrecargar del mismo modo que las propiedades y los métodos de cualquier otra clase base se pueden invalidar o sobrecargar. La herencia de objetos COM resulta útil cuando tiene una biblioteca de clases existente que no desea volver a compilar.

En el procedimiento siguiente se muestra cómo utilizar Visual Basic 6,0 para crear un objeto COM que contenga una clase y, a continuación, utilizarlo como clase base.

[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]

## <a name="to-build-the-com-object-that-is-used-in-this-walkthrough"></a>Para compilar el objeto COM que se usa en este tutorial

1. En Visual Basic 6,0, abra un nuevo proyecto DLL de ActiveX. Se crea un `Project1` proyecto denominado. Tiene una clase denominada `Class1`.

2. En el **Explorador de proyectos**, haga clic con el botón secundario en **Project1**y, a continuación, haga clic en **propiedades de Project1**. Se muestra el cuadro de diálogo **propiedades del proyecto** .

3. En la pestaña **General** del cuadro de diálogo **propiedades del proyecto** , cambie el nombre del proyecto `ComObject1` escribiendo en el campo **nombre del proyecto** .

4. En el **Explorador de proyectos**, haga clic `Class1`con el botón secundario y, a continuación, haga clic en **propiedades**. Se muestra la ventana **propiedades** de la clase.

5. Cambie la `Name` propiedad a `MathFunctions`.

6. En el **Explorador de proyectos**, haga clic `MathFunctions`con el botón secundario y, a continuación, haga clic en **Ver código**. Se muestra el **Editor de código** .

7. Agregue una variable local para que contenga el valor de propiedad:

    ```vb
    ' Local variable to hold property value
    Private mvarProp1 As Integer
    ```

8. Agregue los procedimientos `Get` depropiedadypropiedaddepropiedad:`Let`

    ```vb
    Public Property Let Prop1(ByVal vData As Integer)
       'Used when assigning a value to the property.
       mvarProp1 = vData
    End Property
    Public Property Get Prop1() As Integer
       'Used when retrieving a property's value.
       Prop1 = mvarProp1
    End Property
    ```

9. Agregue una función:

    ```vb
    Function AddNumbers(
       ByVal SomeNumber As Integer,
       ByVal AnotherNumber As Integer) As Integer

       AddNumbers = SomeNumber + AnotherNumber
    End Function
    ```

10. Cree y registre el objeto COM; para ello, haga clic en **crear ComObject1. dll** en el menú **archivo** .

    > [!NOTE]
    > Aunque también puede exponer una clase creada con Visual Basic como un objeto COM, no es un objeto COM verdadero y no se puede usar en este tutorial. Para obtener más información, consulte [interoperabilidad com en aplicaciones .NET Framework](../../../visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md).

## <a name="interop-assemblies"></a>Ensamblados de interoperabilidad

En el procedimiento siguiente, creará un ensamblado de interoperabilidad, que actúa como un puente entre el código no administrado (por ejemplo, un objeto COM) y el código administrado que usa Visual Studio. El ensamblado de interoperabilidad que Visual Basic crea controla muchos de los detalles del trabajo con objetos COM, como el *cálculo de referencias de interoperabilidad*, el proceso de empaquetado de parámetros y valores devueltos en tipos de datos equivalentes a medida que se mueven a objetos com y desde ellos. La referencia de la aplicación Visual Basic apunta al ensamblado de interoperabilidad, no al objeto COM real.

### <a name="to-use-a-com-object-with-visual-basic-2005-and-later-versions"></a>Para usar un objeto COM con Visual Basic 2005 y versiones posteriores

1. Abra un proyecto Aplicación Windows de Visual Basic nuevo.

2. En el menú **Proyecto**, haga clic en **Agregar referencia**.

     Aparecerá el cuadro de diálogo **Agregar referencia**.

3. En la pestaña **com** , haga doble clic `ComObject1` en la lista **nombre de componente** y haga clic en **Aceptar**.

4. En el menú **Proyecto** , haga clic en **Agregar nuevo elemento**.

     Se abrirá el cuadro de diálogo **Agregar nuevo elemento**.

5. En el panel **plantillas** , haga clic en **clase**.

     El nombre de archivo predeterminado `Class1.vb`,, aparece en el campo **nombre** . Cambie este campo a MathClass. VB y haga clic en **Agregar**. Esto crea una clase denominada `MathClass`y muestra su código.

6. Agregue el código siguiente al principio de `MathClass` para que herede de la clase com.

     [!code-vb[VbVbalrInterop#31](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#31)]

7. Sobrecargue el método público de la clase base agregando el código siguiente a `MathClass`:

     [!code-vb[VbVbalrInterop#32](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#32)]

8. Extienda la clase heredada agregando el código siguiente `MathClass`a:

     [!code-vb[VbVbalrInterop#33](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#33)]

La nueva clase hereda las propiedades de la clase base en el objeto COM, sobrecarga un método y define un nuevo método para extender la clase.

### <a name="to-test-the-inherited-class"></a>Para probar la clase heredada

1. Agregue un botón al formulario de inicio y, a continuación, haga doble clic en él para ver su código.

2. En el procedimiento de `Click` controlador de eventos del botón, agregue el código siguiente para crear una `MathClass` instancia de y llamar a los métodos sobrecargados:

     [!code-vb[VbVbalrInterop#34](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#34)]

3. Ejecute el proyecto presionando F5.

Al hacer clic en el botón del formulario, se `AddNumbers` llama primero al método con `Short` números de tipo de datos y Visual Basic elige el método adecuado de la clase base. La segunda llamada a `AddNumbers` se dirige al método de sobrecarga desde `MathClass`. La tercera llamada llama al `SubtractNumbers` método, que extiende la clase. Se establece la propiedad de la clase base y se muestra el valor.

## <a name="next-steps"></a>Pasos siguientes

Es posible que haya observado que la `AddNumbers` función sobrecargada parece tener el mismo tipo de datos que el método heredado de la clase base del objeto com. Esto se debe a que los argumentos y los parámetros del método de la clase base se definen como enteros de 16 bits en Visual Basic 6,0, pero se exponen como enteros de 16 `Short` bits de tipo en versiones posteriores de Visual Basic. La nueva función acepta enteros de 32 bits y sobrecarga la función de clase base.

Al trabajar con objetos COM, asegúrese de comprobar el tamaño y los tipos de datos de los parámetros. Por ejemplo, cuando se usa un objeto COM que acepta un objeto de colección Visual Basic 6,0 como argumento, no se puede proporcionar una colección de una versión posterior de Visual Basic.

Se pueden invalidar las propiedades y los métodos heredados de las clases COM, lo que significa que puede declarar una propiedad o un método local que reemplace una propiedad o un método heredado de una clase COM base. Las reglas para reemplazar propiedades COM heredadas son similares a las reglas para invalidar otras propiedades y métodos con las siguientes excepciones:

- Si invalida cualquier propiedad o método heredado de una clase COM, debe invalidar todas las demás propiedades y métodos heredados.

- Las propiedades que `ByRef` usan parámetros no se pueden invalidar.

## <a name="see-also"></a>Vea también

- [Interoperabilidad COM en aplicaciones .NET Framework](../../../visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md)
- [Inherits (instrucción)](../../../visual-basic/language-reference/statements/inherits-statement.md)
- [Short (tipo de datos)](../../../visual-basic/language-reference/data-types/short-data-type.md)
