---
title: <add> de <participants>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 3c730850-6f8e-4102-acb8-8effb4e09463
ms.openlocfilehash: 65b8a34250a22da79e900f6bee894b501c5ad6ba
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2019
ms.locfileid: "57368264"
---
# <a name="add-of-participants"></a><span data-ttu-id="eeabd-102">\<Agregar > de \<participantes ></span><span class="sxs-lookup"><span data-stu-id="eeabd-102">\<add> of \<participants></span></span>
<span data-ttu-id="eeabd-103">Configure un participante del seguimiento que escucha los registros de seguimiento que se emiten del tiempo de ejecución directamente y los procesa del modo en que cada uno esté configurado.</span><span class="sxs-lookup"><span data-stu-id="eeabd-103">Configure a tracking participant that listens to the tracking records being emitted from the runtime directly and process them in whatever way it was configured.</span></span> <span data-ttu-id="eeabd-104">Esto incluye la escritura en un resultado concreto (p. ej., un archivo, la consola o ETW), procesar o agregar los registros, o cualquier otra combinación que pueda resultar necesaria.</span><span class="sxs-lookup"><span data-stu-id="eeabd-104">This includes writing to a specific output (e.g., file, Console, ETW), processing/aggregating the records, or any other combination that might be required.</span></span>  
  
 <span data-ttu-id="eeabd-105">Para obtener más información de seguimiento de flujo de trabajo y los participantes de seguimiento, vea [seguimiento y traza del flujo de trabajo](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md) y [participantes de seguimiento](../../../../../docs/framework/windows-workflow-foundation/tracking-participants.md).</span><span class="sxs-lookup"><span data-stu-id="eeabd-105">For more information in workflow tracking and tracking participants, see [Workflow Tracking and Tracing](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md) and [Tracking Participants](../../../../../docs/framework/windows-workflow-foundation/tracking-participants.md).</span></span>  
  
<span data-ttu-id="eeabd-106">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="eeabd-106">\<system.serviceModel></span></span>  
<span data-ttu-id="eeabd-107">\<tracking></span><span class="sxs-lookup"><span data-stu-id="eeabd-107">\<tracking></span></span>  
<span data-ttu-id="eeabd-108">\<participants></span><span class="sxs-lookup"><span data-stu-id="eeabd-108">\<participants></span></span>  
<span data-ttu-id="eeabd-109">\<add></span><span class="sxs-lookup"><span data-stu-id="eeabd-109">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eeabd-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="eeabd-110">Syntax</span></span>  
  
