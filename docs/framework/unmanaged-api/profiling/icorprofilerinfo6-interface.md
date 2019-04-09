---
title: Interfaz ICorProfilerInfo6
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo6
api_location:
- mscorwks.dll
api_type:
- COM
ms.assetid: 6f2bb148-1e2b-4e45-a5a5-0ceddc40064b
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: febe130b4d61b6179aeab3bfcd63891c38b13fbe
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59128939"
---
# <a name="icorprofilerinfo6-interface"></a><span data-ttu-id="da06d-102">Interfaz ICorProfilerInfo6</span><span class="sxs-lookup"><span data-stu-id="da06d-102">ICorProfilerInfo6 Interface</span></span>
<span data-ttu-id="da06d-103">[Compatible con .NET Framework 4.6 y versiones posteriores]</span><span class="sxs-lookup"><span data-stu-id="da06d-103">[Supported in the .NET Framework 4.6 and later versions]</span></span>  
  
 <span data-ttu-id="da06d-104">Una subclase de [ICorProfilerInfo5](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-interface.md) que proporciona un enumerador para todos los métodos que se definen en un determinado módulo NGen y en línea un método determinado.</span><span class="sxs-lookup"><span data-stu-id="da06d-104">A subclass of [ICorProfilerInfo5](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-interface.md) that provides an enumerator for all methods that are defined in a given NGen module and inline a given method.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="da06d-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="da06d-105">Methods</span></span>  
  
|<span data-ttu-id="da06d-106">Método</span><span class="sxs-lookup"><span data-stu-id="da06d-106">Method</span></span>|<span data-ttu-id="da06d-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="da06d-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="da06d-108">Método ICorProfilerInfo6::EnumNgenModuleMethodsInliningThisMethod</span><span class="sxs-lookup"><span data-stu-id="da06d-108">ICorProfilerInfo6::EnumNgenModuleMethodsInliningThisMethod Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo6-enumngenmodulemethodsinliningthismethod-method.md)|<span data-ttu-id="da06d-109">Devuelve un enumerador para todos los métodos que pertenecen a un módulo NGen determinado y que se alinean en el cuerpo de un método determinado.</span><span class="sxs-lookup"><span data-stu-id="da06d-109">Returns an enumerator for all methods that belong to a given NGen module and that are inlined in the body of a given method.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="da06d-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="da06d-110">Requirements</span></span>  
 <span data-ttu-id="da06d-111">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="da06d-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="da06d-112">**Encabezado**: CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="da06d-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 **<span data-ttu-id="da06d-113">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="da06d-113">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="da06d-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="da06d-114">See also</span></span>

- [<span data-ttu-id="da06d-115">Interfaces para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="da06d-115">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
