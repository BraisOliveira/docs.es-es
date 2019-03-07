---
title: IHostCrst::SetSpinCount (Método)
ms.date: 03/30/2017
api_name:
- IHostCrst.SetSpinCount
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostCrst::SetSpinCount
helpviewer_keywords:
- IHostCrst::SetSpinCount method [.NET Framework hosting]
- SetSpinCount method [.NET Framework hosting]
ms.assetid: 863fc8ce-9b8a-477e-8dd8-75c8544bb43a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cf83c7755bc099275c02ff0049f663573c582faf
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57469566"
---
# <a name="ihostcrstsetspincount-method"></a><span data-ttu-id="7c73f-102">IHostCrst::SetSpinCount (Método)</span><span class="sxs-lookup"><span data-stu-id="7c73f-102">IHostCrst::SetSpinCount Method</span></span>
<span data-ttu-id="7c73f-103">Establece el recuento circular actual [IHostCrst](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md) instancia.</span><span class="sxs-lookup"><span data-stu-id="7c73f-103">Sets the spin count for the current [IHostCrst](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md) instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7c73f-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7c73f-104">Syntax</span></span>  
  
```  
HRESULT SetSpinCount (  
    [in] DWORD dwSpinCount  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7c73f-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="7c73f-105">Parameters</span></span>  
 `dwSpinCount`  
 <span data-ttu-id="7c73f-106">[in] El nuevo recuento de rotación actual `IHostCrst` instancia.</span><span class="sxs-lookup"><span data-stu-id="7c73f-106">[in] The new spin count for the current `IHostCrst` instance.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7c73f-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="7c73f-107">Return Value</span></span>  
  
|<span data-ttu-id="7c73f-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="7c73f-108">HRESULT</span></span>|<span data-ttu-id="7c73f-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="7c73f-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="7c73f-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="7c73f-110">S_OK</span></span>|<span data-ttu-id="7c73f-111">`SetSpinCount` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="7c73f-111">`SetSpinCount` returned successfully.</span></span>|  
|<span data-ttu-id="7c73f-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="7c73f-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="7c73f-113">Common language runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="7c73f-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="7c73f-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="7c73f-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="7c73f-115">La llamada ha agotado el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="7c73f-115">The call timed out.</span></span>|  
|<span data-ttu-id="7c73f-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="7c73f-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="7c73f-117">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="7c73f-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="7c73f-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="7c73f-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="7c73f-119">Se canceló un evento mientras un subproceso bloqueado o fibra estaba esperando en ella.</span><span class="sxs-lookup"><span data-stu-id="7c73f-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="7c73f-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="7c73f-120">E_FAIL</span></span>|<span data-ttu-id="7c73f-121">Se ha producido un error irrecuperable desconocido.</span><span class="sxs-lookup"><span data-stu-id="7c73f-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="7c73f-122">Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="7c73f-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="7c73f-123">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="7c73f-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7c73f-124">Comentarios</span><span class="sxs-lookup"><span data-stu-id="7c73f-124">Remarks</span></span>  
 <span data-ttu-id="7c73f-125">En sistemas multiprocesador, si la sección crítica representada por el actual `IHostCrst` instancia no está disponible, un subproceso que realiza la llamada da `dwSpinCount` veces antes de llamar a [IHostSemaphore](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-wait-method.md) en un semáforo asociado con la sección crítica.</span><span class="sxs-lookup"><span data-stu-id="7c73f-125">On multi-processor systems, if the critical section represented by the current `IHostCrst` instance is unavailable, a calling thread spins `dwSpinCount` times before calling [IHostSemaphore::Wait](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-wait-method.md) on a semaphore associated with the critical section.</span></span> <span data-ttu-id="7c73f-126">Si la sección crítica deja de estar disponible durante la operación de giro, el subproceso que realiza la llamada evita la operación de espera.</span><span class="sxs-lookup"><span data-stu-id="7c73f-126">If the critical section becomes free during the spin operation, the calling thread avoids the wait operation.</span></span>  
  
 <span data-ttu-id="7c73f-127">El uso de `dwSpinCount` es idéntico al uso del parámetro del mismo nombre en Win32 `InitializeCriticalSectionAndSpinCount` función.</span><span class="sxs-lookup"><span data-stu-id="7c73f-127">The usage of `dwSpinCount` is identical to the usage of the parameter of the same name in the Win32 `InitializeCriticalSectionAndSpinCount` function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7c73f-128">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7c73f-128">Requirements</span></span>  
 <span data-ttu-id="7c73f-129">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7c73f-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7c73f-130">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="7c73f-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="7c73f-131">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="7c73f-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7c73f-132">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7c73f-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7c73f-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="7c73f-133">See also</span></span>
- [<span data-ttu-id="7c73f-134">ICLRSyncManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="7c73f-134">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="7c73f-135">IHostCrst (interfaz)</span><span class="sxs-lookup"><span data-stu-id="7c73f-135">IHostCrst Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md)
- [<span data-ttu-id="7c73f-136">IHostSyncManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="7c73f-136">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
