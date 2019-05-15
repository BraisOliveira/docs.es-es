---
title: Procedimiento para acceder a propiedades específicas de HTTP
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: f8848c7e-f5c5-4d42-b86d-9951ff8f4146
ms.openlocfilehash: 044a48aaffbd2d4ef490405a65236b17ecca1fbf
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64645797"
---
# <a name="how-to-access-http-specific-properties"></a><span data-ttu-id="620b8-102">Procedimiento para acceder a propiedades específicas de HTTP</span><span class="sxs-lookup"><span data-stu-id="620b8-102">How to: Access HTTP-Specific Properties</span></span>
<span data-ttu-id="620b8-103">En este ejemplo se muestra cómo desactivar el comportamiento de **conexión persistente** HTTP y obtener el número de versión del protocolo de servidor web.</span><span class="sxs-lookup"><span data-stu-id="620b8-103">This sample shows how to turn off the HTTP **Keep-alive** behavior and get the protocol version number from the Web server.</span></span>  
  
## <a name="example"></a><span data-ttu-id="620b8-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="620b8-104">Example</span></span>  
  
```vb  
Dim HttpWReq As HttpWebRequest= _  
    CType(WebRequest.Create("http://www.contoso.com"), HttpWebRequest)  
' Turn off connection keep-alives.  
HttpWReq.KeepAlive = False  
  
Dim HttpWResp As HttpWebResponse = _  
    CType(HttpWReq.GetResponse(), HttpWebResponse)  
  
' Get the HTTP protocol version number returned by the server.  
Dim ver As String = HttpWResp.ProtocolVersion.ToString()  
HttpWResp.Close()  
```  
  
```csharp  
HttpWebRequest HttpWReq =   
    (HttpWebRequest)WebRequest.Create("http://www.contoso.com");  
// Turn off connection keep-alives.  
HttpWReq.KeepAlive = false;  
  
HttpWebResponse HttpWResp = (HttpWebResponse)HttpWReq.GetResponse();  
  
// Get the HTTP protocol version number returned by the server.  
String ver = HttpWResp.ProtocolVersion.ToString();  
HttpWResp.Close();  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="620b8-105">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="620b8-105">Compiling the Code</span></span>  
 <span data-ttu-id="620b8-106">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="620b8-106">This example requires:</span></span>  
  
- <span data-ttu-id="620b8-107">Referencias al espacio de nombres **System.Net**.</span><span class="sxs-lookup"><span data-stu-id="620b8-107">References to the **System.Net** namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="620b8-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="620b8-108">See also</span></span>

- [<span data-ttu-id="620b8-109">Acceso a Internet a través de un proxy</span><span class="sxs-lookup"><span data-stu-id="620b8-109">Accessing the Internet Through a Proxy</span></span>](../../../docs/framework/network-programming/accessing-the-internet-through-a-proxy.md)
- [<span data-ttu-id="620b8-110">Usar protocolos de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="620b8-110">Using Application Protocols</span></span>](../../../docs/framework/network-programming/using-application-protocols.md)
- [<span data-ttu-id="620b8-111">HTTP</span><span class="sxs-lookup"><span data-stu-id="620b8-111">HTTP</span></span>](../../../docs/framework/network-programming/http.md)
