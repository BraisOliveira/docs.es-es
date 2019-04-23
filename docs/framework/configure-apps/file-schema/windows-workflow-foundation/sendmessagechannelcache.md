---
title: <sendMessageChannelCache>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 241e428e-5030-4b13-8a0a-69f05288d3d9
ms.openlocfilehash: 60847f423c61b9e7f49a4a7594c965fb75354714
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59140184"
---
# <a name="sendmessagechannelcache"></a><span data-ttu-id="5c25e-101">\<sendMessageChannelCache></span><span class="sxs-lookup"><span data-stu-id="5c25e-101">\<sendMessageChannelCache></span></span>
<span data-ttu-id="5c25e-102">Un comportamiento de servicio que permite la personalización de la memoria caché compartida niveles, la configuración de la memoria caché de fábrica de canales y la configuración de la memoria caché de canales para los flujos de trabajo que envían mensajes a puntos de conexión de servicio mediante actividades de mensajería de envío.</span><span class="sxs-lookup"><span data-stu-id="5c25e-102">A service behavior that enables the customization of the cache sharing levels, the settings of the channel factory cache, and the settings of the channel cache for workflows that send messages to service endpoints using Send messaging activities.</span></span>  
  
<span data-ttu-id="5c25e-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="5c25e-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="5c25e-104">\<comportamientos ></span><span class="sxs-lookup"><span data-stu-id="5c25e-104">\<behaviors></span></span>  
<span data-ttu-id="5c25e-105">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="5c25e-105">\<serviceBehaviors></span></span>  
<span data-ttu-id="5c25e-106">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="5c25e-106">\<behavior></span></span>  
<span data-ttu-id="5c25e-107">\<sendMessageChannelCache></span><span class="sxs-lookup"><span data-stu-id="5c25e-107">\<sendMessageChannelCache></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5c25e-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5c25e-108">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <sendMessageChannelCache allowUnsafeCaching="Boolean">
        <channelSettings idleTimeout="TimeSpan"
                         leaseTimeout="TimeSpan" 
                         maxItemsInCache="Integer" />
        <factorySettings idleTimeout="TimeSpan" 
                         leaseTimeout="TimeSpan" 
                         maxItemsInCache="Integer" />
      </sendMessageChannelCache>
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5c25e-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="5c25e-109">Attributes and Elements</span></span>  
 <span data-ttu-id="5c25e-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="5c25e-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5c25e-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="5c25e-111">Attributes</span></span>  
  
|<span data-ttu-id="5c25e-112">Atributo</span><span class="sxs-lookup"><span data-stu-id="5c25e-112">Attribute</span></span>|<span data-ttu-id="5c25e-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="5c25e-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="5c25e-114">allowUnsafeCaching</span><span class="sxs-lookup"><span data-stu-id="5c25e-114">allowUnsafeCaching</span></span>|<span data-ttu-id="5c25e-115">Un valor booleano que indica si debe activarse el almacenamiento en la memoria caché.</span><span class="sxs-lookup"><span data-stu-id="5c25e-115">A Boolean value that indicates whether to turn caching on.</span></span> <span data-ttu-id="5c25e-116">Si su servicio de flujo de trabajo tiene enlaces personalizados o los comportamientos personalizados, el almacenamiento en la memoria caché podría no ser seguro y, por consiguiente, está deshabilitado de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="5c25e-116">If your workflow service has custom bindings or custom behaviors, caching could be unsecure and therefore is disabled by default.</span></span> <span data-ttu-id="5c25e-117">Sin embargo, si desea activar almacenamiento en caché en establezca esta propiedad **true**.</span><span class="sxs-lookup"><span data-stu-id="5c25e-117">However, if you want to turn caching on set this property to **true**.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5c25e-118">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="5c25e-118">Child Elements</span></span>  
  
