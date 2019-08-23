---
title: <resolver>
ms.date: 03/30/2017
ms.assetid: 0c00200c-f135-4e5c-a024-76b72bcbc021
ms.openlocfilehash: e3a9ee00aab6ab48a1ba891565b63824e62b20fe
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69934226"
---
# <a name="resolver"></a><span data-ttu-id="a6ccb-101">\<resolver></span><span class="sxs-lookup"><span data-stu-id="a6ccb-101">\<resolver></span></span>
<span data-ttu-id="a6ccb-102">Especifica una resolución del mismo nivel que se utiliza para resolver un id. de malla del mismo nivel como un conjunto de direcciones del nodo del mismo nivel que representa varios nodos que participan en la malla.</span><span class="sxs-lookup"><span data-stu-id="a6ccb-102">Specifies a peer resolver that is used to resolve a peer mesh ID to a set of peer node addresses that represents several nodes that participate in the mesh.</span></span>  
  
 <span data-ttu-id="a6ccb-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="a6ccb-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="a6ccb-104">\<bindings></span><span class="sxs-lookup"><span data-stu-id="a6ccb-104">\<bindings></span></span>  
<span data-ttu-id="a6ccb-105">\<netPeerBinding></span><span class="sxs-lookup"><span data-stu-id="a6ccb-105">\<netPeerBinding></span></span>  
<span data-ttu-id="a6ccb-106">\<binding></span><span class="sxs-lookup"><span data-stu-id="a6ccb-106">\<binding></span></span>  
<span data-ttu-id="a6ccb-107">\<resolver></span><span class="sxs-lookup"><span data-stu-id="a6ccb-107">\<resolver></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a6ccb-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a6ccb-108">Syntax</span></span>  
  
```xml  
<resolver mode="Auto/Custom/Pnrp"
          referralPolicy="DoNotShare/Service/Share">
</resolver>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a6ccb-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="a6ccb-109">Attributes and Elements</span></span>  
 <span data-ttu-id="a6ccb-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="a6ccb-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a6ccb-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="a6ccb-111">Attributes</span></span>  
  
|<span data-ttu-id="a6ccb-112">Atributo</span><span class="sxs-lookup"><span data-stu-id="a6ccb-112">Attribute</span></span>|<span data-ttu-id="a6ccb-113">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="a6ccb-113">Description</span></span>|  
|---------------|-----------------|  
|`mode`|<span data-ttu-id="a6ccb-114">Una cadena que especifica si la instancia de la resolución del mismo nivel asociada con este servicio es específica del PNRP, una resolución personalizada o si se determina de manera automática.</span><span class="sxs-lookup"><span data-stu-id="a6ccb-114">A string that specifies whether the peer resolver instance associated with this service is either PNRP-specific, a custom resolver, or automatically determined.</span></span> <span data-ttu-id="a6ccb-115">Este atributo es del tipo <xref:System.ServiceModel.PeerResolvers.PeerResolverMode>.</span><span class="sxs-lookup"><span data-stu-id="a6ccb-115">This attribute is of type <xref:System.ServiceModel.PeerResolvers.PeerResolverMode>.</span></span>|  
|`referralPolicy`|<span data-ttu-id="a6ccb-116">Una cadena que especifica la manera en que las referencias se comparten entre pares.</span><span class="sxs-lookup"><span data-stu-id="a6ccb-116">A string that specifies the way referrals are shared among peers.</span></span> <span data-ttu-id="a6ccb-117">Este atributo es del tipo <xref:System.ServiceModel.PeerResolvers.PeerReferralPolicy>.</span><span class="sxs-lookup"><span data-stu-id="a6ccb-117">This attribute is of type <xref:System.ServiceModel.PeerResolvers.PeerReferralPolicy>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a6ccb-118">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="a6ccb-118">Child Elements</span></span>  
  
|<span data-ttu-id="a6ccb-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="a6ccb-119">Element</span></span>|<span data-ttu-id="a6ccb-120">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="a6ccb-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a6ccb-121">\<headers></span><span class="sxs-lookup"><span data-stu-id="a6ccb-121">\<headers></span></span>](headers.md)|<span data-ttu-id="a6ccb-122">Especifica la configuración concreta para un servicio de resolución del mismo nivel personalizado.</span><span class="sxs-lookup"><span data-stu-id="a6ccb-122">Specifies settings for a custom peer resolver service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="a6ccb-123">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="a6ccb-123">Parent Elements</span></span>  
  
|<span data-ttu-id="a6ccb-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="a6ccb-124">Element</span></span>|<span data-ttu-id="a6ccb-125">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="a6ccb-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a6ccb-126">\<binding></span><span class="sxs-lookup"><span data-stu-id="a6ccb-126">\<binding></span></span>](../../../misc/binding.md)|<span data-ttu-id="a6ccb-127">Define todas las funciones de enlace del [ \<> netPeerTcpBinding](netpeertcpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="a6ccb-127">Defines all binding capabilities of the [\<netPeerTcpBinding>](netpeertcpbinding.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a6ccb-128">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a6ccb-128">Remarks</span></span>  
 <span data-ttu-id="a6ccb-129">Una resolución de nombres del mismo nivel es un servicio de descubrimiento utilizado por los canales del mismo nivel para buscar nodos del mismo nivel que participen en una malla del mismo nivel.</span><span class="sxs-lookup"><span data-stu-id="a6ccb-129">A peer name resolver is a discovery service used by peer channels to find peer nodes that participate in a peer mesh.</span></span> <span data-ttu-id="a6ccb-130">También se utiliza para "registrar" un nodo con una malla del mismo nivel, el mecanismo por el que se conoce el nodo del mismo nivel y está disponible en la malla del mismo nivel.</span><span class="sxs-lookup"><span data-stu-id="a6ccb-130">It is also used to "register" a node with a peer mesh, the mechanism by which the peer node becomes known and available from the peer mesh.</span></span> <span data-ttu-id="a6ccb-131">Para obtener más información sobre las resoluciones del mismo nivel, consulte [solucionadores del mismo nivel](../../../wcf/feature-details/peer-resolvers.md).</span><span class="sxs-lookup"><span data-stu-id="a6ccb-131">For more information on peer resolvers, see [Peer Resolvers](../../../wcf/feature-details/peer-resolvers.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a6ccb-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="a6ccb-132">See also</span></span>

- <xref:System.ServiceModel.PeerResolver>
- <xref:System.ServiceModel.PeerResolvers.PeerResolverSettings>
- <xref:System.ServiceModel.NetPeerTcpBinding.Resolver%2A>
- <xref:System.ServiceModel.Configuration.NetPeerTcpBindingElement.Resolver%2A>
- <xref:System.ServiceModel.Configuration.PeerResolverElement>
- [<span data-ttu-id="a6ccb-133">Resoluciones del mismo nivel</span><span class="sxs-lookup"><span data-stu-id="a6ccb-133">Peer Resolvers</span></span>](../../../wcf/feature-details/peer-resolvers.md)
- <span data-ttu-id="a6ccb-134">[Adición de un solucionador personalizado a una aplicación de PeerChannel](https://docs.microsoft.com/previous-versions/ms730105(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="a6ccb-134">[Adding a Custom Resolver to a PeerChannel Application](https://docs.microsoft.com/previous-versions/ms730105(v=vs.90))</span></span>
