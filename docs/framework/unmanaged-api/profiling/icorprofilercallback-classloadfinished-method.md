---
title: ICorProfilerCallback::ClassLoadFinished (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ClassLoadFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ClassLoadFinished
helpviewer_keywords:
- ClassLoadFinished method [.NET Framework profiling]
- ICorProfilerCallback::ClassLoadFinished method [.NET Framework profiling]
ms.assetid: 3dd80fbe-d62d-4d4d-acf8-5b7d0efe607e
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 6508c989b143780090d582fd4175fe20bedeb770
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67745440"
---
# <a name="icorprofilercallbackclassloadfinished-method"></a><span data-ttu-id="e84b7-102">ICorProfilerCallback::ClassLoadFinished (Método)</span><span class="sxs-lookup"><span data-stu-id="e84b7-102">ICorProfilerCallback::ClassLoadFinished Method</span></span>
<span data-ttu-id="e84b7-103">Notifica al generador de perfiles que una clase ha terminado de cargarse.</span><span class="sxs-lookup"><span data-stu-id="e84b7-103">Notifies the profiler that a class has finished loading.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e84b7-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e84b7-104">Syntax</span></span>  
  
```cpp  
HRESULT ClassLoadFinished(  
    [in] ClassID classId,  
    [in] HRESULT hrStatus);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e84b7-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e84b7-105">Parameters</span></span>  
 `classId`  
 <span data-ttu-id="e84b7-106">[in] Identifica la clase que se cargó.</span><span class="sxs-lookup"><span data-stu-id="e84b7-106">[in] Identifies the class that was loaded.</span></span>  
  
 `hrStatus`  
 <span data-ttu-id="e84b7-107">[in] Un HRESULT que indica si la clase se ha cargado correctamente.</span><span class="sxs-lookup"><span data-stu-id="e84b7-107">[in] An HRESULT that indicates whether the class loaded successfully.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e84b7-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e84b7-108">Remarks</span></span>  
 <span data-ttu-id="e84b7-109">El valor de `classId` no es válido para una solicitud de información hasta que el `ClassLoadFinished` se llama al método.</span><span class="sxs-lookup"><span data-stu-id="e84b7-109">The value of `classId` is not valid for an information request until the `ClassLoadFinished` method is called.</span></span>  
  
 <span data-ttu-id="e84b7-110">Algunas partes de la carga de la clase podrían continuar después de la `ClassLoadFinished` devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="e84b7-110">Some parts of loading the class might continue after the `ClassLoadFinished` callback.</span></span> <span data-ttu-id="e84b7-111">Un error HRESULT en `hrStatus` indica un error.</span><span class="sxs-lookup"><span data-stu-id="e84b7-111">A failure HRESULT in `hrStatus` indicates a failure.</span></span> <span data-ttu-id="e84b7-112">Sin embargo, un valor HRESULT correcto en `hrStatus` sólo indica que la primera parte de la carga de la clase se ha realizado correctamente.</span><span class="sxs-lookup"><span data-stu-id="e84b7-112">However, a success HRESULT in `hrStatus` indicates only that the first part of loading the class has succeeded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e84b7-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e84b7-113">Requirements</span></span>  
 <span data-ttu-id="e84b7-114">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e84b7-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e84b7-115">**Encabezado**: CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="e84b7-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="e84b7-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e84b7-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e84b7-117">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e84b7-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e84b7-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="e84b7-118">See also</span></span>

- [<span data-ttu-id="e84b7-119">ICorProfilerCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="e84b7-119">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="e84b7-120">ClassLoadStarted (método)</span><span class="sxs-lookup"><span data-stu-id="e84b7-120">ClassLoadStarted Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-classloadstarted-method.md)
