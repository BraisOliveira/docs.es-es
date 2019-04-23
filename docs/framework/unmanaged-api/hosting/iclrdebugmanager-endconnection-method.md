---
title: ICLRDebugManager::EndConnection (Método)
ms.date: 03/30/2017
api_name:
- ICLRDebugManager.EndConnection
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRDebugManager::EndConnection
helpviewer_keywords:
- ICLRDebugManager::EndConnection method [.NET Framework hosting]
- EndConnection method [.NET Framework hosting]
ms.assetid: 89dc7363-2f29-4eb2-8f23-fccdda6a76a6
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cf21e1844ea99b231054f8350ddacb8bb707a94e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59200120"
---
# <a name="iclrdebugmanagerendconnection-method"></a><span data-ttu-id="c37b9-102">ICLRDebugManager::EndConnection (Método)</span><span class="sxs-lookup"><span data-stu-id="c37b9-102">ICLRDebugManager::EndConnection Method</span></span>
<span data-ttu-id="c37b9-103">Quita la asociación entre una lista de tareas y un identificador y un nombre descriptivo.</span><span class="sxs-lookup"><span data-stu-id="c37b9-103">Removes the association between a list of tasks and an identifier and a friendly name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c37b9-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c37b9-104">Syntax</span></span>  
  
```  
HRESULT EndConnection (  
    [in] CONNID dwConnectionId  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c37b9-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c37b9-105">Parameters</span></span>  
 `dwConnectionId`  
 <span data-ttu-id="c37b9-106">[in] El identificador de host específico para la conexión y la lista asociada de tareas de common language runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="c37b9-106">[in] The host-specific identifier for the connection and the associated list of common language runtime (CLR) tasks.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c37b9-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="c37b9-107">Return Value</span></span>  
  
|<span data-ttu-id="c37b9-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c37b9-108">HRESULT</span></span>|<span data-ttu-id="c37b9-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="c37b9-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c37b9-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="c37b9-110">S_OK</span></span>|<span data-ttu-id="c37b9-111">`EndConnection` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="c37b9-111">`EndConnection` returned successfully.</span></span>|  
|<span data-ttu-id="c37b9-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="c37b9-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="c37b9-113">El CLR no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="c37b9-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="c37b9-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="c37b9-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="c37b9-115">La llamada ha agotado el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="c37b9-115">The call timed out.</span></span>|  
|<span data-ttu-id="c37b9-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="c37b9-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="c37b9-117">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="c37b9-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="c37b9-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="c37b9-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="c37b9-119">Se canceló un evento mientras un subproceso bloqueado o fibra estaba esperando en ella.</span><span class="sxs-lookup"><span data-stu-id="c37b9-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="c37b9-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="c37b9-120">E_FAIL</span></span>|<span data-ttu-id="c37b9-121">Se ha producido un error irrecuperable desconocido.</span><span class="sxs-lookup"><span data-stu-id="c37b9-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="c37b9-122">Después de un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="c37b9-122">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="c37b9-123">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="c37b9-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="c37b9-124">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="c37b9-124">E_INVALIDARG</span></span>|<span data-ttu-id="c37b9-125">[BeginConnection](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-beginconnection-method.md) nunca se llamó mediante `dwConnectionId`, o `dwConnectionId` es cero.</span><span class="sxs-lookup"><span data-stu-id="c37b9-125">[BeginConnection](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-beginconnection-method.md) was never called using `dwConnectionId`, or `dwConnectionId` was zero.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c37b9-126">Comentarios</span><span class="sxs-lookup"><span data-stu-id="c37b9-126">Remarks</span></span>  
 <span data-ttu-id="c37b9-127">[ICLRDebugManager](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md) proporciona tres métodos, `BeginConnection`, [SetConnectionTasks](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setconnectiontasks-method.md), y `EndConnection`, para asociar listas de tareas con identificadores y nombres descriptivos.</span><span class="sxs-lookup"><span data-stu-id="c37b9-127">[ICLRDebugManager](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md) provides three methods, `BeginConnection`, [SetConnectionTasks](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setconnectiontasks-method.md), and `EndConnection`, for associating task lists with identifiers and friendly names.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="c37b9-128">Estos tres métodos deben llamarse en un orden específico para cada conjunto de tareas.</span><span class="sxs-lookup"><span data-stu-id="c37b9-128">These three methods must be called in a specific order for each set of tasks.</span></span> <span data-ttu-id="c37b9-129">`BeginConnection` se llama en primer lugar para establecer una conexión nueva.</span><span class="sxs-lookup"><span data-stu-id="c37b9-129">`BeginConnection` is called first to establish a new connection.</span></span> <span data-ttu-id="c37b9-130">`SetConnectionTasks` se llama a continuación para proporcionar el conjunto de tareas que se asociará con esa conexión.</span><span class="sxs-lookup"><span data-stu-id="c37b9-130">`SetConnectionTasks` is called next to provide the set of tasks to be associated with that connection.</span></span> <span data-ttu-id="c37b9-131">`EndConnection` se llama en último lugar para quitar la asociación entre la lista de tareas y el identificador y el nombre descriptivo. Sin embargo, se pueden anidar llamadas para las conexiones diferentes.</span><span class="sxs-lookup"><span data-stu-id="c37b9-131">`EndConnection` is called last to remove the association between the task list and the identifier and friendly name.However, calls for different connections can be nested.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c37b9-132">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c37b9-132">Requirements</span></span>  
 <span data-ttu-id="c37b9-133">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c37b9-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c37b9-134">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="c37b9-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c37b9-135">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="c37b9-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c37b9-136">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c37b9-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c37b9-137">Vea también</span><span class="sxs-lookup"><span data-stu-id="c37b9-137">See also</span></span>

- [<span data-ttu-id="c37b9-138">ICLRControl (interfaz)</span><span class="sxs-lookup"><span data-stu-id="c37b9-138">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="c37b9-139">ICLRDebugManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="c37b9-139">ICLRDebugManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md)
- [<span data-ttu-id="c37b9-140">BeginConnection (método)</span><span class="sxs-lookup"><span data-stu-id="c37b9-140">BeginConnection Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-beginconnection-method.md)
- [<span data-ttu-id="c37b9-141">SetConnectionTasks (método)</span><span class="sxs-lookup"><span data-stu-id="c37b9-141">SetConnectionTasks Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setconnectiontasks-method.md)
- [<span data-ttu-id="c37b9-142">IHostControl (interfaz)</span><span class="sxs-lookup"><span data-stu-id="c37b9-142">IHostControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)
