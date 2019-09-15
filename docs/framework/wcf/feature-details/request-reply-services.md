---
title: Servicios de solicitud-respuesta
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Communication Foundation [WCF], request-reply services
- contracts [WCF], request-reply services
- WCF [WCF], request-reply services
- request-reply contracts [WCF]
ms.assetid: 2fa710f1-47f4-4598-b063-3ab3bd22ebba
ms.openlocfilehash: f58da6f1cdaad1b976659ee2e9febe12cc07726f
ms.sourcegitcommit: 005980b14629dfc193ff6cdc040800bc75e0a5a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/14/2019
ms.locfileid: "70991143"
---
# <a name="request-reply-services"></a><span data-ttu-id="98739-102">Servicios de solicitud-respuesta</span><span class="sxs-lookup"><span data-stu-id="98739-102">Request-Reply Services</span></span>
<span data-ttu-id="98739-103">Los servicios de solicitud-respuesta son el tipo predeterminado de contrato de operación en Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="98739-103">Request-reply services are the default type of operation contract in Windows Communication Foundation (WCF).</span></span> <span data-ttu-id="98739-104">Los clientes realizan las llamadas a operaciones de servicio y esperan una respuesta del servicio.</span><span class="sxs-lookup"><span data-stu-id="98739-104">Clients make calls to service operations and wait for a response from the service.</span></span> <span data-ttu-id="98739-105">Puede realizar llamadas a una operación de servicio de manera sincrónica, donde el cliente se bloquea hasta que recibe una respuesta del servicio o la llamada supera el tiempo de espera, o de forma asincrónica, donde el cliente realiza una llamada a la operación del servicio, continúa funcionando y recibe la respuesta del servicio en otro subproceso.</span><span class="sxs-lookup"><span data-stu-id="98739-105">You can perform calls to a service operation either synchronously, where the client blocks until it receives a response from the service or the call times, or asynchronously, where the client makes a call to the service operation, continues working, and receives the response from the service on another thread.</span></span>  
  
 <span data-ttu-id="98739-106">Para crear un contrato de servicios de la respuesta de la solicitud, defina su contrato de servicios y aplique la clase <xref:System.ServiceModel.OperationContractAttribute> a cada operación, como se muestra en el código de muestra siguiente.</span><span class="sxs-lookup"><span data-stu-id="98739-106">To create a request-reply service contract, define your service contract, and apply the <xref:System.ServiceModel.OperationContractAttribute> class to each operation, as shown in the following sample code.</span></span>  
  
```csharp
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples")]  
public interface IRequestReplyCalculator  
{  
    [OperationContract]  
    double Add(double n1, double n2);  
}  
```  
  
 <span data-ttu-id="98739-107">No tiene que establecer la propiedad <xref:System.ServiceModel.OperationContractAttribute.IsOneWay%2A> en `false` porque se trata del comportamiento predeterminado.</span><span class="sxs-lookup"><span data-stu-id="98739-107">You do not have to set the  <xref:System.ServiceModel.OperationContractAttribute.IsOneWay%2A> property to `false` because this is the default behavior.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="98739-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="98739-108">See also</span></span>

- [<span data-ttu-id="98739-109">Servicios unidireccionales</span><span class="sxs-lookup"><span data-stu-id="98739-109">One-Way Services</span></span>](../../../../docs/framework/wcf/feature-details/one-way-services.md)
- [<span data-ttu-id="98739-110">Servicios dúplex</span><span class="sxs-lookup"><span data-stu-id="98739-110">Duplex Services</span></span>](../../../../docs/framework/wcf/feature-details/duplex-services.md)
