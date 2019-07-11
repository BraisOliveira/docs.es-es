---
title: EClrOperation (Enumeración)
ms.date: 03/30/2017
api_name:
- EClrOperation
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- EClrOperation
helpviewer_keywords:
- EClrOperation enumeration [.NET Framework hosting]
ms.assetid: 5aef6808-5aac-4b2f-a2c7-fee1575c55ed
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 01b000ed3d75ddb6a7882cb8f03ff2cec64fb9fe
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67767875"
---
# <a name="eclroperation-enumeration"></a><span data-ttu-id="a6812-102">EClrOperation (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="a6812-102">EClrOperation Enumeration</span></span>
<span data-ttu-id="a6812-103">Describe el conjunto de operaciones para que un host puede aplicar acciones de directiva.</span><span class="sxs-lookup"><span data-stu-id="a6812-103">Describes the set of operations for which a host can apply policy actions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a6812-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a6812-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    OPR_ThreadAbort,  
    OPR_ThreadRudeAbortInNonCriticalRegion,  
    OPR_ThreadRudeAbortInCriticalRegion,  
    OPR_AppDomainUnload,  
    OPR_AppDomainRudeUnload,  
    OPR_ProcessExit,  
    OPR_FinalizerRun  
} EClrOperation;  
```  
  
## <a name="members"></a><span data-ttu-id="a6812-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="a6812-105">Members</span></span>  
  
|<span data-ttu-id="a6812-106">Member</span><span class="sxs-lookup"><span data-stu-id="a6812-106">Member</span></span>|<span data-ttu-id="a6812-107">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="a6812-107">Description</span></span>|  
|------------|-----------------|  
|`OPR_AppDomainRudeUnload`|<span data-ttu-id="a6812-108">El host puede especificar acciones de directiva va a realizarse cuando un <xref:System.AppDomain> se descargan de forma que no sea estable (forzada).</span><span class="sxs-lookup"><span data-stu-id="a6812-108">The host can specify policy actions to be taken when an <xref:System.AppDomain> is unloaded in a non-graceful (rude) manner.</span></span>|  
|`OPR_AppDomainUnload`|<span data-ttu-id="a6812-109">El host puede especificar acciones de directiva va a realizarse cuando un <xref:System.AppDomain> se descarga.</span><span class="sxs-lookup"><span data-stu-id="a6812-109">The host can specify policy actions to be taken when an <xref:System.AppDomain> is unloaded.</span></span>|  
|`OPR_FinalizerRun`|<span data-ttu-id="a6812-110">El host puede especificar acciones de directiva que se realizarán cuando ejecutan los finalizadores.</span><span class="sxs-lookup"><span data-stu-id="a6812-110">The host can specify policy actions to be taken when finalizers run.</span></span>|  
|`OPR_ProcessExit`|<span data-ttu-id="a6812-111">El host puede especificar acciones de directiva que se realizará cuando se cierra el proceso.</span><span class="sxs-lookup"><span data-stu-id="a6812-111">The host can specify policy actions to be taken when the process exits.</span></span>|  
|`OPR_ThreadAbort`|<span data-ttu-id="a6812-112">El host puede especificar acciones de directiva que se realizará cuando se anula un subproceso.</span><span class="sxs-lookup"><span data-stu-id="a6812-112">The host can specify policy actions to be taken when a thread is aborted.</span></span>|  
|`OPR_ThreadRudeAbortInCriticalRegion`|<span data-ttu-id="a6812-113">El host puede especificar acciones de directiva que se realizarán cuando se produce una anulación a la fuerza en una región crítica del código.</span><span class="sxs-lookup"><span data-stu-id="a6812-113">The host can specify policy actions to be taken when a rude thread abort occurs in a critical region of code.</span></span>|  
|`OPR_ThreadRudeAbortInNonCriticalRegion`|<span data-ttu-id="a6812-114">El host puede especificar acciones de directiva que se realizará cuando se produzca una anulación a la fuerza en una región no crítica del código.</span><span class="sxs-lookup"><span data-stu-id="a6812-114">The host can specify policy actions to be take when a rude thread abort occurs in a non-critical region of code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a6812-115">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a6812-115">Remarks</span></span>  
 <span data-ttu-id="a6812-116">La infraestructura de confiabilidad de common language runtime (CLR) distingue entre recursos y las anulaciones de errores de asignación que se producen en regiones críticas del código y las que se producen en las regiones no críticas de código.</span><span class="sxs-lookup"><span data-stu-id="a6812-116">The common language runtime (CLR) reliability infrastructure distinguishes between aborts and resource allocation failures that occur in critical regions of code and those that occur in non-critical regions of code.</span></span> <span data-ttu-id="a6812-117">Esta distinción está diseñada para permitir que los hosts establecer directivas distintas dependiendo de dónde se produce un error en el código.</span><span class="sxs-lookup"><span data-stu-id="a6812-117">This distinction is designed to allow hosts to set different policies depending on where a failure occurs in the code.</span></span>  
  
 <span data-ttu-id="a6812-118">Un *región crítica del código* cualquier espacio que el CLR no puede garantizar que no puede completar una solicitud para los recursos afectará únicamente a la tarea actual o anulación de una tarea.</span><span class="sxs-lookup"><span data-stu-id="a6812-118">A *critical region of code* is any space where the CLR cannot guarantee that aborting a task or failing to complete a request for resources will affect only the current task.</span></span> <span data-ttu-id="a6812-119">Por ejemplo, si una tarea mantiene un bloqueo y recibe un valor HRESULT que indica un error al realizar una solicitud de asignación de memoria, es suficiente con anular la tarea para garantizar la estabilidad de la <xref:System.AppDomain>, porque el <xref:System.AppDomain> podría contener otros tareas en espera para el mismo bloqueo.</span><span class="sxs-lookup"><span data-stu-id="a6812-119">For example, if a task is holding a lock and receives an HRESULT that indicates failure upon making a memory allocation request, it is insufficient simply to abort that task to ensure the stability of the <xref:System.AppDomain>, because the <xref:System.AppDomain> might contain other tasks waiting for the same lock.</span></span> <span data-ttu-id="a6812-120">Para abandonar actual tarea podría provocar que deje de responder esas otras tareas.</span><span class="sxs-lookup"><span data-stu-id="a6812-120">To abandon the current task might cause those other tasks to stop responding.</span></span> <span data-ttu-id="a6812-121">En tal caso, el host necesita la capacidad de descargar toda la <xref:System.AppDomain> en lugar de riesgo potencial de inestabilidad.</span><span class="sxs-lookup"><span data-stu-id="a6812-121">In such a case, the host needs the ability to unload the entire <xref:System.AppDomain> rather than risk potential instability.</span></span>  
  
 <span data-ttu-id="a6812-122">Un *región no crítica del código*, por otro lado, es una región en el CLR puede garantizar que una anulación o un error afectará únicamente a la tarea en el que se produce el error.</span><span class="sxs-lookup"><span data-stu-id="a6812-122">A *non-critical region of code*, on the other hand, is a region where the CLR can guarantee that an abort or a failure will affect only the task upon which the error occurs.</span></span>  
  
 <span data-ttu-id="a6812-123">CLR también distingue entre estables y que no sea estable forzadas.</span><span class="sxs-lookup"><span data-stu-id="a6812-123">The CLR also distinguishes between graceful and non-graceful (rude) aborts.</span></span> <span data-ttu-id="a6812-124">En general, una anulación normal o correcta hace todo lo posible para ejecutar rutinas y los finalizadores de control de excepciones antes de anular una tarea, mientras que una anulación a la fuerza ofrece ninguna garantía de este tipo.</span><span class="sxs-lookup"><span data-stu-id="a6812-124">In general, a normal or graceful abort makes every effort to run exception-handling routines and finalizers before aborting a task, while a rude abort makes no such guarantees.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a6812-125">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a6812-125">Requirements</span></span>  
 <span data-ttu-id="a6812-126">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a6812-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a6812-127">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="a6812-127">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a6812-128">**Biblioteca:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a6812-128">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a6812-129">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a6812-129">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a6812-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="a6812-130">See also</span></span>

- [<span data-ttu-id="a6812-131">EClrFailure (enumeración)</span><span class="sxs-lookup"><span data-stu-id="a6812-131">EClrFailure Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md)
- [<span data-ttu-id="a6812-132">EPolicyAction (enumeración)</span><span class="sxs-lookup"><span data-stu-id="a6812-132">EPolicyAction Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)
- [<span data-ttu-id="a6812-133">ICLRPolicyManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="a6812-133">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)
- [<span data-ttu-id="a6812-134">IHostPolicyManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="a6812-134">IHostPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-interface.md)
- [<span data-ttu-id="a6812-135">Enumeraciones para hosts</span><span class="sxs-lookup"><span data-stu-id="a6812-135">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
