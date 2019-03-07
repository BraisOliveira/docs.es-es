---
title: ICoreClrDebugTarget::FreeMemory (Método)
ms.date: 03/30/2017
api_name:
- ICoreDebugTarget.FreeMemory
api_location:
- mscordbi_macx86.dll
api_type:
- COM
f1_keywords:
- ICoreClrDebugTarget::FreeMemory
helpviewer_keywords:
- remote debugging API [Silverlight]
- FreeMemory method, ICoreClrDebugTarget interface [Silverlight debugging]
- ICorClrDebugTarget::FreeMemory method [Silverlight debugging]
- Silverlight, remote debugging
ms.assetid: 98f2a0db-a6ec-4f9b-861d-f82485237d08
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1a3448512cb486419e524df012fcd1b8fcf639f1
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57466380"
---
# <a name="icoreclrdebugtargetfreememory-method"></a><span data-ttu-id="75490-102">ICoreClrDebugTarget::FreeMemory (Método)</span><span class="sxs-lookup"><span data-stu-id="75490-102">ICoreClrDebugTarget::FreeMemory Method</span></span>
<span data-ttu-id="75490-103">Libera la memoria asignada por el [Icoreclrdebugtarget](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-enumprocesses-method.md) y [Icoreclrdebugtarget](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-enumruntimes-method.md) métodos.</span><span class="sxs-lookup"><span data-stu-id="75490-103">Frees the memory allocated by the [ICoreClrDebugTarget::EnumProcesses](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-enumprocesses-method.md) and [ICoreClrDebugTarget::EnumRuntimes](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-enumruntimes-method.md) methods.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="75490-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="75490-104">Syntax</span></span>  
  
```  
void FreeMemory (  
     [in] void*pMemory);  
```  
  
## <a name="parameters"></a><span data-ttu-id="75490-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="75490-105">Parameters</span></span>  
 `pMemory`  
 <span data-ttu-id="75490-106">[in] Un puntero a la matriz que es devuelto por la [Icoreclrdebugtarget](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-enumprocesses-method.md) o [Icoreclrdebugtarget](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-enumruntimes-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="75490-106">[in] A pointer to the array that is returned by either the [ICoreClrDebugTarget::EnumProcesses](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-enumprocesses-method.md) or the [ICoreClrDebugTarget::EnumRuntimes](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-enumruntimes-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="75490-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="75490-107">Requirements</span></span>  
 <span data-ttu-id="75490-108">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="75490-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="75490-109">**Encabezado**: CoreClrRemoteDebuggingInterfaces.h</span><span class="sxs-lookup"><span data-stu-id="75490-109">**Header:** CoreClrRemoteDebuggingInterfaces.h</span></span>  
  
 <span data-ttu-id="75490-110">**Library:** mscordbi_macx86.dll</span><span class="sxs-lookup"><span data-stu-id="75490-110">**Library:** mscordbi_macx86.dll</span></span>  
  
 <span data-ttu-id="75490-111">**Versiones de .NET framework:** 3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="75490-111">**.NET Framework Versions:** 3.5 SP1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="75490-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="75490-112">See also</span></span>
- [<span data-ttu-id="75490-113">ICoreClrDebugTarget (interfaz)</span><span class="sxs-lookup"><span data-stu-id="75490-113">ICoreClrDebugTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-interface.md)
