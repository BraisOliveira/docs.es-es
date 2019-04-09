---
title: ICorProfilerCallback::ExceptionSearchFilterLeave (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ExceptionSearchFilterLeave
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ExceptionSearchFilterLeave
helpviewer_keywords:
- ICorProfilerCallback::ExceptionSearchFilterLeave method [.NET Framework profiling]
- ExceptionSearchFilterLeave method [.NET Framework profiling]
ms.assetid: c28a2a82-dd11-4385-843f-b509fb61753b
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: e89b76f7a246277737123e180c20874940437506
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59124649"
---
# <a name="icorprofilercallbackexceptionsearchfilterleave-method"></a><span data-ttu-id="98c8f-102">ICorProfilerCallback::ExceptionSearchFilterLeave (Método)</span><span class="sxs-lookup"><span data-stu-id="98c8f-102">ICorProfilerCallback::ExceptionSearchFilterLeave Method</span></span>
<span data-ttu-id="98c8f-103">Notifica al generador de perfiles que un filtro de usuario acaba de ejecutar.</span><span class="sxs-lookup"><span data-stu-id="98c8f-103">Notifies the profiler that a user filter has just finished executing.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="98c8f-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="98c8f-104">Syntax</span></span>  
  
```  
HRESULT ExceptionSearchFilterLeave();  
```  
  
## <a name="requirements"></a><span data-ttu-id="98c8f-105">Requisitos</span><span class="sxs-lookup"><span data-stu-id="98c8f-105">Requirements</span></span>  
 <span data-ttu-id="98c8f-106">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="98c8f-106">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="98c8f-107">**Encabezado**: CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="98c8f-107">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="98c8f-108">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="98c8f-108">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="98c8f-109">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="98c8f-109">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="98c8f-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="98c8f-110">See also</span></span>

- [<span data-ttu-id="98c8f-111">ICorProfilerCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="98c8f-111">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="98c8f-112">Método ExceptionSearchFilterEnter</span><span class="sxs-lookup"><span data-stu-id="98c8f-112">ExceptionSearchFilterEnter Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfilterenter-method.md)
