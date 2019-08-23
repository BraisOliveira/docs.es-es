---
title: <webSocketSettings>
ms.date: 03/30/2017
ms.assetid: bbf97e02-8dd1-4922-acac-3cd33397b249
ms.openlocfilehash: 5c9dbec13dd0d71ba1b92ea971d067540013b6f9
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69940314"
---
# <a name="websocketsettings"></a><span data-ttu-id="d3ab8-101">\<webSocketSettings></span><span class="sxs-lookup"><span data-stu-id="d3ab8-101">\<webSocketSettings></span></span>
<span data-ttu-id="d3ab8-102">Un elemento de configuración usado para especificar valores de WebSockets.</span><span class="sxs-lookup"><span data-stu-id="d3ab8-102">A configuration element used to specify Web Socket settings.</span></span>  
  
<span data-ttu-id="d3ab8-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="d3ab8-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="d3ab8-104">\<bindings></span><span class="sxs-lookup"><span data-stu-id="d3ab8-104">\<bindings></span></span>  
<span data-ttu-id="d3ab8-105">\<netHttpBinding></span><span class="sxs-lookup"><span data-stu-id="d3ab8-105">\<netHttpBinding></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d3ab8-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d3ab8-106">Syntax</span></span>  
  
```xml  
<netHttpBinding>
  <binding>
    <webSocketSettings createNotificationOnConnection="Boolean"
                       disablePayloadMasking="Boolean"
                       keepAliveInterval="TimeSpan"
                       maxPendingConnections="Integer"
                       receiveBufferSize="Integer"
                       sendBufferSize="Integer"
                       subProtocol="String"
                       transportUsage="WhenDuplex/Always/Never" />
  </binding>
</netHttpBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d3ab8-107">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="d3ab8-107">Attributes and Elements</span></span>  
 <span data-ttu-id="d3ab8-108">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="d3ab8-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d3ab8-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="d3ab8-109">Attributes</span></span>  
  
|<span data-ttu-id="d3ab8-110">Atributo</span><span class="sxs-lookup"><span data-stu-id="d3ab8-110">Attribute</span></span>|<span data-ttu-id="d3ab8-111">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="d3ab8-111">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="d3ab8-112">createNotificationOnConnection</span><span class="sxs-lookup"><span data-stu-id="d3ab8-112">createNotificationOnConnection</span></span>|<span data-ttu-id="d3ab8-113">Especifica si se envía una notificación al realizar la conexión.</span><span class="sxs-lookup"><span data-stu-id="d3ab8-113">Specifies whether a notification is sent upon connection.</span></span>|  
|<span data-ttu-id="d3ab8-114">disablePayloadMasking</span><span class="sxs-lookup"><span data-stu-id="d3ab8-114">disablePayloadMasking</span></span>|<span data-ttu-id="d3ab8-115">Especifica si el enmascaramiento de WebSocket está deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="d3ab8-115">Specifies whether Web Socket masking is disabled.</span></span>|  
|<span data-ttu-id="d3ab8-116">keepAliveInterval</span><span class="sxs-lookup"><span data-stu-id="d3ab8-116">keepAliveInterval</span></span>|<span data-ttu-id="d3ab8-117">Especifica el intervalo entre mensajes de mantenimiento de conexión.</span><span class="sxs-lookup"><span data-stu-id="d3ab8-117">Specifies the keep alive interval.</span></span>|  
|<span data-ttu-id="d3ab8-118">maxPendingConnections</span><span class="sxs-lookup"><span data-stu-id="d3ab8-118">maxPendingConnections</span></span>|<span data-ttu-id="d3ab8-119">Especifica el número máximo de conexiones pendientes de distribución en el servicio.</span><span class="sxs-lookup"><span data-stu-id="d3ab8-119">Specifies the maximum number of connections awaiting dispatch on the service.</span></span>|  
|<span data-ttu-id="d3ab8-120">receiveBufferSize</span><span class="sxs-lookup"><span data-stu-id="d3ab8-120">receiveBufferSize</span></span>|<span data-ttu-id="d3ab8-121">Especifica el tamaño de búfer de recibir.</span><span class="sxs-lookup"><span data-stu-id="d3ab8-121">Specifies the size of the receive buffer.</span></span>|  
|<span data-ttu-id="d3ab8-122">sendBufferSize</span><span class="sxs-lookup"><span data-stu-id="d3ab8-122">sendBufferSize</span></span>|<span data-ttu-id="d3ab8-123">Especifica el tamaño de búfer de enviar.</span><span class="sxs-lookup"><span data-stu-id="d3ab8-123">Specifies the size of the send buffer.</span></span>|  
|<span data-ttu-id="d3ab8-124">subProtocol</span><span class="sxs-lookup"><span data-stu-id="d3ab8-124">subProtocol</span></span>|<span data-ttu-id="d3ab8-125">Especifica el subprotocolo WebSocket.</span><span class="sxs-lookup"><span data-stu-id="d3ab8-125">Specifies the Web Socket subprotocol.</span></span>|  
|<span data-ttu-id="d3ab8-126">transportUsage</span><span class="sxs-lookup"><span data-stu-id="d3ab8-126">transportUsage</span></span>|<span data-ttu-id="d3ab8-127">Especifica cuándo usar WebSockets.</span><span class="sxs-lookup"><span data-stu-id="d3ab8-127">Specifies when to use Web Sockets.</span></span>|  
  
## <a name="transportusage-attribute"></a><span data-ttu-id="d3ab8-128">Atributo transportUsage</span><span class="sxs-lookup"><span data-stu-id="d3ab8-128">transportUsage Attribute</span></span>  
  
|<span data-ttu-id="d3ab8-129">Value</span><span class="sxs-lookup"><span data-stu-id="d3ab8-129">Value</span></span>|<span data-ttu-id="d3ab8-130">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="d3ab8-130">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="d3ab8-131">WhenDuplex</span><span class="sxs-lookup"><span data-stu-id="d3ab8-131">WhenDuplex</span></span>|<span data-ttu-id="d3ab8-132">Use el protocolo WebSocket cuando el contrato sea dúplex.</span><span class="sxs-lookup"><span data-stu-id="d3ab8-132">Use the Web Socket protocol when the contract is duplex.</span></span>|  
|<span data-ttu-id="d3ab8-133">Siempre</span><span class="sxs-lookup"><span data-stu-id="d3ab8-133">Always</span></span>|<span data-ttu-id="d3ab8-134">Use siempre el protocolo WebSocket independientemente del contrato.</span><span class="sxs-lookup"><span data-stu-id="d3ab8-134">Always use the Web Socket protocol regardless of the contract.</span></span>|  
|<span data-ttu-id="d3ab8-135">Nunca</span><span class="sxs-lookup"><span data-stu-id="d3ab8-135">Never</span></span>|<span data-ttu-id="d3ab8-136">Nunca use el protocolo WebSocket.</span><span class="sxs-lookup"><span data-stu-id="d3ab8-136">Never use the Web Socket protocol.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d3ab8-137">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="d3ab8-137">Child Elements</span></span>  
 <span data-ttu-id="d3ab8-138">None</span><span class="sxs-lookup"><span data-stu-id="d3ab8-138">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d3ab8-139">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="d3ab8-139">Parent Elements</span></span>  
  
|<span data-ttu-id="d3ab8-140">Elemento</span><span class="sxs-lookup"><span data-stu-id="d3ab8-140">Element</span></span>|<span data-ttu-id="d3ab8-141">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="d3ab8-141">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="d3ab8-142">\<netHttpBinding></span><span class="sxs-lookup"><span data-stu-id="d3ab8-142">\<netHttpBinding></span></span>|<span data-ttu-id="d3ab8-143">Especifica el NetHttpBinding</span><span class="sxs-lookup"><span data-stu-id="d3ab8-143">Specifies the NetHttpBinding</span></span>|  
  
## <a name="example"></a><span data-ttu-id="d3ab8-144">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d3ab8-144">Example</span></span>  
 <span data-ttu-id="d3ab8-145">En el ejemplo siguiente se muestra cómo usar \<el elemento > de webSocketSettings.</span><span class="sxs-lookup"><span data-stu-id="d3ab8-145">The following example shows how to use the \<webSocketSettings> element.</span></span>  
  
```xml  
<netHttpBinding>
  <binding>
    <webSocketSettings createNotificationOnConnection="true"
                       disablePayloadMasking="false"
                       keepAliveInterval="00:10:00"
                       maxPendingConnections="100"
                       receiveBufferSize="1000"
                       sendBufferSize="1000"
                       subProtocol="Soap"
                       transportUsage="WhenDuplex/Always/Never" />
  </binding>
</netHttpBinding>
```  
  
## <a name="see-also"></a><span data-ttu-id="d3ab8-146">Vea también</span><span class="sxs-lookup"><span data-stu-id="d3ab8-146">See also</span></span>

- <xref:System.ServiceModel.Channels.Binding>
- <xref:System.ServiceModel.Channels.BindingElement>
- <xref:System.ServiceModel.BasicHttpBinding>
- <xref:System.ServiceModel.Configuration.BasicHttpBindingElement>
- [<span data-ttu-id="d3ab8-147">Enlaces</span><span class="sxs-lookup"><span data-stu-id="d3ab8-147">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="d3ab8-148">Configuración de enlaces proporcionados por el sistema</span><span class="sxs-lookup"><span data-stu-id="d3ab8-148">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="d3ab8-149">Utilización de enlaces para configurar servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="d3ab8-149">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="d3ab8-150">\<binding></span><span class="sxs-lookup"><span data-stu-id="d3ab8-150">\<binding></span></span>](../../../misc/binding.md)
