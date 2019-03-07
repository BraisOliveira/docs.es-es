---
title: IHostThreadPoolManager::GetAvailableThreads (Método)
ms.date: 03/30/2017
api_name:
- IHostThreadPoolManager.GetAvailableThreads
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostThreadPoolManager::GetAvailableThreads
helpviewer_keywords:
- GetAvailableThreads method, IHostThreadPoolManager interface [.NET Framework hosting]
- IHostThreadPoolManager::GetAvailableThreads method [.NET Framework hosting]
ms.assetid: 61d26dfd-7f24-4e7d-a63e-b30a463f08e1
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6f9eb28ea1a60991d047494336035aaf239b9edd
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57478601"
---
# <a name="ihostthreadpoolmanagergetavailablethreads-method"></a><span data-ttu-id="a4c72-102">IHostThreadPoolManager::GetAvailableThreads (Método)</span><span class="sxs-lookup"><span data-stu-id="a4c72-102">IHostThreadPoolManager::GetAvailableThreads Method</span></span>
<span data-ttu-id="a4c72-103">Obtiene el número de subprocesos en el grupo de subprocesos que no se están procesando actualmente elementos de trabajo.</span><span class="sxs-lookup"><span data-stu-id="a4c72-103">Gets the number of threads in the thread pool that are not currently processing work items.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a4c72-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a4c72-104">Syntax</span></span>  
  
```  
HRESULT GetAvailableThreads (  
    [out] DWORD *pdwAvailableWorkerThreads  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a4c72-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a4c72-105">Parameters</span></span>  
 `pdwAvailableWorkerThreads`  
 <span data-ttu-id="a4c72-106">[out] Puntero al número de subprocesos en el grupo de subprocesos que no se están procesando actualmente elementos de trabajo.</span><span class="sxs-lookup"><span data-stu-id="a4c72-106">[out] Pointer to the number of threads in the thread pool that are not currently processing work items.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a4c72-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="a4c72-107">Return Value</span></span>  
  
|<span data-ttu-id="a4c72-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="a4c72-108">HRESULT</span></span>|<span data-ttu-id="a4c72-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="a4c72-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a4c72-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="a4c72-110">S_OK</span></span>|<span data-ttu-id="a4c72-111">`GetAvailableThreads` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="a4c72-111">`GetAvailableThreads` returned successfully.</span></span>|  
|<span data-ttu-id="a4c72-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="a4c72-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="a4c72-113">Common language runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="a4c72-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="a4c72-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="a4c72-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="a4c72-115">La llamada ha agotado el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="a4c72-115">The call timed out.</span></span>|  
|<span data-ttu-id="a4c72-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="a4c72-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="a4c72-117">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="a4c72-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="a4c72-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="a4c72-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="a4c72-119">Se canceló un evento mientras un subproceso bloqueado o fibra estaba esperando en ella.</span><span class="sxs-lookup"><span data-stu-id="a4c72-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="a4c72-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="a4c72-120">E_FAIL</span></span>|<span data-ttu-id="a4c72-121">Se ha producido un error irrecuperable desconocido.</span><span class="sxs-lookup"><span data-stu-id="a4c72-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="a4c72-122">Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="a4c72-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="a4c72-123">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="a4c72-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="a4c72-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="a4c72-124">E_NOTIMPL</span></span>|<span data-ttu-id="a4c72-125">El host no proporciona una implementación de `GetAvailableThreads`.</span><span class="sxs-lookup"><span data-stu-id="a4c72-125">The host does not provide an implementation of `GetAvailableThreads`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a4c72-126">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a4c72-126">Remarks</span></span>  
 <span data-ttu-id="a4c72-127">Si el host no proporciona una implementación de `GetAvailableThreads`, debe devolver un valor HRESULT de E_NOTIMPL.</span><span class="sxs-lookup"><span data-stu-id="a4c72-127">If the host does not provide an implementation of `GetAvailableThreads`, it should return an HRESULT value of E_NOTIMPL.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a4c72-128">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a4c72-128">Requirements</span></span>  
 <span data-ttu-id="a4c72-129">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a4c72-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a4c72-130">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="a4c72-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a4c72-131">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a4c72-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a4c72-132">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a4c72-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a4c72-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="a4c72-133">See also</span></span>
- <xref:System.Threading.ThreadPool.GetAvailableThreads%2A>
- <xref:System.Threading.ThreadPool>
- [<span data-ttu-id="a4c72-134">IHostThreadPoolManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="a4c72-134">IHostThreadPoolManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)
