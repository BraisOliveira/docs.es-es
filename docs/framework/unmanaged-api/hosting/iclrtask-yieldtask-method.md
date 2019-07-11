---
title: ICLRTask::YieldTask (Método)
ms.date: 03/30/2017
api_name:
- ICLRTask.YieldTask
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTask::YieldTask
helpviewer_keywords:
- ICLRTask::YieldTask method [.NET Framework hosting]
- YieldTask method [.NET Framework hosting]
ms.assetid: b8eb4095-3a8f-4be3-9446-63e9893dce7d
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6fde9586c1b3736b5db2c4814058dd23713dd34d
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67770334"
---
# <a name="iclrtaskyieldtask-method"></a><span data-ttu-id="2d9dd-102">ICLRTask::YieldTask (Método)</span><span class="sxs-lookup"><span data-stu-id="2d9dd-102">ICLRTask::YieldTask Method</span></span>
<span data-ttu-id="2d9dd-103">Solicita que common language runtime (CLR) aparte la tarea que actual [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) representa la instancia y que el tiempo de procesador esté disponible para otras tareas.</span><span class="sxs-lookup"><span data-stu-id="2d9dd-103">Requests that the common language runtime (CLR) put aside the task that the current [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instance represents, and make the processor time available to other tasks.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2d9dd-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2d9dd-104">Syntax</span></span>  
  
```cpp  
HRESULT YieldTask ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="2d9dd-105">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="2d9dd-105">Return Value</span></span>  
  
|<span data-ttu-id="2d9dd-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="2d9dd-106">HRESULT</span></span>|<span data-ttu-id="2d9dd-107">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="2d9dd-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="2d9dd-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="2d9dd-108">S_OK</span></span>|<span data-ttu-id="2d9dd-109">`YieldTask` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="2d9dd-109">`YieldTask` returned successfully.</span></span>|  
|<span data-ttu-id="2d9dd-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="2d9dd-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="2d9dd-111">El CLR no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="2d9dd-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="2d9dd-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="2d9dd-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="2d9dd-113">La llamada ha agotado el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="2d9dd-113">The call timed out.</span></span>|  
|<span data-ttu-id="2d9dd-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="2d9dd-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="2d9dd-115">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="2d9dd-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="2d9dd-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="2d9dd-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="2d9dd-117">Se canceló un evento mientras un subproceso bloqueado o fibra estaba esperando en ella.</span><span class="sxs-lookup"><span data-stu-id="2d9dd-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="2d9dd-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="2d9dd-118">E_FAIL</span></span>|<span data-ttu-id="2d9dd-119">Se ha producido un error irrecuperable desconocido.</span><span class="sxs-lookup"><span data-stu-id="2d9dd-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="2d9dd-120">Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="2d9dd-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="2d9dd-121">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="2d9dd-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2d9dd-122">Comentarios</span><span class="sxs-lookup"><span data-stu-id="2d9dd-122">Remarks</span></span>  
 <span data-ttu-id="2d9dd-123">Un host llama `YieldTask` para solicitar recursos del procesador para otras tareas o procesos.</span><span class="sxs-lookup"><span data-stu-id="2d9dd-123">A host calls `YieldTask` to request processor resources for other tasks or processes.</span></span> <span data-ttu-id="2d9dd-124">Este método está pensado principalmente para permitir que el código de ejecución prolongada dar tiempo de CPU.</span><span class="sxs-lookup"><span data-stu-id="2d9dd-124">This method is primarily intended to allow long-running code to give up CPU time.</span></span> <span data-ttu-id="2d9dd-125">El tiempo de ejecución intenta colocar la tarea que actual `ICLRTask` instancia representa un estado donde se puede producir tiempo de procesamiento, pero no otorga ninguna garantía de éxito.</span><span class="sxs-lookup"><span data-stu-id="2d9dd-125">The runtime attempts to put the task that the current `ICLRTask` instance represents in a state where it can yield processing time, but makes no guarantee of success.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2d9dd-126">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2d9dd-126">Requirements</span></span>  
 <span data-ttu-id="2d9dd-127">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2d9dd-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2d9dd-128">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="2d9dd-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="2d9dd-129">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="2d9dd-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2d9dd-130">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2d9dd-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2d9dd-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="2d9dd-131">See also</span></span>

- [<span data-ttu-id="2d9dd-132">ICLRTask (interfaz)</span><span class="sxs-lookup"><span data-stu-id="2d9dd-132">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="2d9dd-133">ICLRTaskManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="2d9dd-133">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="2d9dd-134">IHostTask (interfaz)</span><span class="sxs-lookup"><span data-stu-id="2d9dd-134">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="2d9dd-135">IHostTaskManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="2d9dd-135">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
