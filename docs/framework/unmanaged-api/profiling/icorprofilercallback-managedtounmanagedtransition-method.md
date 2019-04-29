---
title: ICorProfilerCallback::ManagedToUnmanagedTransition (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ManagedToUnmanagedTransition
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ManagedToUnmanagedTransition
helpviewer_keywords:
- ManagedToUnmanagedTransition method [.NET Framework profiling]
- ICorProfilerCallback::ManagedToUnmanagedTransition method [.NET Framework profiling]
ms.assetid: ef3cd619-912d-40c5-a449-03ba02a39ee7
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b00394d0b08e7e4a02b95437908dd65a51d0a042
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61597679"
---
# <a name="icorprofilercallbackmanagedtounmanagedtransition-method"></a><span data-ttu-id="9091e-102">ICorProfilerCallback::ManagedToUnmanagedTransition (Método)</span><span class="sxs-lookup"><span data-stu-id="9091e-102">ICorProfilerCallback::ManagedToUnmanagedTransition Method</span></span>
<span data-ttu-id="9091e-103">Notifica al generador de perfiles que se ha producido una transición desde código administrado a código no administrado.</span><span class="sxs-lookup"><span data-stu-id="9091e-103">Notifies the profiler that a transition from managed code to unmanaged code has occurred.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9091e-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9091e-104">Syntax</span></span>  
  
```  
HRESULT ManagedToUnmanagedTransition(  
    [in] FunctionID functionId,  
    [in] COR_PRF_TRANSITION_REASON reason);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9091e-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="9091e-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="9091e-106">[in] El identificador de la función que se llama.</span><span class="sxs-lookup"><span data-stu-id="9091e-106">[in] The ID of the function that is being called.</span></span>  
  
 `reason`  
 <span data-ttu-id="9091e-107">[in] Un valor de la [COR_PRF_TRANSITION_REASON](../../../../docs/framework/unmanaged-api/profiling/cor-prf-transition-reason-enumeration.md) enumeración que indica si la transición se produjo debido a una llamada a código no administrado desde código administrado, o debido a una devolución de una función administrada llamada por una no administrada.</span><span class="sxs-lookup"><span data-stu-id="9091e-107">[in] A value of the [COR_PRF_TRANSITION_REASON](../../../../docs/framework/unmanaged-api/profiling/cor-prf-transition-reason-enumeration.md) enumeration that indicates whether the transition occurred because of a call into unmanaged code from managed code, or because of a return from a managed function called by an unmanaged one.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9091e-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="9091e-108">Remarks</span></span>  
 <span data-ttu-id="9091e-109">Si el valor de `reason` es COR_PRF_TRANSITION_CALL, la función ID es que de la función no administrada, que nunca habrá sido compilado mediante el compilador just-in-time.</span><span class="sxs-lookup"><span data-stu-id="9091e-109">If the value of `reason` is COR_PRF_TRANSITION_CALL, the function ID is that of the unmanaged function, which will never have been compiled using the just-in-time compiler.</span></span> <span data-ttu-id="9091e-110">Funciones no administradas tengan asociada con ellos, como el nombre y algunos metadatos de información básica.</span><span class="sxs-lookup"><span data-stu-id="9091e-110">Unmanaged functions have basic information associated with them, such as a name and some metadata.</span></span> <span data-ttu-id="9091e-111">Si se llamó a la función no administrada mediante el uso de implícita de plataforma (PInvoke) de invocación, el tiempo de ejecución no puede determinar el destino de la llamada y el valor de `functionId` será null.</span><span class="sxs-lookup"><span data-stu-id="9091e-111">If the unmanaged function was called by using implicit platform invoke (PInvoke), the runtime cannot determine the destination of the call and the value of `functionId` will be null.</span></span> <span data-ttu-id="9091e-112">Para obtener más información sobre PInvoke implícito, consulte [utilizando interoperabilidad de C++ (PInvoke implícito)](/cpp/dotnet/using-cpp-interop-implicit-pinvoke).</span><span class="sxs-lookup"><span data-stu-id="9091e-112">For more information on implicit PInvoke, see [Using C++ Interop (Implicit PInvoke)](/cpp/dotnet/using-cpp-interop-implicit-pinvoke).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9091e-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9091e-113">Requirements</span></span>  
 <span data-ttu-id="9091e-114">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9091e-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9091e-115">**Encabezado**: CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="9091e-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="9091e-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9091e-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9091e-117">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9091e-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9091e-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="9091e-118">See also</span></span>

- [<span data-ttu-id="9091e-119">ICorProfilerCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="9091e-119">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="9091e-120">UnmanagedToManagedTransition (método)</span><span class="sxs-lookup"><span data-stu-id="9091e-120">UnmanagedToManagedTransition Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-unmanagedtomanagedtransition-method.md)
- [<span data-ttu-id="9091e-121">Usar un elemento PInvoke explícito en C++ (Atributo DllImport)</span><span class="sxs-lookup"><span data-stu-id="9091e-121">Using Explicit PInvoke in C++ (DllImport Attribute)</span></span>](/cpp/dotnet/using-explicit-pinvoke-in-cpp-dllimport-attribute)
