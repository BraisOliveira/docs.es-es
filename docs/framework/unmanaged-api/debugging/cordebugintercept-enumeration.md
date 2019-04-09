---
title: CorDebugIntercept (Enumeración)
ms.date: 03/30/2017
api_name:
- CorDebugIntercept
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugIntercept
helpviewer_keywords:
- CorDebugIntercept enumeration [.NET Framework debugging]
ms.assetid: 3d5b642e-7ef2-428b-a5ae-509c35ed461a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0791a59e0325668960dcfc98816920db55bcfb87
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59199939"
---
# <a name="cordebugintercept-enumeration"></a><span data-ttu-id="801ab-102">CorDebugIntercept (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="801ab-102">CorDebugIntercept Enumeration</span></span>
<span data-ttu-id="801ab-103">Indica los tipos de código que se pueden interceptar, es decir, ejecutar paso a paso.</span><span class="sxs-lookup"><span data-stu-id="801ab-103">Indicates the types of code that can be intercepted (that is, stepped into).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="801ab-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="801ab-104">Syntax</span></span>  
  
```  
typedef enum CorDebugIntercept {  
    INTERCEPT_NONE                = 0x0,  
    INTERCEPT_CLASS_INIT          = 0x01,  
    INTERCEPT_EXCEPTION_FILTER    = 0x02,  
    INTERCEPT_SECURITY            = 0x04,  
    INTERCEPT_CONTEXT_POLICY      = 0x08,  
    INTERCEPT_INTERCEPTION        = 0x10,  
    INTERCEPT_ALL                 = 0xffff  
} CorDebugIntercept;  
```  
  
## <a name="members"></a><span data-ttu-id="801ab-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="801ab-105">Members</span></span>  
  
|<span data-ttu-id="801ab-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="801ab-106">Member</span></span>|<span data-ttu-id="801ab-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="801ab-107">Description</span></span>|  
|------------|-----------------|  
|`INTERCEPT_NONE`|<span data-ttu-id="801ab-108">No se puede interceptar ningún código.</span><span class="sxs-lookup"><span data-stu-id="801ab-108">No code can be intercepted.</span></span>|  
|`INTERCEPT_CLASS_INIT`|<span data-ttu-id="801ab-109">Se puede interceptar un constructor.</span><span class="sxs-lookup"><span data-stu-id="801ab-109">A constructor can be intercepted.</span></span>|  
|`INTERCEPT_EXCEPTION_FILTER`|<span data-ttu-id="801ab-110">Se puede interceptar un filtro de excepción.</span><span class="sxs-lookup"><span data-stu-id="801ab-110">An exception filter can be intercepted.</span></span>|  
|`INTERCEPT_SECURITY`|<span data-ttu-id="801ab-111">Se puede interceptar código que exija seguridad.</span><span class="sxs-lookup"><span data-stu-id="801ab-111">Code that enforces security can be intercepted.</span></span>|  
|`INTERCEPT_CONTEXT_POLICY`|<span data-ttu-id="801ab-112">Se puede interceptar una directiva de contexto.</span><span class="sxs-lookup"><span data-stu-id="801ab-112">A context policy can be intercepted.</span></span>|  
|`INTERCEPT_INTERCEPTION`|<span data-ttu-id="801ab-113">No se utiliza.</span><span class="sxs-lookup"><span data-stu-id="801ab-113">Not used.</span></span>|  
|`INTERCEPT_ALL`|<span data-ttu-id="801ab-114">Se puede interceptar todo el código.</span><span class="sxs-lookup"><span data-stu-id="801ab-114">All code can be intercepted.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="801ab-115">Comentarios</span><span class="sxs-lookup"><span data-stu-id="801ab-115">Remarks</span></span>  
 <span data-ttu-id="801ab-116">Use la [SetInterceptMask](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setinterceptmask-method.md) método para establecer los tipos de código que se pueden interceptar.</span><span class="sxs-lookup"><span data-stu-id="801ab-116">Use the [ICorDebugStepper::SetInterceptMask](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setinterceptmask-method.md) method to establish the types of code that can be intercepted.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="801ab-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="801ab-117">Requirements</span></span>  
 <span data-ttu-id="801ab-118">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="801ab-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="801ab-119">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="801ab-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="801ab-120">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="801ab-120">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="801ab-121">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="801ab-121">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="801ab-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="801ab-122">See also</span></span>

- [<span data-ttu-id="801ab-123">Enumeraciones de depuración</span><span class="sxs-lookup"><span data-stu-id="801ab-123">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
