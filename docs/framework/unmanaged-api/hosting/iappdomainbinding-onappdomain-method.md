---
title: IAppDomainBinding::OnAppDomain (Método)
ms.date: 03/30/2017
api_name:
- IAppDomainBinding.OnAppDomain
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- OnAppDomain
helpviewer_keywords:
- IAppDomainBinding::OnAppDomain method [.NET Framework hosting]
- OnAppDomain method [.NET Framework hosting]
ms.assetid: b419dcc9-e8aa-484b-af0d-0f40358edb99
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 523f90966501e06994fb0e11b3c77aa62c378eef
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67770459"
---
# <a name="iappdomainbindingonappdomain-method"></a><span data-ttu-id="8fe07-102">IAppDomainBinding::OnAppDomain (Método)</span><span class="sxs-lookup"><span data-stu-id="8fe07-102">IAppDomainBinding::OnAppDomain Method</span></span>
<span data-ttu-id="8fe07-103">Lo llama common language runtime (CLR) para notificar al host que se ha creado un dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="8fe07-103">Called by the common language runtime (CLR) to notify the host that an application domain has been created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8fe07-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8fe07-104">Syntax</span></span>  
  
```cpp  
HRESULT OnAppDomain (  
    [in] IUnknown* pAppdomain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8fe07-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="8fe07-105">Parameters</span></span>  
 `pAppdomain`  
 <span data-ttu-id="8fe07-106">[in] Un puntero a un [IUnknown](/cpp/atl/iunknown) objeto de interfaz que representa el nuevo dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="8fe07-106">[in] A pointer to an [IUnknown](/cpp/atl/iunknown) interface object that represents the new application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8fe07-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8fe07-107">Requirements</span></span>  
 <span data-ttu-id="8fe07-108">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8fe07-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8fe07-109">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="8fe07-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="8fe07-110">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="8fe07-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8fe07-111">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8fe07-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8fe07-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="8fe07-112">See also</span></span>

- [<span data-ttu-id="8fe07-113">IAppDomainBinding (interfaz)</span><span class="sxs-lookup"><span data-stu-id="8fe07-113">IAppDomainBinding Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iappdomainbinding-interface.md)
