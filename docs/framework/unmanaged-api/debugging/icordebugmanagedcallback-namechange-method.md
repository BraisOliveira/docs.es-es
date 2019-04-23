---
title: ICorDebugManagedCallback::NameChange (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.NameChange
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::NameChange
helpviewer_keywords:
- ICorDebugManagedCallback::NameChange method [.NET Framework debugging]
- NameChange method [.NET Framework debugging]
ms.assetid: a7018a0e-880e-4b68-b52a-1cd22c7aad62
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 975353403a82956912fa41047253bb0dbf138502
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59124129"
---
# <a name="icordebugmanagedcallbacknamechange-method"></a><span data-ttu-id="0d3fa-102">ICorDebugManagedCallback::NameChange (Método)</span><span class="sxs-lookup"><span data-stu-id="0d3fa-102">ICorDebugManagedCallback::NameChange Method</span></span>
<span data-ttu-id="0d3fa-103">Notifica al depurador que se ha cambiado el nombre de un dominio de aplicación o un subproceso.</span><span class="sxs-lookup"><span data-stu-id="0d3fa-103">Notifies the debugger that the name of either an application domain or a thread has changed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0d3fa-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0d3fa-104">Syntax</span></span>  
  
```  
HRESULT NameChange (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugThread    *pThread  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0d3fa-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="0d3fa-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="0d3fa-106">[in] Un puntero a un objeto ICorDebugAppDomain que representa el dominio de aplicación que tuvo un cambio de nombre o que contiene el subproceso que tuvo un cambio de nombre.</span><span class="sxs-lookup"><span data-stu-id="0d3fa-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain that either had a name change or that contains the thread that had a name change.</span></span>  
  
 `pThread`  
 <span data-ttu-id="0d3fa-107">[in] Un puntero a un objeto ICorDebugThread que representa el subproceso que tuvo un cambio de nombre.</span><span class="sxs-lookup"><span data-stu-id="0d3fa-107">[in] A pointer to an ICorDebugThread object that represents the thread that had a name change.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0d3fa-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0d3fa-108">Requirements</span></span>  
 <span data-ttu-id="0d3fa-109">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0d3fa-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0d3fa-110">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0d3fa-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0d3fa-111">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0d3fa-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0d3fa-112">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0d3fa-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0d3fa-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="0d3fa-113">See also</span></span>

- [<span data-ttu-id="0d3fa-114">ICorDebugManagedCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="0d3fa-114">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
