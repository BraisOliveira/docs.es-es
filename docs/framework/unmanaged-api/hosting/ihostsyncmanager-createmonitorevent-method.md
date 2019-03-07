---
title: IHostSyncManager::CreateMonitorEvent (Método)
ms.date: 03/30/2017
api_name:
- IHostSyncManager.CreateMonitorEvent
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSyncManager::CreateMonitorEvent
helpviewer_keywords:
- CreateMonitorEvent method [.NET Framework hosting]
- IHostSyncManager::CreateMonitorEvent method [.NET Framework hosting]
ms.assetid: 524c7fd3-9b5c-46e7-99ba-555fd2fe33f0
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 99f2b7128ab984d023ce0aed73dd96167a661682
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57497137"
---
# <a name="ihostsyncmanagercreatemonitorevent-method"></a><span data-ttu-id="a8c0f-102">IHostSyncManager::CreateMonitorEvent (Método)</span><span class="sxs-lookup"><span data-stu-id="a8c0f-102">IHostSyncManager::CreateMonitorEvent Method</span></span>
<span data-ttu-id="a8c0f-103">Crea un objeto de evento de restablecimiento automático supervisado.</span><span class="sxs-lookup"><span data-stu-id="a8c0f-103">Creates a monitored auto-reset event object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a8c0f-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a8c0f-104">Syntax</span></span>  
  
```  
HRESULT CreateMonitorEvent (  
    [in]  SIZE_T cookie,  
    [out] IHostAutoEvent **ppEvent  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a8c0f-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a8c0f-105">Parameters</span></span>  
 `cookie`  
 <span data-ttu-id="a8c0f-106">[in] Una cookie para asociar el objeto de evento.</span><span class="sxs-lookup"><span data-stu-id="a8c0f-106">[in] A cookie to associate with the event object.</span></span>  
  
 `ppEvent`  
 <span data-ttu-id="a8c0f-107">[out] Un puntero a la dirección de un [IHostAutoEvent](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md) de instancia, o null si no se pudo crear el objeto de evento.</span><span class="sxs-lookup"><span data-stu-id="a8c0f-107">[out] A pointer to the address of an [IHostAutoEvent](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md) instance, or null if the event object could not be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a8c0f-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="a8c0f-108">Return Value</span></span>  
  
|<span data-ttu-id="a8c0f-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="a8c0f-109">HRESULT</span></span>|<span data-ttu-id="a8c0f-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="a8c0f-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a8c0f-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="a8c0f-111">S_OK</span></span>|<span data-ttu-id="a8c0f-112">`CreateMonitorEvent` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="a8c0f-112">`CreateMonitorEvent` returned successfully.</span></span>|  
|<span data-ttu-id="a8c0f-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="a8c0f-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="a8c0f-114">Common language runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="a8c0f-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="a8c0f-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="a8c0f-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="a8c0f-116">La llamada ha agotado el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="a8c0f-116">The call timed out.</span></span>|  
|<span data-ttu-id="a8c0f-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="a8c0f-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="a8c0f-118">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="a8c0f-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="a8c0f-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="a8c0f-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="a8c0f-120">Se canceló un evento mientras un subproceso bloqueado o fibra estaba esperando en ella.</span><span class="sxs-lookup"><span data-stu-id="a8c0f-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="a8c0f-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="a8c0f-121">E_FAIL</span></span>|<span data-ttu-id="a8c0f-122">Se ha producido un error irrecuperable desconocido.</span><span class="sxs-lookup"><span data-stu-id="a8c0f-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="a8c0f-123">Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="a8c0f-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="a8c0f-124">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="a8c0f-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="a8c0f-125">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="a8c0f-125">E_OUTOFMEMORY</span></span>|<span data-ttu-id="a8c0f-126">No había suficiente memoria disponible para crear el objeto de evento solicitado.</span><span class="sxs-lookup"><span data-stu-id="a8c0f-126">Not enough memory was available to create the requested event object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a8c0f-127">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a8c0f-127">Remarks</span></span>  
 <span data-ttu-id="a8c0f-128">`CreateMonitorEvent` Devuelve un `IHostAutoEvent` que CLR usa en su implementación de los recursos administrados <xref:System.Threading.Monitor?displayProperty=nameWithType> tipo.</span><span class="sxs-lookup"><span data-stu-id="a8c0f-128">`CreateMonitorEvent` returns an `IHostAutoEvent` that the CLR uses in its implementation of the managed <xref:System.Threading.Monitor?displayProperty=nameWithType> type.</span></span> <span data-ttu-id="a8c0f-129">Este método refleja Win32 `CreateEvent` función con un valor de `false` especificado para el `bManualReset` parámetro.</span><span class="sxs-lookup"><span data-stu-id="a8c0f-129">This method mirrors the Win32 `CreateEvent` function, with a value of `false` specified for the `bManualReset` parameter.</span></span>  
  
 <span data-ttu-id="a8c0f-130">El host puede utilizar la cookie para determinar qué tarea está esperando en el monitor mediante una llamada a la [ICLRSyncManager:: GetMonitorOwner](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-getmonitorowner-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="a8c0f-130">The host can use the cookie to determine which task is waiting on the monitor by calling the [ICLRSyncManager::GetMonitorOwner](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-getmonitorowner-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a8c0f-131">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a8c0f-131">Requirements</span></span>  
 <span data-ttu-id="a8c0f-132">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a8c0f-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a8c0f-133">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="a8c0f-133">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a8c0f-134">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a8c0f-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a8c0f-135">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a8c0f-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a8c0f-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="a8c0f-136">See also</span></span>
- [<span data-ttu-id="a8c0f-137">ICLRSyncManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="a8c0f-137">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="a8c0f-138">IHostAutoEvent (interfaz)</span><span class="sxs-lookup"><span data-stu-id="a8c0f-138">IHostAutoEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)
- [<span data-ttu-id="a8c0f-139">IHostSyncManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="a8c0f-139">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
- <xref:System.Threading.Monitor>
