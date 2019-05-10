---
title: FunctionLeave (Función)
ms.date: 03/30/2017
api_name:
- FunctionLeave
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- FunctionLeave
helpviewer_keywords:
- FunctionLeave function [.NET Framework profiling]
ms.assetid: 18e89f45-e068-426a-be16-9f53a4346860
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 412a01dc1dd498c2f55307958e5feec36a556b9c
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64586918"
---
# <a name="functionleave-function"></a><span data-ttu-id="732a0-102">FunctionLeave (Función)</span><span class="sxs-lookup"><span data-stu-id="732a0-102">FunctionLeave Function</span></span>
<span data-ttu-id="732a0-103">Notifica al generador de perfiles que una función está a punto de devolver al llamador.</span><span class="sxs-lookup"><span data-stu-id="732a0-103">Notifies the profiler that a function is about to return to the caller.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="732a0-104">El `FunctionLeave` función está en desuso en .NET Framework 2.0.</span><span class="sxs-lookup"><span data-stu-id="732a0-104">The `FunctionLeave` function is deprecated in the .NET Framework 2.0.</span></span> <span data-ttu-id="732a0-105">Seguirán funcionando, pero se incurrirá en una penalización de rendimiento.</span><span class="sxs-lookup"><span data-stu-id="732a0-105">It will continue to work, but will incur a performance penalty.</span></span> <span data-ttu-id="732a0-106">Use la [FunctionLeave2](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md) funcione en su lugar.</span><span class="sxs-lookup"><span data-stu-id="732a0-106">Use the [FunctionLeave2](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md) function instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="732a0-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="732a0-107">Syntax</span></span>  
  
```  
void __stdcall FunctionLeave (  
    [in] FunctionID funcID  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="732a0-108">Parámetros</span><span class="sxs-lookup"><span data-stu-id="732a0-108">Parameters</span></span>  
 `funcID`  
 <span data-ttu-id="732a0-109">[in] El identificador de la función que devuelve.</span><span class="sxs-lookup"><span data-stu-id="732a0-109">[in] The identifier of the function that is returning.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="732a0-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="732a0-110">Remarks</span></span>  
 <span data-ttu-id="732a0-111">El `FunctionLeave` función es una devolución de llamada; debe implementar.</span><span class="sxs-lookup"><span data-stu-id="732a0-111">The `FunctionLeave` function is a callback; you must implement it.</span></span> <span data-ttu-id="732a0-112">La implementación debe usar el `__declspec`(`naked`) el atributo de clase de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="732a0-112">The implementation must use the `__declspec`(`naked`) storage-class attribute.</span></span>  
  
 <span data-ttu-id="732a0-113">El motor de ejecución no guarda ningún registro antes de llamar a esta función.</span><span class="sxs-lookup"><span data-stu-id="732a0-113">The execution engine does not save any registers before calling this function.</span></span>  
  
- <span data-ttu-id="732a0-114">En la entrada, debe guardar todos los registros que utilice, incluidos los de la unidad de punto flotante (FPU).</span><span class="sxs-lookup"><span data-stu-id="732a0-114">On entry, you must save all registers that you use, including those in the floating-point unit (FPU).</span></span>  
  
- <span data-ttu-id="732a0-115">En la salida, debe restaurar la pila debe extraer todos los parámetros que se insertaron su llamador.</span><span class="sxs-lookup"><span data-stu-id="732a0-115">On exit, you must restore the stack by popping off all the parameters that were pushed by its caller.</span></span>  
  
 <span data-ttu-id="732a0-116">La implementación de `FunctionLeave` no debe bloquearse porque retrasará la recolección de elementos.</span><span class="sxs-lookup"><span data-stu-id="732a0-116">The implementation of `FunctionLeave` should not block because it will delay garbage collection.</span></span> <span data-ttu-id="732a0-117">La implementación no debe intentar una recolección porque la pila no puede estar en un estado compatible con la colección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="732a0-117">The implementation should not attempt a garbage collection because the stack may not be in a garbage collection-friendly state.</span></span> <span data-ttu-id="732a0-118">Si se intenta realizar una recolección, el tiempo de ejecución se bloqueará hasta que `FunctionLeave` devuelve.</span><span class="sxs-lookup"><span data-stu-id="732a0-118">If a garbage collection is attempted, the runtime will block until `FunctionLeave` returns.</span></span>  
  
 <span data-ttu-id="732a0-119">Además, el `FunctionLeave` función no debe llamar a código administrado o en modo alguno provocar una asignación de memoria administrada.</span><span class="sxs-lookup"><span data-stu-id="732a0-119">Also, the `FunctionLeave` function must not call into managed code or in any way cause a managed memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="732a0-120">Requisitos</span><span class="sxs-lookup"><span data-stu-id="732a0-120">Requirements</span></span>  
 <span data-ttu-id="732a0-121">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="732a0-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="732a0-122">**Encabezado**: CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="732a0-122">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="732a0-123">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="732a0-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="732a0-124">**Versiones de .NET framework:** 1.1, 1.0</span><span class="sxs-lookup"><span data-stu-id="732a0-124">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="732a0-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="732a0-125">See also</span></span>

- [<span data-ttu-id="732a0-126">FunctionEnter2 (Función)</span><span class="sxs-lookup"><span data-stu-id="732a0-126">FunctionEnter2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md)
- [<span data-ttu-id="732a0-127">FunctionLeave2 (Función)</span><span class="sxs-lookup"><span data-stu-id="732a0-127">FunctionLeave2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md)
- [<span data-ttu-id="732a0-128">FunctionTailcall2 (Función)</span><span class="sxs-lookup"><span data-stu-id="732a0-128">FunctionTailcall2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md)
- [<span data-ttu-id="732a0-129">SetEnterLeaveFunctionHooks2 (método)</span><span class="sxs-lookup"><span data-stu-id="732a0-129">SetEnterLeaveFunctionHooks2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md)
- [<span data-ttu-id="732a0-130">Funciones estáticas globales para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="732a0-130">Profiling Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
