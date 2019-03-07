---
title: ICorProfilerCallback::ExceptionThrown (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ExceptionThrown
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ExceptionThrown
helpviewer_keywords:
- ExceptionThrown method [.NET Framework profiling]
- ICorProfilerCallback::ExceptionThrown method [.NET Framework profiling]
ms.assetid: f1a23f3b-ac21-4905-8abf-8ea59f15af53
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c3f21d6e26c9105a564ddc60b6dd125ab49e9cd6
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57465886"
---
# <a name="icorprofilercallbackexceptionthrown-method"></a><span data-ttu-id="dce96-102">ICorProfilerCallback::ExceptionThrown (Método)</span><span class="sxs-lookup"><span data-stu-id="dce96-102">ICorProfilerCallback::ExceptionThrown Method</span></span>
<span data-ttu-id="dce96-103">Notifica al generador de perfiles que se ha producido una excepción.</span><span class="sxs-lookup"><span data-stu-id="dce96-103">Notifies the profiler that an exception has been thrown.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="dce96-104">Esta función se invoca sólo si la excepción llega a código administrado.</span><span class="sxs-lookup"><span data-stu-id="dce96-104">This function is called only if the exception reaches managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dce96-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="dce96-105">Syntax</span></span>  
  
```  
HRESULT ExceptionThrown(  
    [in] ObjectID thrownObjectId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="dce96-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="dce96-106">Parameters</span></span>  
 `thrownObjectId`  
 <span data-ttu-id="dce96-107">[in] El identificador del objeto que produjo la excepción que se produzca.</span><span class="sxs-lookup"><span data-stu-id="dce96-107">[in] The ID of the object that caused the exception to be thrown.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="dce96-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="dce96-108">Remarks</span></span>  
 <span data-ttu-id="dce96-109">El generador de perfiles no debe bloquearse en su implementación de este método porque la pila no puede estar en un estado que permita la recolección de elementos y, por lo tanto, no se puede habilitar la recolección preferente.</span><span class="sxs-lookup"><span data-stu-id="dce96-109">The profiler should not block in its implementation of this method because the stack may not be in a state that allows garbage collection, and therefore preemptive garbage collection cannot be enabled.</span></span> <span data-ttu-id="dce96-110">Si el generador de perfiles se bloquea aquí y se intenta realizar la recolección de elementos, el tiempo de ejecución se bloqueará hasta que devuelve esta devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="dce96-110">If the profiler blocks here and garbage collection is attempted, the runtime will block until this callback returns.</span></span>  
  
 <span data-ttu-id="dce96-111">Implementación del generador de perfiles de este método no debe llamar a código administrado o en modo alguno provocar una asignación de memoria administrada.</span><span class="sxs-lookup"><span data-stu-id="dce96-111">The profiler's implementation of this method should not call into managed code or in any way cause a managed-memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dce96-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="dce96-112">Requirements</span></span>  
 <span data-ttu-id="dce96-113">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dce96-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dce96-114">**Encabezado**: CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="dce96-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="dce96-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="dce96-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="dce96-116">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dce96-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dce96-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="dce96-117">See also</span></span>
- [<span data-ttu-id="dce96-118">ICorProfilerCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="dce96-118">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
