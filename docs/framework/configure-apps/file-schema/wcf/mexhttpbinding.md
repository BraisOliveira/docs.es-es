---
title: <mexHttpBinding>
ms.date: 03/30/2017
ms.assetid: e50b2e1f-9668-41a5-8077-dee7abff9f0f
ms.openlocfilehash: bb9e1fc0b3ec62c824864a74efb64c34d2076e66
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69931297"
---
# <a name="mexhttpbinding"></a><span data-ttu-id="74733-101">\<mexHttpBinding></span><span class="sxs-lookup"><span data-stu-id="74733-101">\<mexHttpBinding></span></span>
<span data-ttu-id="74733-102">Especifica los valores para un enlace utilizado para el intercambio de mensajes de WS-MetadataExchange (WS-MEX) sobre HTTP.</span><span class="sxs-lookup"><span data-stu-id="74733-102">Specifies the settings for a binding used for the WS-MetadataExchange (WS-MEX) message exchange over HTTP.</span></span>  
  
 <span data-ttu-id="74733-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="74733-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="74733-104">\<bindings></span><span class="sxs-lookup"><span data-stu-id="74733-104">\<bindings></span></span>  
<span data-ttu-id="74733-105">\<mexHttpBinding></span><span class="sxs-lookup"><span data-stu-id="74733-105">\<mexHttpBinding></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="74733-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="74733-106">Syntax</span></span>  
  
