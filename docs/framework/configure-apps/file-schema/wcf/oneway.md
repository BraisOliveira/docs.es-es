---
title: <oneWay>
ms.date: 03/30/2017
ms.assetid: 00e67e0e-77c0-4695-9138-c0997b0e5f3c
ms.openlocfilehash: f12969d8b752e54916b45c3d0e64f114971b8944
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/06/2019
ms.locfileid: "70397650"
---
# <a name="oneway"></a><span data-ttu-id="85c00-101">\<oneWay></span><span class="sxs-lookup"><span data-stu-id="85c00-101">\<oneWay></span></span>
<span data-ttu-id="85c00-102">Habilita el enrutamiento de paquetes y el uso de métodos unidireccionales para un enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="85c00-102">Enables packet routing and the use of one-way methods for a custom binding.</span></span>  
  
<span data-ttu-id="85c00-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="85c00-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="85c00-104">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="85c00-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="85c00-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> de enlaces**](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="85c00-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="85c00-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<customBinding >** ](custombinding.md)</span><span class="sxs-lookup"><span data-stu-id="85c00-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)</span></span>\
<span data-ttu-id="85c00-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> de enlace**</span><span class="sxs-lookup"><span data-stu-id="85c00-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="85c00-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> oneWay**</span><span class="sxs-lookup"><span data-stu-id="85c00-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<oneWay>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="85c00-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="85c00-109">Syntax</span></span>  
  
```xml  
<oneWay packetRoutable="Boolean">
  <channelPoolSettings idleTimeout="TimeSpan"
                       leaseTimeout="TimeSpan"
                       maxOutboundConnectionsPerEndpoint="Integer" />
</oneWay>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="85c00-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="85c00-110">Attributes and Elements</span></span>  
 <span data-ttu-id="85c00-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="85c00-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="85c00-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="85c00-112">Attributes</span></span>  
  
|<span data-ttu-id="85c00-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="85c00-113">Attribute</span></span>|<span data-ttu-id="85c00-114">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="85c00-114">Description</span></span>|  
|---------------|-----------------|  
|`packetRoutable`|<span data-ttu-id="85c00-115">Un valor booleano que especifica si se habilita el enrutamiento del paquete.</span><span class="sxs-lookup"><span data-stu-id="85c00-115">A Boolean value that specifies whether packet routing is enabled.</span></span> <span data-ttu-id="85c00-116">El valor predeterminado es `false`.</span><span class="sxs-lookup"><span data-stu-id="85c00-116">The default is `false`.</span></span>|  
|`MaxAcceptedChannels`|<span data-ttu-id="85c00-117">Un entero que especifica el número máximo de canales que se pueden aceptar.</span><span class="sxs-lookup"><span data-stu-id="85c00-117">An integer that specifies the maximum number of channels that can be accepted.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="85c00-118">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="85c00-118">Child Elements</span></span>  
  
|<span data-ttu-id="85c00-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="85c00-119">Element</span></span>|<span data-ttu-id="85c00-120">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="85c00-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="85c00-121">\<channelPoolSettings></span><span class="sxs-lookup"><span data-stu-id="85c00-121">\<channelPoolSettings></span></span>](channelpoolsettings.md)|<span data-ttu-id="85c00-122">Un objeto <xref:System.ServiceModel.Configuration.ChannelPoolSettingsElement> que contiene propiedades del grupo de canales para el canal actual.</span><span class="sxs-lookup"><span data-stu-id="85c00-122">A <xref:System.ServiceModel.Configuration.ChannelPoolSettingsElement> object that contains properties of the channel pool for the current channel.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="85c00-123">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="85c00-123">Parent Elements</span></span>  
  
|<span data-ttu-id="85c00-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="85c00-124">Element</span></span>|<span data-ttu-id="85c00-125">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="85c00-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="85c00-126">\<binding></span><span class="sxs-lookup"><span data-stu-id="85c00-126">\<binding></span></span>](../../../misc/binding.md)|<span data-ttu-id="85c00-127">Define todas las funcionalidades de enlace del enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="85c00-127">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="85c00-128">Comentarios</span><span class="sxs-lookup"><span data-stu-id="85c00-128">Remarks</span></span>  
 <span data-ttu-id="85c00-129">Para habilitar el enrutamiento de paquetes, se necesita una capa de conversión unidireccional, que proporciona este elemento.</span><span class="sxs-lookup"><span data-stu-id="85c00-129">To enable packet routing, a one-way conversion layer is required, which this element provides.</span></span> <span data-ttu-id="85c00-130">Un usuario puede crear un enlace personalizado que coloque este enlace en una capa a través de un transporte consciente de sesión o de solicitud/respuesta para que se pueda realizar el enrutamiento de paquetes.</span><span class="sxs-lookup"><span data-stu-id="85c00-130">A user can create a custom binding that layers this binding over a session-aware or request-reply transport to make it packet routable.</span></span> <span data-ttu-id="85c00-131">Este elemento también es útil cuando desea exponer los métodos unidireccionales de una manera más nativa.</span><span class="sxs-lookup"><span data-stu-id="85c00-131">This element is also useful when you want to expose one-way methods in a more native fashion.</span></span> <span data-ttu-id="85c00-132">Se pueden aplicar más transformaciones sobre esta capa, como Dúplex Compuesto y Mensajería de confianza.</span><span class="sxs-lookup"><span data-stu-id="85c00-132">More transformations can be applied over this layer, such as Composite Duplex and Reliable Messaging.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="85c00-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="85c00-133">See also</span></span>

- <xref:System.ServiceModel.Channels.OneWayBindingElement>
- <xref:System.ServiceModel.Configuration.OneWayElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="85c00-134">Enlaces</span><span class="sxs-lookup"><span data-stu-id="85c00-134">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="85c00-135">Extensión de enlaces</span><span class="sxs-lookup"><span data-stu-id="85c00-135">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="85c00-136">Enlaces personalizados</span><span class="sxs-lookup"><span data-stu-id="85c00-136">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="85c00-137">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="85c00-137">\<customBinding></span></span>](custombinding.md)
