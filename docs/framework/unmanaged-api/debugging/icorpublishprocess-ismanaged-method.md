---
title: ICorPublishProcess::IsManaged (Método)
ms.date: 03/30/2017
api_name:
- ICorPublishProcess.IsManaged
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishProcess::IsManaged
helpviewer_keywords:
- IsManaged method, ICorPublishProcess interface [.NET Framework debugging]
- ICorPublishProcess::IsManaged method [.NET Framework debugging]
ms.assetid: 06b1f7cc-acdf-47a6-9d53-d9dec2424152
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 29c5f96bab374d6e2d43424370bff2a4a2ab6df3
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59218295"
---
# <a name="icorpublishprocessismanaged-method"></a><span data-ttu-id="1aa17-102">ICorPublishProcess::IsManaged (Método)</span><span class="sxs-lookup"><span data-stu-id="1aa17-102">ICorPublishProcess::IsManaged Method</span></span>
<span data-ttu-id="1aa17-103">Obtiene un valor que indica si el proceso que hace referencia esta [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md) se sabe que tienen código administrado.</span><span class="sxs-lookup"><span data-stu-id="1aa17-103">Gets a value that indicates whether the process referenced by this [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md) is known to have managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1aa17-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1aa17-104">Syntax</span></span>  
  
```  
HRESULT IsManaged (  
    [out] BOOL   *pbManaged  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1aa17-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="1aa17-105">Parameters</span></span>  
 `pbManaged`  
 <span data-ttu-id="1aa17-106">[out] Un puntero a un valor booleano que indica si el proceso tiene código administrado.</span><span class="sxs-lookup"><span data-stu-id="1aa17-106">[out] A pointer to a Boolean value that indicates whether the process has managed code.</span></span> <span data-ttu-id="1aa17-107">El valor es `true` si el proceso tiene código administrado; en caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="1aa17-107">The value is `true` if the process has managed code; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1aa17-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="1aa17-108">Remarks</span></span>  
 <span data-ttu-id="1aa17-109">Desde la versión actual de `ICorPublishProcess` permite el acceso solo a los procesos que haya código administrado, `IsManaged` siempre devuelve `true`.</span><span class="sxs-lookup"><span data-stu-id="1aa17-109">Since the current version of `ICorPublishProcess` allows access only to processes that have managed code, `IsManaged` always returns `true`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1aa17-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1aa17-110">Requirements</span></span>  
 <span data-ttu-id="1aa17-111">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1aa17-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1aa17-112">**Encabezado**: CorPub.idl, CorPub.h</span><span class="sxs-lookup"><span data-stu-id="1aa17-112">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="1aa17-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1aa17-113">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="1aa17-114">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="1aa17-114">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="1aa17-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="1aa17-115">See also</span></span>

- [<span data-ttu-id="1aa17-116">ICorPublishProcess (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="1aa17-116">ICorPublishProcess Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md)
