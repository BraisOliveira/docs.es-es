---
title: ICorDebugArrayValue::HasBaseIndicies (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugArrayValue.HasBaseIndicies
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugArrayValue::HasBaseIndicies
helpviewer_keywords:
- HasBaseIndicies method [.NET Framework debugging]
- ICorDebugArrayValue::HasBaseIndicies method [.NET Framework debugging]
ms.assetid: aa26df07-e0a6-4608-bdef-d4afafec89aa
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 49f5ed8b24d81ba8f32a9fe0ad7488693718bde9
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61645674"
---
# <a name="icordebugarrayvaluehasbaseindicies-method"></a><span data-ttu-id="5d001-102">ICorDebugArrayValue::HasBaseIndicies (Método)</span><span class="sxs-lookup"><span data-stu-id="5d001-102">ICorDebugArrayValue::HasBaseIndicies Method</span></span>
<span data-ttu-id="5d001-103">Obtiene un valor que indica si las dimensiones de esta matriz tienen un índice base distinto de cero.</span><span class="sxs-lookup"><span data-stu-id="5d001-103">Gets a value that indicates whether any dimensions of this array have a base index of non-zero.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5d001-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5d001-104">Syntax</span></span>  
  
```  
HRESULT HasBaseIndicies (  
    [out] BOOL    *pbHasBaseIndicies  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5d001-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="5d001-105">Parameters</span></span>  
 `pbHasBaseIndicies`  
 <span data-ttu-id="5d001-106">[out] Un puntero a un valor booleano que es `true` si uno o más dimensiones de esta `ICorDebugArrayValue` objeto tiene un índice base distinto de cero; en caso contrario, es el valor booleano `false`.</span><span class="sxs-lookup"><span data-stu-id="5d001-106">[out] A pointer to a Boolean value that is `true` if one or more dimensions of this `ICorDebugArrayValue` object have a base index of non-zero; otherwise, the Boolean value is `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5d001-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5d001-107">Requirements</span></span>  
 <span data-ttu-id="5d001-108">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5d001-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5d001-109">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5d001-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5d001-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5d001-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5d001-111">**Versiones de .NET Framework:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5d001-111">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>