|<span data-ttu-id="5c25e-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="5c25e-119">Element</span></span>|<span data-ttu-id="5c25e-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="5c25e-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5c25e-121">\<channelSettings></span><span class="sxs-lookup"><span data-stu-id="5c25e-121">\<channelSettings></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/channelsettings.md)|<span data-ttu-id="5c25e-122">Especifica los valores de la memoria caché del canal.</span><span class="sxs-lookup"><span data-stu-id="5c25e-122">Specifies the settings of the channel cache.</span></span>|  
|[<span data-ttu-id="5c25e-123">\<factorySettings></span><span class="sxs-lookup"><span data-stu-id="5c25e-123">\<factorySettings></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/factorysettings.md)|<span data-ttu-id="5c25e-124">Especifica los valores de la memoria caché del generador de canales.</span><span class="sxs-lookup"><span data-stu-id="5c25e-124">Specifies the settings of the channel factory cache.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="5c25e-125">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="5c25e-125">Parent Elements</span></span>  
  
|<span data-ttu-id="5c25e-126">Elemento</span><span class="sxs-lookup"><span data-stu-id="5c25e-126">Element</span></span>|<span data-ttu-id="5c25e-127">Descripción</span><span class="sxs-lookup"><span data-stu-id="5c25e-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5c25e-128">\<comportamiento > de \<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="5c25e-128">\<behavior> of \<serviceBehaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/behavior-of-servicebehaviors-of-workflow.md)|<span data-ttu-id="5c25e-129">Especifica un elemento de comportamiento.</span><span class="sxs-lookup"><span data-stu-id="5c25e-129">Specifies a behavior element.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5c25e-130">Comentarios</span><span class="sxs-lookup"><span data-stu-id="5c25e-130">Remarks</span></span>  
 <span data-ttu-id="5c25e-131">Este comportamiento del servicio está orientado para los flujos de trabajo que envían mensajes a los extremos de servicio.</span><span class="sxs-lookup"><span data-stu-id="5c25e-131">This service behavior is intended for workflows that send messages to service endpoints.</span></span> <span data-ttu-id="5c25e-132">Estos flujos de trabajo son normalmente flujos de trabajo del cliente pero podrían ser también servicios de flujo de trabajo que se hospedan en <xref:System.ServiceModel.WorkflowServiceHost>.</span><span class="sxs-lookup"><span data-stu-id="5c25e-132">These workflows are typically client workflows but could also be workflow services that are hosted in a <xref:System.ServiceModel.WorkflowServiceHost>.</span></span>  
  
 <span data-ttu-id="5c25e-133">De manera predeterminada, en un flujo de trabajo hospedado por <xref:System.ServiceModel.WorkflowServiceHost>, la memoria caché usada por las actividades de mensajería de <xref:System.ServiceModel.Activities.Send> se comparte en todas las instancias de flujo de trabajo en <xref:System.ServiceModel.WorkflowServiceHost> (el almacenamiento en caché de nivel de host).</span><span class="sxs-lookup"><span data-stu-id="5c25e-133">By default, in a workflow hosted by a <xref:System.ServiceModel.WorkflowServiceHost>, the cache used by <xref:System.ServiceModel.Activities.Send> messaging activities is shared across all workflow instances in the <xref:System.ServiceModel.WorkflowServiceHost> (host-level caching).</span></span> <span data-ttu-id="5c25e-134">Para un flujo de trabajo del cliente que no esté hospedado por <xref:System.ServiceModel.WorkflowServiceHost>, la memoria caché está solo disponible para la instancia de flujo de trabajo (almacenamiento en caché en el nivel de instancia).</span><span class="sxs-lookup"><span data-stu-id="5c25e-134">For a client workflow that is not hosted by a <xref:System.ServiceModel.WorkflowServiceHost>, the cache is available only to the workflow instance (instance-level caching).</span></span> <span data-ttu-id="5c25e-135">El almacenamiento en la memoria caché está deshabilitado de forma predeterminada para cualquier actividad de envío del flujo de trabajo que tenga definidos extremos en su configuración.</span><span class="sxs-lookup"><span data-stu-id="5c25e-135">Caching is disabled by default for any send activity in your workflow that has endpoints defined in configuration.</span></span>  
  
 <span data-ttu-id="5c25e-136">Para obtener más información sobre cómo cambiar la caché predeterminada de uso compartido de los niveles y opciones de caché para el generador de canales y la memoria caché del canal, consulte [cambiar los niveles de uso compartido de caché para actividades Send](../../../../../docs/framework/wcf/feature-details/changing-the-cache-sharing-levels-for-send-activities.md).</span><span class="sxs-lookup"><span data-stu-id="5c25e-136">For more information about how to change the default cache sharing levels and cache settings for the channel factory and channel cache, see [Changing the Cache Sharing Levels for Send Activities](../../../../../docs/framework/wcf/feature-details/changing-the-cache-sharing-levels-for-send-activities.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="5c25e-137">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="5c25e-137">Example</span></span>  
 <span data-ttu-id="5c25e-138">En un servicio de flujo de trabajo hospedado, puede especificar la configuración de la memoria caché del generador y del canal en el archivo de configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="5c25e-138">In a hosted workflow service, you can specify the factory cache and channel cache settings in the application configuration file.</span></span> <span data-ttu-id="5c25e-139">Para ello, agregue un comportamiento de servicio que contenga los valores de memoria caché para el generador y memoria caché del canal, y agregue este comportamiento de servicio a su servicio.</span><span class="sxs-lookup"><span data-stu-id="5c25e-139">To do so, add a service behavior that contains the cache settings for the factory and channel cache and add this service behavior to your service.</span></span> <span data-ttu-id="5c25e-140">El ejemplo siguiente muestra el contenido de un archivo de configuración que contiene el **MyChannelCacheBehavior** comportamiento del servicio con la configuración de caché de memoria caché y canal de generador personalizado.</span><span class="sxs-lookup"><span data-stu-id="5c25e-140">The following example shows the contents of a configuration file that contains the **MyChannelCacheBehavior**  service behavior with the custom factory cache and channel cache settings.</span></span> <span data-ttu-id="5c25e-141">Este comportamiento del servicio se agrega al servicio mediante el **behaviorConfiguarion** atributo.</span><span class="sxs-lookup"><span data-stu-id="5c25e-141">This service behavior is added to the service through the **behaviorConfiguarion** attribute.</span></span>  
  
```xml  
<configuration>    
  <system.serviceModel>  
    <!-- List of other config sections here -->   
    <behaviors>  
      <serviceBehaviors>  
        <behavior name="MyChannelCacheBehavior">  
          <sendMessageChannelCache allowUnsafeCaching ="false" >  
            <!-- Control only the host level settings -->   
            <factorySettings maxItemsInCache = "8" idleTimeout = "00:05:00" leaseTimeout="10:00:00" />  
            <channelSettings maxItemsInCache = "32" idleTimeout = "00:05:00" leaseTimeout="00:06:00" />  
          </sendMessageChannelCache>  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
    <services>  
      <service name="MyService" behaviorConfiguration="MyChannelCacheBehavior" />  
    </services>  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="5c25e-142">Vea también</span><span class="sxs-lookup"><span data-stu-id="5c25e-142">See also</span></span>

- <xref:System.ServiceModel.Activities.SendMessageChannelCache>
- <xref:System.ServiceModel.Activities.Configuration.SendMessageChannelCacheElement>
- <xref:System.ServiceModel.Activities.Send>
- [<span data-ttu-id="5c25e-143">Cambio de los niveles de uso compartido de caché para actividades Send</span><span class="sxs-lookup"><span data-stu-id="5c25e-143">Changing the Cache Sharing Levels for Send Activities</span></span>](../../../../../docs/framework/wcf/feature-details/changing-the-cache-sharing-levels-for-send-activities.md)
