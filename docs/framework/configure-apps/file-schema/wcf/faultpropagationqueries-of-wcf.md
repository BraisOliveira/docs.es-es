---
title: <faultPropagationQueries> de WCF
ms.date: 03/30/2017
ms.assetid: d85f66a7-e7b0-4dbb-83cc-89fa06fc9161
ms.openlocfilehash: bc016827c5bb243bc83dbb53c1eda7eec1bfd8c4
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61704016"
---
# <a name="faultpropagationqueries-of-wcf"></a><span data-ttu-id="e3647-102">\<faultPropagationQueries > de WCF</span><span class="sxs-lookup"><span data-stu-id="e3647-102">\<faultPropagationQueries> of WCF</span></span>

<span data-ttu-id="e3647-103">Representa una colección de consultas que se utilizan para realizar el seguimiento del control de errores que se producen dentro de una actividad.</span><span class="sxs-lookup"><span data-stu-id="e3647-103">Represents a collection of queries that are used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="e3647-104">Este evento se produce cada vez que un FaultHandler procesa un error.</span><span class="sxs-lookup"><span data-stu-id="e3647-104">This event occurs each time a FaultHandler processes a fault.</span></span> <span data-ttu-id="e3647-105">Debería usar tal consulta para realizar el seguimiento del control de errores que se producen dentro de una actividad.</span><span class="sxs-lookup"><span data-stu-id="e3647-105">You should use such query to track the handling of faults that occur within an activity.</span></span> <span data-ttu-id="e3647-106">La consulta es necesaria que un participante del seguimiento se suscriba a los registros de propagación de errores.</span><span class="sxs-lookup"><span data-stu-id="e3647-106">The query is necessary for a  tracking participant to subscribe to fault propagation records.</span></span>  
  
<span data-ttu-id="e3647-107">Para obtener más información sobre las consultas de perfil de seguimiento, vea [perfiles de seguimiento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="e3647-107">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="e3647-108">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="e3647-108">\<system.serviceModel></span></span>  
<span data-ttu-id="e3647-109">\<tracking></span><span class="sxs-lookup"><span data-stu-id="e3647-109">\<tracking></span></span>  
<span data-ttu-id="e3647-110">\<profiles></span><span class="sxs-lookup"><span data-stu-id="e3647-110">\<profiles></span></span>  
<span data-ttu-id="e3647-111">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="e3647-111">\<trackingProfile></span></span>  
<span data-ttu-id="e3647-112">\<flujo de trabajo ></span><span class="sxs-lookup"><span data-stu-id="e3647-112">\<workflow></span></span>  
<span data-ttu-id="e3647-113">\<faultPropagationQueries></span><span class="sxs-lookup"><span data-stu-id="e3647-113">\<faultPropagationQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e3647-114">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e3647-114">Syntax</span></span>  
  
```xml  
<tracking>
  <profiles>
    <trackingProfile name="Name">
      <workflow>
        <faultPropagationQueries>
          <faultPropagationQuery faultSourceActivityName="String"
                                 faultHandlerActivityName="String"/>
        </faultPropagationQueries>
      </workflow>
    </trackingProfile>
  </profiles>
</tracking>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e3647-115">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="e3647-115">Attributes and elements</span></span>

<span data-ttu-id="e3647-116">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="e3647-116">The following sections describe attributes, child elements, and parent elements.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="e3647-117">Atributos</span><span class="sxs-lookup"><span data-stu-id="e3647-117">Attributes</span></span>

<span data-ttu-id="e3647-118">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="e3647-118">None.</span></span>
  
### <a name="child-elements"></a><span data-ttu-id="e3647-119">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="e3647-119">Child elements</span></span>

|<span data-ttu-id="e3647-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="e3647-120">Element</span></span>|<span data-ttu-id="e3647-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="e3647-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e3647-122">\<faultPropagationQuery></span><span class="sxs-lookup"><span data-stu-id="e3647-122">\<faultPropagationQuery></span></span>](faultpropagationquery-of-wcf.md)|<span data-ttu-id="e3647-123">Una consulta que se utiliza para realizar el seguimiento del control de errores que se producen dentro de una actividad.</span><span class="sxs-lookup"><span data-stu-id="e3647-123">A query that is used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="e3647-124">Este evento se produce cada vez que un FaultHandler procesa un error.</span><span class="sxs-lookup"><span data-stu-id="e3647-124">This event occurs each time a FaultHandler processes a fault.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="e3647-125">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="e3647-125">Parent elements</span></span>  
  
|<span data-ttu-id="e3647-126">Elemento</span><span class="sxs-lookup"><span data-stu-id="e3647-126">Element</span></span>|<span data-ttu-id="e3647-127">Descripción</span><span class="sxs-lookup"><span data-stu-id="e3647-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e3647-128">\<workflow></span><span class="sxs-lookup"><span data-stu-id="e3647-128">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="e3647-129">Un elemento de configuración que contiene todas las consultas para un flujo de trabajo concreto identificado por la propiedad `activityDefinitionId`.</span><span class="sxs-lookup"><span data-stu-id="e3647-129">A configuration element that contains all queries for a specific workflow identified by the `activityDefinitionId` property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e3647-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="e3647-130">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.FaultPropagationQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.FaultPropagationQuery?displayProperty=nameWithType>
- [<span data-ttu-id="e3647-131">Seguimiento y traza de flujos de trabajo</span><span class="sxs-lookup"><span data-stu-id="e3647-131">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="e3647-132">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="e3647-132">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
