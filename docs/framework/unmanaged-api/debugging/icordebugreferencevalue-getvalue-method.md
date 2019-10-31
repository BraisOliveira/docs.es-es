---
title: ICorDebugReferenceValue::GetValue (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugReferenceValue.GetValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugReferenceValue::GetValue
helpviewer_keywords:
- GetValue method, ICorDebugReferenceValue interface [.NET Framework debugging]
- ICorDebugReferenceValue::GetValue method [.NET Framework debugging]
ms.assetid: 5da07f99-6c70-46ec-b997-5ab6fb7106cd
topic_type:
- apiref
ms.openlocfilehash: 7a2288eb84bd51795995032954e41525c2ce605a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73137723"
---
# <a name="icordebugreferencevaluegetvalue-method"></a><span data-ttu-id="bed9a-102">ICorDebugReferenceValue::GetValue (Método)</span><span class="sxs-lookup"><span data-stu-id="bed9a-102">ICorDebugReferenceValue::GetValue Method</span></span>
<span data-ttu-id="bed9a-103">Obtiene la dirección de memoria actual del objeto al que se hace referencia.</span><span class="sxs-lookup"><span data-stu-id="bed9a-103">Gets the current memory address of the referenced object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bed9a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="bed9a-104">Syntax</span></span>  
  
```cpp  
HRESULT GetValue (  
    [out] CORDB_ADDRESS   *pValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bed9a-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="bed9a-105">Parameters</span></span>  
 `pValue`  
 <span data-ttu-id="bed9a-106">enuncia Puntero a un valor de `CORDB_ADDRESS` que especifica la dirección del objeto al que señala este objeto ICorDebugReferenceValue.</span><span class="sxs-lookup"><span data-stu-id="bed9a-106">[out] A pointer to a `CORDB_ADDRESS` value that specifies the address of the object to which this ICorDebugReferenceValue object points.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bed9a-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="bed9a-107">Requirements</span></span>  
 <span data-ttu-id="bed9a-108">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bed9a-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bed9a-109">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="bed9a-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="bed9a-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bed9a-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bed9a-111">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bed9a-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
