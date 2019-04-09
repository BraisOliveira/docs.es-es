---
title: Interfaz ICorDebugController
ms.date: 03/30/2017
api_name:
- ICorDebugController
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugController
helpviewer_keywords:
- ICorDebugController interface [.NET Framework debugging]
ms.assetid: dbb1c4dc-269a-459b-ab1d-6c70788782ce
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7628aa0ad10398f92d475c4c776810e13fac22b7
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59107554"
---
# <a name="icordebugcontroller-interface"></a><span data-ttu-id="22f51-102">Interfaz ICorDebugController</span><span class="sxs-lookup"><span data-stu-id="22f51-102">ICorDebugController Interface</span></span>

<span data-ttu-id="22f51-103">Representa un ámbito, <xref:System.Diagnostics.Process> o <xref:System.AppDomain>, en el que se puede controlar el contexto de ejecución de código.</span><span class="sxs-lookup"><span data-stu-id="22f51-103">Represents a scope, either a <xref:System.Diagnostics.Process> or an <xref:System.AppDomain>, in which code execution context can be controlled.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="22f51-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="22f51-104">Methods</span></span>  
  
|<span data-ttu-id="22f51-105">Método</span><span class="sxs-lookup"><span data-stu-id="22f51-105">Method</span></span>|<span data-ttu-id="22f51-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="22f51-106">Description</span></span>|  
|------------|-----------------|  
|`ICorDebugController::CanCommitChanges`|<span data-ttu-id="22f51-107">Este método está obsoleto.</span><span class="sxs-lookup"><span data-stu-id="22f51-107">This method is obsolete.</span></span>|  
|`ICorDebugController::CommitChanges`|<span data-ttu-id="22f51-108">Este método está obsoleto.</span><span class="sxs-lookup"><span data-stu-id="22f51-108">This method is obsolete.</span></span>|  
|[<span data-ttu-id="22f51-109">Método Continue</span><span class="sxs-lookup"><span data-stu-id="22f51-109">Continue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md)|<span data-ttu-id="22f51-110">Reanuda la ejecución de subprocesos administrados después de llamar a [ICorDebugController](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-stop-method.md).</span><span class="sxs-lookup"><span data-stu-id="22f51-110">Resumes execution of managed threads after a call to [ICorDebugController::Stop](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-stop-method.md).</span></span>|  
|[<span data-ttu-id="22f51-111">Método Detach</span><span class="sxs-lookup"><span data-stu-id="22f51-111">Detach Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-detach-method.md)|<span data-ttu-id="22f51-112">Desasocia al depurador desde el dominio de aplicación o proceso.</span><span class="sxs-lookup"><span data-stu-id="22f51-112">Detaches the debugger from the process or application domain.</span></span>|  
|[<span data-ttu-id="22f51-113">Método EnumerateThreads</span><span class="sxs-lookup"><span data-stu-id="22f51-113">EnumerateThreads Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-enumeratethreads-method.md)|<span data-ttu-id="22f51-114">Obtiene un enumerador para los subprocesos administrados activos en el proceso.</span><span class="sxs-lookup"><span data-stu-id="22f51-114">Gets an enumerator for the active managed threads in the process.</span></span>|  
|[<span data-ttu-id="22f51-115">Método HasQueuedCallbacks</span><span class="sxs-lookup"><span data-stu-id="22f51-115">HasQueuedCallbacks Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-hasqueuedcallbacks-method.md)|<span data-ttu-id="22f51-116">Obtiene un valor que indica si las devoluciones de llamada administradas actualmente están en cola para el subproceso especificado.</span><span class="sxs-lookup"><span data-stu-id="22f51-116">Gets a value that indicates whether any managed callbacks are currently queued for the specified thread.</span></span>|  
|[<span data-ttu-id="22f51-117">Método IsRunning</span><span class="sxs-lookup"><span data-stu-id="22f51-117">IsRunning Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-isrunning-method.md)|<span data-ttu-id="22f51-118">Obtiene un valor que indica si los subprocesos del proceso se están ejecutando libremente.</span><span class="sxs-lookup"><span data-stu-id="22f51-118">Gets a value that indicates whether the threads in the process are currently running freely.</span></span>|  
|[<span data-ttu-id="22f51-119">Método SetAllThreadsDebugState</span><span class="sxs-lookup"><span data-stu-id="22f51-119">SetAllThreadsDebugState Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-setallthreadsdebugstate-method.md)|<span data-ttu-id="22f51-120">Establece el estado de depuración de todos los subprocesos administrados en el proceso.</span><span class="sxs-lookup"><span data-stu-id="22f51-120">Sets the debug state of all managed threads in the process.</span></span>|  
|[<span data-ttu-id="22f51-121">Método Stop</span><span class="sxs-lookup"><span data-stu-id="22f51-121">Stop Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-stop-method.md)|<span data-ttu-id="22f51-122">Realiza una detención cooperativa de todos los subprocesos que ejecutan código administrado en el proceso.</span><span class="sxs-lookup"><span data-stu-id="22f51-122">Performs a cooperative stop on all threads that are running managed code in the process.</span></span>|  
|[<span data-ttu-id="22f51-123">Método Terminate</span><span class="sxs-lookup"><span data-stu-id="22f51-123">Terminate Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-terminate-method.md)|<span data-ttu-id="22f51-124">Finaliza el proceso con el código de salida especificado.</span><span class="sxs-lookup"><span data-stu-id="22f51-124">Terminates the process with the specified exit code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="22f51-125">Comentarios</span><span class="sxs-lookup"><span data-stu-id="22f51-125">Remarks</span></span>  
 <span data-ttu-id="22f51-126">Si `ICorDebugController` es controlar un proceso, el ámbito incluye todos los subprocesos del proceso.</span><span class="sxs-lookup"><span data-stu-id="22f51-126">If `ICorDebugController` is controlling a process, the scope includes all threads of the process.</span></span> <span data-ttu-id="22f51-127">Si `ICorDebugController` es controlar un dominio de aplicación, el ámbito incluye solo los subprocesos de ese dominio de aplicación determinado.</span><span class="sxs-lookup"><span data-stu-id="22f51-127">If `ICorDebugController` is controlling an application domain, the scope includes only the threads of that particular application domain.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="22f51-128">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="22f51-128">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="22f51-129">Requisitos</span><span class="sxs-lookup"><span data-stu-id="22f51-129">Requirements</span></span>  
 <span data-ttu-id="22f51-130">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="22f51-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="22f51-131">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="22f51-131">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="22f51-132">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="22f51-132">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="22f51-133">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="22f51-133">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="22f51-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="22f51-134">See also</span></span>

- [<span data-ttu-id="22f51-135">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="22f51-135">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
