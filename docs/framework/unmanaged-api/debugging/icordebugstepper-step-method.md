---
title: ICorDebugStepper::Step (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugStepper.Step
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStepper::Step
helpviewer_keywords:
- Step method, ICorDebugStepper interface [.NET Framework debugging]
- ICorDebugStepper::Step method [.NET Framework debugging]
ms.assetid: 38c1940b-ada1-40ba-8295-4c0833744e1e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 444390622ca68244661b91dc85814b05556b12a2
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61994323"
---
# <a name="icordebugstepperstep-method"></a><span data-ttu-id="d2c26-102">ICorDebugStepper::Step (Método)</span><span class="sxs-lookup"><span data-stu-id="d2c26-102">ICorDebugStepper::Step Method</span></span>
<span data-ttu-id="d2c26-103">Hace que este ICorDebugStepper paso a paso a través del subproceso que la contiene y, opcionalmente, para continuar pasando solo a través de funciones que se llaman dentro del subproceso.</span><span class="sxs-lookup"><span data-stu-id="d2c26-103">Causes this ICorDebugStepper to single-step through its containing thread, and optionally, to continue single-stepping through functions that are called within the thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d2c26-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d2c26-104">Syntax</span></span>  
  
```  
HRESULT Step (  
    [in] BOOL   bStepIn  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d2c26-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d2c26-105">Parameters</span></span>  
 `bStepIn`  
 <span data-ttu-id="d2c26-106">[in] Establecido en `true` para adentrarse en una función que se llama dentro del subproceso.</span><span class="sxs-lookup"><span data-stu-id="d2c26-106">[in] Set to `true` to step into a function that is called within the thread.</span></span> <span data-ttu-id="d2c26-107">Establecido en `false` al paso a través de la función.</span><span class="sxs-lookup"><span data-stu-id="d2c26-107">Set to `false` to step over the function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d2c26-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d2c26-108">Remarks</span></span>  
 <span data-ttu-id="d2c26-109">El paso finaliza cuando common language runtime ejecuta la siguiente instrucción administrada en el marco de este motor de paso a paso.</span><span class="sxs-lookup"><span data-stu-id="d2c26-109">The step completes when the common language runtime performs the next managed instruction in this stepper's frame.</span></span> <span data-ttu-id="d2c26-110">Si `Step` es llamado en un motor paso a paso, que no está en código administrado, el paso finalizará cuando se ejecuta la siguiente instrucción de código administrado por el subproceso.</span><span class="sxs-lookup"><span data-stu-id="d2c26-110">If `Step` is called on a stepper, which is not in managed code, the step will complete when the next managed code instruction is executed by the thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d2c26-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d2c26-111">Requirements</span></span>  
 <span data-ttu-id="d2c26-112">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d2c26-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d2c26-113">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d2c26-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d2c26-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d2c26-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d2c26-115">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d2c26-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