```xml
<tracking>
  <participants>
    <add name="String" profileName="String" type="String" />
  </participants>
</tracking>   
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="eeabd-111">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="eeabd-111">Attributes and Elements</span></span>  
 <span data-ttu-id="eeabd-112">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="eeabd-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="eeabd-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="eeabd-113">Attributes</span></span>  
  
|<span data-ttu-id="eeabd-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="eeabd-114">Element</span></span>|<span data-ttu-id="eeabd-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="eeabd-115">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="eeabd-116">name</span><span class="sxs-lookup"><span data-stu-id="eeabd-116">name</span></span>|<span data-ttu-id="eeabd-117">Cadena que especifica el nombre de un participante de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="eeabd-117">A string that specifies the name of a tracking participant.</span></span>|  
|<span data-ttu-id="eeabd-118">profileName</span><span class="sxs-lookup"><span data-stu-id="eeabd-118">profileName</span></span>|<span data-ttu-id="eeabd-119">Una cadena que especifica el nombre del perfil de seguimiento que define los registros de seguimiento a los que se ha suscrito el participante de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="eeabd-119">A string that specifies the name of the tracking profile which defines the tracking records the tracking participant has subscribed to.</span></span>|  
|<span data-ttu-id="eeabd-120">tipo</span><span class="sxs-lookup"><span data-stu-id="eeabd-120">type</span></span>|<span data-ttu-id="eeabd-121">Una cadena que especifica el tipo de un participante de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="eeabd-121">A string that specifies the type of a tracking participant.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="eeabd-122">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="eeabd-122">Child Elements</span></span>  
 <span data-ttu-id="eeabd-123">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="eeabd-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="eeabd-124">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="eeabd-124">Parent Elements</span></span>  
  
|<span data-ttu-id="eeabd-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="eeabd-125">Element</span></span>|<span data-ttu-id="eeabd-126">Descripción</span><span class="sxs-lookup"><span data-stu-id="eeabd-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="eeabd-127">\<participants></span><span class="sxs-lookup"><span data-stu-id="eeabd-127">\<participants></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/participants.md)|<span data-ttu-id="eeabd-128">Una lista de los participantes de seguimiento</span><span class="sxs-lookup"><span data-stu-id="eeabd-128">A list of tracking participants</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="eeabd-129">Comentarios</span><span class="sxs-lookup"><span data-stu-id="eeabd-129">Remarks</span></span>  
 <span data-ttu-id="eeabd-130">Los participantes de seguimiento se usan para obtener los datos de seguimiento emitidos del flujo de trabajo y almacenarlos en los distintos medios.</span><span class="sxs-lookup"><span data-stu-id="eeabd-130">Tracking participants are used to get the tracking data emitted from the workflow and store it into different mediums.</span></span> <span data-ttu-id="eeabd-131">Del mismo modo, cualquier procesamiento posterior en los Registros de seguimiento también puede realizarse dentro del participante de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="eeabd-131">Likewise, any post processing on the tracking Records can also be done within the tracking participant.</span></span>  
  
 <span data-ttu-id="eeabd-132">Varios participantes de seguimiento pueden utilizar los eventos de seguimiento de forma simultánea.</span><span class="sxs-lookup"><span data-stu-id="eeabd-132">Multiple tracking participants can consume the tracking events simultaneously.</span></span> <span data-ttu-id="eeabd-133">Cada participante de seguimiento puede asociarse con un perfil de seguimiento distinto.</span><span class="sxs-lookup"><span data-stu-id="eeabd-133">Each tracking participant can be associated with a different tracking profile.</span></span>  
  
 <span data-ttu-id="eeabd-134">Se proporciona un participante de seguimiento estándar que escribe los registros de seguimiento en una sesión de ETW.</span><span class="sxs-lookup"><span data-stu-id="eeabd-134">A standard tracking participant is provided which writes the tracking records to an ETW session.</span></span> <span data-ttu-id="eeabd-135">El participante se configura en un servicio de flujo de trabajo agregando un comportamiento específico del seguimiento en un archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="eeabd-135">The participant is configured on a workflow service by adding a tracking-specific behavior in a configuration file.</span></span> <span data-ttu-id="eeabd-136">Habilitar un participante de seguimiento de ETW permite realizar un seguimiento de los registros que se van a ver en el visor de eventos.</span><span class="sxs-lookup"><span data-stu-id="eeabd-136">Enabling an ETW tracking participant allows tracking records to be viewed in the event viewer.</span></span> <span data-ttu-id="eeabd-137">Si eso no cumple sus requisitos, también puede escribir un participante de seguimiento personalizado.</span><span class="sxs-lookup"><span data-stu-id="eeabd-137">If that does not meet your requirements, you can also write a custom tracking participant.</span></span>  
  
## <a name="example"></a><span data-ttu-id="eeabd-138">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="eeabd-138">Example</span></span>  
 <span data-ttu-id="eeabd-139">El siguiente ejemplo de configuración muestra el participante de seguimiento de ETW estándar que se está configurando en el archivo Web.config.</span><span class="sxs-lookup"><span data-stu-id="eeabd-139">The following configuration example shows the standard ETW tracking participant being configured in the Web.config file.</span></span>  
  
 <span data-ttu-id="eeabd-140">El identificador del proveedor que el participante de seguimiento de ETW usa para escribir los registros de seguimiento en ETW se define en el  **\<diagnósticos >** sección.</span><span class="sxs-lookup"><span data-stu-id="eeabd-140">The Provider Id that the ETW Tracking Participant uses for writing the Tracking Records to ETW is defined in the **\<diagnostics>** section.</span></span> <span data-ttu-id="eeabd-141">El participante de seguimiento tiene un perfil asociado para especificar los registros de seguimiento a los que se ha suscrito.</span><span class="sxs-lookup"><span data-stu-id="eeabd-141">The tracking participant has a profile associated with it to specify the tracking records it has subscribed to.</span></span> <span data-ttu-id="eeabd-142">Esto viene definido por el **profileName** atributo de la  **\<Agregar >** elemento.</span><span class="sxs-lookup"><span data-stu-id="eeabd-142">This is defined by the **profileName** attribute of the **\<add>** element.</span></span> <span data-ttu-id="eeabd-143">Una vez que se definen, el participante de seguimiento se agrega a la  **\<etwTracking >** comportamiento del servicio.</span><span class="sxs-lookup"><span data-stu-id="eeabd-143">Once these are defined, the Tracking Participant is added to the **\<etwTracking>** service behavior.</span></span> <span data-ttu-id="eeabd-144">Esto agregará los participantes de seguimiento seleccionados a las extensiones de la instancia de flujo de trabajo para que puedan empezar a recibir los registros de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="eeabd-144">This will add the selected Tracking Participants to the Workflow instance’s extensions, so that they begin to receive the Tracking Records.</span></span>  
  
```xml  
<configuration>   
  <system.web>   
    <compilation targetFrameworkMoniker=".NETFramework,Version=v4.0"/>   
  </system.web>   
  <system.serviceModel>   
    <diagnostics etwProviderId="52A3165D-4AD9-405C-B1E8-7D9A257EAC9F" />                
    <tracking>   
      <participants>   
        <add name="EtwTrackingParticipant"   
             type="System.Activities.Tracking.EtwTrackingParticipant, System.Activities, Version=4.0.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35"   
             profileName="HealthMonitoring_Tracking_Profile"/>   
      </participants>   
    </tracking>   
    <behaviors>   
      <serviceBehaviors>   
        <behavior>   
          <etwTracking profileName="Sample Tracking Profile"/>  
        </behavior>   
      </serviceBehaviors>   
    </behaviors>   
  </system.serviceModel>   
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="eeabd-145">Vea también</span><span class="sxs-lookup"><span data-stu-id="eeabd-145">See also</span></span>
- <xref:System.ServiceModel.Activities.Tracking.Configuration.TrackingSection>
- <xref:System.ServiceModel.Activities.Description.EtwTrackingBehavior>
- <xref:System.ServiceModel.Activities.Configuration.EtwTrackingBehaviorElement>
- [<span data-ttu-id="eeabd-146">Seguimiento y traza de flujos de trabajo</span><span class="sxs-lookup"><span data-stu-id="eeabd-146">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="eeabd-147">Participantes de seguimiento</span><span class="sxs-lookup"><span data-stu-id="eeabd-147">Tracking Participants</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-participants.md)
