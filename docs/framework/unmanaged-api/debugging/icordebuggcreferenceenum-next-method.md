---
title: ICorDebugGCReferenceEnum::Next (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugGCReferenceEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugGCReferenceEnum::Next
helpviewer_keywords:
- Next method, ICorDebugGCReferenceEnum interface [.NET Framework debugging]
- ICorDebugGCReferenceEnum::Next method [.NET Framework debugging]
ms.assetid: 91b1345c-a94f-4ef8-9696-3823d06c6d05
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 33ad221f2a05357484d0877b6306d78e3864eff6
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59120177"
---
# <a name="icordebuggcreferenceenumnext-method"></a><span data-ttu-id="51a70-102">ICorDebugGCReferenceEnum::Next (Método)</span><span class="sxs-lookup"><span data-stu-id="51a70-102">ICorDebugGCReferenceEnum::Next Method</span></span>
<span data-ttu-id="51a70-103">Obtiene el número especificado de [COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) instancias que contienen información sobre los objetos que se pueden recolectar.</span><span class="sxs-lookup"><span data-stu-id="51a70-103">Gets the specified number of [COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) instances that contain information about objects that will be garbage-collected.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="51a70-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="51a70-104">Syntax</span></span>  
  
```  
HRESULT Next(  
    [in] ULONG celt,    [out, size_is(celt), length_is(*pceltFetched)] COR_GC_REFERENCE roots[],   
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="51a70-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="51a70-105">Parameters</span></span>  
 <span data-ttu-id="51a70-106">celt</span><span class="sxs-lookup"><span data-stu-id="51a70-106">celt</span></span>  
 <span data-ttu-id="51a70-107">[in] El número de raíces va a recuperar.</span><span class="sxs-lookup"><span data-stu-id="51a70-107">[in] The number of roots to be retrieved.</span></span>  
  
 <span data-ttu-id="51a70-108">raíces</span><span class="sxs-lookup"><span data-stu-id="51a70-108">roots</span></span>  
 <span data-ttu-id="51a70-109">[out] Una matriz de punteros, cada uno de los cuales señala a un [COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) objeto que representa la raíz de un objeto para recopilar los elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="51a70-109">[out] An array of pointers, each of which points to a [COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) object that represents the root of an object to be garbage-collected.</span></span>  
  
 <span data-ttu-id="51a70-110">pceltFetched</span><span class="sxs-lookup"><span data-stu-id="51a70-110">pceltFetched</span></span>  
 <span data-ttu-id="51a70-111">[out] Un puntero al número de [COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) los objetos devueltos realmente en `roots`.</span><span class="sxs-lookup"><span data-stu-id="51a70-111">[out] A pointer to the number of [COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) objects actually returned in `roots`.</span></span> <span data-ttu-id="51a70-112">Este valor puede ser `null` si `celt` es 1.</span><span class="sxs-lookup"><span data-stu-id="51a70-112">This value may be `null` if `celt` is 1.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="51a70-113">Comentarios</span><span class="sxs-lookup"><span data-stu-id="51a70-113">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="51a70-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="51a70-114">Requirements</span></span>  
 <span data-ttu-id="51a70-115">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="51a70-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="51a70-116">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="51a70-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="51a70-117">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="51a70-117">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="51a70-118">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="51a70-118">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="51a70-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="51a70-119">See also</span></span>

- [<span data-ttu-id="51a70-120">ICorDebugGCReferenceEnum (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="51a70-120">ICorDebugGCReferenceEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuggcreferenceenum-interface.md)
- [<span data-ttu-id="51a70-121">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="51a70-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
