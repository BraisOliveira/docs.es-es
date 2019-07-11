---
title: ICorProfilerCallback::RuntimeSuspendAborted (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.RuntimeSuspendAborted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::RuntimeSuspendAborted
helpviewer_keywords:
- ICorProfilerCallback::RuntimeSuspendAborted method [.NET Framework profiling]
- RuntimeSuspendAborted method [.NET Framework profiling]
ms.assetid: 5a8a4277-345b-448b-a028-fc8cff9998aa
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 62682ca19b9f987370ca11d2bda63fba27f28474
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67782996"
---
# <a name="icorprofilercallbackruntimesuspendaborted-method"></a><span data-ttu-id="d54df-102">ICorProfilerCallback::RuntimeSuspendAborted (Método)</span><span class="sxs-lookup"><span data-stu-id="d54df-102">ICorProfilerCallback::RuntimeSuspendAborted Method</span></span>
<span data-ttu-id="d54df-103">Notifica al generador de perfiles que el tiempo de ejecución ha anulado la suspensión en tiempo de ejecución que se está produciendo.</span><span class="sxs-lookup"><span data-stu-id="d54df-103">Notifies the profiler that the runtime has aborted the runtime suspension that was occurring.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d54df-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d54df-104">Syntax</span></span>  
  
```cpp  
HRESULT RuntimeSuspendAborted();  
```  
  
## <a name="remarks"></a><span data-ttu-id="d54df-105">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d54df-105">Remarks</span></span>  
 <span data-ttu-id="d54df-106">Si dos subprocesos intentan suspender el tiempo de ejecución al mismo tiempo, se podría anular la suspensión de tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="d54df-106">The run-time suspension might be aborted if two threads simultaneously attempt to suspend the runtime.</span></span>  
  
 <span data-ttu-id="d54df-107">Ya sea el [RuntimeSuspendFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendfinished-method.md) devolución de llamada o el `RuntimeSuspendAborted` se producirá la devolución de llamada siguiente a un único subproceso un [RuntimeSuspendStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendstarted-method.md) devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="d54df-107">Either the [ICorProfilerCallback::RuntimeSuspendFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendfinished-method.md) callback or the `RuntimeSuspendAborted` callback will occur on a single thread following a [ICorProfilerCallback::RuntimeSuspendStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendstarted-method.md) callback.</span></span>  
  
 <span data-ttu-id="d54df-108">El `RuntimeSuspendAborted` devolución de llamada se garantiza que se producen en el mismo subproceso que la `RuntimeSuspendStarted` devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="d54df-108">The `RuntimeSuspendAborted` callback is guaranteed to occur on the same thread as the `RuntimeSuspendStarted` callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d54df-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d54df-109">Requirements</span></span>  
 <span data-ttu-id="d54df-110">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d54df-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d54df-111">**Encabezado**: CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="d54df-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="d54df-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d54df-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d54df-113">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d54df-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d54df-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="d54df-114">See also</span></span>

- [<span data-ttu-id="d54df-115">ICorProfilerCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="d54df-115">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
