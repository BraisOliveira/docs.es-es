---
title: ICorDebugFrame::GetCode (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugFrame.GetCode
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFrame::GetCode
helpviewer_keywords:
- GetCode method, ICorDebugFrame interface [.NET Framework debugging]
- ICorDebugFrame::GetCode method [.NET Framework debugging]
ms.assetid: fbaa0794-a031-4015-8beb-2749e47ac340
topic_type:
- apiref
ms.openlocfilehash: 9a4f533c0ab817d800c2d35b7d64c7aee78faaea
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73121168"
---
# <a name="icordebugframegetcode-method"></a><span data-ttu-id="70e4e-102">ICorDebugFrame::GetCode (Método)</span><span class="sxs-lookup"><span data-stu-id="70e4e-102">ICorDebugFrame::GetCode Method</span></span>
<span data-ttu-id="70e4e-103">Obtiene un puntero al código asociado a este marco de pila.</span><span class="sxs-lookup"><span data-stu-id="70e4e-103">Gets a pointer to the code associated with this stack frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="70e4e-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="70e4e-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCode (  
    [out] ICorDebugCode      **ppCode  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="70e4e-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="70e4e-105">Parameters</span></span>  
 `ppCode`  
 <span data-ttu-id="70e4e-106">enuncia Puntero a la dirección de un objeto ICorDebugCode que representa el código asociado a este marco.</span><span class="sxs-lookup"><span data-stu-id="70e4e-106">[out] A pointer to the address of an ICorDebugCode object that represents the code associated with this frame.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="70e4e-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="70e4e-107">Requirements</span></span>  
 <span data-ttu-id="70e4e-108">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="70e4e-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="70e4e-109">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="70e4e-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="70e4e-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="70e4e-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="70e4e-111">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="70e4e-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
