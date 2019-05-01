---
title: ICorDebugStepper::Deactivate (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugStepper.Deactivate
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStepper::Deactivate
helpviewer_keywords:
- Deactivate method [.NET Framework debugging]
- ICorDebugStepper::Deactivate method [.NET Framework debugging]
ms.assetid: 855f4199-b62d-40ce-998e-1eb4a1772142
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bcd7bfb52cadf740d8fe3cb92a09b071f530b7ee
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61994336"
---
# <a name="icordebugstepperdeactivate-method"></a><span data-ttu-id="bf077-102">ICorDebugStepper::Deactivate (Método)</span><span class="sxs-lookup"><span data-stu-id="bf077-102">ICorDebugStepper::Deactivate Method</span></span>
<span data-ttu-id="bf077-103">Hace que este ICorDebugStepper cancelar el último comando de paso que recibió.</span><span class="sxs-lookup"><span data-stu-id="bf077-103">Causes this ICorDebugStepper to cancel the last step command that it received.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bf077-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="bf077-104">Syntax</span></span>  
  
```  
HRESULT Deactivate ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="bf077-105">Comentarios</span><span class="sxs-lookup"><span data-stu-id="bf077-105">Remarks</span></span>  
 <span data-ttu-id="bf077-106">Después de que se ha cancelado el comando de paso recibido más recientemente, se puede emitir un nuevo comando de ejecución paso a paso.</span><span class="sxs-lookup"><span data-stu-id="bf077-106">A new stepping command may be issued after the most recently received step command has been canceled.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bf077-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="bf077-107">Requirements</span></span>  
 <span data-ttu-id="bf077-108">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bf077-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bf077-109">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="bf077-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="bf077-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bf077-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bf077-111">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bf077-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
