---
title: <namedPipeTransport>
ms.date: 03/30/2017
ms.assetid: 9fc3f42f-43e2-4ab1-8bc7-3c95a9220df1
ms.openlocfilehash: 819639eabf0332a34d6a7250159d24e42552f874
ms.sourcegitcommit: 9b1ac36b6c80176fd4e20eb5bfcbd9d56c3264cf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/28/2019
ms.locfileid: "67423099"
---
# <a name="namedpipetransport"></a><span data-ttu-id="31e7c-101">\<namedPipeTransport></span><span class="sxs-lookup"><span data-stu-id="31e7c-101">\<namedPipeTransport></span></span>
<span data-ttu-id="31e7c-102">Define un transporte que hace que un canal transfiera mensajes mediante las canalizaciones con nombre cuando está incluido en un enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="31e7c-102">Defines a transport that causes a channel to transfer messages using named pipes when it is included in a custom binding.</span></span>  
  
<span data-ttu-id="31e7c-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="31e7c-103">\<system.serviceModel></span></span>  
<span data-ttu-id="31e7c-104">\<bindings></span><span class="sxs-lookup"><span data-stu-id="31e7c-104">\<bindings></span></span>  
<span data-ttu-id="31e7c-105">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="31e7c-105">\<customBinding></span></span>  
<span data-ttu-id="31e7c-106">\<binding></span><span class="sxs-lookup"><span data-stu-id="31e7c-106">\<binding></span></span>  
<span data-ttu-id="31e7c-107">\<namePipeTransport></span><span class="sxs-lookup"><span data-stu-id="31e7c-107">\<namePipeTransport></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="31e7c-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="31e7c-108">Syntax</span></span>  
  
