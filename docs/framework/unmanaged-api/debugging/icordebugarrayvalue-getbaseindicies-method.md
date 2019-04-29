---
title: ICorDebugArrayValue::GetBaseIndicies (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugArrayValue.GetBaseIndicies
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugArrayValue::GetBaseIndicies
helpviewer_keywords:
- ICorDebugArrayValue::GetBaseIndicies method [.NET Framework debugging]
- GetBaseIndicies method [.NET Framework debugging]
ms.assetid: 868b339b-acdb-4fe0-91c7-b85f4fba99eb
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f24a1434f737e8281a0c68dd09d2e17b34371694
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61786287"
---
# <a name="icordebugarrayvaluegetbaseindicies-method"></a><span data-ttu-id="ecb33-102">ICorDebugArrayValue::GetBaseIndicies (Método)</span><span class="sxs-lookup"><span data-stu-id="ecb33-102">ICorDebugArrayValue::GetBaseIndicies Method</span></span>
<span data-ttu-id="ecb33-103">Obtiene el índice de base de cada dimensión de la matriz.</span><span class="sxs-lookup"><span data-stu-id="ecb33-103">Gets the base index of each dimension in the array.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ecb33-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ecb33-104">Syntax</span></span>  
  
```  
HRESULT GetBaseIndicies (  
    [in] ULONG32          cdim,  
    [out, size_is(cdim), length_is(cdim)]   
        ULONG32           indicies[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ecb33-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ecb33-105">Parameters</span></span>  
 `cdim`  
 <span data-ttu-id="ecb33-106">[in] El número de dimensiones de esta `ICorDebugArrayValue` objeto.</span><span class="sxs-lookup"><span data-stu-id="ecb33-106">[in] The number of dimensions of this `ICorDebugArrayValue` object.</span></span> <span data-ttu-id="ecb33-107">Este valor también es el tamaño de la `indicies` matriz porque su tamaño es igual al número de dimensiones de la `ICorDebugArrayValue` objeto.</span><span class="sxs-lookup"><span data-stu-id="ecb33-107">This value is also the size of the `indicies` array because its size is equal to the number of dimensions of the `ICorDebugArrayValue` object.</span></span>  
  
 `indicies`  
 <span data-ttu-id="ecb33-108">[out] Una matriz de enteros, cada uno de los cuales es el índice de base (es decir, el índice inicial) de una dimensión de este `ICorDebugArrayValue` objeto.</span><span class="sxs-lookup"><span data-stu-id="ecb33-108">[out] An array of integers, each of which is the base index (that is, the starting index) of a dimension of this `ICorDebugArrayValue` object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ecb33-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ecb33-109">Requirements</span></span>  
 <span data-ttu-id="ecb33-110">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ecb33-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ecb33-111">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ecb33-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ecb33-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ecb33-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ecb33-113">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ecb33-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
