---
title: ICorDebugManagedCallback::UnloadClass (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.UnloadClass
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::UnloadClass
helpviewer_keywords:
- ICorDebugManagedCallback::UnloadClass method [.NET Framework debugging]
- UnloadClass method [.NET Framework debugging]
ms.assetid: 66a59b18-ce9a-41f4-b23b-4dd6753d6d36
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b3eb8bf59ee2a91c62a6ff74b1903d92607a9ffe
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59197881"
---
# <a name="icordebugmanagedcallbackunloadclass-method"></a><span data-ttu-id="63f7a-102">ICorDebugManagedCallback::UnloadClass (Método)</span><span class="sxs-lookup"><span data-stu-id="63f7a-102">ICorDebugManagedCallback::UnloadClass Method</span></span>
<span data-ttu-id="63f7a-103">Notifica al depurador que se está descargando una clase.</span><span class="sxs-lookup"><span data-stu-id="63f7a-103">Notifies the debugger that a class is being unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="63f7a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="63f7a-104">Syntax</span></span>  
  
```  
HRESULT UnloadClass (  
    [in] ICorDebugAppDomain  *pAppDomain,  
    [in] ICorDebugClass      *c  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="63f7a-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="63f7a-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="63f7a-106">[in] Un puntero a un objeto ICorDebugAppDomain que representa el dominio de aplicación que contiene la clase.</span><span class="sxs-lookup"><span data-stu-id="63f7a-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain containing the class.</span></span>  
  
 `c`  
 <span data-ttu-id="63f7a-107">[in] Un puntero a un objeto ICorDebugClass que representa la clase.</span><span class="sxs-lookup"><span data-stu-id="63f7a-107">[in] A pointer to an ICorDebugClass object that represents the class.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="63f7a-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="63f7a-108">Remarks</span></span>  
 <span data-ttu-id="63f7a-109">No se debe hacer referencia a la clase después de esta llamada.</span><span class="sxs-lookup"><span data-stu-id="63f7a-109">The class should not be referenced after this call.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="63f7a-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="63f7a-110">Requirements</span></span>  
 <span data-ttu-id="63f7a-111">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="63f7a-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="63f7a-112">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="63f7a-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="63f7a-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="63f7a-113">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="63f7a-114">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="63f7a-114">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="63f7a-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="63f7a-115">See also</span></span>

- [<span data-ttu-id="63f7a-116">Método LoadClass</span><span class="sxs-lookup"><span data-stu-id="63f7a-116">LoadClass Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadclass-method.md)
- [<span data-ttu-id="63f7a-117">ICorDebugManagedCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="63f7a-117">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
