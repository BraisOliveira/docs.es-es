---
title: <faultPropagationQueries>de WCF
ms.date: 03/30/2017
ms.assetid: d85f66a7-e7b0-4dbb-83cc-89fa06fc9161
ms.openlocfilehash: aeb964fc8c96c8cb9aeb316bb95f9565fc4a7f18
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69918940"
---
# <a name="faultpropagationqueries-of-wcf"></a><span data-ttu-id="0a2c2-102">\<faultPropagationQueries > de WCF</span><span class="sxs-lookup"><span data-stu-id="0a2c2-102">\<faultPropagationQueries> of WCF</span></span>

<span data-ttu-id="0a2c2-103">Representa una colección de consultas que se utilizan para realizar el seguimiento del control de errores que se producen dentro de una actividad.</span><span class="sxs-lookup"><span data-stu-id="0a2c2-103">Represents a collection of queries that are used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="0a2c2-104">Este evento se produce cada vez que un FaultHandler procesa un error.</span><span class="sxs-lookup"><span data-stu-id="0a2c2-104">This event occurs each time a FaultHandler processes a fault.</span></span> <span data-ttu-id="0a2c2-105">Debería usar tal consulta para realizar el seguimiento del control de errores que se producen dentro de una actividad.</span><span class="sxs-lookup"><span data-stu-id="0a2c2-105">You should use such query to track the handling of faults that occur within an activity.</span></span> <span data-ttu-id="0a2c2-106">La consulta es necesaria que un participante del seguimiento se suscriba a los registros de propagación de errores.</span><span class="sxs-lookup"><span data-stu-id="0a2c2-106">The query is necessary for a  tracking participant to subscribe to fault propagation records.</span></span>  
  
<span data-ttu-id="0a2c2-107">Para obtener más información sobre las consultas de Perfil de seguimiento, consulte [perfiles de seguimiento](../../../windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="0a2c2-107">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="0a2c2-108">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="0a2c2-108">\<system.serviceModel></span></span>  
<span data-ttu-id="0a2c2-109">\<> de seguimiento</span><span class="sxs-lookup"><span data-stu-id="0a2c2-109">\<tracking></span></span>  
<span data-ttu-id="0a2c2-110">\<perfiles ></span><span class="sxs-lookup"><span data-stu-id="0a2c2-110">\<profiles></span></span>  
<span data-ttu-id="0a2c2-111">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="0a2c2-111">\<trackingProfile></span></span>  
<span data-ttu-id="0a2c2-112">\<> de flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="0a2c2-112">\<workflow></span></span>  
<span data-ttu-id="0a2c2-113">\<faultPropagationQueries></span><span class="sxs-lookup"><span data-stu-id="0a2c2-113">\<faultPropagationQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0a2c2-114">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0a2c2-114">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0a2c2-115">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="0a2c2-115">Attributes and elements</span></span>

<span data-ttu-id="0a2c2-116">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="0a2c2-116">The following sections describe attributes, child elements, and parent elements.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="0a2c2-117">Atributos</span><span class="sxs-lookup"><span data-stu-id="0a2c2-117">Attributes</span></span>

<span data-ttu-id="0a2c2-118">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="0a2c2-118">None.</span></span>
  
### <a name="child-elements"></a><span data-ttu-id="0a2c2-119">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="0a2c2-119">Child elements</span></span>

|<span data-ttu-id="0a2c2-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="0a2c2-120">Element</span></span>|<span data-ttu-id="0a2c2-121">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="0a2c2-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0a2c2-122">\<faultPropagationQuery></span><span class="sxs-lookup"><span data-stu-id="0a2c2-122">\<faultPropagationQuery></span></span>](faultpropagationquery-of-wcf.md)|<span data-ttu-id="0a2c2-123">Una consulta que se utiliza para realizar el seguimiento del control de errores que se producen dentro de una actividad.</span><span class="sxs-lookup"><span data-stu-id="0a2c2-123">A query that is used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="0a2c2-124">Este evento se produce cada vez que un FaultHandler procesa un error.</span><span class="sxs-lookup"><span data-stu-id="0a2c2-124">This event occurs each time a FaultHandler processes a fault.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="0a2c2-125">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="0a2c2-125">Parent elements</span></span>  
  
|<span data-ttu-id="0a2c2-126">Elemento</span><span class="sxs-lookup"><span data-stu-id="0a2c2-126">Element</span></span>|<span data-ttu-id="0a2c2-127">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="0a2c2-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0a2c2-128">\<workflow></span><span class="sxs-lookup"><span data-stu-id="0a2c2-128">\<workflow></span></span>](../windows-workflow-foundation/workflow.md)|<span data-ttu-id="0a2c2-129">Un elemento de configuración que contiene todas las consultas para un flujo de trabajo concreto identificado por la propiedad `activityDefinitionId`.</span><span class="sxs-lookup"><span data-stu-id="0a2c2-129">A configuration element that contains all queries for a specific workflow identified by the `activityDefinitionId` property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="0a2c2-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="0a2c2-130">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.FaultPropagationQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.FaultPropagationQuery?displayProperty=nameWithType>
- [<span data-ttu-id="0a2c2-131">Seguimiento y traza de flujos de trabajo</span><span class="sxs-lookup"><span data-stu-id="0a2c2-131">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="0a2c2-132">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="0a2c2-132">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
