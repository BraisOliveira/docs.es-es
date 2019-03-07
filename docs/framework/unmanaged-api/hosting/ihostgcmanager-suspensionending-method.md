---
title: IHostGCManager::SuspensionEnding (Método)
ms.date: 03/30/2017
api_name:
- IHostGCManager.SuspensionEnding
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostGCManager::SuspensionEnding
helpviewer_keywords:
- SuspensionEnding method, IHostGCManager interface [.NET Framework hosting]
- IHostGCManager::SuspensionEnding method [.NET Framework hosting]
ms.assetid: 8849a1db-17f0-44b7-880a-bd36d431eb91
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1995321e8598d010188fee2437640b4489eaa294
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57472036"
---
# <a name="ihostgcmanagersuspensionending-method"></a><span data-ttu-id="d656a-102">IHostGCManager::SuspensionEnding (Método)</span><span class="sxs-lookup"><span data-stu-id="d656a-102">IHostGCManager::SuspensionEnding Method</span></span>
<span data-ttu-id="d656a-103">Notifica al host que common language runtime (CLR) está reanudando la ejecución de tareas en subprocesos que se habían suspendidos para una colección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="d656a-103">Notifies the host that the common language runtime (CLR) is resuming execution of tasks on threads that had been suspended for a garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d656a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d656a-104">Syntax</span></span>  
  
```  
HRESULT SuspensionEnding (  
    [in] DWORD generation  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d656a-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d656a-105">Parameters</span></span>  
 `generation`  
 <span data-ttu-id="d656a-106">[in] La generación de recolección que está finalizando, desde la que se reanuda el subproceso.</span><span class="sxs-lookup"><span data-stu-id="d656a-106">[in] The garbage collection generation that is just finishing, from which the thread is resuming.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d656a-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="d656a-107">Return Value</span></span>  
  
|<span data-ttu-id="d656a-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="d656a-108">HRESULT</span></span>|<span data-ttu-id="d656a-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="d656a-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="d656a-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="d656a-110">S_OK</span></span>|<span data-ttu-id="d656a-111">`SuspensionEnding` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="d656a-111">`SuspensionEnding` returned successfully.</span></span>|  
|<span data-ttu-id="d656a-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="d656a-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="d656a-113">El CLR no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="d656a-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="d656a-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="d656a-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="d656a-115">La llamada ha agotado el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="d656a-115">The call timed out.</span></span>|  
|<span data-ttu-id="d656a-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="d656a-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="d656a-117">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="d656a-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="d656a-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="d656a-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="d656a-119">Se canceló un evento mientras un subproceso bloqueado o fibra estaba esperando en ella.</span><span class="sxs-lookup"><span data-stu-id="d656a-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="d656a-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="d656a-120">E_FAIL</span></span>|<span data-ttu-id="d656a-121">Se ha producido un error irrecuperable desconocido.</span><span class="sxs-lookup"><span data-stu-id="d656a-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="d656a-122">Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="d656a-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="d656a-123">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="d656a-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d656a-124">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d656a-124">Remarks</span></span>  
 <span data-ttu-id="d656a-125">CLR llama a `SuspensionEnding` después de que realiza una recolección de elementos no utilizados, para informar al host que el subproceso está reanudando la ejecución.</span><span class="sxs-lookup"><span data-stu-id="d656a-125">The CLR calls `SuspensionEnding` after it performs a garbage collection, to inform the host that the thread is resuming execution.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="d656a-126">No se vuelva a programar el subproceso de que la llamada al método se realizó desde.</span><span class="sxs-lookup"><span data-stu-id="d656a-126">Do not reschedule the thread the method call was made from.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d656a-127">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d656a-127">Requirements</span></span>  
 <span data-ttu-id="d656a-128">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d656a-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d656a-129">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="d656a-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d656a-130">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="d656a-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d656a-131">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d656a-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d656a-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="d656a-132">See also</span></span>
- [<span data-ttu-id="d656a-133">ICLRTask (interfaz)</span><span class="sxs-lookup"><span data-stu-id="d656a-133">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="d656a-134">ICLRTaskManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="d656a-134">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="d656a-135">IHostTask (interfaz)</span><span class="sxs-lookup"><span data-stu-id="d656a-135">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="d656a-136">IHostTaskManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="d656a-136">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
- [<span data-ttu-id="d656a-137">IHostGCManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="d656a-137">IHostGCManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-interface.md)
