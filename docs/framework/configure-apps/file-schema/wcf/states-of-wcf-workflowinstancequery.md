---
title: <states> de WCF, <workflowInstanceQuery>
ms.date: 03/30/2017
ms.assetid: d17f7525-8035-4e9e-85a0-4cddae59f85d
ms.openlocfilehash: fad6f9c8871f79e4a1e26c893eed86ba168f6d01
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61757955"
---
# <a name="states-of-wcf-workflowinstancequery"></a><span data-ttu-id="73cc8-102">\<Estados > de WCF, \<workflowInstanceQuery ></span><span class="sxs-lookup"><span data-stu-id="73cc8-102">\<states> of WCF, \<workflowInstanceQuery></span></span>

<span data-ttu-id="73cc8-103">Representa una colección de estados suscritos de la instancia de flujo de trabajo de la que se ha realizado el seguimiento cuando se crean los registros del seguimiento.</span><span class="sxs-lookup"><span data-stu-id="73cc8-103">Represents a collection of subscribed states from the tracked workflow instance when the tracking records are created.</span></span>  
  
<span data-ttu-id="73cc8-104">Para obtener más información sobre las consultas de perfil de seguimiento, vea [perfiles de seguimiento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="73cc8-104">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="73cc8-105">\<system.serviceModel> \<tracking></span><span class="sxs-lookup"><span data-stu-id="73cc8-105">\<system.serviceModel> \<tracking></span></span>  
<span data-ttu-id="73cc8-106">\<profiles></span><span class="sxs-lookup"><span data-stu-id="73cc8-106">\<profiles></span></span>  
<span data-ttu-id="73cc8-107">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="73cc8-107">\<trackingProfile></span></span>  
<span data-ttu-id="73cc8-108">\<flujo de trabajo ></span><span class="sxs-lookup"><span data-stu-id="73cc8-108">\<workflow></span></span>  
<span data-ttu-id="73cc8-109">\<workflowInstanceQueries></span><span class="sxs-lookup"><span data-stu-id="73cc8-109">\<workflowInstanceQueries></span></span>  
<span data-ttu-id="73cc8-110">\<workflowInstanceQuery></span><span class="sxs-lookup"><span data-stu-id="73cc8-110">\<workflowInstanceQuery></span></span>  
<span data-ttu-id="73cc8-111">\<states></span><span class="sxs-lookup"><span data-stu-id="73cc8-111">\<states></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="73cc8-112">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="73cc8-112">Syntax</span></span>  
  
```xml  
<tracking>
  <profiles>
    <trackingProfile name="Name">
      <workflow>
        <workflowInstanceQueries>
          <workflowInstanceQuery>
            <states>
              <state name="Name" />
            </states>
          </workflowInstanceQuery>
        </workflowInstanceQueries>
      </workflow>
    </trackingProfile>
  </profiles>
</tracking>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="73cc8-113">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="73cc8-113">Attributes and elements</span></span>

<span data-ttu-id="73cc8-114">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="73cc8-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="73cc8-115">Atributos</span><span class="sxs-lookup"><span data-stu-id="73cc8-115">Attributes</span></span>  

<span data-ttu-id="73cc8-116">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="73cc8-116">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="73cc8-117">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="73cc8-117">Child elements</span></span>
  
|<span data-ttu-id="73cc8-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="73cc8-118">Element</span></span>|<span data-ttu-id="73cc8-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="73cc8-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="73cc8-120">\<states></span><span class="sxs-lookup"><span data-stu-id="73cc8-120">\<states></span></span>](state-of-wcf-workflowinstancequery.md)|<span data-ttu-id="73cc8-121">Un estado suscrito de la instancia de flujo de trabajo de la que se ha realizado el seguimiento cuando se crea el registro del seguimiento.</span><span class="sxs-lookup"><span data-stu-id="73cc8-121">A subscribed state from the tracked workflow instance when the tracking record is created.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="73cc8-122">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="73cc8-122">Parent elements</span></span>  
  
|<span data-ttu-id="73cc8-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="73cc8-123">Element</span></span>|<span data-ttu-id="73cc8-124">Descripción</span><span class="sxs-lookup"><span data-stu-id="73cc8-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="73cc8-125">\<workflowInstanceQuery></span><span class="sxs-lookup"><span data-stu-id="73cc8-125">\<workflowInstanceQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflowinstancequery.md)|<span data-ttu-id="73cc8-126">Una consulta que realiza el seguimiento de los cambios del ciclo de vida de la instancia de flujo de trabajo, como por ejemplo, un evento iniciado o completado.</span><span class="sxs-lookup"><span data-stu-id="73cc8-126">A query that tracks workflow instance life cycle changes such as a started or completed event.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="73cc8-127">Comentarios</span><span class="sxs-lookup"><span data-stu-id="73cc8-127">Remarks</span></span>

<span data-ttu-id="73cc8-128">Los registros devueltos se filtran por los estados de esta colección.</span><span class="sxs-lookup"><span data-stu-id="73cc8-128">The returned records are filtered by the states in this collection.</span></span>  
  
<span data-ttu-id="73cc8-129">En la siguiente tabla se describen los valores de estado posibles.</span><span class="sxs-lookup"><span data-stu-id="73cc8-129">Possible state values are described in the following table.</span></span>  
  
|<span data-ttu-id="73cc8-130">Estado</span><span class="sxs-lookup"><span data-stu-id="73cc8-130">State</span></span>|<span data-ttu-id="73cc8-131">Descripción</span><span class="sxs-lookup"><span data-stu-id="73cc8-131">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="73cc8-132">Anulado</span><span class="sxs-lookup"><span data-stu-id="73cc8-132">Aborted</span></span>|<span data-ttu-id="73cc8-133">Se ha anulado la instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="73cc8-133">The workflow instance is aborted.</span></span>|  
|<span data-ttu-id="73cc8-134">Completada</span><span class="sxs-lookup"><span data-stu-id="73cc8-134">Completed</span></span>|<span data-ttu-id="73cc8-135">Se ha completado la instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="73cc8-135">The workflow instance is completed.</span></span>|  
|<span data-ttu-id="73cc8-136">Deleted</span><span class="sxs-lookup"><span data-stu-id="73cc8-136">Deleted</span></span>|<span data-ttu-id="73cc8-137">Se ha eliminado la instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="73cc8-137">The workflow instance is deleted.</span></span>|  
|<span data-ttu-id="73cc8-138">Inactivo</span><span class="sxs-lookup"><span data-stu-id="73cc8-138">Idle</span></span>|<span data-ttu-id="73cc8-139">La instancia de flujo de trabajo está inactiva.</span><span class="sxs-lookup"><span data-stu-id="73cc8-139">The workflow instance is idle.</span></span>|  
|<span data-ttu-id="73cc8-140">Conservado</span><span class="sxs-lookup"><span data-stu-id="73cc8-140">Persisted</span></span>|<span data-ttu-id="73cc8-141">Se ha guardado la instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="73cc8-141">The workflow instance is persisted.</span></span>|  
|<span data-ttu-id="73cc8-142">Reanudado</span><span class="sxs-lookup"><span data-stu-id="73cc8-142">Resumed</span></span>|<span data-ttu-id="73cc8-143">Se ha reanudado la instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="73cc8-143">The workflow instance is resumed.</span></span>|  
|<span data-ttu-id="73cc8-144">Comenzado</span><span class="sxs-lookup"><span data-stu-id="73cc8-144">Started</span></span>|<span data-ttu-id="73cc8-145">Se ha iniciado la instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="73cc8-145">The workflow instance is started.</span></span>|  
|<span data-ttu-id="73cc8-146">UnhandledException</span><span class="sxs-lookup"><span data-stu-id="73cc8-146">UnhandledException</span></span>|<span data-ttu-id="73cc8-147">La instancia de flujo de trabajo ha detectado una excepción no controlada.</span><span class="sxs-lookup"><span data-stu-id="73cc8-147">The workflow instance encountered an unhandled exception.</span></span>|  
|<span data-ttu-id="73cc8-148">Descargado</span><span class="sxs-lookup"><span data-stu-id="73cc8-148">Unloaded</span></span>|<span data-ttu-id="73cc8-149">Se ha descargado la instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="73cc8-149">The workflow instance is unloaded.</span></span>|  
|<span data-ttu-id="73cc8-150">Cancelado</span><span class="sxs-lookup"><span data-stu-id="73cc8-150">Canceled</span></span>|<span data-ttu-id="73cc8-151">Se ha cancelado la instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="73cc8-151">The workflow instance is canceled.</span></span>|  
|<span data-ttu-id="73cc8-152">Suspendido</span><span class="sxs-lookup"><span data-stu-id="73cc8-152">Suspended</span></span>|<span data-ttu-id="73cc8-153">Se suspende la instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="73cc8-153">The workflow instance is suspended.</span></span>|  
|<span data-ttu-id="73cc8-154">Terminado</span><span class="sxs-lookup"><span data-stu-id="73cc8-154">Terminated</span></span>|<span data-ttu-id="73cc8-155">Se ha terminado la instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="73cc8-155">The workflow instance is terminated.</span></span>|  
|<span data-ttu-id="73cc8-156">No suspendido</span><span class="sxs-lookup"><span data-stu-id="73cc8-156">Unsuspended</span></span>|<span data-ttu-id="73cc8-157">No se suspende la instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="73cc8-157">The workflow instance is unsuspended.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="73cc8-158">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="73cc8-158">Example</span></span>

<span data-ttu-id="73cc8-159">La siguiente configuración se suscribe a los registros de seguimiento de nivel de instancia de flujo de trabajo del estado de instancia `Started` mediante esta consulta.</span><span class="sxs-lookup"><span data-stu-id="73cc8-159">The following configuration subscribes to workflow instance-level tracking records for the `Started` instance state using this query.</span></span>  
  
```xml  
<workflowInstanceQueries>
  <workflowInstanceQuery>
    <states>
      <state name="Started" />
    </states>
  </workflowInstanceQuery>
</workflowInstanceQueries>
```  
  
## <a name="see-also"></a><span data-ttu-id="73cc8-160">Vea también</span><span class="sxs-lookup"><span data-stu-id="73cc8-160">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElement?displayProperty=nameWithType>
- <xref:System.ServiceModel.Activities.Tracking.Configuration.StateElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType>
- [<span data-ttu-id="73cc8-161">Seguimiento y traza de flujos de trabajo</span><span class="sxs-lookup"><span data-stu-id="73cc8-161">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="73cc8-162">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="73cc8-162">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
