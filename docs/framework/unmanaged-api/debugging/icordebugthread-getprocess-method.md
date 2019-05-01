---
title: ICorDebugThread::GetProcess (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugThread.GetProcess
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::GetProcess
helpviewer_keywords:
- ICorDebugThread::GetProcess method [.NET Framework debugging]
- GetProcess method, ICorDebugThread interface [.NET Framework debugging]
ms.assetid: 163816e7-0739-4566-b3df-cd256be8b8a4
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 46aa2ec5a282ef56f28d5fa0499571028e6602e6
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61987038"
---
# <a name="icordebugthreadgetprocess-method"></a><span data-ttu-id="343dd-102">ICorDebugThread::GetProcess (Método)</span><span class="sxs-lookup"><span data-stu-id="343dd-102">ICorDebugThread::GetProcess Method</span></span>
<span data-ttu-id="343dd-103">Obtiene un puntero de interfaz al proceso del que este ICorDebugThread forma parte.</span><span class="sxs-lookup"><span data-stu-id="343dd-103">Gets an interface pointer to the process of which this ICorDebugThread forms a part.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="343dd-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="343dd-104">Syntax</span></span>  
  
```  
HRESULT GetProcess (  
    [out] ICorDebugProcess   **ppProcess  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="343dd-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="343dd-105">Parameters</span></span>  
 `ppProcess`  
 <span data-ttu-id="343dd-106">[out] Un puntero a la dirección de un objeto de interfaz ICorDebugProcess que representa el proceso.</span><span class="sxs-lookup"><span data-stu-id="343dd-106">[out] A pointer to the address of an ICorDebugProcess interface object that represents the process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="343dd-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="343dd-107">Requirements</span></span>  
 <span data-ttu-id="343dd-108">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="343dd-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="343dd-109">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="343dd-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="343dd-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="343dd-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="343dd-111">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="343dd-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
