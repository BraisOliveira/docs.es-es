---
title: LoggingLevelEnum (Enumeración)
ms.date: 03/30/2017
api_name:
- LoggingLevelEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- LoggingLevelEnum
helpviewer_keywords:
- LoggingLevelEnum enumeration [.NET Framework debugging]
ms.assetid: 09daac08-005a-46b2-beab-408d0820c5e5
topic_type:
- apiref
ms.openlocfilehash: 01e1eafd9955a0876f77e34eb73c2a3fc6d815c2
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73139204"
---
# <a name="logginglevelenum-enumeration"></a><span data-ttu-id="7ebdc-102">LoggingLevelEnum (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="7ebdc-102">LoggingLevelEnum Enumeration</span></span>
<span data-ttu-id="7ebdc-103">Indica el nivel de gravedad de un mensaje descriptivo que se escribe en el registro de eventos cuando un subproceso administrado registra un evento.</span><span class="sxs-lookup"><span data-stu-id="7ebdc-103">Indicates the severity level of a descriptive message that is written to the event log when a managed thread logs an event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7ebdc-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7ebdc-104">Syntax</span></span>  
  
```cpp  
typedef enum LoggingLevelEnum {  
    LTraceLevel0 = 0,  
    LTraceLevel1,  
    LTraceLevel2,  
    LTraceLevel3,  
    LTraceLevel4,  
    LStatusLevel0 = 20,  
    LStatusLevel1,  
    LStatusLevel2,  
    LStatusLevel3,  
    LStatusLevel4,  
    LWarningLevel = 40,  
    LErrorLevel = 50,  
    LPanicLevel = 100  
} LoggingLevelEnum;  
```  
  
## <a name="members"></a><span data-ttu-id="7ebdc-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="7ebdc-105">Members</span></span>  
  
|<span data-ttu-id="7ebdc-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="7ebdc-106">Member</span></span>|<span data-ttu-id="7ebdc-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="7ebdc-107">Description</span></span>|  
|------------|-----------------|  
|`LTraceLevel0`|<span data-ttu-id="7ebdc-108">El mensaje es un nivel de seguimiento 0.</span><span class="sxs-lookup"><span data-stu-id="7ebdc-108">The message is a trace level 0.</span></span>|  
|`LTraceLevel1`|<span data-ttu-id="7ebdc-109">El mensaje es un nivel de seguimiento 1.</span><span class="sxs-lookup"><span data-stu-id="7ebdc-109">The message is a trace level 1.</span></span>|  
|`LTraceLevel2`|<span data-ttu-id="7ebdc-110">El mensaje es un nivel de seguimiento 2.</span><span class="sxs-lookup"><span data-stu-id="7ebdc-110">The message is a trace level 2.</span></span>|  
|`LTraceLevel3`|<span data-ttu-id="7ebdc-111">El mensaje es un nivel de seguimiento 3.</span><span class="sxs-lookup"><span data-stu-id="7ebdc-111">The message is a trace level 3.</span></span>|  
|`LTraceLevel4`|<span data-ttu-id="7ebdc-112">El mensaje es un nivel de seguimiento 4.</span><span class="sxs-lookup"><span data-stu-id="7ebdc-112">The message is a trace level 4.</span></span>|  
|`LStatusLevel0`|<span data-ttu-id="7ebdc-113">El mensaje es un nivel de estado 0.</span><span class="sxs-lookup"><span data-stu-id="7ebdc-113">The message is a status level 0.</span></span>|  
|`LStatusLevel1`|<span data-ttu-id="7ebdc-114">El mensaje es un nivel de estado 1.</span><span class="sxs-lookup"><span data-stu-id="7ebdc-114">The message is a status level 1.</span></span>|  
|`LStatusLevel2`|<span data-ttu-id="7ebdc-115">El mensaje es un nivel de estado 2.</span><span class="sxs-lookup"><span data-stu-id="7ebdc-115">The message is a status level 2.</span></span>|  
|`LStatusLevel3`|<span data-ttu-id="7ebdc-116">El mensaje es un nivel de estado 3.</span><span class="sxs-lookup"><span data-stu-id="7ebdc-116">The message is a status level 3.</span></span>|  
|`LStatusLevel4`|<span data-ttu-id="7ebdc-117">El mensaje es un nivel de estado 4.</span><span class="sxs-lookup"><span data-stu-id="7ebdc-117">The message is a status level 4.</span></span>|  
|`LWarningLevel`|<span data-ttu-id="7ebdc-118">El mensaje es un nivel de advertencia.</span><span class="sxs-lookup"><span data-stu-id="7ebdc-118">The message is a warning level.</span></span>|  
|`LErrorLevel`|<span data-ttu-id="7ebdc-119">El mensaje es un nivel de error.</span><span class="sxs-lookup"><span data-stu-id="7ebdc-119">The message is an error level.</span></span>|  
|`LPanicLevel`|<span data-ttu-id="7ebdc-120">El mensaje es un nivel de pánico.</span><span class="sxs-lookup"><span data-stu-id="7ebdc-120">The message is a panic level.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7ebdc-121">Comentarios</span><span class="sxs-lookup"><span data-stu-id="7ebdc-121">Remarks</span></span>  
 <span data-ttu-id="7ebdc-122">El Common Language Runtime (CLR) llama al método [ICorDebugManagedCallback:: LogMessage](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-logmessage-method.md) para notificar al depurador que un subproceso administrado ha registrado un evento.</span><span class="sxs-lookup"><span data-stu-id="7ebdc-122">The common language runtime (CLR) calls the [ICorDebugManagedCallback::LogMessage](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-logmessage-method.md) method to notify the debugger that a managed thread has logged an event.</span></span> <span data-ttu-id="7ebdc-123">El CLR pasa un valor de la enumeración `LoggingLevelEnum` para indicar el nivel de gravedad del mensaje que el subproceso administrado escribió en el registro de eventos.</span><span class="sxs-lookup"><span data-stu-id="7ebdc-123">The CLR passes a value of the `LoggingLevelEnum` enumeration to indicate the severity level of the message that the managed thread wrote to the event log.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7ebdc-124">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7ebdc-124">Requirements</span></span>  
 <span data-ttu-id="7ebdc-125">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7ebdc-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7ebdc-126">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7ebdc-126">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7ebdc-127">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7ebdc-127">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7ebdc-128">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7ebdc-128">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7ebdc-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="7ebdc-129">See also</span></span>

- <xref:System.Diagnostics.EventLog>
- [<span data-ttu-id="7ebdc-130">Enumeraciones de depuración</span><span class="sxs-lookup"><span data-stu-id="7ebdc-130">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
