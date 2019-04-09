---
title: ICorRuntimeHost::Stop (Método)
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost.Stop
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::Stop
helpviewer_keywords:
- Stop method, ICorRuntimeHost interface [.NET Framework hosting]
- ICorRuntimeHost::Stop method [.NET Framework hosting]
ms.assetid: 46a0d450-b516-4bef-8b71-8d3bf265cbed
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3c59a0c5ef1e89c2853a566bd3b587d15a1ed80c
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59119267"
---
# <a name="icorruntimehoststop-method"></a><span data-ttu-id="19c3a-102">ICorRuntimeHost::Stop (Método)</span><span class="sxs-lookup"><span data-stu-id="19c3a-102">ICorRuntimeHost::Stop Method</span></span>
<span data-ttu-id="19c3a-103">Detiene la ejecución de código en tiempo de ejecución para el proceso actual.</span><span class="sxs-lookup"><span data-stu-id="19c3a-103">Stops the execution of code in the runtime for the current process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="19c3a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="19c3a-104">Syntax</span></span>  
  
```  
HRESULT Stop ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="19c3a-105">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="19c3a-105">Return Value</span></span>  
  
|<span data-ttu-id="19c3a-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="19c3a-106">HRESULT</span></span>|<span data-ttu-id="19c3a-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="19c3a-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="19c3a-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="19c3a-108">S_OK</span></span>|<span data-ttu-id="19c3a-109">La operación fue correcta.</span><span class="sxs-lookup"><span data-stu-id="19c3a-109">The operation was successful.</span></span>|  
|<span data-ttu-id="19c3a-110">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="19c3a-110">S_FALSE</span></span>|<span data-ttu-id="19c3a-111">No se pudo completar la operación.</span><span class="sxs-lookup"><span data-stu-id="19c3a-111">The operation failed to complete.</span></span>|  
|<span data-ttu-id="19c3a-112">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="19c3a-112">E_FAIL</span></span>|<span data-ttu-id="19c3a-113">Se ha producido un error catastrófico desconocido.</span><span class="sxs-lookup"><span data-stu-id="19c3a-113">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="19c3a-114">Si el método devuelve E_FAIL, common language runtime (CLR) ya no es utilizable en el proceso.</span><span class="sxs-lookup"><span data-stu-id="19c3a-114">If a method returns E_FAIL, the common language runtime (CLR) is no longer usable in the process.</span></span> <span data-ttu-id="19c3a-115">Las llamadas subsiguientes a cualquier API de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="19c3a-115">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="19c3a-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="19c3a-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="19c3a-117">El CLR no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="19c3a-117">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="19c3a-118">Comentarios</span><span class="sxs-lookup"><span data-stu-id="19c3a-118">Remarks</span></span>  
 <span data-ttu-id="19c3a-119">Normalmente no es necesario llamar a la `Stop` método, porque el código deja de ejecutarse cuando finaliza el proceso.</span><span class="sxs-lookup"><span data-stu-id="19c3a-119">It is typically unnecessary to call the `Stop` method, because the code stops executing when the process exits.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="19c3a-120">Después de llamar a `Stop`, CLR no se pueden reinicializar en el mismo proceso.</span><span class="sxs-lookup"><span data-stu-id="19c3a-120">After a call to `Stop`, the CLR cannot be reinitialized into the same process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="19c3a-121">Requisitos</span><span class="sxs-lookup"><span data-stu-id="19c3a-121">Requirements</span></span>  
 <span data-ttu-id="19c3a-122">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="19c3a-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="19c3a-123">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="19c3a-123">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="19c3a-124">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="19c3a-124">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="19c3a-125">**Versiones de .NET framework:** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="19c3a-125">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="19c3a-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="19c3a-126">See also</span></span>

- [<span data-ttu-id="19c3a-127">ICorRuntimeHost (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="19c3a-127">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
