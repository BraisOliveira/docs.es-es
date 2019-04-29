---
title: ICorProfilerCallback::ExceptionUnwindFunctionLeave (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ExceptionUnwindFunctionLeave
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ExceptionUnwindFunctionLeave
helpviewer_keywords:
- ICorProfilerCallback::ExceptionUnwindFunctionLeave method [.NET Framework profiling]
- ExceptionUnwindFunctionLeave method [.NET Framework profiling]
ms.assetid: ebaad1d5-ee0a-4cb0-96bc-8ba5d371b747
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 305c8c7abf778ea68efe06f3bdb57af001ea1b9a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61597355"
---
# <a name="icorprofilercallbackexceptionunwindfunctionleave-method"></a><span data-ttu-id="ec1d3-102">ICorProfilerCallback::ExceptionUnwindFunctionLeave (Método)</span><span class="sxs-lookup"><span data-stu-id="ec1d3-102">ICorProfilerCallback::ExceptionUnwindFunctionLeave Method</span></span>
<span data-ttu-id="ec1d3-103">Notifica al generador de perfiles que ha terminado la fase de desenredo de excepciones de desenredado de una función.</span><span class="sxs-lookup"><span data-stu-id="ec1d3-103">Notifies the profiler that the unwind phase of exception handling has finished unwinding a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ec1d3-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ec1d3-104">Syntax</span></span>  
  
```  
HRESULT ExceptionUnwindFunctionLeave();  
```  
  
## <a name="remarks"></a><span data-ttu-id="ec1d3-105">Comentarios</span><span class="sxs-lookup"><span data-stu-id="ec1d3-105">Remarks</span></span>  
 <span data-ttu-id="ec1d3-106">Cuando el `ExceptionUnwindFunctionLeave` se llama al método, se quitan de la pila de la instancia de la función y sus datos de la pila.</span><span class="sxs-lookup"><span data-stu-id="ec1d3-106">When the `ExceptionUnwindFunctionLeave` method is called, the function instance and its stack data are removed from the stack.</span></span>  
  
 <span data-ttu-id="ec1d3-107">El generador de perfiles no debe bloquearse durante esta llamada porque la pila no puede estar en un estado que permita la recolección de elementos y, por lo tanto, no se puede habilitar la recolección preferente.</span><span class="sxs-lookup"><span data-stu-id="ec1d3-107">The profiler should not block during this call because the stack may not be in a state that allows garbage collection, and therefore preemptive garbage collection cannot be enabled.</span></span> <span data-ttu-id="ec1d3-108">Si se intenta aquí los bloques del generador de perfiles y una colección de elementos no utilizados, el tiempo de ejecución se bloqueará hasta que devuelve esta devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="ec1d3-108">If the profiler blocks here and a garbage collection is attempted, the runtime will block until this callback returns.</span></span>  
  
 <span data-ttu-id="ec1d3-109">Asimismo, durante esta llamada, el generador de perfiles no debe llamar a código administrado o en modo alguno provocar una asignación de memoria administrada.</span><span class="sxs-lookup"><span data-stu-id="ec1d3-109">Also, during this call, the profiler must not call into managed code or in any way cause a managed-memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ec1d3-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ec1d3-110">Requirements</span></span>  
 <span data-ttu-id="ec1d3-111">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ec1d3-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ec1d3-112">**Encabezado**: CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="ec1d3-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="ec1d3-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ec1d3-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ec1d3-114">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ec1d3-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ec1d3-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="ec1d3-115">See also</span></span>

- [<span data-ttu-id="ec1d3-116">ICorProfilerCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ec1d3-116">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="ec1d3-117">ExceptionUnwindFunctionEnter (método)</span><span class="sxs-lookup"><span data-stu-id="ec1d3-117">ExceptionUnwindFunctionEnter Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionunwindfunctionenter-method.md)
