---
title: ICorProfilerCallback::ClassUnloadFinished (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ClassUnloadFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ClassUnloadFinished
helpviewer_keywords:
- ICorProfilerCallback::ClassUnloadFinished method [.NET Framework profiling]
- ClassUnloadFinished method [.NET Framework profiling]
ms.assetid: 55674b68-678a-4747-ae06-4e91519c7305
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 4c1bf9e572ee88bd299f23ebb435c1b4d24ed717
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67762919"
---
# <a name="icorprofilercallbackclassunloadfinished-method"></a><span data-ttu-id="36678-102">ICorProfilerCallback::ClassUnloadFinished (Método)</span><span class="sxs-lookup"><span data-stu-id="36678-102">ICorProfilerCallback::ClassUnloadFinished Method</span></span>
<span data-ttu-id="36678-103">Notifica al generador de perfiles que una clase ha terminado de descargarse.</span><span class="sxs-lookup"><span data-stu-id="36678-103">Notifies the profiler that a class has finished unloading.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="36678-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="36678-104">Syntax</span></span>  
  
```cpp  
HRESULT ClassUnloadFinished(  
    [in] ClassID classId,  
    [in] HRESULT hrStatus);  
```  
  
## <a name="parameters"></a><span data-ttu-id="36678-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="36678-105">Parameters</span></span>  
 `classId`  
 <span data-ttu-id="36678-106">[in] Identifica la clase que se ha descargado.</span><span class="sxs-lookup"><span data-stu-id="36678-106">[in] Identifies the class that was unloaded.</span></span>  
  
 `hrStatus`  
 <span data-ttu-id="36678-107">[in] Un HRESULT que indica si la clase se descargó correctamente.</span><span class="sxs-lookup"><span data-stu-id="36678-107">[in] An HRESULT that indicates whether the class was unloaded successfully.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="36678-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="36678-108">Remarks</span></span>  
 <span data-ttu-id="36678-109">Algunas partes de la descarga de la clase podrían continuar después de la `ClassUnloadFinished` devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="36678-109">Some parts of unloading the class might continue after the `ClassUnloadFinished` callback.</span></span> <span data-ttu-id="36678-110">Un error HRESULT en `hrStatus` indica un error.</span><span class="sxs-lookup"><span data-stu-id="36678-110">A failure HRESULT in `hrStatus` indicates a failure.</span></span> <span data-ttu-id="36678-111">Sin embargo, un valor HRESULT correcto en `hrStatus` sólo indica que la primera parte de la descarga de la clase se ha realizado correctamente.</span><span class="sxs-lookup"><span data-stu-id="36678-111">However, a success HRESULT in `hrStatus` indicates only that the first part of unloading the class has succeeded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="36678-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="36678-112">Requirements</span></span>  
 <span data-ttu-id="36678-113">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="36678-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="36678-114">**Encabezado**: CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="36678-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="36678-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="36678-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="36678-116">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="36678-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="36678-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="36678-117">See also</span></span>

- [<span data-ttu-id="36678-118">ICorProfilerCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="36678-118">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="36678-119">ClassUnloadStarted (método)</span><span class="sxs-lookup"><span data-stu-id="36678-119">ClassUnloadStarted Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-classunloadstarted-method.md)