```xml  
<mexHttpBinding>
  <binding closeTimeout="TimeSpan"
           name="string"
           openTimeout="TimeSpan"
           receiveTimeout="TimeSpan"
           sendTimeout="TimeSpan">
  </binding>
</mexHttpBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="74733-107">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="74733-107">Attributes and Elements</span></span>  
 <span data-ttu-id="74733-108">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="74733-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="74733-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="74733-109">Attributes</span></span>  
  
|<span data-ttu-id="74733-110">Atributo</span><span class="sxs-lookup"><span data-stu-id="74733-110">Attribute</span></span>|<span data-ttu-id="74733-111">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="74733-111">Description</span></span>|  
|---------------|-----------------|  
|`closeTimeout`|<span data-ttu-id="74733-112">Un valor <xref:System.TimeSpan> que especifica el intervalo de tiempo del que dispone una operación de cierre para completarse.</span><span class="sxs-lookup"><span data-stu-id="74733-112">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="74733-113">Este valor debe ser mayor o igual que <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="74733-113">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="74733-114">El valor predeterminado es 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="74733-114">The default is 00:01:00.</span></span>|  
|`name`|<span data-ttu-id="74733-115">Cadena que contiene el nombre de configuración del enlace.</span><span class="sxs-lookup"><span data-stu-id="74733-115">A string that contains the configuration name of the binding.</span></span> <span data-ttu-id="74733-116">Este valor debe ser único porque se usa como identificación del enlace.</span><span class="sxs-lookup"><span data-stu-id="74733-116">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="74733-117">Cada enlace tiene los atributos `name` y `namespace` que, juntos, lo identifican de forma exclusiva en los metadatos del servicio.</span><span class="sxs-lookup"><span data-stu-id="74733-117">Each binding has a `name` and `namespace` attribute that together uniquely identify it in the metadata of the service.</span></span> <span data-ttu-id="74733-118">Además, este nombre es único entre los enlaces del mismo tipo.</span><span class="sxs-lookup"><span data-stu-id="74733-118">In addition, this name is unique among bindings of the same type.</span></span> <span data-ttu-id="74733-119">A partir de [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], no es necesario que los enlaces y los comportamientos tengan nombre.</span><span class="sxs-lookup"><span data-stu-id="74733-119">Starting with [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="74733-120">Para obtener más información sobre la configuración predeterminada y los enlaces y comportamientos sin nombre, vea [configuración simplificada](../../../wcf/simplified-configuration.md) y [configuración simplificada para servicios WCF](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="74733-120">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
|`openTimeout`|<span data-ttu-id="74733-121">Valor de la estructura <xref:System.TimeSpan> que especifica el intervalo de tiempo del que dispone una operación de apertura para completarse.</span><span class="sxs-lookup"><span data-stu-id="74733-121">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="74733-122">Este valor debe ser mayor o igual que <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="74733-122">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="74733-123">El valor predeterminado es 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="74733-123">The default is 00:01:00.</span></span>|  
|`receiveTimeout`|<span data-ttu-id="74733-124">Un valor <xref:System.TimeSpan> que especifica el intervalo de tiempo del que dispone una operación de recepción para completarse.</span><span class="sxs-lookup"><span data-stu-id="74733-124">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="74733-125">Este valor debe ser mayor o igual que <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="74733-125">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="74733-126">El valor predeterminado es 00:10:00.</span><span class="sxs-lookup"><span data-stu-id="74733-126">The default is 00:10:00.</span></span>|  
|`sendTimeout`|<span data-ttu-id="74733-127">Un valor <xref:System.TimeSpan> que especifica el intervalo de tiempo del que dispone una operación de envío para completarse.</span><span class="sxs-lookup"><span data-stu-id="74733-127">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="74733-128">Este valor debe ser mayor o igual que <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="74733-128">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="74733-129">El valor predeterminado es 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="74733-129">The default is 00:01:00.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="74733-130">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="74733-130">Child Elements</span></span>  
 <span data-ttu-id="74733-131">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="74733-131">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="74733-132">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="74733-132">Parent Elements</span></span>  
  
|<span data-ttu-id="74733-133">Elemento</span><span class="sxs-lookup"><span data-stu-id="74733-133">Element</span></span>|<span data-ttu-id="74733-134">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="74733-134">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="74733-135">\<bindings></span><span class="sxs-lookup"><span data-stu-id="74733-135">\<bindings></span></span>](bindings.md)|<span data-ttu-id="74733-136">Este elemento contiene una colección de enlaces estándar y personalizados.</span><span class="sxs-lookup"><span data-stu-id="74733-136">This element holds a collection of standard and custom bindings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="74733-137">Comentarios</span><span class="sxs-lookup"><span data-stu-id="74733-137">Remarks</span></span>  
 <span data-ttu-id="74733-138">Este enlace es esencialmente un enlace `WSHttpBinding` con la seguridad deshabilitada.</span><span class="sxs-lookup"><span data-stu-id="74733-138">This binding is essentially a `WSHttpBinding` binding with security disabled.</span></span> <span data-ttu-id="74733-139">Admite la mayoría de las solicitudes de metadatos.</span><span class="sxs-lookup"><span data-stu-id="74733-139">It supports most metadata requests.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="74733-140">Vea también</span><span class="sxs-lookup"><span data-stu-id="74733-140">See also</span></span>

- <xref:System.ServiceModel.Description.MetadataExchangeBindings.CreateMexHttpBinding%2A>
- <xref:System.ServiceModel.Configuration.MexHttpBindingElement>
- [<span data-ttu-id="74733-141">Procedimientos: Publicar metadatos para un servicio mediante un archivo de configuración</span><span class="sxs-lookup"><span data-stu-id="74733-141">How to: Publish Metadata for a Service Using a Configuration File</span></span>](../../../wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)
- [<span data-ttu-id="74733-142">Publicación y recuperación de metadatos a través de un enlace personalizado</span><span class="sxs-lookup"><span data-stu-id="74733-142">Publishing and Retrieving Metadata Over a Custom Binding</span></span>](../../../wcf/extending/publishing-and-retrieving-metadata-over-a-custom-binding.md)
- [<span data-ttu-id="74733-143">Metadatos</span><span class="sxs-lookup"><span data-stu-id="74733-143">Metadata</span></span>](../../../wcf/feature-details/metadata.md)
- [<span data-ttu-id="74733-144">Enlaces</span><span class="sxs-lookup"><span data-stu-id="74733-144">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="74733-145">Configuración de enlaces proporcionados por el sistema</span><span class="sxs-lookup"><span data-stu-id="74733-145">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="74733-146">Utilización de enlaces para configurar servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="74733-146">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="74733-147">\<binding></span><span class="sxs-lookup"><span data-stu-id="74733-147">\<binding></span></span>](../../../misc/binding.md)
