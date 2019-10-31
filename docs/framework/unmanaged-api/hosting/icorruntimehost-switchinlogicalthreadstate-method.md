---
title: ICorRuntimeHost::SwitchInLogicalThreadState (Método)
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost.SwitchInLogicalThreadState
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::SwitchInLogicalThreadState
helpviewer_keywords:
- ICorRuntimeHost::SwitchInLogicalThreadState method [.NET Framework hosting]
- SwitchInLogicalThreadState method [.NET Framework hosting]
ms.assetid: 7df1e492-8014-43ea-80d1-a4743e9b1c17
topic_type:
- apiref
ms.openlocfilehash: b6569b5dab89a88a24cf2dfc873da9740e5af505
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133379"
---
# <a name="icorruntimehostswitchinlogicalthreadstate-method"></a><span data-ttu-id="e2240-102">ICorRuntimeHost::SwitchInLogicalThreadState (Método)</span><span class="sxs-lookup"><span data-stu-id="e2240-102">ICorRuntimeHost::SwitchInLogicalThreadState Method</span></span>
<span data-ttu-id="e2240-103">Este método es compatible con la infraestructura de .NET Framework y no está diseñado para utilizarse directamente desde el código.</span><span class="sxs-lookup"><span data-stu-id="e2240-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e2240-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e2240-104">Syntax</span></span>  
  
```cpp  
HRESULT SwitchInLogicalThreadState(  
    [in] DWORD *pFiberCookie  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e2240-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e2240-105">Parameters</span></span>  
 `pFiberCookie`  
 <span data-ttu-id="e2240-106">de Cookie que indica la fibra que se va a usar.</span><span class="sxs-lookup"><span data-stu-id="e2240-106">[in] Cookie that indicates the fiber to use.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e2240-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e2240-107">Requirements</span></span>  
 <span data-ttu-id="e2240-108">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e2240-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e2240-109">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="e2240-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e2240-110">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="e2240-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e2240-111">**Versión de .NET Framework:** 1,0, 1,1</span><span class="sxs-lookup"><span data-stu-id="e2240-111">**.NET Framework Version:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e2240-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="e2240-112">See also</span></span>

- [<span data-ttu-id="e2240-113">ICorRuntimeHost (interfaz)</span><span class="sxs-lookup"><span data-stu-id="e2240-113">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
