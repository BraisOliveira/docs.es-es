---
title: ITypeName::GetTypeArguments (Método)
ms.date: 03/30/2017
api_name:
- ITypeName.GetTypeArguments
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- GetTypeArguments
helpviewer_keywords:
- ITypeName::GetTypeArguments method [.NET Framework hosting]
- GetTypeArguments method [.NET Framework hosting]
ms.assetid: 638d77df-ff9c-40d9-88ee-930f5f87ada1
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f4c56f6a2eecb614d2d8fbc7c402e90a7cb3ff7d
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67753200"
---
# <a name="itypenamegettypearguments-method"></a><span data-ttu-id="0f4b0-102">ITypeName::GetTypeArguments (Método)</span><span class="sxs-lookup"><span data-stu-id="0f4b0-102">ITypeName::GetTypeArguments Method</span></span>
<span data-ttu-id="0f4b0-103">Este método es compatible con la infraestructura de .NET Framework y no está diseñado para utilizarse directamente desde el código.</span><span class="sxs-lookup"><span data-stu-id="0f4b0-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0f4b0-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0f4b0-104">Syntax</span></span>  
  
```cpp  
HRESULT GetTypeArguments (  
    [in] DWORD           count,  
    [out] ITypeName**    rgpArguments,  
    [out, retval] DWORD* pCount  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="0f4b0-105">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0f4b0-105">Requirements</span></span>  
 <span data-ttu-id="0f4b0-106">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0f4b0-106">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0f4b0-107">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="0f4b0-107">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="0f4b0-108">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="0f4b0-108">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0f4b0-109">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0f4b0-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0f4b0-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="0f4b0-110">See also</span></span>

- [<span data-ttu-id="0f4b0-111">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="0f4b0-111">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
