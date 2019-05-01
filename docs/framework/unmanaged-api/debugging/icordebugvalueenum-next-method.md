---
title: ICorDebugValueEnum::Next (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugValueEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugValueEnum::Next
helpviewer_keywords:
- ICorDebugValueEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugValueEnum interface [.NET Framework debugging]
ms.assetid: f5ef94dd-dfee-49d3-a398-b110f8906dd8
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b24507c7cb0860fc04fa519c6bd95113483f629d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61993712"
---
# <a name="icordebugvalueenumnext-method"></a><span data-ttu-id="ca328-102">ICorDebugValueEnum::Next (Método)</span><span class="sxs-lookup"><span data-stu-id="ca328-102">ICorDebugValueEnum::Next Method</span></span>
<span data-ttu-id="ca328-103">Obtiene el número especificado de instancias de "ICorDebugValue" de la enumeración, comenzando en la posición actual.</span><span class="sxs-lookup"><span data-stu-id="ca328-103">Gets the specified number of "ICorDebugValue" instances from the enumeration, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ca328-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ca328-104">Syntax</span></span>  
  
```  
HRESULT Next (  
    [in]  ULONG  celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugValue *values[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ca328-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ca328-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="ca328-106">[in] El número de `ICorDebugValue` instancias va a recuperar.</span><span class="sxs-lookup"><span data-stu-id="ca328-106">[in] The number of `ICorDebugValue` instances to be retrieved.</span></span>  
  
 `values`  
 <span data-ttu-id="ca328-107">[out] Una matriz de punteros, cada uno de los cuales señala a una `ICorDebugValue` objeto.</span><span class="sxs-lookup"><span data-stu-id="ca328-107">[out] An array of pointers, each of which points to an `ICorDebugValue` object.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="ca328-108">[out] Puntero al número de `ICorDebugValue` instancias devueltas realmente.</span><span class="sxs-lookup"><span data-stu-id="ca328-108">[out] Pointer to the number of `ICorDebugValue` instances actually returned.</span></span> <span data-ttu-id="ca328-109">Este valor puede ser null si `celt` es uno.</span><span class="sxs-lookup"><span data-stu-id="ca328-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ca328-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ca328-110">Requirements</span></span>  
 <span data-ttu-id="ca328-111">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ca328-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ca328-112">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ca328-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ca328-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ca328-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ca328-114">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ca328-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ca328-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="ca328-115">See also</span></span>
