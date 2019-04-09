---
title: ICLRTask::ExitTask (Método)
ms.date: 03/30/2017
api_name:
- ICLRTask.ExitTask
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTask::ExitTask
helpviewer_keywords:
- ExitTask method [.NET Framework hosting]
- ICLRTask::ExitTask method [.NET Framework hosting]
ms.assetid: 746c85a6-4b33-4f72-a2e9-379fdf2e96af
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6a55b62c7c71510435b980a4e5938c20628046f4
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59075892"
---
# <a name="iclrtaskexittask-method"></a><span data-ttu-id="dd7c6-102">ICLRTask::ExitTask (Método)</span><span class="sxs-lookup"><span data-stu-id="dd7c6-102">ICLRTask::ExitTask Method</span></span>
<span data-ttu-id="dd7c6-103">Notifica a common language runtime (CLR) que la tarea representada por el actual [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instancia está finalizando e intenta cerrar la tarea correctamente.</span><span class="sxs-lookup"><span data-stu-id="dd7c6-103">Notifies the common language runtime (CLR) that the task represented by the current [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instance is ending, and attempts to shut the task down gracefully.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dd7c6-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="dd7c6-104">Syntax</span></span>  
  
```  
HRESULT ExitTask ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="dd7c6-105">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="dd7c6-105">Return Value</span></span>  
  
|<span data-ttu-id="dd7c6-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="dd7c6-106">HRESULT</span></span>|<span data-ttu-id="dd7c6-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="dd7c6-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="dd7c6-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="dd7c6-108">S_OK</span></span>|`ExitTask` <span data-ttu-id="dd7c6-109">se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="dd7c6-109">returned successfully.</span></span>|  
|<span data-ttu-id="dd7c6-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="dd7c6-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="dd7c6-111">El CLR no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="dd7c6-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="dd7c6-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="dd7c6-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="dd7c6-113">La llamada ha agotado el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="dd7c6-113">The call timed out.</span></span>|  
|<span data-ttu-id="dd7c6-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="dd7c6-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="dd7c6-115">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="dd7c6-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="dd7c6-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="dd7c6-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="dd7c6-117">Se canceló un evento mientras un subproceso bloqueado o fibra estaba esperando en ella.</span><span class="sxs-lookup"><span data-stu-id="dd7c6-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="dd7c6-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="dd7c6-118">E_FAIL</span></span>|<span data-ttu-id="dd7c6-119">Se ha producido un error irrecuperable desconocido.</span><span class="sxs-lookup"><span data-stu-id="dd7c6-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="dd7c6-120">Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="dd7c6-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="dd7c6-121">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="dd7c6-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="dd7c6-122">Comentarios</span><span class="sxs-lookup"><span data-stu-id="dd7c6-122">Remarks</span></span>  
 `ExitTask` <span data-ttu-id="dd7c6-123">intentos de cierre de una tarea, de forma análoga a una biblioteca de tipos no administrados se desasocia un subproceso.</span><span class="sxs-lookup"><span data-stu-id="dd7c6-123">attempts a clean shutdown of a task, in a manner analogous to detaching a thread from an unmanaged type library.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dd7c6-124">Requisitos</span><span class="sxs-lookup"><span data-stu-id="dd7c6-124">Requirements</span></span>  
 <span data-ttu-id="dd7c6-125">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dd7c6-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dd7c6-126">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="dd7c6-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="dd7c6-127">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="dd7c6-127">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="dd7c6-128">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="dd7c6-128">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="dd7c6-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="dd7c6-129">See also</span></span>

- [<span data-ttu-id="dd7c6-130">ICLRTask (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="dd7c6-130">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="dd7c6-131">ICLRTaskManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="dd7c6-131">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="dd7c6-132">IHostTask (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="dd7c6-132">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="dd7c6-133">IHostTaskManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="dd7c6-133">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
