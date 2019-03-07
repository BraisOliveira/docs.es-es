---
title: ICorDebugCode::GetAddress (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugCode.GetAddress
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode::GetAddress
helpviewer_keywords:
- GetAddress method, ICorDebugCode interface [.NET Framework debugging]
- ICorDebugCode::GetAddress method [.NET Framework debugging]
ms.assetid: cc507cb0-df2e-49c2-b32e-0c3271a8df9a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: dda5883d8a1de11fa282e8b8e0fafe924f2d8b7a
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57494511"
---
# <a name="icordebugcodegetaddress-method"></a><span data-ttu-id="d47cf-102">ICorDebugCode::GetAddress (Método)</span><span class="sxs-lookup"><span data-stu-id="d47cf-102">ICorDebugCode::GetAddress Method</span></span>
<span data-ttu-id="d47cf-103">Obtiene la dirección virtual relativa (RVA) del segmento de código que representa esta interfaz "ICorDebugCode".</span><span class="sxs-lookup"><span data-stu-id="d47cf-103">Gets the relative virtual address (RVA) of the code segment that this "ICorDebugCode" interface represents.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d47cf-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d47cf-104">Syntax</span></span>  
  
```  
HRESULT GetAddress (  
    [out] CORDB_ADDRESS *pStart  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d47cf-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d47cf-105">Parameters</span></span>  
 `pStart`  
 <span data-ttu-id="d47cf-106">[out] Un puntero a la dirección RVA del segmento de código.</span><span class="sxs-lookup"><span data-stu-id="d47cf-106">[out] A pointer to the RVA of the code segment.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d47cf-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d47cf-107">Requirements</span></span>  
 <span data-ttu-id="d47cf-108">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d47cf-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d47cf-109">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d47cf-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d47cf-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d47cf-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d47cf-111">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d47cf-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d47cf-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="d47cf-112">See also</span></span>

