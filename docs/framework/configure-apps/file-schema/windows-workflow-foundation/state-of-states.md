---
title: <state> de <states>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: ab483c7f-a091-4933-ba6b-708d96846d38
ms.openlocfilehash: ff75895949c50cd369e4297ea77dc21106994067
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59073941"
---
# <a name="state-of-states"></a><span data-ttu-id="1733b-102">\<estado > de \<Estados ></span><span class="sxs-lookup"><span data-stu-id="1733b-102">\<state> of \<states></span></span>
<span data-ttu-id="1733b-103">Un elemento de configuración que contiene el estado de la actividad suscrita para la que se debería emitir un registro de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="1733b-103">A configuration element that contains the state of the subscribed activity for which a tracking record should be emitted.</span></span>  
  
 <span data-ttu-id="1733b-104">Para obtener más información sobre las consultas de perfil de seguimiento, vea [perfiles de seguimiento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="1733b-104">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="1733b-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="1733b-105">\<system.serviceModel></span></span>  
<span data-ttu-id="1733b-106">\<tracking></span><span class="sxs-lookup"><span data-stu-id="1733b-106">\<tracking></span></span>  
<span data-ttu-id="1733b-107">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="1733b-107">\<trackingProfile></span></span>  
<span data-ttu-id="1733b-108">\<flujo de trabajo ></span><span class="sxs-lookup"><span data-stu-id="1733b-108">\<workflow></span></span>  
<span data-ttu-id="1733b-109">\<activityStateQueries></span><span class="sxs-lookup"><span data-stu-id="1733b-109">\<activityStateQueries></span></span>  
<span data-ttu-id="1733b-110">\<activityStateQuery></span><span class="sxs-lookup"><span data-stu-id="1733b-110">\<activityStateQuery></span></span>  
<span data-ttu-id="1733b-111">\<states></span><span class="sxs-lookup"><span data-stu-id="1733b-111">\<states></span></span>  
<span data-ttu-id="1733b-112">\<state></span><span class="sxs-lookup"><span data-stu-id="1733b-112">\<state></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1733b-113">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1733b-113">Syntax</span></span>  
  
```xml  
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <activityStateQueries>
        <activityStateQuery activityName="String" />
        <states>
          <state name="String" />
        </states>
      </activityStateQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1733b-114">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="1733b-114">Attributes and Elements</span></span>  
 <span data-ttu-id="1733b-115">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="1733b-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1733b-116">Atributos</span><span class="sxs-lookup"><span data-stu-id="1733b-116">Attributes</span></span>  
  
|<span data-ttu-id="1733b-117">Atributo</span><span class="sxs-lookup"><span data-stu-id="1733b-117">Attribute</span></span>|<span data-ttu-id="1733b-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="1733b-118">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="1733b-119">name</span><span class="sxs-lookup"><span data-stu-id="1733b-119">name</span></span>|<span data-ttu-id="1733b-120">Una cadena que especifica el estado de la actividad suscrita para la que se debería emitir un registro de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="1733b-120">A string that specifies the state of the subscribed activity for which a tracking record should be emitted.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1733b-121">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="1733b-121">Child Elements</span></span>  
 <span data-ttu-id="1733b-122">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="1733b-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="1733b-123">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="1733b-123">Parent Elements</span></span>  
  
|<span data-ttu-id="1733b-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="1733b-124">Element</span></span>|<span data-ttu-id="1733b-125">Descripción</span><span class="sxs-lookup"><span data-stu-id="1733b-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1733b-126">\<states></span><span class="sxs-lookup"><span data-stu-id="1733b-126">\<states></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states-of-activitystatequery.md)|<span data-ttu-id="1733b-127">Una colección de elementos de configuración que contienen los estados de la actividad suscrita para la que se debería emitir un registro del seguimiento.</span><span class="sxs-lookup"><span data-stu-id="1733b-127">A collection of configuration elements that contain the states of the subscribed activity for which a tracking record should be emitted.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1733b-128">Comentarios</span><span class="sxs-lookup"><span data-stu-id="1733b-128">Remarks</span></span>  
 <span data-ttu-id="1733b-129">Una característica única de ActivityStateQuery es la capacidad de extraer los datos al realizar el seguimiento de la ejecución de un flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="1733b-129">One unique feature of an ActivityStateQuery is the ability to extract data when tracking the execution of a workflow.</span></span> <span data-ttu-id="1733b-130">Esto proporciona contexto adicional al tener acceso a los registros de seguimiento tras la ejecución.</span><span class="sxs-lookup"><span data-stu-id="1733b-130">This provides additional context when accessing the tracking records post execution.</span></span> <span data-ttu-id="1733b-131">Puede usar el [ \<argumentos >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md), [ \<Estados >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) y [ \<Estados >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) para extraer cualquier variable o argumento de cualquier actividad de un flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="1733b-131">You can use the [\<arguments>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md), [\<states>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) and [\<states>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) elements to extract any variable or argument from any activity in a workflow.</span></span> <span data-ttu-id="1733b-132">El siguiente ejemplo muestra una consulta de estado de actividad que extrae variables y argumentos cuando se emite el registro de seguimiento de la actividad `Closed`.</span><span class="sxs-lookup"><span data-stu-id="1733b-132">The following example shows an activity state query that extracts variables and arguments when the activity’s `Closed` tracking record is emitted.</span></span> <span data-ttu-id="1733b-133">Variables y argumentos se pueden extraer con ActivityStateRecord y, por tanto, se suscriben dentro de un seguimiento de generar perfiles usando [ \<activityStateQuery >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md).</span><span class="sxs-lookup"><span data-stu-id="1733b-133">Variables and arguments can be extracted only with an ActivityStateRecord and thus are subscribed to within a tracking profile using [\<activityStateQuery>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="1733b-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="1733b-134">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.StateElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType>
- [<span data-ttu-id="1733b-135">Seguimiento y traza del flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="1733b-135">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="1733b-136">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="1733b-136">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
