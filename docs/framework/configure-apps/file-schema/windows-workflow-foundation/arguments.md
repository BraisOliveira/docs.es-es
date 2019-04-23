---
title: <arguments>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 0f327196-f468-4be3-b6c4-68ba981a1bd6
ms.openlocfilehash: 2b0d982997ab590ce7f0fc4c482b1ddfa6bc758f
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59152807"
---
# <a name="arguments"></a><span data-ttu-id="78822-101">\<arguments></span><span class="sxs-lookup"><span data-stu-id="78822-101">\<arguments></span></span>
<span data-ttu-id="78822-102">Representa una recopilación de argumentos asociada a una consulta de estado de actividad.</span><span class="sxs-lookup"><span data-stu-id="78822-102">Represents a collection of arguments associated with an activity state query.</span></span>  
  
 <span data-ttu-id="78822-103">Para obtener más información sobre las consultas de perfil de seguimiento, vea [perfiles de seguimiento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="78822-103">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="78822-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="78822-104">\<system.serviceModel></span></span>  
<span data-ttu-id="78822-105">\<tracking></span><span class="sxs-lookup"><span data-stu-id="78822-105">\<tracking></span></span>  
<span data-ttu-id="78822-106">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="78822-106">\<trackingProfile></span></span>  
<span data-ttu-id="78822-107">\<flujo de trabajo ></span><span class="sxs-lookup"><span data-stu-id="78822-107">\<workflow></span></span>  
<span data-ttu-id="78822-108">\<activityStateQueries></span><span class="sxs-lookup"><span data-stu-id="78822-108">\<activityStateQueries></span></span>  
<span data-ttu-id="78822-109">\<activityStateQuery></span><span class="sxs-lookup"><span data-stu-id="78822-109">\<activityStateQuery></span></span>  
<span data-ttu-id="78822-110">\<arguments></span><span class="sxs-lookup"><span data-stu-id="78822-110">\<arguments></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="78822-111">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="78822-111">Syntax</span></span>  
  
```xml
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <activityStateQueries>
        <activityStateQuery activityName="String" />
        <arguments>
          <argument name="String" />
        </arguments>
      </activityStateQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="78822-112">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="78822-112">Attributes and Elements</span></span>  
 <span data-ttu-id="78822-113">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="78822-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="78822-114">Atributos</span><span class="sxs-lookup"><span data-stu-id="78822-114">Attributes</span></span>  
 <span data-ttu-id="78822-115">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="78822-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="78822-116">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="78822-116">Child Elements</span></span>  
  
|<span data-ttu-id="78822-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="78822-117">Element</span></span>|<span data-ttu-id="78822-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="78822-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="78822-119">\<argument></span><span class="sxs-lookup"><span data-stu-id="78822-119">\<argument></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/argument.md)|<span data-ttu-id="78822-120">Un argumento asociado a una consulta de estado de actividad.</span><span class="sxs-lookup"><span data-stu-id="78822-120">An argument associated with an activity state query.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="78822-121">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="78822-121">Parent Elements</span></span>  
  
|<span data-ttu-id="78822-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="78822-122">Element</span></span>|<span data-ttu-id="78822-123">Descripción</span><span class="sxs-lookup"><span data-stu-id="78822-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="78822-124">\<activityStateQuery></span><span class="sxs-lookup"><span data-stu-id="78822-124">\<activityStateQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md)|<span data-ttu-id="78822-125">Representa un elemento de configuración que se utiliza para realizar el seguimiento de las solicitudes para cancelar una actividad secundaria por la actividad primaria.</span><span class="sxs-lookup"><span data-stu-id="78822-125">Represents a configuration element that is used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="78822-126">La consulta es necesaria para que un participante del seguimiento se suscriba con el fin de cancelar los objetos de registro de solicitud.</span><span class="sxs-lookup"><span data-stu-id="78822-126">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="78822-127">Comentarios</span><span class="sxs-lookup"><span data-stu-id="78822-127">Remarks</span></span>  
 <span data-ttu-id="78822-128">Una característica única de ActivityStateQuery es la capacidad de extraer los datos al realizar el seguimiento de la ejecución de un flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="78822-128">One unique feature of an ActivityStateQuery is the ability to extract data when tracking the execution of a workflow.</span></span> <span data-ttu-id="78822-129">Esto proporciona contexto adicional al tener acceso a los registros de seguimiento tras la ejecución.</span><span class="sxs-lookup"><span data-stu-id="78822-129">This provides additional context when accessing the tracking records post execution.</span></span> <span data-ttu-id="78822-130">Puede usar el [ \<argumentos >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md), [ \<Estados >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) y [ \<Estados >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) para extraer cualquier variable o argumento de cualquier actividad de un flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="78822-130">You can use the [\<arguments>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md), [\<states>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) and [\<states>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) elements to extract any variable or argument from any activity in a workflow.</span></span> <span data-ttu-id="78822-131">El siguiente ejemplo muestra una consulta de estado de actividad que extrae variables y argumentos cuando se emite el registro de seguimiento de la actividad `Closed`.</span><span class="sxs-lookup"><span data-stu-id="78822-131">The following example shows an activity state query that extracts variables and arguments when the activity’s `Closed` tracking record is emitted.</span></span> <span data-ttu-id="78822-132">Variables y argumentos se pueden extraer con ActivityStateRecord y, por tanto, se suscriben dentro de un seguimiento de generar perfiles usando [ \<activityStateQuery >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md).</span><span class="sxs-lookup"><span data-stu-id="78822-132">Variables and arguments can be extracted only with an ActivityStateRecord and thus are subscribed to within a tracking profile using [\<activityStateQuery>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md).</span></span>  
  
```xml  
<activityStateQuery activityName="SendEmailActivity">  
  <states>  
    <state name="Closed"/>  
  </states>  
  <variables>  
    <variable name="FromAddress"/>  
  </variables>  
  <arguments>  
    <argument name="Result"/>  
  </arguments>  
</activityStateQuery>  
```  
  
## <a name="see-also"></a><span data-ttu-id="78822-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="78822-133">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ArgumentElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType>
- [<span data-ttu-id="78822-134">Seguimiento y traza de flujos de trabajo</span><span class="sxs-lookup"><span data-stu-id="78822-134">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="78822-135">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="78822-135">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
