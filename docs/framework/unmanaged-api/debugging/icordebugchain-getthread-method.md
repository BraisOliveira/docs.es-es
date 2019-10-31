---
title: ICorDebugChain::GetThread (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugChain.GetThread
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugChain::GetThread
helpviewer_keywords:
- GetThread method, ICorDebugChain interface [.NET Framework debugging]
- ICorDebugChain::GetThread method [.NET Framework debugging]
ms.assetid: b3390319-6366-418c-ba80-b552ac4dfc1e
topic_type:
- apiref
ms.openlocfilehash: b964d58bddb174da38fc8988ec807fd3129b5fcf
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73123824"
---
# <a name="icordebugchaingetthread-method"></a><span data-ttu-id="8db9a-102">ICorDebugChain::GetThread (Método)</span><span class="sxs-lookup"><span data-stu-id="8db9a-102">ICorDebugChain::GetThread Method</span></span>
<span data-ttu-id="8db9a-103">Obtiene el subproceso físico del que forma parte esta cadena de llamadas.</span><span class="sxs-lookup"><span data-stu-id="8db9a-103">Gets the physical thread this call chain is part of.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8db9a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8db9a-104">Syntax</span></span>  
  
```cpp  
HRESULT GetThread (  
    [out] ICorDebugThread    **ppThread  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8db9a-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="8db9a-105">Parameters</span></span>  
 `ppThread`  
 <span data-ttu-id="8db9a-106">enuncia Un puntero a un objeto ICorDebugThread que representa el subproceso físico del que forma parte esta cadena de llamadas.</span><span class="sxs-lookup"><span data-stu-id="8db9a-106">[out] A pointer to an ICorDebugThread object that represents the physical thread this call chain is part of.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8db9a-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8db9a-107">Requirements</span></span>  
 <span data-ttu-id="8db9a-108">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8db9a-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8db9a-109">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8db9a-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8db9a-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8db9a-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8db9a-111">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8db9a-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
