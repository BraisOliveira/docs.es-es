---
title: ICLRTask::SetTaskIdentifier (Método)
ms.date: 03/30/2017
api_name:
- ICLRTask.SetTaskIdentifier
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTask::SetTaskIdentifier
helpviewer_keywords:
- SetTaskIdentifier method [.NET Framework hosting]
- ICLRTask::SetTaskIdentifier method [.NET Framework hosting]
ms.assetid: bdb7f047-1e90-40fc-9e3b-d44a16509073
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 58a010def407751a49cbb1de51c59a3df85cfb18
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57487778"
---
# <a name="iclrtasksettaskidentifier-method"></a><span data-ttu-id="0f949-102">ICLRTask::SetTaskIdentifier (Método)</span><span class="sxs-lookup"><span data-stu-id="0f949-102">ICLRTask::SetTaskIdentifier Method</span></span>
<span data-ttu-id="0f949-103">Indica a common language runtime (CLR) para asociar el valor de identificador especificado a la tarea actual [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instancia.</span><span class="sxs-lookup"><span data-stu-id="0f949-103">Instructs the common language runtime (CLR) to associate the specified identifier value with the task represented by the current [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0f949-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0f949-104">Syntax</span></span>  
  
```  
HRESULT SetTaskIdentifier (  
    [in] DWORD Asked  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0f949-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="0f949-105">Parameters</span></span>  
 `Asked`  
 <span data-ttu-id="0f949-106">[in] El identificador único para common language runtime asociar a la tarea representada por el actual `ICLRTask` instancia.</span><span class="sxs-lookup"><span data-stu-id="0f949-106">[in] The unique identifier for the common language runtime to associate with the task represented by the current `ICLRTask` instance.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0f949-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="0f949-107">Return Value</span></span>  
  
|<span data-ttu-id="0f949-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="0f949-108">HRESULT</span></span>|<span data-ttu-id="0f949-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="0f949-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="0f949-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="0f949-110">S_OK</span></span>|<span data-ttu-id="0f949-111">`SetTaskIdentifier` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="0f949-111">`SetTaskIdentifier` returned successfully.</span></span>|  
|<span data-ttu-id="0f949-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="0f949-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="0f949-113">El CLR no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="0f949-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="0f949-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="0f949-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="0f949-115">La llamada ha agotado el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="0f949-115">The call timed out.</span></span>|  
|<span data-ttu-id="0f949-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="0f949-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="0f949-117">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="0f949-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="0f949-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="0f949-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="0f949-119">Se canceló un evento mientras un subproceso bloqueado o fibra estaba esperando en ella.</span><span class="sxs-lookup"><span data-stu-id="0f949-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="0f949-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="0f949-120">E_FAIL</span></span>|<span data-ttu-id="0f949-121">Se ha producido un error irrecuperable desconocido.</span><span class="sxs-lookup"><span data-stu-id="0f949-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="0f949-122">Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="0f949-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="0f949-123">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="0f949-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0f949-124">Comentarios</span><span class="sxs-lookup"><span data-stu-id="0f949-124">Remarks</span></span>  
 <span data-ttu-id="0f949-125">El host puede asociar un identificador a una tarea para ayudar a integrar CLR y el host en un entorno de depuración.</span><span class="sxs-lookup"><span data-stu-id="0f949-125">The host can associate an identifier with a task to help integrate the CLR and the host in a debugging environment.</span></span> <span data-ttu-id="0f949-126">El identificador no tiene ningún significado para CLR.</span><span class="sxs-lookup"><span data-stu-id="0f949-126">The identifier has no meaning for the CLR.</span></span> <span data-ttu-id="0f949-127">El CLR lo pasa a la aplicación del depurador.</span><span class="sxs-lookup"><span data-stu-id="0f949-127">The CLR passes it along to a debugger application.</span></span> <span data-ttu-id="0f949-128">El depurador puede usar este identificador para asociar una pila de llamadas CLR a una pila de llamadas de host y habilitar su información de seguimiento correspondiente cuando se ve en la interfaz de usuario del depurador.</span><span class="sxs-lookup"><span data-stu-id="0f949-128">The debugger can use this identifier to associate a CLR call stack with a host call stack, and enable their respective trace information to be unified when viewed in the debugger's user interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0f949-129">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0f949-129">Requirements</span></span>  
 <span data-ttu-id="0f949-130">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0f949-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0f949-131">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="0f949-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="0f949-132">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="0f949-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0f949-133">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0f949-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0f949-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="0f949-134">See also</span></span>
- [<span data-ttu-id="0f949-135">ICLRTask (interfaz)</span><span class="sxs-lookup"><span data-stu-id="0f949-135">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="0f949-136">ICLRTaskManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="0f949-136">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="0f949-137">IHostTask (interfaz)</span><span class="sxs-lookup"><span data-stu-id="0f949-137">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="0f949-138">IHostTaskManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="0f949-138">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
