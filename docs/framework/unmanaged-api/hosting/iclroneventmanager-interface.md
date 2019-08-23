---
title: ICLROnEventManager (Interfaz)
ms.date: 03/30/2017
api_name:
- ICLROnEventManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLROnEventManager
helpviewer_keywords:
- ICLROnEventManager interface [.NET Framework hosting]
ms.assetid: 9e15a0c1-8ab6-43d0-ae28-6ec7a4edd913
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3633db69877db771d919c9f43da4809f8321f77c
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69951199"
---
# <a name="iclroneventmanager-interface"></a><span data-ttu-id="be4ba-102">ICLROnEventManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="be4ba-102">ICLROnEventManager Interface</span></span>
<span data-ttu-id="be4ba-103">Proporciona métodos que permiten al host registrar y anular el registro de devoluciones de llamada para eventos de Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="be4ba-103">Provides methods that allow the host to register and unregister callbacks for common language runtime (CLR) events.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="be4ba-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="be4ba-104">Methods</span></span>  
  
|<span data-ttu-id="be4ba-105">Método</span><span class="sxs-lookup"><span data-stu-id="be4ba-105">Method</span></span>|<span data-ttu-id="be4ba-106">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="be4ba-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="be4ba-107">RegisterActionOnEvent (método)</span><span class="sxs-lookup"><span data-stu-id="be4ba-107">RegisterActionOnEvent Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-registeractiononevent-method.md)|<span data-ttu-id="be4ba-108">Registra un puntero de devolución de llamada para el evento especificado.</span><span class="sxs-lookup"><span data-stu-id="be4ba-108">Registers a callback pointer for the specified event.</span></span>|  
|[<span data-ttu-id="be4ba-109">UnregisterActionOnEvent (método)</span><span class="sxs-lookup"><span data-stu-id="be4ba-109">UnregisterActionOnEvent Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-unregisteractiononevent-method.md)|<span data-ttu-id="be4ba-110">Anula el registro de un puntero de devolución de llamada registrado previamente para el evento especificado.</span><span class="sxs-lookup"><span data-stu-id="be4ba-110">Unregisters a previously registered callback pointer for the specified event.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="be4ba-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="be4ba-111">Remarks</span></span>  
 <span data-ttu-id="be4ba-112">Para registrar y anular el registro de las devoluciones de llamada de `ICLROnEventManager` eventos, el host obtiene una referencia a llamando al método [ICLRControl:: GetCLRManager (](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-getclrmanager-method.md) .</span><span class="sxs-lookup"><span data-stu-id="be4ba-112">To register and unregister event callbacks, the host gets a reference to `ICLROnEventManager` by calling the [ICLRControl::GetCLRManager](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-getclrmanager-method.md) method.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="be4ba-113">Los eventos descritos por [EClrEvent](../../../../docs/framework/unmanaged-api/hosting/eclrevent-enumeration.md) se pueden desencadenar más de una vez y desde distintos subprocesos para indicar una descarga o la deshabilitación de CLR.</span><span class="sxs-lookup"><span data-stu-id="be4ba-113">The events described by [EClrEvent](../../../../docs/framework/unmanaged-api/hosting/eclrevent-enumeration.md) can be fired more than once and from different threads to signal an unload or the disabling of the CLR.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="be4ba-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="be4ba-114">Requirements</span></span>  
 <span data-ttu-id="be4ba-115">**Select** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="be4ba-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="be4ba-116">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="be4ba-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="be4ba-117">**Biblioteca** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="be4ba-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="be4ba-118">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="be4ba-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="be4ba-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="be4ba-119">See also</span></span>

- [<span data-ttu-id="be4ba-120">EClrEvent (enumeración)</span><span class="sxs-lookup"><span data-stu-id="be4ba-120">EClrEvent Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclrevent-enumeration.md)
- [<span data-ttu-id="be4ba-121">IActionOnCLREvent (interfaz)</span><span class="sxs-lookup"><span data-stu-id="be4ba-121">IActionOnCLREvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-interface.md)
- [<span data-ttu-id="be4ba-122">ICLRControl (interfaz)</span><span class="sxs-lookup"><span data-stu-id="be4ba-122">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="be4ba-123">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="be4ba-123">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
