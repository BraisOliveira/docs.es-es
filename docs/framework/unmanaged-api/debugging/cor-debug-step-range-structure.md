---
title: COR_DEBUG_STEP_RANGE (Estructura)
ms.date: 03/30/2017
api_name:
- COR_DEBUG_STEP_RANGE
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- COR_DEBUG_STEP_RANGE
helpviewer_keywords:
- COR_DEBUG_STEP_RANGE structure [.NET Framework debugging]
ms.assetid: 8809d00e-beaa-4dcf-b4e8-e89d0a5406b7
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 57d7c3256d7b52a4e55dbb5bc420b0438983d2f2
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59219686"
---
# <a name="cordebugsteprange-structure"></a><span data-ttu-id="5be3f-102">COR_DEBUG_STEP_RANGE (Estructura)</span><span class="sxs-lookup"><span data-stu-id="5be3f-102">COR_DEBUG_STEP_RANGE Structure</span></span>
<span data-ttu-id="5be3f-103">Contiene información de desplazamiento para un intervalo de código.</span><span class="sxs-lookup"><span data-stu-id="5be3f-103">Contains the offset information for a range of code.</span></span>  
  
 <span data-ttu-id="5be3f-104">Esta estructura se usa por la [ICorDebugStepper:: StepRange](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-steprange-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="5be3f-104">This structure is used by the [ICorDebugStepper::StepRange](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-steprange-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5be3f-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5be3f-105">Syntax</span></span>  
  
```  
typedef struct {  
    ULONG32 startOffset;  
    ULONG32 endOffset;  
} COR_DEBUG_STEP_RANGE;  
```  
  
## <a name="members"></a><span data-ttu-id="5be3f-106">Miembros</span><span class="sxs-lookup"><span data-stu-id="5be3f-106">Members</span></span>  
  
|<span data-ttu-id="5be3f-107">Miembro</span><span class="sxs-lookup"><span data-stu-id="5be3f-107">Member</span></span>|<span data-ttu-id="5be3f-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="5be3f-108">Description</span></span>|  
|------------|-----------------|  
|`startOffset`|<span data-ttu-id="5be3f-109">El desplazamiento del principio del intervalo.</span><span class="sxs-lookup"><span data-stu-id="5be3f-109">The offset of the beginning of the range.</span></span>|  
|`endOffset`|<span data-ttu-id="5be3f-110">El desplazamiento del final del intervalo.</span><span class="sxs-lookup"><span data-stu-id="5be3f-110">The offset of the end of the range.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="5be3f-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5be3f-111">Requirements</span></span>  
 <span data-ttu-id="5be3f-112">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5be3f-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5be3f-113">**Encabezado**: CorDebug.idl</span><span class="sxs-lookup"><span data-stu-id="5be3f-113">**Header:** CorDebug.idl</span></span>  
  
 <span data-ttu-id="5be3f-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5be3f-114">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="5be3f-115">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="5be3f-115">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="5be3f-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="5be3f-116">See also</span></span>

- [<span data-ttu-id="5be3f-117">Método StepRange</span><span class="sxs-lookup"><span data-stu-id="5be3f-117">StepRange Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-steprange-method.md)
- [<span data-ttu-id="5be3f-118">Estructuras de depuración</span><span class="sxs-lookup"><span data-stu-id="5be3f-118">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
- [<span data-ttu-id="5be3f-119">Depuración</span><span class="sxs-lookup"><span data-stu-id="5be3f-119">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
