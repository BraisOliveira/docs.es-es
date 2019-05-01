---
title: ICorDebugModule2::GetJITCompilerFlags (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugModule2.GetJITCompilerFlags
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule2::GetJITCompilerFlags
helpviewer_keywords:
- GetJITCompilerFlags method [.NET Framework debugging]
- ICorDebugModule2::GetJITCompilerFlags method [.NET Framework debugging]
ms.assetid: 7212d9f4-989b-44e3-b8d4-ffc35922f6a0
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 77f4e745e4bd45be51b497fdd5bab95cd24c9685
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61994817"
---
# <a name="icordebugmodule2getjitcompilerflags-method"></a><span data-ttu-id="802e8-102">ICorDebugModule2::GetJITCompilerFlags (Método)</span><span class="sxs-lookup"><span data-stu-id="802e8-102">ICorDebugModule2::GetJITCompilerFlags Method</span></span>
<span data-ttu-id="802e8-103">Obtiene las marcas que controlan la compilación just-in-time (JIT) de este ICorDebugModule2.</span><span class="sxs-lookup"><span data-stu-id="802e8-103">Gets the flags that control the just-in-time (JIT) compilation of this ICorDebugModule2.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="802e8-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="802e8-104">Syntax</span></span>  
  
```  
HRESULT GetJITCompilerFlags (  
    [out] DWORD   *pdwFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="802e8-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="802e8-105">Parameters</span></span>  
 `pdwFlags`  
 <span data-ttu-id="802e8-106">[out] Un puntero a un valor de la [CorDebugJITCompilerFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugjitcompilerflags-enumeration.md) enumeración que controla la compilación JIT.</span><span class="sxs-lookup"><span data-stu-id="802e8-106">[out] A pointer to a value of the [CorDebugJITCompilerFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugjitcompilerflags-enumeration.md) enumeration that controls the JIT compilation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="802e8-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="802e8-107">Requirements</span></span>  
 <span data-ttu-id="802e8-108">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="802e8-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="802e8-109">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="802e8-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="802e8-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="802e8-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="802e8-111">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="802e8-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
