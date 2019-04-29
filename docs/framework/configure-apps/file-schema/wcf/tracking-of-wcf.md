---
title: <tracking> de WCF
ms.date: 03/30/2017
ms.assetid: 70cfaf24-a91c-4e56-ac47-d2ed87a963b3
ms.openlocfilehash: 4aac9f28de746e2a75a079cbaf774f01f4a08fca
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61758150"
---
# <a name="tracking-of-wcf"></a><span data-ttu-id="dfe17-102">\<seguimiento > de WCF</span><span class="sxs-lookup"><span data-stu-id="dfe17-102">\<tracking> of WCF</span></span>
<span data-ttu-id="dfe17-103">Representa una sección de configuración para definir los valores de seguimiento de un servicio de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="dfe17-103">Represents a configuration section for defining tracking settings for a workflow service.</span></span>  
  
 <span data-ttu-id="dfe17-104">Para obtener más información del seguimiento de flujo de trabajo y su configuración, consulte [seguimiento y traza del flujo de trabajo](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md) y [configuración del seguimiento para un flujo de trabajo](../../../../../docs/framework/windows-workflow-foundation/configuring-tracking-for-a-workflow.md).</span><span class="sxs-lookup"><span data-stu-id="dfe17-104">For more information in workflow tracking and its configuration, see [Workflow Tracking and Tracing](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md) and [Configuring Tracking for a Workflow](../../../../../docs/framework/windows-workflow-foundation/configuring-tracking-for-a-workflow.md).</span></span>  
  
 <span data-ttu-id="dfe17-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="dfe17-105">\<system.serviceModel></span></span>  
<span data-ttu-id="dfe17-106">\<tracking></span><span class="sxs-lookup"><span data-stu-id="dfe17-106">\<tracking></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dfe17-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="dfe17-107">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <tracking>
    <participants>
      <add name="String"
           profileName="String"
           type="String" />
    </participants>
    <profiles>
      <trackingProfile name="String">
        <workflow activityDefinitionId="String">
          <activityScheduledQueries>
            <activityScheduledQuery activityName="String"
                                    childActivityName="String"/>
          </activityScheduledQueries>
          <activityStateQueries>
            <activityStateQuery activityName="String" />
            <arguments>
              <argument name="String"/>
            </arguments>
            <states>
              <state name="String"/>
            </states>
            <variables>
              <variable name="String"/>
            </variables>
          </activityStateQueries>
          <bookmarkResumptionQueries>
            <bookmarkResumptionQuery name="String" />
          </bookmarkResumptionQueries>
          <cancelRequestQueries>
            <cancelRequestQuery activityName="String"
                                childActivityName="String"/>
          </cancelRequestQueries>
          <customTrackingQueries>
            <customTrackingQuery activityName="String"
                                 name="String"/>
          </customTrackingQueries>
          <faultPropagationQueries>
            <faultPropagationQuery activityName="String"
                                   faultHandlerActivityName="String"/>
          </faultPropagationQueries>
          <workflowInstanceQueries>
            <workflowInstanceQuery>
              <states>
                <state name="String"/>
              </states>
            </workflowInstanceQuery>
          </workflowInstanceQueries>
        </workflow>
      </trackingProfile>
    </profiles>
  </tracking>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="dfe17-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="dfe17-108">Attributes and Elements</span></span>  
 <span data-ttu-id="dfe17-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="dfe17-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="dfe17-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="dfe17-110">Attributes</span></span>  
 <span data-ttu-id="dfe17-111">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="dfe17-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="dfe17-112">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="dfe17-112">Child Elements</span></span>  
  
|<span data-ttu-id="dfe17-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="dfe17-113">Element</span></span>|<span data-ttu-id="dfe17-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="dfe17-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="dfe17-115">\<participants></span><span class="sxs-lookup"><span data-stu-id="dfe17-115">\<participants></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/participants.md)|<span data-ttu-id="dfe17-116">Una colección de elementos de configuración que definen a participantes que suscribirse a registros de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="dfe17-116">A collection of configuration elements defining participants that subscribe to tracking records.</span></span> <span data-ttu-id="dfe17-117">Los participantes de seguimiento contienen la lógica para procesar la carga de los registros de seguimiento (por ejemplo, podrían escribir en un archivo).</span><span class="sxs-lookup"><span data-stu-id="dfe17-117">The tracking participants contain the logic to process the payload from the tracking records (for example, they could choose to write to a file).</span></span>|  
|[<span data-ttu-id="dfe17-118">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="dfe17-118">\<trackingProfile></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/trackingprofile.md)|<span data-ttu-id="dfe17-119">Un perfil de seguimiento para filtrar registros de seguimiento emitidos desde una instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="dfe17-119">A tracking profile to filter tracking records emitted from a workflow instance.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="dfe17-120">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="dfe17-120">Parent Elements</span></span>  
  
|<span data-ttu-id="dfe17-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="dfe17-121">Element</span></span>|<span data-ttu-id="dfe17-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="dfe17-122">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="dfe17-123">system.ServiceModel</span><span class="sxs-lookup"><span data-stu-id="dfe17-123">system.ServiceModel</span></span>|<span data-ttu-id="dfe17-124">El elemento raíz de todos los elementos de configuración de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="dfe17-124">The root element of all workflow configuration elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="dfe17-125">Comentarios</span><span class="sxs-lookup"><span data-stu-id="dfe17-125">Remarks</span></span>  
 <span data-ttu-id="dfe17-126">El seguimiento ofrece la posibilidad de examinar la ejecución de un flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="dfe17-126">Tracking provides you with the ability to examine the execution of a workflow.</span></span> <span data-ttu-id="dfe17-127">La infraestructura de seguimiento del flujo de trabajo instrumenta un flujo de trabajo para emitir registros que reflejan los eventos clave durante la ejecución.</span><span class="sxs-lookup"><span data-stu-id="dfe17-127">The workflow tracking infrastructure instruments a workflow to emit records reflecting key events during the execution.</span></span> <span data-ttu-id="dfe17-128">Por ejemplo, cuando una instancia de flujo de trabajo se inicia o completa, se emiten los registros de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="dfe17-128">For example, when a workflow instance starts or completes tracking records are emitted.</span></span> <span data-ttu-id="dfe17-129">El seguimiento también puede extraer datos comerciales relevantes asociados a las variables de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="dfe17-129">Tracking can also extract business relevant data associated with the workflow variables.</span></span> <span data-ttu-id="dfe17-130">Por ejemplo, si el flujo de trabajo representa un sistema de procesamiento de pedidos, el Id. del pedido se puede extraer junto con el registro de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="dfe17-130">For example, if the workflow represents an order processing system the order id can be extracted along with the tracking record.</span></span> <span data-ttu-id="dfe17-131">En general, la habilitación del seguimiento de WF facilita el diagnóstico o los análisis comerciales durante la ejecución de un flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="dfe17-131">In general, enabling WF tracking facilitates diagnostics or business analytics over a workflow execution.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dfe17-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="dfe17-132">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.TrackingSection?displayProperty=nameWithType>
- [<span data-ttu-id="dfe17-133">Seguimiento y traza de flujos de trabajo</span><span class="sxs-lookup"><span data-stu-id="dfe17-133">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
