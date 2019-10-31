---
title: ICorDebugEnum::Skip (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugEnum.Skip
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEnum::Skip
helpviewer_keywords:
- ICorDebugEnum::Skip method [.NET Framework debugging]
- Skip method, ICorDebugEnum interface [.NET Framework debugging]
ms.assetid: e925d88a-67a5-4f76-88b8-09cedeed0232
topic_type:
- apiref
ms.openlocfilehash: 2c5cd7435ec34e852b80031cfe0310ee517b7bc5
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73103474"
---
# <a name="icordebugenumskip-method"></a><span data-ttu-id="7b58b-102">ICorDebugEnum::Skip (Método)</span><span class="sxs-lookup"><span data-stu-id="7b58b-102">ICorDebugEnum::Skip Method</span></span>
<span data-ttu-id="7b58b-103">Mueve el cursor hacia delante en la enumeración el número de elementos especificado.</span><span class="sxs-lookup"><span data-stu-id="7b58b-103">Moves the cursor forward in the enumeration by the specified number of items.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7b58b-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7b58b-104">Syntax</span></span>  
  
```cpp  
HRESULT Skip (  
    [in] ULONG celt  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7b58b-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="7b58b-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="7b58b-106">de Número de elementos por los que se va a desplazar el cursor hacia delante.</span><span class="sxs-lookup"><span data-stu-id="7b58b-106">[in] The number of items by which to move the cursor forward.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7b58b-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7b58b-107">Requirements</span></span>  
 <span data-ttu-id="7b58b-108">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7b58b-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7b58b-109">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7b58b-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7b58b-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7b58b-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7b58b-111">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7b58b-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7b58b-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="7b58b-112">See also</span></span>

- [<span data-ttu-id="7b58b-113">ICorDebugEnum (interfaz)</span><span class="sxs-lookup"><span data-stu-id="7b58b-113">ICorDebugEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugenum-interface1.md)
