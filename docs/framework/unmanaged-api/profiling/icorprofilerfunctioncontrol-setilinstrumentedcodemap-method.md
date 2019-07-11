---
title: ICorProfilerFunctionControl::SetILInstrumentedCodeMap (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerFunctionControl.SetILInstrumentedCodeMap
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerFunctionControl::SetILInstrumentedCodeMap
helpviewer_keywords:
- ICorProfilerFunctionControl::SetILInstrumentedCodeMap method [.NET Framework profiling]
- SetIILInstrumentedCodeMap method, ICorProfilerFunctionControl interface [.NET Framework profiling]
ms.assetid: ecf56646-7e5f-46c4-8340-f3a04e88920f
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 31caa87b1eaa48532ffb20b46c593242379c7ae8
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67780343"
---
# <a name="icorprofilerfunctioncontrolsetilinstrumentedcodemap-method"></a><span data-ttu-id="263b8-102">ICorProfilerFunctionControl::SetILInstrumentedCodeMap (Método)</span><span class="sxs-lookup"><span data-stu-id="263b8-102">ICorProfilerFunctionControl::SetILInstrumentedCodeMap Method</span></span>
<span data-ttu-id="263b8-103">Establece un mapa de código para la función especificada usando las entradas del mapa de Common Intermediate Language (CIL) especificadas.</span><span class="sxs-lookup"><span data-stu-id="263b8-103">Sets a code map for the specified function by using the specified Common Intermediate Language (CIL) map entries.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="263b8-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="263b8-104">Syntax</span></span>  
  
```cpp  
HRESULT SetILInstrumentedCodeMap(  
    [in]   ULONG      cILMapEntries,  
    [in, size_is(cILMapEntries)] COR_IL_MAP rgILMapEntries[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="263b8-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="263b8-105">Parameters</span></span>  
 `cILMapEntries`  
 <span data-ttu-id="263b8-106">[in] Número de entradas en el mapa.</span><span class="sxs-lookup"><span data-stu-id="263b8-106">[in] The number of entries in the map.</span></span>  
  
 `rgILMapEntries`  
 <span data-ttu-id="263b8-107">[in] Matriz de entradas COR_IL_MAP asignada por el llamador.</span><span class="sxs-lookup"><span data-stu-id="263b8-107">[in] The caller-allocated array of COR_IL_MAP  entries.</span></span> <span data-ttu-id="263b8-108">La interpretación de estas entradas es la misma que para el [SetILInstrumentedCodeMap](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setilinstrumentedcodemap-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="263b8-108">The interpretation of these entries is the same as for the [ICorProfilerInfo::SetILInstrumentedCodeMap](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setilinstrumentedcodemap-method.md) method.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="263b8-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="263b8-109">Remarks</span></span>  
 <span data-ttu-id="263b8-110">Establecer la asignación mediante una llamada a este método permite al depurador recuperar la asignación mediante una llamada a [Icordebugilcode2](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode2-getinstrumentedilmap-method.md).</span><span class="sxs-lookup"><span data-stu-id="263b8-110">Setting the mapping by calling this method allows the debugger to retrieve the mapping by calling [ICorDebugILCode2::GetInstrumentedILMap](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode2-getinstrumentedilmap-method.md).</span></span> <span data-ttu-id="263b8-111">También permite al depurador usar la asignación internamente al calcular los desplazamientos del IL para los seguimientos de pila y la duración de las variables.</span><span class="sxs-lookup"><span data-stu-id="263b8-111">It also allows the debugger to use the mapping internally when calculating IL offsets for stack traces and variable lifetimes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="263b8-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="263b8-112">Requirements</span></span>  
 <span data-ttu-id="263b8-113">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="263b8-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="263b8-114">**Encabezado**: CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="263b8-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="263b8-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="263b8-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="263b8-116">**Versiones de .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="263b8-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="263b8-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="263b8-117">See also</span></span>

- [<span data-ttu-id="263b8-118">ICorProfilerInfo (interfaz)</span><span class="sxs-lookup"><span data-stu-id="263b8-118">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
