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
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59119267"
---
# <a name="icorruntimehoststop-method"></a><span data-ttu-id="81742-102">ICorRuntimeHost::Stop (Método)</span><span class="sxs-lookup"><span data-stu-id="81742-102">ICorRuntimeHost::Stop Method</span></span>
<span data-ttu-id="81742-103">Detiene la ejecución de código en tiempo de ejecución para el proceso actual.</span><span class="sxs-lookup"><span data-stu-id="81742-103">Stops the execution of code in the runtime for the current process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="81742-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="81742-104">Syntax</span></span>  
  
```  
HRESULT Stop ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="81742-105">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="81742-105">Return Value</span></span>  
  
|<span data-ttu-id="81742-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="81742-106">HRESULT</span></span>|<span data-ttu-id="81742-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="81742-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="81742-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="81742-108">S_OK</span></span>|<span data-ttu-id="81742-109">La operación fue correcta.</span><span class="sxs-lookup"><span data-stu-id="81742-109">The operation was successful.</span></span>|  
|<span data-ttu-id="81742-110">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="81742-110">S_FALSE</span></span>|<span data-ttu-id="81742-111">No se pudo completar la operación.</span><span class="sxs-lookup"><span data-stu-id="81742-111">The operation failed to complete.</span></span>|  
|<span data-ttu-id="81742-112">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="81742-112">E_FAIL</span></span>|<span data-ttu-id="81742-113">Se ha producido un error catastrófico desconocido.</span><span class="sxs-lookup"><span data-stu-id="81742-113">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="81742-114">Si el método devuelve E_FAIL, common language runtime (CLR) ya no es utilizable en el proceso.</span><span class="sxs-lookup"><span data-stu-id="81742-114">If a method returns E_FAIL, the common language runtime (CLR) is no longer usable in the process.</span></span> <span data-ttu-id="81742-115">Las llamadas subsiguientes a cualquier API de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="81742-115">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="81742-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="81742-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="81742-117">El CLR no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="81742-117">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="81742-118">Comentarios</span><span class="sxs-lookup"><span data-stu-id="81742-118">Remarks</span></span>  
 <span data-ttu-id="81742-119">Normalmente no es necesario llamar a la `Stop` método, porque el código deja de ejecutarse cuando finaliza el proceso.</span><span class="sxs-lookup"><span data-stu-id="81742-119">It is typically unnecessary to call the `Stop` method, because the code stops executing when the process exits.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="81742-120">Después de llamar a `Stop`, CLR no se pueden reinicializar en el mismo proceso.</span><span class="sxs-lookup"><span data-stu-id="81742-120">After a call to `Stop`, the CLR cannot be reinitialized into the same process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="81742-121">Requisitos</span><span class="sxs-lookup"><span data-stu-id="81742-121">Requirements</span></span>  
 <span data-ttu-id="81742-122">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="81742-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="81742-123">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="81742-123">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="81742-124">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="81742-124">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="81742-125">**Versiones de .NET framework:** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="81742-125">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="81742-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="81742-126">See also</span></span>

- [<span data-ttu-id="81742-127">ICorRuntimeHost (interfaz)</span><span class="sxs-lookup"><span data-stu-id="81742-127">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
