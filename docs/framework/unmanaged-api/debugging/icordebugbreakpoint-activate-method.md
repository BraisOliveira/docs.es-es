---
title: ICorDebugBreakpoint::Activate (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugBreakpoint.Activate
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugBreakpoint::Activate
helpviewer_keywords:
- ICorDebugBreakpoint::Activate method [.NET Framework debugging]
- Activate method [.NET Framework debugging]
ms.assetid: e30c29f7-3f19-4081-b572-a731aa14cd44
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2ac37df58762dac4e3a6161361cafd8ea87e2657
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61645388"
---
# <a name="icordebugbreakpointactivate-method"></a><span data-ttu-id="30f99-102">ICorDebugBreakpoint::Activate (Método)</span><span class="sxs-lookup"><span data-stu-id="30f99-102">ICorDebugBreakpoint::Activate Method</span></span>
<span data-ttu-id="30f99-103">Establece el estado activo de este `ICorDebugBreakpoint`.</span><span class="sxs-lookup"><span data-stu-id="30f99-103">Sets the active state of this `ICorDebugBreakpoint`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="30f99-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="30f99-104">Syntax</span></span>  
  
```  
HRESULT Activate (  
    [in] BOOL bActive  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="30f99-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="30f99-105">Parameters</span></span>  
 `bActive`  
 <span data-ttu-id="30f99-106">[in] Establezca este valor en `true` para especificar el estado como activo; en caso contrario, establezca este valor en `false`.</span><span class="sxs-lookup"><span data-stu-id="30f99-106">[in] Set this value to `true` to specify the state as active; otherwise, set this value to `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="30f99-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="30f99-107">Requirements</span></span>  
 <span data-ttu-id="30f99-108">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="30f99-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="30f99-109">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="30f99-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="30f99-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="30f99-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="30f99-111">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="30f99-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
