---
title: ICorDebugEval::GetThread (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugEval.GetThread
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval::GetThread
helpviewer_keywords:
- GetThread method, ICorDebugEval interface [.NET Framework debugging]
- ICorDebugEval::GetThread method [.NET Framework debugging]
ms.assetid: 57163b0d-c8a7-44af-9078-e7a895d29f9a
topic_type:
- apiref
ms.openlocfilehash: 6a7d9465a454175b58bb7b9566d31f3c65420610
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73085056"
---
# <a name="icordebugevalgetthread-method"></a><span data-ttu-id="7b97e-102">ICorDebugEval::GetThread (Método)</span><span class="sxs-lookup"><span data-stu-id="7b97e-102">ICorDebugEval::GetThread Method</span></span>
<span data-ttu-id="7b97e-103">Obtiene el subproceso en el que se ejecuta esta evaluación o que se ejecutará.</span><span class="sxs-lookup"><span data-stu-id="7b97e-103">Gets the thread in which this evaluation is executing or will execute.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7b97e-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7b97e-104">Syntax</span></span>  
  
```cpp  
HRESULT GetThread (  
    [out] ICorDebugThread   **ppThread  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7b97e-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="7b97e-105">Parameters</span></span>  
 `ppThread`  
 <span data-ttu-id="7b97e-106">enuncia Puntero a la dirección de un objeto ICorDebugThread que representa el subproceso.</span><span class="sxs-lookup"><span data-stu-id="7b97e-106">[out] A pointer to the address of an ICorDebugThread object that represents the thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7b97e-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7b97e-107">Requirements</span></span>  
 <span data-ttu-id="7b97e-108">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7b97e-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7b97e-109">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7b97e-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7b97e-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7b97e-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7b97e-111">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7b97e-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
