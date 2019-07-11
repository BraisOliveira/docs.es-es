---
title: ICorProfilerCallback::ObjectAllocated (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ObjectAllocated
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ObjectAllocated
helpviewer_keywords:
- ObjectAllocated method [.NET Framework profiling]
- ICorProfilerCallback::ObjectAllocated method [.NET Framework profiling]
ms.assetid: eb412622-77cc-4abd-a2cd-c910fe8edd54
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 10a000fd98ad12dc39f8f8338485d6bb4093ee07
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67782986"
---
# <a name="icorprofilercallbackobjectallocated-method"></a><span data-ttu-id="1083e-102">ICorProfilerCallback::ObjectAllocated (Método)</span><span class="sxs-lookup"><span data-stu-id="1083e-102">ICorProfilerCallback::ObjectAllocated Method</span></span>
<span data-ttu-id="1083e-103">Notifica al generador de perfiles que se ha asignado la memoria del montón de un objeto.</span><span class="sxs-lookup"><span data-stu-id="1083e-103">Notifies the profiler that memory within the heap has been allocated for an object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1083e-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1083e-104">Syntax</span></span>  
  
```cpp  
HRESULT ObjectAllocated(  
    [in] ObjectID objectId,  
    [in] ClassID classId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1083e-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="1083e-105">Parameters</span></span>  
 `objectId`  
 <span data-ttu-id="1083e-106">[in] El identificador del objeto para el que se asignó la memoria.</span><span class="sxs-lookup"><span data-stu-id="1083e-106">[in] The ID of the object for which memory was allocated.</span></span>  
  
 `classId`  
 <span data-ttu-id="1083e-107">[in] El identificador de la clase que el objeto es una instancia.</span><span class="sxs-lookup"><span data-stu-id="1083e-107">[in] The ID of the class of which the object is an instance.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1083e-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="1083e-108">Remarks</span></span>  
 <span data-ttu-id="1083e-109">El `ObjectedAllocated` no se llama al método para las asignaciones en la pila o memoria no administrada.</span><span class="sxs-lookup"><span data-stu-id="1083e-109">The `ObjectedAllocated` method is not called for allocations from either the stack or unmanaged memory.</span></span> <span data-ttu-id="1083e-110">El `classId` parámetro puede hacer referencia a una clase en código administrado que no se ha cargado aún.</span><span class="sxs-lookup"><span data-stu-id="1083e-110">The `classId` parameter can refer to a class in managed code that has not been loaded yet.</span></span> <span data-ttu-id="1083e-111">El generador de perfiles recibirá una devolución de llamada de carga de clase para esa clase inmediatamente después de la `ObjectAllocated` devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="1083e-111">The profiler will receive a class load callback for that class immediately after the `ObjectAllocated` callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1083e-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1083e-112">Requirements</span></span>  
 <span data-ttu-id="1083e-113">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1083e-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1083e-114">**Encabezado**: CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="1083e-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="1083e-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1083e-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1083e-116">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1083e-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1083e-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="1083e-117">See also</span></span>

- [<span data-ttu-id="1083e-118">ICorProfilerCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="1083e-118">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="1083e-119">ClassLoadStarted (método)</span><span class="sxs-lookup"><span data-stu-id="1083e-119">ClassLoadStarted Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-classloadstarted-method.md)
- [<span data-ttu-id="1083e-120">ClassLoadFinished (método)</span><span class="sxs-lookup"><span data-stu-id="1083e-120">ClassLoadFinished Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-classloadfinished-method.md)
