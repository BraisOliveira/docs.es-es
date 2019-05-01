---
title: Interfaz ICorDebugModule
ms.date: 03/30/2017
api_name:
- ICorDebugModule
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule
helpviewer_keywords:
- ICorDebugModule interface [.NET Framework debugging]
ms.assetid: 32e4d6fa-e5a3-413e-9166-d5e2871d3114
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 257011562a9ea687ef70b842c6d47219283e158e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61988044"
---
# <a name="icordebugmodule-interface"></a><span data-ttu-id="9bc78-102">Interfaz ICorDebugModule</span><span class="sxs-lookup"><span data-stu-id="9bc78-102">ICorDebugModule Interface</span></span>

<span data-ttu-id="9bc78-103">Representa un módulo de common language runtime (CLR), que es un archivo ejecutable o una biblioteca de vínculos dinámicos (DLL).</span><span class="sxs-lookup"><span data-stu-id="9bc78-103">Represents a common language runtime (CLR) module, which is either an executable file or a dynamic-link library (DLL).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="9bc78-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="9bc78-104">Methods</span></span>  
  
|<span data-ttu-id="9bc78-105">Método</span><span class="sxs-lookup"><span data-stu-id="9bc78-105">Method</span></span>|<span data-ttu-id="9bc78-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="9bc78-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="9bc78-107">CreateBreakpoint (método)</span><span class="sxs-lookup"><span data-stu-id="9bc78-107">CreateBreakpoint Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-createbreakpoint-method.md)|<span data-ttu-id="9bc78-108">Sin implementar.</span><span class="sxs-lookup"><span data-stu-id="9bc78-108">Not implemented.</span></span>|  
|[<span data-ttu-id="9bc78-109">EnableClassLoadCallbacks (método)</span><span class="sxs-lookup"><span data-stu-id="9bc78-109">EnableClassLoadCallbacks Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-enableclassloadcallbacks-method.md)|<span data-ttu-id="9bc78-110">Determina si el [loadClass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadclass-method.md) y [UnloadClass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-unloadclass-method.md) devoluciones de llamada se llaman para este módulo.</span><span class="sxs-lookup"><span data-stu-id="9bc78-110">Determines whether the [ICorDebugManagedCallback::LoadClass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadclass-method.md) and [ICorDebugManagedCallback::UnloadClass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-unloadclass-method.md) callbacks are called for this module.</span></span>|  
|[<span data-ttu-id="9bc78-111">EnableJITDebugging (método)</span><span class="sxs-lookup"><span data-stu-id="9bc78-111">EnableJITDebugging Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-enablejitdebugging-method.md)|<span data-ttu-id="9bc78-112">Determina si el compilador de just-in-time (JIT) conserva la información de depuración para los métodos de este módulo.</span><span class="sxs-lookup"><span data-stu-id="9bc78-112">Determines whether the just-in-time (JIT) compiler preserves debugging information for methods within this module.</span></span>|  
|[<span data-ttu-id="9bc78-113">GetAssembly (método)</span><span class="sxs-lookup"><span data-stu-id="9bc78-113">GetAssembly Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getassembly-method.md)|<span data-ttu-id="9bc78-114">Obtiene el ensamblado que contiene este módulo.</span><span class="sxs-lookup"><span data-stu-id="9bc78-114">Gets the containing assembly for this module.</span></span>|  
|[<span data-ttu-id="9bc78-115">GetBaseAddress (método)</span><span class="sxs-lookup"><span data-stu-id="9bc78-115">GetBaseAddress Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getbaseaddress-method.md)|<span data-ttu-id="9bc78-116">Obtiene la dirección base del módulo.</span><span class="sxs-lookup"><span data-stu-id="9bc78-116">Gets the base address of the module.</span></span>|  
|[<span data-ttu-id="9bc78-117">GetClassFromToken (método)</span><span class="sxs-lookup"><span data-stu-id="9bc78-117">GetClassFromToken Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getclassfromtoken-method.md)|<span data-ttu-id="9bc78-118">Obtiene el ICorDebugClass desde los metadatos.</span><span class="sxs-lookup"><span data-stu-id="9bc78-118">Gets the ICorDebugClass from the metadata.</span></span>|  
|[<span data-ttu-id="9bc78-119">GetEditAndContinueSnapshot (método)</span><span class="sxs-lookup"><span data-stu-id="9bc78-119">GetEditAndContinueSnapshot Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-geteditandcontinuesnapshot-method.md)|<span data-ttu-id="9bc78-120">Desusado.</span><span class="sxs-lookup"><span data-stu-id="9bc78-120">Deprecated.</span></span>|  
|[<span data-ttu-id="9bc78-121">GetFunctionFromRVA (método)</span><span class="sxs-lookup"><span data-stu-id="9bc78-121">GetFunctionFromRVA Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getfunctionfromrva-method.md)|<span data-ttu-id="9bc78-122">Sin implementar.</span><span class="sxs-lookup"><span data-stu-id="9bc78-122">Not implemented.</span></span>|  
|[<span data-ttu-id="9bc78-123">GetFunctionFromToken (método)</span><span class="sxs-lookup"><span data-stu-id="9bc78-123">GetFunctionFromToken Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getfunctionfromtoken-method.md)|<span data-ttu-id="9bc78-124">Obtiene la función especificada por el token de metadatos.</span><span class="sxs-lookup"><span data-stu-id="9bc78-124">Gets the function that is specified by the metadata token.</span></span>|  
|[<span data-ttu-id="9bc78-125">GetGlobalVariableValue (método)</span><span class="sxs-lookup"><span data-stu-id="9bc78-125">GetGlobalVariableValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getglobalvariablevalue-method.md)|<span data-ttu-id="9bc78-126">Obtiene un objeto de valor para la variable global especificada.</span><span class="sxs-lookup"><span data-stu-id="9bc78-126">Gets a value object for the specified global variable.</span></span>|  
|[<span data-ttu-id="9bc78-127">GetMetaDataInterface (método)</span><span class="sxs-lookup"><span data-stu-id="9bc78-127">GetMetaDataInterface Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getmetadatainterface-method.md)|<span data-ttu-id="9bc78-128">Obtiene un puntero de interfaz de metadatos que puede usarse para examinar los metadatos para el módulo.</span><span class="sxs-lookup"><span data-stu-id="9bc78-128">Gets a metadata interface pointer that can be used to examine the metadata for the module.</span></span>|  
|[<span data-ttu-id="9bc78-129">GetName (método)</span><span class="sxs-lookup"><span data-stu-id="9bc78-129">GetName Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getname-method.md)|<span data-ttu-id="9bc78-130">Obtiene el nombre de archivo del módulo.</span><span class="sxs-lookup"><span data-stu-id="9bc78-130">Gets the file name of the module.</span></span>|  
|[<span data-ttu-id="9bc78-131">GetProcess (método)</span><span class="sxs-lookup"><span data-stu-id="9bc78-131">GetProcess Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getprocess-method.md)|<span data-ttu-id="9bc78-132">Obtiene el proceso que contiene este módulo.</span><span class="sxs-lookup"><span data-stu-id="9bc78-132">Gets the containing process for this module.</span></span>|  
|[<span data-ttu-id="9bc78-133">GetSize (método)</span><span class="sxs-lookup"><span data-stu-id="9bc78-133">GetSize Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getsize-method.md)|<span data-ttu-id="9bc78-134">Obtiene el tamaño del módulo en bytes.</span><span class="sxs-lookup"><span data-stu-id="9bc78-134">Gets the size of the module in bytes.</span></span>|  
|[<span data-ttu-id="9bc78-135">GetToken (método)</span><span class="sxs-lookup"><span data-stu-id="9bc78-135">GetToken Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-gettoken-method.md)|<span data-ttu-id="9bc78-136">Obtiene el token para la entrada de tabla para este módulo.</span><span class="sxs-lookup"><span data-stu-id="9bc78-136">Gets the token for the table entry for this module.</span></span>|  
|[<span data-ttu-id="9bc78-137">IsDynamic (método)</span><span class="sxs-lookup"><span data-stu-id="9bc78-137">IsDynamic Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-isdynamic-method.md)|<span data-ttu-id="9bc78-138">Indica si el módulo es dinámico.</span><span class="sxs-lookup"><span data-stu-id="9bc78-138">Indicates whether the module is dynamic.</span></span>|  
|[<span data-ttu-id="9bc78-139">IsInMemory (método)</span><span class="sxs-lookup"><span data-stu-id="9bc78-139">IsInMemory Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-isinmemory-method.md)|<span data-ttu-id="9bc78-140">Indica si este módulo solo existe en memoria.</span><span class="sxs-lookup"><span data-stu-id="9bc78-140">Indicates whether this module exists only in memory.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9bc78-141">Comentarios</span><span class="sxs-lookup"><span data-stu-id="9bc78-141">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9bc78-142">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="9bc78-142">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9bc78-143">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9bc78-143">Requirements</span></span>  
 <span data-ttu-id="9bc78-144">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9bc78-144">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9bc78-145">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9bc78-145">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9bc78-146">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9bc78-146">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9bc78-147">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9bc78-147">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9bc78-148">Vea también</span><span class="sxs-lookup"><span data-stu-id="9bc78-148">See also</span></span>

- [<span data-ttu-id="9bc78-149">ICorDebug (interfaz)</span><span class="sxs-lookup"><span data-stu-id="9bc78-149">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
- [<span data-ttu-id="9bc78-150">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="9bc78-150">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
