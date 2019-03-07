---
title: ICorDebugBlockingObjectEnum::Next (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugBlockingObjectEnum.Next Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugBlockingObjectEnum::Next
helpviewer_keywords:
- Next method, ICorDebugBlockingObjectEnum interface [.NET Framework debugging]
- ICorDebugBlockingObjectEnum::Next method [.NET Framework debugging]
ms.assetid: 0121753f-ebea-48d0-aeb2-ed7fda76dc60
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ccab0f311e51c0e82998b58f75f38359271065e3
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57493146"
---
# <a name="icordebugblockingobjectenumnext-method"></a><span data-ttu-id="f0cf6-102">ICorDebugBlockingObjectEnum::Next (Método)</span><span class="sxs-lookup"><span data-stu-id="f0cf6-102">ICorDebugBlockingObjectEnum::Next Method</span></span>
<span data-ttu-id="f0cf6-103">Obtiene el número especificado de [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) objetos de la enumeración, comenzando en la posición actual.</span><span class="sxs-lookup"><span data-stu-id="f0cf6-103">Gets the specified number of [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) objects from the enumeration, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f0cf6-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f0cf6-104">Syntax</span></span>  
  
```  
HRESULT Next([in] ULONG  celt,  
             [out, size_is(celt), length_is(*pceltFetched)]  
                           CorDebugBlockingObject values[],  
             [out] ULONG *pceltFetched;  
```  
  
## <a name="parameters"></a><span data-ttu-id="f0cf6-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f0cf6-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="f0cf6-106">[in] El número de objetos que se va a recuperar.</span><span class="sxs-lookup"><span data-stu-id="f0cf6-106">[in] The number of objects to retrieve.</span></span>  
  
 `values`  
 <span data-ttu-id="f0cf6-107">[out] Una matriz de punteros a [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) objetos.</span><span class="sxs-lookup"><span data-stu-id="f0cf6-107">[out] An array of pointers to [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) objects.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="f0cf6-108">[out] Un puntero al número de objetos que se recuperaron.</span><span class="sxs-lookup"><span data-stu-id="f0cf6-108">[out] A pointer to the number of objects that were retrieved.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f0cf6-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="f0cf6-109">Return Value</span></span>  
 <span data-ttu-id="f0cf6-110">Este método devuelve los siguientes HRESULT concretos.</span><span class="sxs-lookup"><span data-stu-id="f0cf6-110">This method returns the following specific HRESULTs.</span></span>  
  
|<span data-ttu-id="f0cf6-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="f0cf6-111">HRESULT</span></span>|<span data-ttu-id="f0cf6-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="f0cf6-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="f0cf6-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="f0cf6-113">S_OK</span></span>|<span data-ttu-id="f0cf6-114">El método se completó correctamente.</span><span class="sxs-lookup"><span data-stu-id="f0cf6-114">The method completed successfully.</span></span>|  
|<span data-ttu-id="f0cf6-115">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="f0cf6-115">S_FALSE</span></span>|<span data-ttu-id="f0cf6-116">`pceltFetched` no es igual a `celt`.</span><span class="sxs-lookup"><span data-stu-id="f0cf6-116">`pceltFetched` does not equal `celt`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f0cf6-117">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f0cf6-117">Remarks</span></span>  
 <span data-ttu-id="f0cf6-118">Este método funciona como un enumerador COM típico.</span><span class="sxs-lookup"><span data-stu-id="f0cf6-118">This method functions like a typical COM enumerator.</span></span>  
  
 <span data-ttu-id="f0cf6-119">Los valores de la matriz de entrada deben ser al menos del tamaño `celt`.</span><span class="sxs-lookup"><span data-stu-id="f0cf6-119">The input array values must be at least of size `celt`.</span></span> <span data-ttu-id="f0cf6-120">La matriz se rellenará con cualquiera siguiente `celt` si hay menos de los valores de la enumeración o con todos los valores restantes `celt` permanecen.</span><span class="sxs-lookup"><span data-stu-id="f0cf6-120">The array will be filled with either the next `celt` values in the enumeration or with all remaining values if fewer than `celt` remain.</span></span> <span data-ttu-id="f0cf6-121">Cuando este método finaliza, `pceltFetched` se rellenará con el número de valores que se recuperaron.</span><span class="sxs-lookup"><span data-stu-id="f0cf6-121">When this method returns, `pceltFetched` will be filled with the number of values that were retrieved.</span></span> <span data-ttu-id="f0cf6-122">Si `values` contiene punteros no válidos o apunta a un búfer que es menor que `celt`, o si `pceltFetched` es un puntero no válido, el resultado es indefinido.</span><span class="sxs-lookup"><span data-stu-id="f0cf6-122">If `values` contains invalid pointers or points to a buffer that is smaller than `celt`, or if `pceltFetched` is an invalid pointer, the result is undefined.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f0cf6-123">Aunque el [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) estructura no tiene que liberarse, debe ser liberado la interfaz "ICorDebugValue" dentro de él.</span><span class="sxs-lookup"><span data-stu-id="f0cf6-123">Although the [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) structure does not need to be released, the "ICorDebugValue" interface inside of it does need to be released.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f0cf6-124">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f0cf6-124">Requirements</span></span>  
 <span data-ttu-id="f0cf6-125">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f0cf6-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f0cf6-126">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f0cf6-126">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f0cf6-127">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f0cf6-127">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f0cf6-128">**Versiones de .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f0cf6-128">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f0cf6-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="f0cf6-129">See also</span></span>
- [<span data-ttu-id="f0cf6-130">ICorDebugDataTarget (interfaz)</span><span class="sxs-lookup"><span data-stu-id="f0cf6-130">ICorDebugDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md)
- [<span data-ttu-id="f0cf6-131">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="f0cf6-131">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="f0cf6-132">Depuración</span><span class="sxs-lookup"><span data-stu-id="f0cf6-132">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
