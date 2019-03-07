---
title: ICorProfilerInfo3::GetAppDomainsContainingModule (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo3.GetAppDomainsContainingModule Method
api_location:
- Mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo3::GetAppDomainsContainingModule
helpviewer_keywords:
- GetAppDomainsContainingModule method [.NET Framework profiling]
- ICorProfilerInfo3::GetAppDomainsContainingModule method [.NET Framework profiling]
ms.assetid: 603b3881-ea94-4dca-95cd-91eebac873a0
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 4ed9a9a91f4e802e6251add965306cf13f19139e
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57494238"
---
# <a name="icorprofilerinfo3getappdomainscontainingmodule-method"></a><span data-ttu-id="9c0ea-102">ICorProfilerInfo3::GetAppDomainsContainingModule (Método)</span><span class="sxs-lookup"><span data-stu-id="9c0ea-102">ICorProfilerInfo3::GetAppDomainsContainingModule Method</span></span>
<span data-ttu-id="9c0ea-103">Obtiene los identificadores de los dominios de la aplicación en la que se cargó el módulo especificado.</span><span class="sxs-lookup"><span data-stu-id="9c0ea-103">Gets the identifiers of the application domains in which the given module has been loaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9c0ea-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9c0ea-104">Syntax</span></span>  
  
```  
HRESULT GetAppDomainsContainingModule(  
            [in] ModuleID moduleId,  
            [in] ULONG32 cAppDomainIds,  
            [out] ULONG32 *pcAppDomainIds,  
            [out, size_is(cAppDomainIds), length_is(*pcAppDomainIds)]  
                    AppDomainID appDomainIds[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9c0ea-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="9c0ea-105">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="9c0ea-106">[in] Identificador del módulo cargado.</span><span class="sxs-lookup"><span data-stu-id="9c0ea-106">[in] The ID of the loaded module.</span></span>  
  
 `cAppDomainIds`  
 <span data-ttu-id="9c0ea-107">[in] Tamaño de la matriz `appDomainIds`.</span><span class="sxs-lookup"><span data-stu-id="9c0ea-107">[in] The size of the `appDomainIds` array.</span></span>  
  
 `pcAppDomainIds`  
 <span data-ttu-id="9c0ea-108">[out] Puntero al número total de elementos devueltos.</span><span class="sxs-lookup"><span data-stu-id="9c0ea-108">[out] A pointer to the total number of returned elements.</span></span>  
  
 `appDomainIds`  
 <span data-ttu-id="9c0ea-109">[out] Matriz de valores de identificador de dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="9c0ea-109">[out] An array of application domain ID values.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9c0ea-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="9c0ea-110">Remarks</span></span>  
 <span data-ttu-id="9c0ea-111">El método usa búferes asignados al llamador.</span><span class="sxs-lookup"><span data-stu-id="9c0ea-111">The method uses caller allocated buffers.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9c0ea-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9c0ea-112">Requirements</span></span>  
 <span data-ttu-id="9c0ea-113">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9c0ea-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9c0ea-114">**Encabezado**: CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="9c0ea-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="9c0ea-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9c0ea-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9c0ea-116">**Versiones de .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9c0ea-116">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9c0ea-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="9c0ea-117">See also</span></span>
- [<span data-ttu-id="9c0ea-118">ICorProfilerFunctionEnum (interfaz)</span><span class="sxs-lookup"><span data-stu-id="9c0ea-118">ICorProfilerFunctionEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-interface.md)
- [<span data-ttu-id="9c0ea-119">ICorProfilerInfo3 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="9c0ea-119">ICorProfilerInfo3 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-interface.md)
- [<span data-ttu-id="9c0ea-120">Interfaces para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="9c0ea-120">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [<span data-ttu-id="9c0ea-121">Generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="9c0ea-121">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
