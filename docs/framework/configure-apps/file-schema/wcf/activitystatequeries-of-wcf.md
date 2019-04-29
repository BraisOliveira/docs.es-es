---
title: <activityStateQueries> de WCF
ms.date: 10/08/2018
ms.assetid: 9e45db49-ed85-4fdf-bd65-0d5477e31823
ms.openlocfilehash: c9c78b6929b4550204a22fe2e2786891b516a818
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61701091"
---
# <a name="activitystatequeries-of-wcf"></a><span data-ttu-id="c2ce1-102">\<activityStateQueries > de WCF</span><span class="sxs-lookup"><span data-stu-id="c2ce1-102">\<activityStateQueries> of WCF</span></span>

<span data-ttu-id="c2ce1-103">Representa una colección de consultas que se usan para realizar el seguimiento de los cambios del ciclo de vida de las actividades que constituyen una instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="c2ce1-103">Represents a collection of queries that are used to track life cycle changes of the activities that make up a workflow instance.</span></span> <span data-ttu-id="c2ce1-104">Por ejemplo, desea realizar un seguimiento de cada vez que se complete la actividad "Enviar correo electrónico" dentro de una instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="c2ce1-104">For example, you may want to keep track of every time the "Send E-Mail" activity completes within a workflow instance.</span></span> <span data-ttu-id="c2ce1-105">Esta consulta es necesaria para que un participante de seguimiento se suscriba a los objetos de registro de estado de actividad.</span><span class="sxs-lookup"><span data-stu-id="c2ce1-105">This query is necessary for a tracking participant to subscribe to activity state record objects.</span></span> <span data-ttu-id="c2ce1-106">Los estados de suscripción disponibles se especifican en ActivityStates.</span><span class="sxs-lookup"><span data-stu-id="c2ce1-106">The available states to subscribe to are specified in ActivityStates.</span></span>

<span data-ttu-id="c2ce1-107">Para obtener más información sobre las consultas de perfil de seguimiento, vea [perfiles de seguimiento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="c2ce1-107">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>

<span data-ttu-id="c2ce1-108">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="c2ce1-108">\<system.serviceModel></span></span>  
<span data-ttu-id="c2ce1-109">\<tracking></span><span class="sxs-lookup"><span data-stu-id="c2ce1-109">\<tracking></span></span>  
<span data-ttu-id="c2ce1-110">\<profiles></span><span class="sxs-lookup"><span data-stu-id="c2ce1-110">\<profiles></span></span>  
<span data-ttu-id="c2ce1-111">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="c2ce1-111">\<trackingProfile></span></span>  
<span data-ttu-id="c2ce1-112">\<flujo de trabajo ></span><span class="sxs-lookup"><span data-stu-id="c2ce1-112">\<workflow></span></span>  
<span data-ttu-id="c2ce1-113">\<activityStateQueries></span><span class="sxs-lookup"><span data-stu-id="c2ce1-113">\<activityStateQueries></span></span>  

## <a name="syntax"></a><span data-ttu-id="c2ce1-114">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c2ce1-114">Syntax</span></span>  
  
```xml  
<tracking>
  <profiles>
    <trackingProfile name="Name">
      <workflow>
        <activityStateQueries>
          <activityStateQuery activityName="String">
            <arguments>
              <argument name="String" />
            </arguments>
            <states>
              <state name="String" />
            </states>
            <variables>
              <variable name="String" />
            </variables>
          </activityStateQuery>
        </activityStateQueries>
      </workflow>
    </trackingProfile>
  </profiles>
</tracking>
```  

## <a name="attributes-and-elements"></a><span data-ttu-id="c2ce1-115">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="c2ce1-115">Attributes and elements</span></span>

<span data-ttu-id="c2ce1-116">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="c2ce1-116">The following sections describe attributes, child elements, and parent elements.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="c2ce1-117">Atributos</span><span class="sxs-lookup"><span data-stu-id="c2ce1-117">Attributes</span></span>  

<span data-ttu-id="c2ce1-118">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="c2ce1-118">None.</span></span>  

### <a name="child-elements"></a><span data-ttu-id="c2ce1-119">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="c2ce1-119">Child elements</span></span>

|<span data-ttu-id="c2ce1-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="c2ce1-120">Element</span></span>|<span data-ttu-id="c2ce1-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="c2ce1-121">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="c2ce1-122">\<activityStateQuery></span><span class="sxs-lookup"><span data-stu-id="c2ce1-122">\<activityStateQuery></span></span>](activitystatequery-of-wcf.md)|<span data-ttu-id="c2ce1-123">Una consulta que se utiliza para realizar el seguimiento del control de errores que se producen dentro de una actividad.</span><span class="sxs-lookup"><span data-stu-id="c2ce1-123">A query that is used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="c2ce1-124">Este evento se produce cada vez que un FaultHandler procesa un error.</span><span class="sxs-lookup"><span data-stu-id="c2ce1-124">This event occurs each time a FaultHandler processes a fault.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="c2ce1-125">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="c2ce1-125">Parent elements</span></span>

|<span data-ttu-id="c2ce1-126">Elemento</span><span class="sxs-lookup"><span data-stu-id="c2ce1-126">Element</span></span>|<span data-ttu-id="c2ce1-127">Descripción</span><span class="sxs-lookup"><span data-stu-id="c2ce1-127">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="c2ce1-128">\<workflow></span><span class="sxs-lookup"><span data-stu-id="c2ce1-128">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="c2ce1-129">Un elemento de configuración que contiene todas las consultas para un flujo de trabajo concreto identificado por la propiedad `activityDefinitionId`.</span><span class="sxs-lookup"><span data-stu-id="c2ce1-129">A configuration element that contains all queries for a specific workflow identified by the `activityDefinitionId` property.</span></span>|

## <a name="see-also"></a><span data-ttu-id="c2ce1-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="c2ce1-130">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityStateQueryElementCollection>
- <xref:System.Activities.Tracking.ActivityStateQuery>
- [<span data-ttu-id="c2ce1-131">Seguimiento y traza de flujos de trabajo</span><span class="sxs-lookup"><span data-stu-id="c2ce1-131">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="c2ce1-132">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="c2ce1-132">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
