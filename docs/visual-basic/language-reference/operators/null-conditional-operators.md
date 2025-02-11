---
title: Operadores condicionales null (Visual Basic)
ms.date: 10/19/2018
helpviewer_keywords:
- null-conditional operators [Visual Basic]
- ?. operator [Visual Basic]
- ?[] operator [C#]
- ?[] operator [Visual Basic]
ms.openlocfilehash: 40cb63705eda563b4c3cfd30fa9836a8f632dccf
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2019
ms.locfileid: "72581629"
---
# <a name="-and--null-conditional-operators-visual-basic"></a>?. etc? () operadores condicionales null (Visual Basic)

Comprueba el valor del operando izquierdo para null (`Nothing`) antes de realizar una operación de acceso a miembros (`?.`) o de índice (`?()`). Devuelve `Nothing` si el operando izquierdo se evalúa como `Nothing`. Tenga en cuenta que, en las expresiones que normalmente devuelven tipos de valor, el operador condicional null devuelve un <xref:System.Nullable%601>.

Estos operadores le ayudan a escribir menos código para controlar las comprobaciones de valores NULL, especialmente cuando desciende en estructuras de datos. Por ejemplo:

```vb
' Nothing if customers is Nothing
Dim length As Integer? = customers?.Length

' Nothing if customers is Nothing
Dim first As Customer = customers?(0)

' Nothing if customers, the first customer, or Orders is Nothing
Dim count As Integer? = customers?(0)?.Orders?.Count()
```

Para la comparación, el código alternativo para la primera de estas expresiones sin un operador condicional NULL es:

```vb
Dim length As Integer
If customers IsNot Nothing Then
   length = customers.Length
End If
```

A veces es necesario realizar una acción en un objeto que puede ser null, en función del valor de un miembro booleano en ese objeto (como la propiedad booleana `IsAllowedFreeShipping` en el ejemplo siguiente):

```vb
Dim customer = FindCustomerByID(123) 'customer will be Nothing if not found.

If customer IsNot Nothing AndAlso customer.IsAllowedFreeShipping Then
  ApplyFreeShippingToOrders(customer)
End If
```

Puede acortar el código y evitar comprobar manualmente si hay valores NULL mediante el operador condicional null de la siguiente manera:

```vb
Dim customer = FindCustomerByID(123) 'customer will be Nothing if not found.

If customer?.IsAllowedFreeShipping Then ApplyFreeShippingToOrders(customer)
```

Los operadores de condición NULL se cortocircuitan.  Si una operación de una cadena de operaciones de índice y acceso a miembros condicionales devuelve `Nothing`, se detiene el resto de la ejecución de la cadena.  En el ejemplo siguiente, `C(E)` no se evalúa si `A`, `B` o `C` se evalúan como `Nothing`.

```vb
A?.B?.C?(E);
```

Otro uso para el acceso de miembro condicional NULL es invocar delegados de una manera segura para subprocesos con mucho menos código.  En el ejemplo siguiente se definen dos tipos, un `NewsBroadcaster` y un `NewsReceiver`. El delegado de `NewsBroadcaster.SendNews` envía los elementos de noticias al receptor.

```vb
Public Module NewsBroadcaster
   Dim SendNews As Action(Of String)

   Public Sub Main()
      Dim rec As New NewsReceiver()
      Dim rec2 As New NewsReceiver()
      SendNews?.Invoke("Just in: A newsworthy item...")
   End Sub

   Public Sub Register(client As Action(Of String))
      SendNews = SendNews.Combine({SendNews, client})
   End Sub
End Module

Public Class NewsReceiver
   Public Sub New()
      NewsBroadcaster.Register(AddressOf Me.DisplayNews)
   End Sub

   Public Sub DisplayNews(newsItem As String)
      Console.WriteLine(newsItem)
   End Sub
End Class
```

Si no hay ningún elemento en la lista de invocación de `SendNews`, el delegado de `SendNews` produce una <xref:System.NullReferenceException>. Antes de los operadores condicionales null, el código como el siguiente garantiza que la lista de invocación de delegado no se `Nothing`:

```vb
SendNews = SendNews.Combine({SendNews, client})
If SendNews IsNot Nothing Then
   SendNews("Just in...")
End If
```

La nueva manera es mucho más sencilla:

```vb
SendNews = SendNews.Combine({SendNews, client})
SendNews?.Invoke("Just in...")
```

La nueva forma de hacerlo es segura para los subprocesos porque el compilador genera código para evaluar `SendNews` solo una vez, manteniendo el resultado en una variable temporal. Debe llamar explícitamente al método `Invoke` porque no hay ninguna sintaxis de invocación del delegado null condicional `SendNews?(String)`.

## <a name="see-also"></a>Vea también

- [Operadores (Visual Basic)](index.md)
- [Guía de programación en Visual Basic](../../../visual-basic/programming-guide/index.md)
- [Referencia del lenguaje Visual Basic](../../../visual-basic/language-reference/index.md)
