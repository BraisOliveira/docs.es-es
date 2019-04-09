---
title: IHostSecurityManager::SetSecurityContext (Método)
ms.date: 03/30/2017
api_name:
- IHostSecurityManager.SetSecurityContext
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSecurityManager::SetSecurityContext
helpviewer_keywords:
- SetSecurityContext method [.NET Framework hosting]
- IHostSecurityManager::SetSecurityContext method [.NET Framework hosting]
ms.assetid: e4372384-ee69-48d7-97e0-8fab7866597a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d31aa0dfad70bed31bd72be5029c7bdff0925ba2
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59088567"
---
# <a name="ihostsecuritymanagersetsecuritycontext-method"></a><span data-ttu-id="27877-102">IHostSecurityManager::SetSecurityContext (Método)</span><span class="sxs-lookup"><span data-stu-id="27877-102">IHostSecurityManager::SetSecurityContext Method</span></span>
<span data-ttu-id="27877-103">Establece el contexto de seguridad del subproceso en ejecución actualmente.</span><span class="sxs-lookup"><span data-stu-id="27877-103">Sets the security context of the currently executing thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="27877-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="27877-104">Syntax</span></span>  
  
```  
HRESULT SetSecurityContext (  
    [in]  EContextType eContextType,  
    [out] IHostSecurityContext** ppSecurityContext  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="27877-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="27877-105">Parameters</span></span>  
 `eContextType`  
 <span data-ttu-id="27877-106">[in] Uno de los [EContextType](../../../../docs/framework/unmanaged-api/hosting/econtexttype-enumeration.md) valores, que indica qué tipo de contexto de common language runtime (CLR) está colocando en el host.</span><span class="sxs-lookup"><span data-stu-id="27877-106">[in] One of the [EContextType](../../../../docs/framework/unmanaged-api/hosting/econtexttype-enumeration.md) values, indicating what type of context the common language runtime (CLR) is placing on the host.</span></span>  
  
 `ppSecurityContext`  
 <span data-ttu-id="27877-107">[out] Un puntero a la dirección de un nuevo [IHostSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md) objeto.</span><span class="sxs-lookup"><span data-stu-id="27877-107">[out] A pointer to the address of a new [IHostSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md) object.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="27877-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="27877-108">Return Value</span></span>  
  
|<span data-ttu-id="27877-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="27877-109">HRESULT</span></span>|<span data-ttu-id="27877-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="27877-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="27877-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="27877-111">S_OK</span></span>|`SetSecurityContext` <span data-ttu-id="27877-112">se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="27877-112">returned successfully.</span></span>|  
|<span data-ttu-id="27877-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="27877-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="27877-114">El CLR no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="27877-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="27877-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="27877-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="27877-116">La llamada ha agotado el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="27877-116">The call timed out.</span></span>|  
|<span data-ttu-id="27877-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="27877-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="27877-118">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="27877-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="27877-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="27877-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="27877-120">Se canceló un evento mientras un subproceso bloqueado o fibra estaba esperando en ella.</span><span class="sxs-lookup"><span data-stu-id="27877-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="27877-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="27877-121">E_FAIL</span></span>|<span data-ttu-id="27877-122">Se ha producido un error irrecuperable desconocido.</span><span class="sxs-lookup"><span data-stu-id="27877-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="27877-123">Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="27877-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="27877-124">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="27877-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="27877-125">Comentarios</span><span class="sxs-lookup"><span data-stu-id="27877-125">Remarks</span></span>  
 <span data-ttu-id="27877-126">CLR llama a `SetSecurityContext` en varios escenarios.</span><span class="sxs-lookup"><span data-stu-id="27877-126">The CLR calls `SetSecurityContext` in several scenarios.</span></span> <span data-ttu-id="27877-127">Antes de ejecutar los finalizadores y los constructores de módulo y las clases, CLR llama `SetSecurityContext` para proteger el host de errores de ejecución.</span><span class="sxs-lookup"><span data-stu-id="27877-127">Before it executes class and module constructors and finalizers, the CLR calls `SetSecurityContext` to protect the host from execution failures.</span></span> <span data-ttu-id="27877-128">A continuación, restablece el contexto de seguridad a su estado original después de la ejecución del constructor o finalizador, utilizando otra llamada a `SetSecurityContext`.</span><span class="sxs-lookup"><span data-stu-id="27877-128">It then resets the security context to its original state after execution of the constructor or finalizer, by using another call to `SetSecurityContext`.</span></span> <span data-ttu-id="27877-129">Un patrón similar se produce con la finalización de E/S.</span><span class="sxs-lookup"><span data-stu-id="27877-129">A similar pattern occurs with I/O completion.</span></span> <span data-ttu-id="27877-130">Si el host implementa [IHostIoCompletionManager](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md), CLR llama a `SetSecurityContext` después el host llama [ICLRIoCompletionManager:: OnComplete](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-oncomplete-method.md).</span><span class="sxs-lookup"><span data-stu-id="27877-130">If the host implements [IHostIoCompletionManager](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md), the CLR calls `SetSecurityContext` after the host calls [ICLRIoCompletionManager::OnComplete](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-oncomplete-method.md).</span></span>  
  
 <span data-ttu-id="27877-131">En los puntos asincrónicos en subprocesos de trabajo, CLR llama `SetSecurityContext` en <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A?displayProperty=nameWithType> o dentro [IHostThreadPoolManager](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-queueuserworkitem-method.md), dependiendo de si el host o el CLR implementa el grupo de subprocesos.</span><span class="sxs-lookup"><span data-stu-id="27877-131">At asynchronous points in worker threads, the CLR calls `SetSecurityContext` within <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A?displayProperty=nameWithType> or within [IHostThreadPoolManager::QueueUserWorkItem](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-queueuserworkitem-method.md), depending on whether the host or the CLR is implementing the thread pool.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="27877-132">Requisitos</span><span class="sxs-lookup"><span data-stu-id="27877-132">Requirements</span></span>  
 <span data-ttu-id="27877-133">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="27877-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="27877-134">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="27877-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="27877-135">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="27877-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="27877-136">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="27877-136">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="27877-137">Vea también</span><span class="sxs-lookup"><span data-stu-id="27877-137">See also</span></span>

- <xref:System.Threading.ThreadPool?displayProperty=nameWithType>
- [<span data-ttu-id="27877-138">EContextType (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="27877-138">EContextType Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/econtexttype-enumeration.md)
- [<span data-ttu-id="27877-139">ICLRIoCompletionManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="27877-139">ICLRIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)
- [<span data-ttu-id="27877-140">IHostIoCompletionManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="27877-140">IHostIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)
- [<span data-ttu-id="27877-141">IHostSecurityContext (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="27877-141">IHostSecurityContext Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md)
- [<span data-ttu-id="27877-142">IHostSecurityManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="27877-142">IHostSecurityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-interface.md)
- [<span data-ttu-id="27877-143">IHostThreadPoolManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="27877-143">IHostThreadPoolManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)
