---
title: ICorDebugEval::NewArray (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugEval.NewArray
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval::NewArray
helpviewer_keywords:
- NewArray method [.NET Framework debugging]
- ICorDebugEval::NewArray method [.NET Framework debugging]
ms.assetid: cc79a67d-5368-434d-a943-209db90491b9
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d1abe307e3b9fa607912f98e456a11176eb17c56
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57471516"
---
# <a name="icordebugevalnewarray-method"></a><span data-ttu-id="3fc6e-102">ICorDebugEval::NewArray (Método)</span><span class="sxs-lookup"><span data-stu-id="3fc6e-102">ICorDebugEval::NewArray Method</span></span>
<span data-ttu-id="3fc6e-103">Asigna una nueva matriz del tipo de elemento especificado y las dimensiones.</span><span class="sxs-lookup"><span data-stu-id="3fc6e-103">Allocates a new array of the specified element type and dimensions.</span></span>  
  
 <span data-ttu-id="3fc6e-104">Este método está obsoleto en .NET Framework versión 2.0.</span><span class="sxs-lookup"><span data-stu-id="3fc6e-104">This method is obsolete in the .NET Framework version 2.0.</span></span> <span data-ttu-id="3fc6e-105">Use [ICorDebugEval2:: NewParameterizedArray](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newparameterizedarray-method.md) en su lugar.</span><span class="sxs-lookup"><span data-stu-id="3fc6e-105">Use [ICorDebugEval2::NewParameterizedArray](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newparameterizedarray-method.md) instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3fc6e-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3fc6e-106">Syntax</span></span>  
  
```  
HRESULT NewArray (  
    [in] CorElementType     elementType,  
    [in] ICorDebugClass     *pElementClass,  
    [in] ULONG32            rank,  
    [in, size_is(rank)] ULONG32 dims[],  
    [in, size_is(rank)] ULONG32 lowBounds[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3fc6e-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="3fc6e-107">Parameters</span></span>  
 `elementType`  
 <span data-ttu-id="3fc6e-108">[in] Un valor de la enumeración CorElementType que especifica el tipo de elemento de la matriz.</span><span class="sxs-lookup"><span data-stu-id="3fc6e-108">[in] A value of the CorElementType enumeration that specifies the element type of the array.</span></span>  
  
 `pElementClass`  
 <span data-ttu-id="3fc6e-109">[in] Un puntero a un objeto ICorDebugClass que especifica la clase del elemento.</span><span class="sxs-lookup"><span data-stu-id="3fc6e-109">[in] A pointer to a ICorDebugClass object that specifies the class of the element.</span></span> <span data-ttu-id="3fc6e-110">Este valor puede ser null si el tipo de elemento es un tipo primitivo.</span><span class="sxs-lookup"><span data-stu-id="3fc6e-110">This value may be null if the element type is a primitive type.</span></span>  
  
 `rank`  
 <span data-ttu-id="3fc6e-111">[in] El número de dimensiones de la matriz.</span><span class="sxs-lookup"><span data-stu-id="3fc6e-111">[in] The number of dimensions of the array.</span></span> <span data-ttu-id="3fc6e-112">En .NET Framework 2.0, este valor debe ser 1.</span><span class="sxs-lookup"><span data-stu-id="3fc6e-112">In the .NET Framework 2.0, this value must be 1.</span></span>  
  
 `dims`  
 <span data-ttu-id="3fc6e-113">[in] El tamaño, en bytes, de cada dimensión de la matriz.</span><span class="sxs-lookup"><span data-stu-id="3fc6e-113">[in] The size, in bytes, of each dimension of the array.</span></span>  
  
 `lowBounds`  
 <span data-ttu-id="3fc6e-114">[in] Opcional.</span><span class="sxs-lookup"><span data-stu-id="3fc6e-114">[in] Optional.</span></span> <span data-ttu-id="3fc6e-115">El límite inferior de cada dimensión de la matriz.</span><span class="sxs-lookup"><span data-stu-id="3fc6e-115">The lower bound of each dimension of the array.</span></span> <span data-ttu-id="3fc6e-116">Si este valor se omite, se asume un límite inferior de cero para cada dimensión.</span><span class="sxs-lookup"><span data-stu-id="3fc6e-116">If this value is omitted, a lower bound of zero is assumed for each dimension.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3fc6e-117">Comentarios</span><span class="sxs-lookup"><span data-stu-id="3fc6e-117">Remarks</span></span>  
 <span data-ttu-id="3fc6e-118">La matriz siempre se crea en el dominio de aplicación en el que se está ejecutando el subproceso.</span><span class="sxs-lookup"><span data-stu-id="3fc6e-118">The array is always created in the application domain in which the thread is currently executing.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3fc6e-119">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3fc6e-119">Requirements</span></span>  
 <span data-ttu-id="3fc6e-120">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3fc6e-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3fc6e-121">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3fc6e-121">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3fc6e-122">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3fc6e-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3fc6e-123">**Versiones de .NET framework:** 1.1, 1.0</span><span class="sxs-lookup"><span data-stu-id="3fc6e-123">**.NET Framework Versions:** 1.1, 1.0</span></span>
