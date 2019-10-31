---
title: ICorDebugFunction::GetLocalVarSigToken (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugFunction.GetLocalVarSigToken
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunction::GetLocalVarSigToken
helpviewer_keywords:
- ICorDebugFunction::GetLocalVarSigToken method [.NET Framework debugging]
- GetLocalVarSigToken method [.NET Framework debugging]
ms.assetid: 31e53494-bcc9-4981-91a4-f7e0f02cad48
topic_type:
- apiref
ms.openlocfilehash: c159a175ddd380015cc2dc21637c8b63fd3caea6
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73137890"
---
# <a name="icordebugfunctiongetlocalvarsigtoken-method"></a><span data-ttu-id="14e6c-102">ICorDebugFunction::GetLocalVarSigToken (Método)</span><span class="sxs-lookup"><span data-stu-id="14e6c-102">ICorDebugFunction::GetLocalVarSigToken Method</span></span>
<span data-ttu-id="14e6c-103">Obtiene el símbolo (token) de metadatos de la firma de variable local de la función representada por esta instancia de ICorDebugFunction.</span><span class="sxs-lookup"><span data-stu-id="14e6c-103">Gets the metadata token for the local variable signature of the function that is represented by this ICorDebugFunction instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="14e6c-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="14e6c-104">Syntax</span></span>  
  
```cpp  
HRESULT GetLocalVarSigToken (  
    [out] mdSignature *pmdSig  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="14e6c-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="14e6c-105">Parameters</span></span>  
 `pmdSig`  
 <span data-ttu-id="14e6c-106">enuncia Puntero al `mdSignature` token para la firma de variable local de esta función, o `mdSignatureNil`, si esta función no tiene ninguna variable local.</span><span class="sxs-lookup"><span data-stu-id="14e6c-106">[out] A pointer to the `mdSignature` token for the local variable signature of this function, or `mdSignatureNil`, if this function has no local variables.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="14e6c-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="14e6c-107">Requirements</span></span>  
 <span data-ttu-id="14e6c-108">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="14e6c-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="14e6c-109">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="14e6c-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="14e6c-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="14e6c-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="14e6c-111">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="14e6c-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
