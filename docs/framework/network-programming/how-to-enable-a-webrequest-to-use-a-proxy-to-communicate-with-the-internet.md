---
title: Procedimiento para habilitar un elemento WebRequest para usar un proxy para comunicarse con Internet
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 63c0ef2c-44b5-4c54-9804-ba0b9b001ac7
ms.openlocfilehash: a2179e767a0556f5223f2f4c1cc91708133120a5
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59103706"
---
# <a name="how-to-enable-a-webrequest-to-use-a-proxy-to-communicate-with-the-internet"></a><span data-ttu-id="00512-102">Procedimiento para habilitar un elemento WebRequest para usar un proxy para comunicarse con Internet</span><span class="sxs-lookup"><span data-stu-id="00512-102">How to: Enable a WebRequest to Use a Proxy to Communicate With the Internet</span></span>
<span data-ttu-id="00512-103">En este ejemplo se crea una instancia de proxy global que permitirá que cualquier <xref:System.Net.WebRequest> use un proxy para comunicarse con Internet.</span><span class="sxs-lookup"><span data-stu-id="00512-103">This example creates a global proxy instance that will enable any <xref:System.Net.WebRequest> to use a proxy to communicate with the Internet.</span></span> <span data-ttu-id="00512-104">En el ejemplo se da por supuesto que el servidor proxy se denomina `webproxy` y que se comunica en el puerto 80, el puerto HTTP estándar.</span><span class="sxs-lookup"><span data-stu-id="00512-104">The example assumes that the proxy server is named `webproxy` and that it communicates on port 80, the standard HTTP port.</span></span>  
  
## <a name="example"></a><span data-ttu-id="00512-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="00512-105">Example</span></span>  
  
```csharp  
WebProxy proxyObject = new WebProxy("http://webproxy:80/");  
GlobalProxySelection.Select = proxyObject;  
```  
  
```vb  
Dim proxyObject As WebProxy = New WebProxy("http://webproxy:80/")  
GlobalProxySelection.Select = proxyObject  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="00512-106">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="00512-106">Compiling the Code</span></span>  
 <span data-ttu-id="00512-107">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="00512-107">This example requires:</span></span>  
  
-   <span data-ttu-id="00512-108">Una [directiva `using`](../../csharp/language-reference/keywords/using-directive.md) para el espacio de nombres **System.Net**.</span><span class="sxs-lookup"><span data-stu-id="00512-108">A [`using` directive](../../csharp/language-reference/keywords/using-directive.md) for the **System.Net** namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="00512-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="00512-109">See also</span></span>

- [<span data-ttu-id="00512-110">Usar protocolos de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="00512-110">Using Application Protocols</span></span>](../../../docs/framework/network-programming/using-application-protocols.md)
- [<span data-ttu-id="00512-111">Acceso a Internet a través de un proxy</span><span class="sxs-lookup"><span data-stu-id="00512-111">Accessing the Internet Through a Proxy</span></span>](../../../docs/framework/network-programming/accessing-the-internet-through-a-proxy.md)
