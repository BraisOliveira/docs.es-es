---
title: 'Cómo: determinar la versión de detección de una solicitud de sondeo'
ms.date: 03/30/2017
ms.assetid: b3c4e2e2-2957-4074-ae6a-776a5ca84278
ms.openlocfilehash: 6bd112be311eb9397ad89801be5358d67c7499fd
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/09/2019
ms.locfileid: "59332279"
---
# <a name="how-todetermine-the-discovery-version-of-a-probe-request"></a><span data-ttu-id="aca9a-102">Cómo: determinar la versión de detección de una solicitud de sondeo</span><span class="sxs-lookup"><span data-stu-id="aca9a-102">How to:Determine the Discovery Version of a Probe Request</span></span>
<span data-ttu-id="aca9a-103">Un proxy de detección puede exponer varios puntos de conexión de detección mediante distintas versiones de detección.</span><span class="sxs-lookup"><span data-stu-id="aca9a-103">A discovery proxy may expose multiple discovery endpoints using different discovery versions.</span></span> <span data-ttu-id="aca9a-104">Cuando llega una solicitud de sondeo multidifusión UDP al proxy, este debe responder con un mensaje de supresión de multidifusión.</span><span class="sxs-lookup"><span data-stu-id="aca9a-104">When a UDP multicast Probe request arrives at the proxy the proxy should respond with a multicast suppression message.</span></span> <span data-ttu-id="aca9a-105">Para ello, se debe conocer la versión de detección de la solicitud.</span><span class="sxs-lookup"><span data-stu-id="aca9a-105">In order to do this it would have to know the discovery version of the request.</span></span>  
  
### <a name="to-determine-the-discovery-version-of-a-probe-request"></a><span data-ttu-id="aca9a-106">Para determinar la versión de detección de una solicitud de sondeo</span><span class="sxs-lookup"><span data-stu-id="aca9a-106">To Determine the Discovery Version of a Probe Request</span></span>  
  
1. <span data-ttu-id="aca9a-107">En el método que responda a una solicitud de sondeo (por ejemplo, el método <xref:System.ServiceModel.Discovery.DiscoveryProxy.OnBeginFind%2A>) use la propiedad estática <xref:System.ServiceModel.OperationContext.Current%2A> para buscar una extensión <xref:System.ServiceModel.Discovery.DiscoveryOperationContextExtension> como se muestra en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="aca9a-107">In the method that responds to a Probe request (for example <xref:System.ServiceModel.Discovery.DiscoveryProxy.OnBeginFind%2A>) use the static <xref:System.ServiceModel.OperationContext.Current%2A> property to search for a <xref:System.ServiceModel.Discovery.DiscoveryOperationContextExtension> as shown in the following code.</span></span>  
  
    ```  
    DiscoveryOperationContextExtension doce = OperationContext.Current.Extensions.Find<DiscoveryOperationContextExtension>();  
    // Access the discovery version from the DiscoveryOperationContextExtension  
    doce.DiscoveryVersion;  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="aca9a-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="aca9a-108">See also</span></span>

- <xref:System.ServiceModel.Discovery.Configuration.AnnouncementEndpointElement.DiscoveryVersion%2A>
- [<span data-ttu-id="aca9a-109">Implementar un proxy de detección</span><span class="sxs-lookup"><span data-stu-id="aca9a-109">Implementing a Discovery Proxy</span></span>](../../../../docs/framework/wcf/feature-details/implementing-a-discovery-proxy.md)
