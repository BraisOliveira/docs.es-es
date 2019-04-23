---
title: Procedimiento para registrar un protocolo personalizado mediante WebRequest
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 98ddbdb9-66b1-4080-92ad-51f5c447fcf8
ms.openlocfilehash: 5c9a81fc61a2272056ba34fa387fdafee6203824
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59079505"
---
# <a name="how-to-register-a-custom-protocol-using-webrequest"></a><span data-ttu-id="7214c-102">Procedimiento para registrar un protocolo personalizado mediante WebRequest</span><span class="sxs-lookup"><span data-stu-id="7214c-102">How to: Register a Custom Protocol Using WebRequest</span></span>
<span data-ttu-id="7214c-103">En este ejemplo se muestra cómo registrar una clase específica del protocolo que se define en otro lugar.</span><span class="sxs-lookup"><span data-stu-id="7214c-103">This example shows how to register a protocol specific class that is defined elsewhere.</span></span> <span data-ttu-id="7214c-104">En este ejemplo, `CustomWebRequestCreator` es el objeto implementado por el usuario que implementa el método **Create** que devuelve el objeto `CustomWebRequest`.</span><span class="sxs-lookup"><span data-stu-id="7214c-104">In this example, `CustomWebRequestCreator` is the user-implemented object that implements the **Create** method that returns the `CustomWebRequest` object.</span></span> <span data-ttu-id="7214c-105">El ejemplo del código presupone que ha escrito el código `CustomWebRequest` que implementa el protocolo personalizado.</span><span class="sxs-lookup"><span data-stu-id="7214c-105">The code example assumes that you have written the `CustomWebRequest` code that implements the custom protocol.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7214c-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="7214c-106">Example</span></span>  
  
```csharp  
WebRequest.RegisterPrefix("custom", new CustomWebRequestCreator());  
WebRequest req = WebRequest.Create("custom://customHost.contoso.com/");  
```  
  
```vb  
WebRequest.RegisterPrefix("custom", New CustomWebRequestCreator())  
Dim req As WebRequest = WebRequest.Create("custom://customHost.contoso.com/")  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="7214c-107">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="7214c-107">Compiling the Code</span></span>  
 <span data-ttu-id="7214c-108">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="7214c-108">This example requires:</span></span>  
  
 <span data-ttu-id="7214c-109">Referencias al espacio de nombres <xref:System.Net>.</span><span class="sxs-lookup"><span data-stu-id="7214c-109">References to the <xref:System.Net> namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7214c-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="7214c-110">See also</span></span>

- [<span data-ttu-id="7214c-111">Programming Pluggable Protocols (Programar protocolos acoplables)</span><span class="sxs-lookup"><span data-stu-id="7214c-111">Programming Pluggable Protocols</span></span>](../../../docs/framework/network-programming/programming-pluggable-protocols.md)
