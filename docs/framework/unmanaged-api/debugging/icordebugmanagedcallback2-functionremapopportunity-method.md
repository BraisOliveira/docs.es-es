---
title: ICorDebugManagedCallback2::FunctionRemapOpportunity (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback2.FunctionRemapOpportunity
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback2::FunctionRemapOpportunity
helpviewer_keywords:
- FunctionRemapOpportunity method [.NET Framework debugging]
- ICorDebugManagedCallback2::FunctionRemapOpportunity method [.NET Framework debugging]
ms.assetid: 0d6471bc-ad9b-4b1d-a307-c10443918863
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a4ab6dac8302d4e03f5d8adad1267f209f131c00
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57476494"
---
# <a name="icordebugmanagedcallback2functionremapopportunity-method"></a><span data-ttu-id="849a8-102">ICorDebugManagedCallback2::FunctionRemapOpportunity (Método)</span><span class="sxs-lookup"><span data-stu-id="849a8-102">ICorDebugManagedCallback2::FunctionRemapOpportunity Method</span></span>
<span data-ttu-id="849a8-103">Notifica al depurador que la ejecución de código ha alcanzado un punto de secuencia en una versión anterior de una función modificada.</span><span class="sxs-lookup"><span data-stu-id="849a8-103">Notifies the debugger that code execution has reached a sequence point in an older version of an edited function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="849a8-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="849a8-104">Syntax</span></span>  
  
```  
HRESULT FunctionRemapOpportunity (  
    [in] ICorDebugAppDomain   *pAppDomain,  
    [in] ICorDebugThread      *pThread,  
    [in] ICorDebugFunction    *pOldFunction,  
    [in] ICorDebugFunction    *pNewFunction,  
    [in] ULONG32              oldILOffset  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="849a8-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="849a8-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="849a8-106">[in] Un puntero a un objeto ICorDebugAppDomain que representa el dominio de aplicación que contiene la función modificada.</span><span class="sxs-lookup"><span data-stu-id="849a8-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain containing the edited function.</span></span>  
  
 `pThread`  
 <span data-ttu-id="849a8-107">[in] Un puntero a un objeto ICorDebugThread que representa el subproceso en el que se encontró el punto de interrupción de reasignación.</span><span class="sxs-lookup"><span data-stu-id="849a8-107">[in] A pointer to an ICorDebugThread object that represents the thread on which the remap breakpoint was encountered.</span></span>  
  
 `pOldFunction`  
 <span data-ttu-id="849a8-108">[in] Un puntero a un objeto ICorDebugFunction que representa la versión de la función que se está ejecutando actualmente en el subproceso.</span><span class="sxs-lookup"><span data-stu-id="849a8-108">[in] A pointer to an ICorDebugFunction object that represents the version of the function that is currently running on the thread.</span></span>  
  
 `pNewFunction`  
 <span data-ttu-id="849a8-109">[in] Un puntero a un objeto ICorDebugFunction que representa la versión más reciente de la función.</span><span class="sxs-lookup"><span data-stu-id="849a8-109">[in] A pointer to an ICorDebugFunction object that represents the latest version of the function.</span></span>  
  
 `oldILOffset`  
 <span data-ttu-id="849a8-110">[in] El desplazamiento de lenguaje intermedio (MSIL) de Microsoft del puntero de instrucción en la versión anterior de la función.</span><span class="sxs-lookup"><span data-stu-id="849a8-110">[in] The Microsoft intermediate language (MSIL) offset of the instruction pointer in the old version of the function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="849a8-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="849a8-111">Remarks</span></span>  
 <span data-ttu-id="849a8-112">Esta devolución de llamada da la oportunidad de reasignar el puntero de instrucción al lugar adecuado en la nueva versión de la función especificada mediante una llamada al depurador el [Icordebugilframe2](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe2-remapfunction-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="849a8-112">This callback gives the debugger an opportunity to remap the instruction pointer to its proper place in the new version of the specified function by calling the [ICorDebugILFrame2::RemapFunction](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe2-remapfunction-method.md) method.</span></span> <span data-ttu-id="849a8-113">Si el depurador no llama a `RemapFunction` antes de llamar a la [ICorDebugController](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) método, el tiempo de ejecución se seguirán ejecutando el código anterior y se activará otro `FunctionRemapOpportunity` devolución de llamada en el siguiente punto de secuencia.</span><span class="sxs-lookup"><span data-stu-id="849a8-113">If the debugger does not call `RemapFunction` before calling the [ICorDebugController::Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) method, the runtime will continue to execute the old code and will fire another `FunctionRemapOpportunity` callback at the next sequence point.</span></span>  
  
 <span data-ttu-id="849a8-114">Esta devolución de llamada se invocará para cada marco que se está ejecutando una versión anterior de la función especificada hasta que el depurador devuelve S_OK.</span><span class="sxs-lookup"><span data-stu-id="849a8-114">This callback will be invoked for every frame that is executing an older version of the given function until the debugger returns S_OK.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="849a8-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="849a8-115">Requirements</span></span>  
 <span data-ttu-id="849a8-116">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="849a8-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="849a8-117">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="849a8-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="849a8-118">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="849a8-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="849a8-119">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="849a8-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="849a8-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="849a8-120">See also</span></span>
- [<span data-ttu-id="849a8-121">ICorDebugManagedCallback2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="849a8-121">ICorDebugManagedCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md)
- [<span data-ttu-id="849a8-122">ICorDebugManagedCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="849a8-122">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
