---
title: ICorProfilerCallback::FunctionUnloadStarted (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.FunctionUnloadStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::FunctionUnloadStarted
helpviewer_keywords:
- FunctionUnloadStarted method [.NET Framework profiling]
- ICorProfilerCallback::FunctionUnloadStarted method [.NET Framework profiling]
ms.assetid: d6a5fa8b-09c6-47a5-b60e-6cf2e355df30
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c1c1c9a15e9f56765710ffb2015a29b4206b3bd4
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59152612"
---
# <a name="icorprofilercallbackfunctionunloadstarted-method"></a><span data-ttu-id="a53d2-102">ICorProfilerCallback::FunctionUnloadStarted (Método)</span><span class="sxs-lookup"><span data-stu-id="a53d2-102">ICorProfilerCallback::FunctionUnloadStarted Method</span></span>
<span data-ttu-id="a53d2-103">Notifica al generador de perfiles que se ha iniciado el tiempo de ejecución a una función de punto de descargarse.</span><span class="sxs-lookup"><span data-stu-id="a53d2-103">Notifies the profiler that the runtime has started to unload a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a53d2-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a53d2-104">Syntax</span></span>  
  
```  
HRESULT FunctionUnloadStarted(  
    [in] FunctionID functionId);   
```  
  
## <a name="parameters"></a><span data-ttu-id="a53d2-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a53d2-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="a53d2-106">[in] El identificador de la función que se está descargando.</span><span class="sxs-lookup"><span data-stu-id="a53d2-106">[in] The ID of the function that is being unloaded.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a53d2-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a53d2-107">Remarks</span></span>  
 <span data-ttu-id="a53d2-108">El valor de la `functionId` parámetro ya no es válido después de que este método devuelve al llamador.</span><span class="sxs-lookup"><span data-stu-id="a53d2-108">The value of the `functionId` parameter is no longer valid after this method returns to the caller.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a53d2-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a53d2-109">Requirements</span></span>  
 <span data-ttu-id="a53d2-110">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a53d2-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a53d2-111">**Encabezado**: CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="a53d2-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="a53d2-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a53d2-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a53d2-113">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a53d2-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a53d2-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="a53d2-114">See also</span></span>

- [<span data-ttu-id="a53d2-115">ICorProfilerCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="a53d2-115">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
