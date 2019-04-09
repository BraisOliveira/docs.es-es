---
title: IHostIoCompletionManager::CloseIoCompletionPort (Método)
ms.date: 03/30/2017
api_name:
- IHostIoCompletionManager.CloseIoCompletionPort
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostIoCompletionManager::CloseIoCompletionPort
helpviewer_keywords:
- IHostIoCompletionManager::CloseIoCompletionPort method [.NET Framework hosting]
- CloseIoCompletionPort method [.NET Framework hosting]
ms.assetid: e86ad7be-3758-498a-a972-5522d69dfbb3
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 32a7c8b1c1c61eddb18ade1e77af5ea973fbaadc
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59107567"
---
# <a name="ihostiocompletionmanagercloseiocompletionport-method"></a><span data-ttu-id="b7ae9-102">IHostIoCompletionManager::CloseIoCompletionPort (Método)</span><span class="sxs-lookup"><span data-stu-id="b7ae9-102">IHostIoCompletionManager::CloseIoCompletionPort Method</span></span>
<span data-ttu-id="b7ae9-103">Solicita que el host cierre un puerto que se abrió a través de una llamada anterior a [CreateIoCompletionPort](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-createiocompletionport-method.md).</span><span class="sxs-lookup"><span data-stu-id="b7ae9-103">Requests that the host close a port that was opened through an earlier call to [CreateIoCompletionPort](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-createiocompletionport-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b7ae9-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b7ae9-104">Syntax</span></span>  
  
```  
HRESULT CloseIoCompletionPort (  
    [in] HANDLE hPort  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b7ae9-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="b7ae9-105">Parameters</span></span>  
 `hPort`  
 <span data-ttu-id="b7ae9-106">[in] El identificador del puerto que se va a cerrar.</span><span class="sxs-lookup"><span data-stu-id="b7ae9-106">[in] The handle of the port to close.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b7ae9-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="b7ae9-107">Return Value</span></span>  
  
|<span data-ttu-id="b7ae9-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="b7ae9-108">HRESULT</span></span>|<span data-ttu-id="b7ae9-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="b7ae9-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="b7ae9-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="b7ae9-110">S_OK</span></span>|`CloseIoCompletionPort` <span data-ttu-id="b7ae9-111">se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="b7ae9-111">returned successfully.</span></span>|  
|<span data-ttu-id="b7ae9-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="b7ae9-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="b7ae9-113">Common language runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="b7ae9-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="b7ae9-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="b7ae9-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="b7ae9-115">La llamada ha agotado el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="b7ae9-115">The call timed out.</span></span>|  
|<span data-ttu-id="b7ae9-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="b7ae9-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="b7ae9-117">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="b7ae9-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="b7ae9-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="b7ae9-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="b7ae9-119">Se canceló un evento mientras un subproceso bloqueado o fibra estaba esperando en ella.</span><span class="sxs-lookup"><span data-stu-id="b7ae9-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="b7ae9-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="b7ae9-120">E_FAIL</span></span>|<span data-ttu-id="b7ae9-121">Se ha producido un error irrecuperable desconocido.</span><span class="sxs-lookup"><span data-stu-id="b7ae9-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="b7ae9-122">Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="b7ae9-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="b7ae9-123">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="b7ae9-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="b7ae9-124">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="b7ae9-124">E_INVALIDARG</span></span>|<span data-ttu-id="b7ae9-125">Se pasó un identificador de puerto no válido.</span><span class="sxs-lookup"><span data-stu-id="b7ae9-125">An invalid port handle was passed.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b7ae9-126">Comentarios</span><span class="sxs-lookup"><span data-stu-id="b7ae9-126">Remarks</span></span>  
 `hPort` <span data-ttu-id="b7ae9-127">debe ser un identificador a un puerto que se creó mediante una llamada anterior a `CreateIoCompletionPort`.</span><span class="sxs-lookup"><span data-stu-id="b7ae9-127">must be a handle to a port that was created by an earlier call to `CreateIoCompletionPort`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b7ae9-128">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b7ae9-128">Requirements</span></span>  
 <span data-ttu-id="b7ae9-129">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b7ae9-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b7ae9-130">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="b7ae9-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b7ae9-131">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b7ae9-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="b7ae9-132">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="b7ae9-132">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="b7ae9-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="b7ae9-133">See also</span></span>

- [<span data-ttu-id="b7ae9-134">ICLRIoCompletionManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="b7ae9-134">ICLRIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)
- [<span data-ttu-id="b7ae9-135">IHostIoCompletionManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="b7ae9-135">IHostIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)
