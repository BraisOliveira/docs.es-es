---
title: ICorProfilerCallback2::HandleDestroyed (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback2.HandleDestroyed
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback2::HandleDestroyed
helpviewer_keywords:
- ICorProfilerCallback2::HandleDestroyed method [.NET Framework profiling]
- HandleDestroyed method [.NET Framework profiling]
ms.assetid: ab4f4bbd-40c7-4667-bfde-60cd73803110
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: bc6b086b444a769afbf01369b50c69e242a21050
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59090490"
---
# <a name="icorprofilercallback2handledestroyed-method"></a><span data-ttu-id="5e394-102">ICorProfilerCallback2::HandleDestroyed (Método)</span><span class="sxs-lookup"><span data-stu-id="5e394-102">ICorProfilerCallback2::HandleDestroyed Method</span></span>
<span data-ttu-id="5e394-103">Notifica al generador de perfiles de código que se ha destruido un identificador de la colección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="5e394-103">Notifies the code profiler that a garbage collection handle has been destroyed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5e394-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5e394-104">Syntax</span></span>  
  
```  
HRESULT HandleDestroyed(  
    [in] GCHandleID handleId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5e394-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="5e394-105">Parameters</span></span>  
 `handleId`  
 <span data-ttu-id="5e394-106">[in] El identificador del controlador de la colección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="5e394-106">[in] The ID of the handle for the garbage collection.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5e394-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5e394-107">Requirements</span></span>  
 <span data-ttu-id="5e394-108">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5e394-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5e394-109">**Encabezado**: CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="5e394-109">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="5e394-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5e394-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5e394-111">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5e394-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5e394-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="5e394-112">See also</span></span>

- [<span data-ttu-id="5e394-113">ICorProfilerCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="5e394-113">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="5e394-114">ICorProfilerCallback2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="5e394-114">ICorProfilerCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)
