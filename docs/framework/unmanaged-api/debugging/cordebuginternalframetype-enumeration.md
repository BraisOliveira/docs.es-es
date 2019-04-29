---
title: CorDebugInternalFrameType (Enumeración)
ms.date: 03/30/2017
api_name:
- CorDebugInternalFrameType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugInternalFrameType
helpviewer_keywords:
- CorDebugInternalFrameType enumeration [.NET Framework debugging]
ms.assetid: e4412dc2-c338-4cfb-94d8-f682095dd2b1
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 05184ceb3b32eb003951fff5cfdfbfb813992552
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61792891"
---
# <a name="cordebuginternalframetype-enumeration"></a><span data-ttu-id="05e82-102">CorDebugInternalFrameType (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="05e82-102">CorDebugInternalFrameType Enumeration</span></span>
<span data-ttu-id="05e82-103">Identifica el tipo de marco de pila.</span><span class="sxs-lookup"><span data-stu-id="05e82-103">Identifies the type of stack frame.</span></span> <span data-ttu-id="05e82-104">Esta enumeración se utiliza en el [ICorDebugInternalFrame:: GetFrameType](../../../../docs/framework/unmanaged-api/debugging/icordebuginternalframe-getframetype-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="05e82-104">This enumeration is used by the [ICorDebugInternalFrame::GetFrameType](../../../../docs/framework/unmanaged-api/debugging/icordebuginternalframe-getframetype-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="05e82-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="05e82-105">Syntax</span></span>  
  
```  
typedef enum CorDebugInternalFrameType {  
  
    STUBFRAME_NONE                 = 0x00000000,  
    STUBFRAME_M2U                  = 0x00000001,  
    STUBFRAME_U2M                  = 0x00000002,  
    STUBFRAME_APPDOMAIN_TRANSITION = 0x00000003,  
    STUBFRAME_LIGHTWEIGHT_FUNCTION = 0x00000004,  
    STUBFRAME_FUNC_EVAL            = 0x00000005,  
    STUBFRAME_INTERNALCALL         = 0x00000006,  
    STUBFRAME_CLASS_INIT           = 0x00000007,  
    STUBFRAME_EXCEPTION            = 0x00000008,  
    STUBFRAME_SECURITY             = 0x00000009,  
    STUBFRAME_JIT_COMPILATION     = 0x0000000a,  
} CorDebugInternalFrameType;  
```  
  
## <a name="members"></a><span data-ttu-id="05e82-106">Miembros</span><span class="sxs-lookup"><span data-stu-id="05e82-106">Members</span></span>  
  
|<span data-ttu-id="05e82-107">Miembro</span><span class="sxs-lookup"><span data-stu-id="05e82-107">Member</span></span>|<span data-ttu-id="05e82-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="05e82-108">Description</span></span>|  
|------------|-----------------|  
|`STUBFRAME_NONE`|<span data-ttu-id="05e82-109">Un valor cero.</span><span class="sxs-lookup"><span data-stu-id="05e82-109">A null value.</span></span> <span data-ttu-id="05e82-110">El `ICorDebugInternalFrame::GetFrameType` método nunca devuelve este valor.</span><span class="sxs-lookup"><span data-stu-id="05e82-110">The `ICorDebugInternalFrame::GetFrameType` method never returns this value.</span></span>|  
|`STUBFRAME_M2U`|<span data-ttu-id="05e82-111">Un marco de código auxiliar a administrado.</span><span class="sxs-lookup"><span data-stu-id="05e82-111">A managed-to-unmanaged stub frame.</span></span>|  
|`STUBFRAME_U2M`|<span data-ttu-id="05e82-112">Un marco de código auxiliar no administrado a administrado.</span><span class="sxs-lookup"><span data-stu-id="05e82-112">An unmanaged-to-managed stub frame.</span></span>|  
|`STUBFRAME_APPDOMAIN_TRANSITION`|<span data-ttu-id="05e82-113">Una transición entre los dominios de aplicación.</span><span class="sxs-lookup"><span data-stu-id="05e82-113">A transition between application domains.</span></span>|  
|`STUBFRAME_LIGHTWEIGHT_FUNCTION`|<span data-ttu-id="05e82-114">Una llamada de método ligero.</span><span class="sxs-lookup"><span data-stu-id="05e82-114">A lightweight method call.</span></span>|  
|`STUBFRAME_FUNC_EVAL`|<span data-ttu-id="05e82-115">Inicio de la evaluación de función.</span><span class="sxs-lookup"><span data-stu-id="05e82-115">The start of function evaluation.</span></span>|  
|`STUBFRAME_INTERNALCALL`|<span data-ttu-id="05e82-116">Una llamada interna en common language runtime.</span><span class="sxs-lookup"><span data-stu-id="05e82-116">An internal call into the common language runtime.</span></span>|  
|`STUBFRAME_CLASS_INIT`|<span data-ttu-id="05e82-117">Inicio de la inicialización de una clase.</span><span class="sxs-lookup"><span data-stu-id="05e82-117">The start of a class initialization.</span></span>|  
|`STUBFRAME_EXCEPTION`|<span data-ttu-id="05e82-118">Una excepción que se produce.</span><span class="sxs-lookup"><span data-stu-id="05e82-118">An exception that is thrown.</span></span>|  
|`STUBFRAME_SECURITY`|<span data-ttu-id="05e82-119">Un marco que se usa para la seguridad de acceso del código.</span><span class="sxs-lookup"><span data-stu-id="05e82-119">A frame used for code access security.</span></span>|  
|`STUBFRAME_JIT_COMPILATION`|<span data-ttu-id="05e82-120">El tiempo de ejecución es un método de compilación JIT.</span><span class="sxs-lookup"><span data-stu-id="05e82-120">The runtime is JIT-compiling a method.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="05e82-121">Requisitos</span><span class="sxs-lookup"><span data-stu-id="05e82-121">Requirements</span></span>  
 <span data-ttu-id="05e82-122">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="05e82-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="05e82-123">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="05e82-123">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="05e82-124">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="05e82-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="05e82-125">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="05e82-125">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="05e82-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="05e82-126">See also</span></span>

- [<span data-ttu-id="05e82-127">Enumeraciones de depuración</span><span class="sxs-lookup"><span data-stu-id="05e82-127">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
