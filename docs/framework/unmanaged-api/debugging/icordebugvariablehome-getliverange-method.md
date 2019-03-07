---
title: Método IcorDebugVariableHome::GetLiveRange
ms.date: 03/30/2017
api_name:
- ICorDebugVariableHome.GetLiveRange
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugVariableHome::GetLiveRange
helpviewer_keywords:
- ICorDebugVariableHome::GetLiveRange method [.NET Framework debugging]
- GetLiveRange method, ICorDebugVariableFrame interface [.NET Framework debugging]
ms.assetid: 87277e1a-1595-4729-9e25-d1c3ac18ce5f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 06c8ae378c10eda986740dfb73f3bf60ea8647a6
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57468850"
---
# <a name="icordebugvariablehomegetliverange-method"></a><span data-ttu-id="beb06-102">Método IcorDebugVariableHome::GetLiveRange</span><span class="sxs-lookup"><span data-stu-id="beb06-102">IcorDebugVariableHome::GetLiveRange Method</span></span>
<span data-ttu-id="beb06-103">Obtiene el intervalo nativo a través de la que esta variable está activa.</span><span class="sxs-lookup"><span data-stu-id="beb06-103">Gets the native range over which this variable is live.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="beb06-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="beb06-104">Syntax</span></span>  
  
```  
HRESULT GetLiveRange(  
    [out] ULONG32* pStartOffset,  
    [out] ULONG32 *pEndOffset  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="beb06-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="beb06-105">Parameters</span></span>  
 `pStartOffset`  
 <span data-ttu-id="beb06-106">[out] El desplazamiento lógico en el que la variable es el primera en vivo.</span><span class="sxs-lookup"><span data-stu-id="beb06-106">[out] The logical offset at which the variable is first live.</span></span>  
  
 `pEndOffset`  
 <span data-ttu-id="beb06-107">[out] El desplazamiento lógico inmediatamente después del punto en el que la variable es el última en vivo.</span><span class="sxs-lookup"><span data-stu-id="beb06-107">[out] The logical offset immediately after the point at which the variable is last live.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="beb06-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="beb06-108">Requirements</span></span>  
 <span data-ttu-id="beb06-109">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="beb06-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="beb06-110">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="beb06-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="beb06-111">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="beb06-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="beb06-112">**Versiones de .NET Framework:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="beb06-112">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="beb06-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="beb06-113">See also</span></span>
- [<span data-ttu-id="beb06-114">ICorDebugVariableHome (interfaz)</span><span class="sxs-lookup"><span data-stu-id="beb06-114">ICorDebugVariableHome Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)
