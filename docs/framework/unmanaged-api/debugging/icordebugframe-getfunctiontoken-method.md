---
title: ICorDebugFrame::GetFunctionToken (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugFrame.GetFunctionToken
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFrame::GetFunctionToken
helpviewer_keywords:
- ICorDebugFrame::GetFunctionToken method [.NET Framework debugging]
- GetFunctionToken method [.NET Framework debugging]
ms.assetid: a46925b3-3bf8-404f-9f30-a86ae41032c1
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 156c16f73916d2b4efa1c1b3541a772fb43dd470
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57497566"
---
# <a name="icordebugframegetfunctiontoken-method"></a><span data-ttu-id="c67d3-102">ICorDebugFrame::GetFunctionToken (Método)</span><span class="sxs-lookup"><span data-stu-id="c67d3-102">ICorDebugFrame::GetFunctionToken Method</span></span>
<span data-ttu-id="c67d3-103">Obtiene el token de metadatos para la función que contiene el código asociado a este marco de pila.</span><span class="sxs-lookup"><span data-stu-id="c67d3-103">Gets the metadata token for the function that contains the code associated with this stack frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c67d3-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c67d3-104">Syntax</span></span>  
  
```  
HRESULT GetFunctionToken (  
    [out] mdMethodDef        *pToken  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c67d3-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c67d3-105">Parameters</span></span>  
 `pToken`  
 <span data-ttu-id="c67d3-106">[out] Un puntero a un `mdMethodDef` símbolo (token) que hace referencia a los metadatos de la función.</span><span class="sxs-lookup"><span data-stu-id="c67d3-106">[out] A pointer to an `mdMethodDef` token that references the metadata for the function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c67d3-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c67d3-107">Requirements</span></span>  
 <span data-ttu-id="c67d3-108">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c67d3-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c67d3-109">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c67d3-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c67d3-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c67d3-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c67d3-111">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c67d3-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
