---
title: Interfaz ICorDebugDebugEvent
ms.date: 03/30/2017
ms.assetid: a226737a-cb99-4e97-bd94-9a37094ded41
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 013cdfbb6a2904e60d6f7b4df6d40e3d65606fcd
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64606815"
---
# <a name="icordebugdebugevent-interface"></a><span data-ttu-id="e61f5-102">Interfaz ICorDebugDebugEvent</span><span class="sxs-lookup"><span data-stu-id="e61f5-102">ICorDebugDebugEvent Interface</span></span>
<span data-ttu-id="e61f5-103">Define la interfaz base de la que derivan todos los eventos de depuración `ICorDebug`.</span><span class="sxs-lookup"><span data-stu-id="e61f5-103">Defines the base interface from which all `ICorDebug` debug events derive.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e61f5-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="e61f5-104">Methods</span></span>  
  
|<span data-ttu-id="e61f5-105">Método</span><span class="sxs-lookup"><span data-stu-id="e61f5-105">Method</span></span>|<span data-ttu-id="e61f5-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="e61f5-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e61f5-107">GetEventKind (método)</span><span class="sxs-lookup"><span data-stu-id="e61f5-107">GetEventKind Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-geteventkind-method.md)|<span data-ttu-id="e61f5-108">Indica el tipo de evento que este objeto `ICorDebugDebugEvent` representa.</span><span class="sxs-lookup"><span data-stu-id="e61f5-108">Indicates what kind of event this `ICorDebugDebugEvent` object represents.</span></span>|  
|[<span data-ttu-id="e61f5-109">GetThread (método)</span><span class="sxs-lookup"><span data-stu-id="e61f5-109">GetThread Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-getthread-method.md)|<span data-ttu-id="e61f5-110">Obtiene el subproceso en el que se produjo el evento.</span><span class="sxs-lookup"><span data-stu-id="e61f5-110">Gets the thread on which the event occurred.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e61f5-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e61f5-111">Remarks</span></span>  
 <span data-ttu-id="e61f5-112">Las interfaces siguientes derivan de la interfaz `ICorDebugDebugEvent`:</span><span class="sxs-lookup"><span data-stu-id="e61f5-112">The following interfaces are derived from the `ICorDebugDebugEvent` interface:</span></span>  
  
- [<span data-ttu-id="e61f5-113">ICorDebugExceptionDebugEvent</span><span class="sxs-lookup"><span data-stu-id="e61f5-113">ICorDebugExceptionDebugEvent</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptiondebugevent-interface.md)  
  
- [<span data-ttu-id="e61f5-114">ICorDebugModuleDebugEvent</span><span class="sxs-lookup"><span data-stu-id="e61f5-114">ICorDebugModuleDebugEvent</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmoduledebugevent-interface.md)  
  
> [!NOTE]
>  <span data-ttu-id="e61f5-115">La interfaz solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="e61f5-115">The interface is available with .NET Native only.</span></span> <span data-ttu-id="e61f5-116">Al intentar llamar a `QueryInterface` para recuperar un puntero a interfaz, devuelve `E_NOINTERFACE` para escenarios de ICorDebug fuera de .NET nativo.</span><span class="sxs-lookup"><span data-stu-id="e61f5-116">Attempting to call `QueryInterface` to retrieve an interface pointer returns `E_NOINTERFACE` for ICorDebug scenarios outside of .NET Native.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e61f5-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e61f5-117">Requirements</span></span>  
 <span data-ttu-id="e61f5-118">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e61f5-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e61f5-119">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e61f5-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e61f5-120">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e61f5-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e61f5-121">**Versiones de .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e61f5-121">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e61f5-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="e61f5-122">See also</span></span>

- [<span data-ttu-id="e61f5-123">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="e61f5-123">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="e61f5-124">Depuración</span><span class="sxs-lookup"><span data-stu-id="e61f5-124">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