```xml  
<namedPipeTransport channelInitializationTimeout="TimeSpan"
                    connectionBufferSize="Integer"
                    hostNameComparisonMode="StrongWildcard/Exact/WeakWildcard"
                    manualAddressing="Boolean"
                    maxBufferPoolSize="Integer"
                    maxBufferSize="Integer"
                    maxOutputDelay="TimeSpan"
                    maxPendingAccepts="Integer"
                    maxPendingConnections="Integer"
                    maxReceivedMessageSize="Integer"
                    transferMode="Buffered/Streamed/StreamedRequest/StreamedResponse">
  <connectionPoolSettings groupName="String"
                          idleTimeout="TimeSpan"
                          maxOutboundConnectionsPerEndpoint="Integer" />
</namedPipeTransport>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="31e7c-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="31e7c-109">Attributes and Elements</span></span>  
<span data-ttu-id="31e7c-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="31e7c-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="31e7c-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="31e7c-111">Attributes</span></span>  
<span data-ttu-id="31e7c-112">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="31e7c-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="31e7c-113">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="31e7c-113">Child Elements</span></span>  
  
|<span data-ttu-id="31e7c-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="31e7c-114">Element</span></span>|<span data-ttu-id="31e7c-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="31e7c-115">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="31e7c-116">ChannelInitializationTimeout</span><span class="sxs-lookup"><span data-stu-id="31e7c-116">ChannelInitializationTimeout</span></span>|<span data-ttu-id="31e7c-117">Obtiene o establece un <xref:System.TimeSpan> que determina el tiempo máximo que un canal puede estar en el estado de inicialización antes de que se desconecte.</span><span class="sxs-lookup"><span data-stu-id="31e7c-117">Gets or sets a <xref:System.TimeSpan> that determines the maximum time a channel can be in the initialization status before being disconnected.</span></span>|  
|<span data-ttu-id="31e7c-118">ConnectionBufferSize</span><span class="sxs-lookup"><span data-stu-id="31e7c-118">ConnectionBufferSize</span></span>|<span data-ttu-id="31e7c-119">Obtiene o establece el tamaño del búfer usado para transmitir un bloque del mensaje serializado en la conexión del cliente o servicio.</span><span class="sxs-lookup"><span data-stu-id="31e7c-119">Gets or sets the size of the buffer used to transmit a chunk of the serialized message on the wire from the client or service.</span></span>|  
|<span data-ttu-id="31e7c-120">hostNameComparisonMode</span><span class="sxs-lookup"><span data-stu-id="31e7c-120">hostNameComparisonMode</span></span>|<span data-ttu-id="31e7c-121">Obtiene o establece un valor que indica si el nombre del host se usa para alcanzar el servicio al coincidir con el URI.</span><span class="sxs-lookup"><span data-stu-id="31e7c-121">Gets or sets a value that indicates whether the hostname is used to reach the service when matching on the URI.</span></span>|  
|<span data-ttu-id="31e7c-122">manualAddressing</span><span class="sxs-lookup"><span data-stu-id="31e7c-122">manualAddressing</span></span>|<span data-ttu-id="31e7c-123">Obtiene o establece un valor que indica si se requiere la dirección manual del mensaje.</span><span class="sxs-lookup"><span data-stu-id="31e7c-123">Gets or sets a value that indicates whether manual addressing of the message is required.</span></span>|  
|<span data-ttu-id="31e7c-124">maxBufferPoolSize</span><span class="sxs-lookup"><span data-stu-id="31e7c-124">maxBufferPoolSize</span></span>|<span data-ttu-id="31e7c-125">Obtiene o establece el tamaño máximo, en bytes, de cualquier grupo de búferes utilizado por el transporte.</span><span class="sxs-lookup"><span data-stu-id="31e7c-125">Gets or sets the maximum size, in bytes, of any buffer pools used by the transport.</span></span>|  
|<span data-ttu-id="31e7c-126">maxBufferSize</span><span class="sxs-lookup"><span data-stu-id="31e7c-126">maxBufferSize</span></span>|<span data-ttu-id="31e7c-127">Obtiene o establece el tamaño máximo del búfer que se va a usar.</span><span class="sxs-lookup"><span data-stu-id="31e7c-127">Gets or sets the maximum size of the buffer to use.</span></span> <span data-ttu-id="31e7c-128">Para mensajes transmitidos por secuencias, este valor debería ser por lo menos el tamaño máximo posible de los encabezados de mensaje, que se leen en modo almacenado en búfer.</span><span class="sxs-lookup"><span data-stu-id="31e7c-128">For streamed messages, this value should be at least the maximum possible size of the message headers, which are read in buffered mode.</span></span>|  
|<span data-ttu-id="31e7c-129">maxOutputDelay</span><span class="sxs-lookup"><span data-stu-id="31e7c-129">maxOutputDelay</span></span>|<span data-ttu-id="31e7c-130">Obtiene o establece el intervalo máximo de tiempo que un bloque de mensaje o un mensaje completo pueden estar almacenados en búfer en memoria antes de que se envíen.</span><span class="sxs-lookup"><span data-stu-id="31e7c-130">Gets or sets the maximum interval of time that a chunk of a message or a full message can remain buffered in memory before being sent out.</span></span>|  
|<span data-ttu-id="31e7c-131">maxPendingAccepts</span><span class="sxs-lookup"><span data-stu-id="31e7c-131">maxPendingAccepts</span></span>|<span data-ttu-id="31e7c-132">Obtiene o establece el número máximo de canales de que un servicio puede tener en espera en un agente de escucha para procesar conexiones entrantes al servicio.</span><span class="sxs-lookup"><span data-stu-id="31e7c-132">Gets or sets the maximum number of channels a service can have waiting on a listener for processing incoming connections to the service.</span></span>|  
|<span data-ttu-id="31e7c-133">maxPendingConnections</span><span class="sxs-lookup"><span data-stu-id="31e7c-133">maxPendingConnections</span></span>|<span data-ttu-id="31e7c-134">Obtiene o establece el número máximo de conexiones pendientes de distribución en el servicio.</span><span class="sxs-lookup"><span data-stu-id="31e7c-134">Gets or sets the maximum number of connections awaiting dispatch on the service.</span></span>|  
|<span data-ttu-id="31e7c-135">maxReceivedMessageSize</span><span class="sxs-lookup"><span data-stu-id="31e7c-135">maxReceivedMessageSize</span></span>|<span data-ttu-id="31e7c-136">Obtiene y establece el tamaño máximo permitido del mensaje, en bytes, que se pueden recibir.</span><span class="sxs-lookup"><span data-stu-id="31e7c-136">Gets and sets the maximum allowable message size, in bytes, that can be received.</span></span>|  
|<span data-ttu-id="31e7c-137">transferMode</span><span class="sxs-lookup"><span data-stu-id="31e7c-137">transferMode</span></span>|<span data-ttu-id="31e7c-138">Obtiene o establece un valor que indica si los mensajes están almacenados en búfer o se transmiten por secuencias mediante el transporte orientado a la conexión.</span><span class="sxs-lookup"><span data-stu-id="31e7c-138">Gets or sets a value that indicates whether the messages are buffered or streamed with the connection-oriented transport.</span></span>|  
|[<span data-ttu-id="31e7c-139">\<connectionPoolSettings > de \<namedPipeTransport ></span><span class="sxs-lookup"><span data-stu-id="31e7c-139">\<connectionPoolSettings> of \<namedPipeTransport></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/connectionpoolsettings.md)|<span data-ttu-id="31e7c-140">Especifica valores adicionales del grupo de conexiones para un enlace de canalización con nombre.</span><span class="sxs-lookup"><span data-stu-id="31e7c-140">Specifies additional connection pool settings for a Named Pipe binding.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="31e7c-141">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="31e7c-141">Parent Elements</span></span>  
  
|<span data-ttu-id="31e7c-142">Elemento</span><span class="sxs-lookup"><span data-stu-id="31e7c-142">Element</span></span>|<span data-ttu-id="31e7c-143">Descripción</span><span class="sxs-lookup"><span data-stu-id="31e7c-143">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="31e7c-144">\<binding></span><span class="sxs-lookup"><span data-stu-id="31e7c-144">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="31e7c-145">Define todas las funcionalidades de enlace del enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="31e7c-145">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="31e7c-146">Comentarios</span><span class="sxs-lookup"><span data-stu-id="31e7c-146">Remarks</span></span>  
<span data-ttu-id="31e7c-147">Este transporte utiliza los URI del formulario "net.pipe://hostname/path."</span><span class="sxs-lookup"><span data-stu-id="31e7c-147">This transport uses URIs of the form "net.pipe://hostname/path".</span></span> <span data-ttu-id="31e7c-148">Otros componentes URI son opcionales.</span><span class="sxs-lookup"><span data-stu-id="31e7c-148">Other URI components are optional.</span></span>  
  
<span data-ttu-id="31e7c-149">El elemento `namedPipeTransport` es el punto inicial para crear un enlace personalizado que implementa el protocolo de transporte de canalizaciones con nombre.</span><span class="sxs-lookup"><span data-stu-id="31e7c-149">The `namedPipeTransport` element is the starting point for creating a custom binding that implements the named pipes transport protocol.</span></span> <span data-ttu-id="31e7c-150">Este transporte se utiliza para la comunicación entre WCF y Windows Communication Foundation (WCF) en el equipo.</span><span class="sxs-lookup"><span data-stu-id="31e7c-150">This transport is used for on-machine Windows Communication Foundation (WCF)-to-WCF communication.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="31e7c-151">Vea también</span><span class="sxs-lookup"><span data-stu-id="31e7c-151">See also</span></span>

- <xref:System.ServiceModel.Configuration.NamedPipeTransportElement>
- <xref:System.ServiceModel.Channels.NamedPipeTransportBindingElement>
- <xref:System.ServiceModel.Channels.TransportBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="31e7c-152">Transportes</span><span class="sxs-lookup"><span data-stu-id="31e7c-152">Transports</span></span>](../../../../../docs/framework/wcf/feature-details/transports.md)
- [<span data-ttu-id="31e7c-153">Elección del transporte</span><span class="sxs-lookup"><span data-stu-id="31e7c-153">Choosing a Transport</span></span>](../../../../../docs/framework/wcf/feature-details/choosing-a-transport.md)
- [<span data-ttu-id="31e7c-154">Enlaces</span><span class="sxs-lookup"><span data-stu-id="31e7c-154">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="31e7c-155">Extensión de enlaces</span><span class="sxs-lookup"><span data-stu-id="31e7c-155">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)
- [<span data-ttu-id="31e7c-156">Enlaces personalizados</span><span class="sxs-lookup"><span data-stu-id="31e7c-156">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)
- [<span data-ttu-id="31e7c-157">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="31e7c-157">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
