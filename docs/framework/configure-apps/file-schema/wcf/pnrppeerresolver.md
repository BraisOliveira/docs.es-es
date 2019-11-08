---
title: <pnrpPeerResolver>
ms.date: 03/30/2017
ms.assetid: c1b34f3b-68e5-4911-a367-de49fb61dbc6
ms.openlocfilehash: d3e88d7f2dd991091d3d7abdc715e125ddc9ac56
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/07/2019
ms.locfileid: "73738779"
---
# <a name="pnrppeerresolver"></a><span data-ttu-id="66012-101">\<pnrpPeerResolver ></span><span class="sxs-lookup"><span data-stu-id="66012-101">\<pnrpPeerResolver></span></span>
<span data-ttu-id="66012-102">Especifica que la resolución de PNRP (Protocolo de resolución de nombres de mismo nivel) será utilizada como resolución.</span><span class="sxs-lookup"><span data-stu-id="66012-102">Specifies that the PNRP (Peer Name Resolution Protocol) resolver is to be used as a resolver.</span></span> <span data-ttu-id="66012-103">Este elemento es opcional porque PNRP es la resolución predeterminada.</span><span class="sxs-lookup"><span data-stu-id="66012-103">This element is optional because PNRP is the default resolver.</span></span>  
  
<span data-ttu-id="66012-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="66012-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="66012-105">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="66012-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="66012-106">&nbsp;&nbsp;&nbsp;&nbsp;\<[**enlaces**](bindings.md) ></span><span class="sxs-lookup"><span data-stu-id="66012-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="66012-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<[**customBinding**](custombinding.md) ></span><span class="sxs-lookup"><span data-stu-id="66012-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)</span></span>\
<span data-ttu-id="66012-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**enlace** ></span><span class="sxs-lookup"><span data-stu-id="66012-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="66012-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<pnrpResolver >**</span><span class="sxs-lookup"><span data-stu-id="66012-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<pnrpResolver>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="66012-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="66012-110">Syntax</span></span>  
  
```xml  
<pnrpResolver resolverType="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="66012-111">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="66012-111">Attributes and Elements</span></span>  
 <span data-ttu-id="66012-112">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="66012-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="66012-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="66012-113">Attributes</span></span>  
  
|<span data-ttu-id="66012-114">Atributo</span><span class="sxs-lookup"><span data-stu-id="66012-114">Attribute</span></span>|<span data-ttu-id="66012-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="66012-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="66012-116">resolverType</span><span class="sxs-lookup"><span data-stu-id="66012-116">resolverType</span></span>|<span data-ttu-id="66012-117">Una cadena que especifica la resolución que se va a utilizar.</span><span class="sxs-lookup"><span data-stu-id="66012-117">A string that specifies the resolver to be used.</span></span> <span data-ttu-id="66012-118">Este atributo es opcional.</span><span class="sxs-lookup"><span data-stu-id="66012-118">This attribute is optional.</span></span> <span data-ttu-id="66012-119">Si no se establece, o si está establecido en una cadena vacía, se utiliza PNRP.</span><span class="sxs-lookup"><span data-stu-id="66012-119">If it is not set, or if it is set to an empty string, PNRP is used.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="66012-120">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="66012-120">Child Elements</span></span>  
 <span data-ttu-id="66012-121">Ninguno</span><span class="sxs-lookup"><span data-stu-id="66012-121">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="66012-122">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="66012-122">Parent Elements</span></span>  
  
|<span data-ttu-id="66012-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="66012-123">Element</span></span>|<span data-ttu-id="66012-124">Descripción</span><span class="sxs-lookup"><span data-stu-id="66012-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="66012-125">\<> de enlace</span><span class="sxs-lookup"><span data-stu-id="66012-125">\<binding></span></span>](bindings.md)|<span data-ttu-id="66012-126">Define todas las funcionalidades de enlace del enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="66012-126">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="66012-127">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="66012-127">Example</span></span>  
  
```xml  
<pnrpResolver resolverType="String" />
```  
  
## <a name="see-also"></a><span data-ttu-id="66012-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="66012-128">See also</span></span>

- <xref:System.ServiceModel.Configuration.PnrpPeerResolverElement>
- <xref:System.ServiceModel.Channels.PnrpPeerResolverBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="66012-129">Enlaces</span><span class="sxs-lookup"><span data-stu-id="66012-129">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="66012-130">Extensión de enlaces</span><span class="sxs-lookup"><span data-stu-id="66012-130">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="66012-131">Enlaces personalizados</span><span class="sxs-lookup"><span data-stu-id="66012-131">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="66012-132">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="66012-132">\<customBinding></span></span>](custombinding.md)
- [<span data-ttu-id="66012-133">Resoluciones del mismo nivel</span><span class="sxs-lookup"><span data-stu-id="66012-133">Peer Resolvers</span></span>](../../../wcf/feature-details/peer-resolvers.md)
