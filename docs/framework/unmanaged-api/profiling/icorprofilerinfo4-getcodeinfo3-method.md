---
title: ICorProfilerInfo4::GetCodeInfo3 (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo4.GetCodeInfo3
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo4::GetCodeInfo3
helpviewer_keywords:
- GetCodeInfo3 method, ICorProfilerInfo4 interface [.NET Framework profiling]
- ICorProfilerInfo4::GetCodeInfo3 method [.NET Framework profiling]
ms.assetid: bb8c105e-4d9a-4684-8c05-ed6909cc1b8c
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: e0467bd9cbb645d876f88c1da6c8e8e75510f04e
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57481417"
---
# <a name="icorprofilerinfo4getcodeinfo3-method"></a><span data-ttu-id="59e85-102">ICorProfilerInfo4::GetCodeInfo3 (Método)</span><span class="sxs-lookup"><span data-stu-id="59e85-102">ICorProfilerInfo4::GetCodeInfo3 Method</span></span>
<span data-ttu-id="59e85-103">Obtiene las extensiones de código nativo asociadas con la versión recompilada con JIT de la función especificada.</span><span class="sxs-lookup"><span data-stu-id="59e85-103">Gets the extents of native code associated with the JIT-recompiled version of the specified function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="59e85-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="59e85-104">Syntax</span></span>  
  
```  
HRESULT GetCodeInfo3(  
    [in]  FunctionID functionID,  
    [in]  ReJITID reJitId,  
    [in]  ULONG32 cCodeInfos,  
    [out] ULONG32 *pcCodeInfos,  
    [out, size_is(cCodeInfos), length_is(*pcCodeInfos)]  
    COR_PRF_CODE_INFO codeInfos[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="59e85-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="59e85-105">Parameters</span></span>  
 `functionID`  
 <span data-ttu-id="59e85-106">[in] Identificador de función con la que está asociado el código nativo.</span><span class="sxs-lookup"><span data-stu-id="59e85-106">[in] The ID of the function with which the native code is associated.</span></span>  
  
 `reJitId`  
 <span data-ttu-id="59e85-107">[in] Identidad de la función recompilada con JIT.</span><span class="sxs-lookup"><span data-stu-id="59e85-107">[in] The identity of the JIT-recompiled function.</span></span>  
  
 `cCodeInfos`  
 <span data-ttu-id="59e85-108">[in] Tamaño de la matriz `codeInfos`.</span><span class="sxs-lookup"><span data-stu-id="59e85-108">[in] The size of the `codeInfos` array.</span></span>  
  
 `pcCodeInfos`  
 <span data-ttu-id="59e85-109">[out] Un puntero al número total de [COR_PRF_CODE_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-code-info-structure.md) estructuras disponibles.</span><span class="sxs-lookup"><span data-stu-id="59e85-109">[out] A pointer to the total number of [COR_PRF_CODE_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-code-info-structure.md) structures available.</span></span>  
  
 `codeInfos`  
 <span data-ttu-id="59e85-110">[out] Búfer proporcionado por el llamador.</span><span class="sxs-lookup"><span data-stu-id="59e85-110">[out] A caller-provided buffer.</span></span> <span data-ttu-id="59e85-111">Después de que el método vuelva, contiene una matriz de estructuras `COR_PRF_CODE_INFO`, cada una de las cuales describe un bloque de código nativo.</span><span class="sxs-lookup"><span data-stu-id="59e85-111">After the method returns, it contains an array of `COR_PRF_CODE_INFO` structures, each of which describes a block of native code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="59e85-112">Comentarios</span><span class="sxs-lookup"><span data-stu-id="59e85-112">Remarks</span></span>  
 <span data-ttu-id="59e85-113">El `GetCodeInfo3` es similar al método [GetCodeInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getcodeinfo2-method.md), salvo que obtendrá el identificador recompilado con JIT de la función que contiene la dirección IP especificada.</span><span class="sxs-lookup"><span data-stu-id="59e85-113">The `GetCodeInfo3` method is similar to [GetCodeInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getcodeinfo2-method.md), except that it will get the JIT-recompiled ID of the function that contains the specified IP address.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="59e85-114">`GetCodeInfo3` puede desencadenar una recolección de elementos, mientras que [GetCodeInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getcodeinfo2-method.md) no se iniciará.</span><span class="sxs-lookup"><span data-stu-id="59e85-114">`GetCodeInfo3` can trigger a garbage collection, whereas [GetCodeInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getcodeinfo2-method.md) will not.</span></span> <span data-ttu-id="59e85-115">Para obtener más información, consulte el [CORPROF_E_UNSUPPORTED_CALL_SEQUENCE](../../../../docs/framework/unmanaged-api/profiling/corprof-e-unsupported-call-sequence-hresult.md) HRESULT.</span><span class="sxs-lookup"><span data-stu-id="59e85-115">For more information, see the [CORPROF_E_UNSUPPORTED_CALL_SEQUENCE](../../../../docs/framework/unmanaged-api/profiling/corprof-e-unsupported-call-sequence-hresult.md) HRESULT.</span></span>  
  
 <span data-ttu-id="59e85-116">Las extensiones se clasifican en orden creciente de desplazamiento de Common Intermediate Language (CIL).</span><span class="sxs-lookup"><span data-stu-id="59e85-116">The extents are sorted in order of increasing Common Intermediate Language (CIL) offset.</span></span>  
  
 <span data-ttu-id="59e85-117">Después de `GetCodeInfo3` vuelva, debe comprobar que la `codeInfos` búfer era lo suficientemente grande como para contener todos los [COR_PRF_CODE_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-code-info-structure.md) estructuras.</span><span class="sxs-lookup"><span data-stu-id="59e85-117">After `GetCodeInfo3` returns, you must verify that the `codeInfos` buffer was large enough to contain all the [COR_PRF_CODE_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-code-info-structure.md) structures.</span></span> <span data-ttu-id="59e85-118">Para ello, compare el valor de `cCodeInfos` con el valor del parámetro `cchName`.</span><span class="sxs-lookup"><span data-stu-id="59e85-118">To do this, compare the value of `cCodeInfos` with the value of the `cchName` parameter.</span></span> <span data-ttu-id="59e85-119">Si `cCodeInfos` dividido por el tamaño de un [COR_PRF_CODE_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-code-info-structure.md) estructura es menor que `pcCodeInfos`, asignar una mayor `codeInfos` almacenar en búfer, actualice `cCodeInfos` con el nuevo tamaño y llamar a `GetCodeInfo3` de nuevo.</span><span class="sxs-lookup"><span data-stu-id="59e85-119">If `cCodeInfos` divided by the size of a [COR_PRF_CODE_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-code-info-structure.md) structure is smaller than `pcCodeInfos`, allocate a larger `codeInfos` buffer, update `cCodeInfos` with the new, larger size, and call `GetCodeInfo3` again.</span></span>  
  
 <span data-ttu-id="59e85-120">También tiene la opción de llamar primero a `GetCodeInfo3` con un búfer `codeInfos` de longitud de cero para obtener el tamaño de búfer correcto.</span><span class="sxs-lookup"><span data-stu-id="59e85-120">Alternatively, you can first call `GetCodeInfo3` with a zero-length `codeInfos` buffer to obtain the correct buffer size.</span></span> <span data-ttu-id="59e85-121">A continuación, puede establecer el `codeInfos` búfer de tamaño para el valor devuelto en `pcCodeInfos`, multiplicado por el tamaño de un [COR_PRF_CODE_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-code-info-structure.md) estructura y la llamada `GetCodeInfo3` nuevo.</span><span class="sxs-lookup"><span data-stu-id="59e85-121">You can then set the `codeInfos` buffer size to the value returned in `pcCodeInfos`, multiplied by the size of a [COR_PRF_CODE_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-code-info-structure.md) structure, and call `GetCodeInfo3` again.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="59e85-122">Requisitos</span><span class="sxs-lookup"><span data-stu-id="59e85-122">Requirements</span></span>  
 <span data-ttu-id="59e85-123">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="59e85-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="59e85-124">**Encabezado**: CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="59e85-124">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="59e85-125">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="59e85-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="59e85-126">**Versiones de .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="59e85-126">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="59e85-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="59e85-127">See also</span></span>
- [<span data-ttu-id="59e85-128">GetCodeInfo2 (método)</span><span class="sxs-lookup"><span data-stu-id="59e85-128">GetCodeInfo2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getcodeinfo2-method.md)
- [<span data-ttu-id="59e85-129">ICorProfilerInfo4 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="59e85-129">ICorProfilerInfo4 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-interface.md)
- [<span data-ttu-id="59e85-130">Interfaces para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="59e85-130">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [<span data-ttu-id="59e85-131">Generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="59e85-131">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
