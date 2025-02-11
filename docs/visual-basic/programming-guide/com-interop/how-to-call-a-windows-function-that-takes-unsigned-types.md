---
title: Procedimiento Llamar a una función de Windows que toma tipos sin signo (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- Windows functions [Visual Basic], calling
- unsigned data types [Visual Basic]
- UShort data type [Visual Basic], using
- functions [Visual Basic], calling Windows functions
- ULong data type [Visual Basic], using
- UInteger data type [Visual Basic], using
- data types [Visual Basic], using
- unsigned types [Visual Basic]
- data types [Visual Basic], unsigned
- data types [Visual Basic], numeric
- unsigned types [Visual Basic], using
ms.assetid: c2c0e712-8dc2-43b9-b4c6-345fbb02e7ce
ms.openlocfilehash: 97075fb6149ed8c0ce06318d0e5bb6f01b841f30
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/17/2019
ms.locfileid: "71053321"
---
# <a name="how-to-call-a-windows-function-that-takes-unsigned-types-visual-basic"></a>Procedimiento Llamar a una función de Windows que toma tipos sin signo (Visual Basic)

Si está consumiendo una clase, un módulo o una estructura que tiene miembros de tipos enteros sin signo, puede tener acceso a estos miembros con Visual Basic.

## <a name="to-call-a-windows-function-that-takes-an-unsigned-type"></a>Para llamar a una función de Windows que toma un tipo sin signo

1. Use una [instrucción Declare](../../../visual-basic/language-reference/statements/declare-statement.md) para indicar Visual Basic qué biblioteca contiene la función, cuál es su nombre en esa biblioteca, cuál es la secuencia de llamada y cómo convertir cadenas al llamarla.

2. En la `Declare` instrucción, use `UInteger`, `ULong`, `UShort` o`Byte` , según corresponda, para cada parámetro con un tipo sin signo.

3. Consulte la documentación de la función de Windows a la que está llamando para buscar los nombres y valores de las constantes que usa. Muchos de ellos se definen en el archivo WinUser. h.

4. Declare las constantes necesarias en el código. Muchas constantes de Windows son valores sin signo de 32 bits y se deben declarar `As UInteger`.

5. Llame a la función de la forma normal. En el ejemplo siguiente se llama a `MessageBox`la función de Windows, que toma un argumento de entero sin signo.

    ```vb
    Public Class windowsMessage
        Private Declare Auto Function mb Lib "user32.dll" Alias "MessageBox" (
            ByVal hWnd As Integer,
            ByVal lpText As String,
            ByVal lpCaption As String,
            ByVal uType As UInteger) As Integer
        Private Const MB_OK As UInteger = 0
        Private Const MB_ICONEXCLAMATION As UInteger = &H30
        Private Const IDOK As UInteger = 1
        Private Const IDCLOSE As UInteger = 8
        Private Const c As UInteger = MB_OK Or MB_ICONEXCLAMATION
        Public Function messageThroughWindows() As String
            Dim r As Integer = mb(0, "Click OK if you see this!",
                "Windows API call", c)
            Dim s As String = "Windows API MessageBox returned " &
                 CStr(r)& vbCrLf & "(IDOK = " & CStr(IDOK) &
                 ", IDCLOSE = " & CStr(IDCLOSE) & ")"
            Return s
        End Function
    End Class
    ```

     Puede probar la función `messageThroughWindows` con el código siguiente.

    ```vb
    Public Sub consumeWindowsMessage()
        Dim w As New windowsMessage
        w.messageThroughWindows()
    End Sub
    ```

    > [!CAUTION]
    > Los `UInteger`tipos `ULong`de `UShort`datos, `SByte` , y no forman parte de la [independencia del lenguaje y de los componentes independientes del lenguaje](../../../standard/language-independence-and-language-independent-components.md) (CLS), por lo que el código conforme a CLS no puede consumir un componente que los utiliza.

    > [!IMPORTANT]
    > La realización de una llamada a código no administrado, como la interfaz de programación de aplicaciones (API) de Windows, expone el código a posibles riesgos de seguridad.

    > [!IMPORTANT]
    > La llamada a la API de Windows requiere el permiso del código no administrado, lo que puede afectar a su ejecución en situaciones de confianza parcial. Para obtener más información, <xref:System.Security.Permissions.SecurityPermission> vea y [permisos de acceso del código](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/h846e9b3(v=vs.100)).

## <a name="see-also"></a>Vea también

- [Tipos de datos](../../../visual-basic/language-reference/data-types/index.md)
- [Integer (tipo de datos)](../../../visual-basic/language-reference/data-types/integer-data-type.md)
- [UInteger (tipo de datos)](../../../visual-basic/language-reference/data-types/uinteger-data-type.md)
- [Declare (instrucción)](../../../visual-basic/language-reference/statements/declare-statement.md)
- [Tutorial: Llamar a las API de Windows](../../../visual-basic/programming-guide/com-interop/walkthrough-calling-windows-apis.md)
