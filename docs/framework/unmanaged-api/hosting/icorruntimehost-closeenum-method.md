---
title: ICorRuntimeHost::CloseEnum (Método)
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost.CloseEnum
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::CloseEnum
helpviewer_keywords:
- CloseEnum method, ICorRuntimeHost interface [.NET Framework hosting]
- ICorRuntimeHost::CloseEnum method [.NET Framework hosting]
ms.assetid: f7ce7e8c-0a3e-4587-a180-063e2b85940e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f150fe80302cd03e872ca8bdf5d172caae1ce599
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61967687"
---
# <a name="icorruntimehostcloseenum-method"></a><span data-ttu-id="22b86-102">ICorRuntimeHost::CloseEnum (Método)</span><span class="sxs-lookup"><span data-stu-id="22b86-102">ICorRuntimeHost::CloseEnum Method</span></span>
<span data-ttu-id="22b86-103">Restablece un enumerador de dominio al principio de la lista de dominios.</span><span class="sxs-lookup"><span data-stu-id="22b86-103">Resets a domain enumerator back to the beginning of the domain list.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="22b86-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="22b86-104">Syntax</span></span>  
  
```  
HRESULT CloseEnum (  
    [in] HCORENUM hEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="22b86-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="22b86-105">Parameters</span></span>  
 `hEnum`  
 <span data-ttu-id="22b86-106">[in] Para restablecer el enumerador.</span><span class="sxs-lookup"><span data-stu-id="22b86-106">[in] The enumerator to reset.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="22b86-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="22b86-107">Return Value</span></span>  
  
|<span data-ttu-id="22b86-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="22b86-108">HRESULT</span></span>|<span data-ttu-id="22b86-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="22b86-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="22b86-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="22b86-110">S_OK</span></span>|<span data-ttu-id="22b86-111">La operación fue correcta.</span><span class="sxs-lookup"><span data-stu-id="22b86-111">The operation was successful.</span></span>|  
|<span data-ttu-id="22b86-112">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="22b86-112">S_FALSE</span></span>|<span data-ttu-id="22b86-113">No se pudo completar la operación.</span><span class="sxs-lookup"><span data-stu-id="22b86-113">The operation failed to complete.</span></span>|  
|<span data-ttu-id="22b86-114">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="22b86-114">E_FAIL</span></span>|<span data-ttu-id="22b86-115">Se ha producido un error catastrófico desconocido.</span><span class="sxs-lookup"><span data-stu-id="22b86-115">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="22b86-116">Si el método devuelve E_FAIL, common language runtime (CLR) ya no es utilizable en el proceso.</span><span class="sxs-lookup"><span data-stu-id="22b86-116">If a method returns E_FAIL, the common language runtime (CLR) is no longer usable in the process.</span></span> <span data-ttu-id="22b86-117">Las llamadas subsiguientes a cualquier API de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="22b86-117">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="22b86-118">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="22b86-118">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="22b86-119">El CLR no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="22b86-119">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="22b86-120">Requisitos</span><span class="sxs-lookup"><span data-stu-id="22b86-120">Requirements</span></span>  
 <span data-ttu-id="22b86-121">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="22b86-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="22b86-122">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="22b86-122">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="22b86-123">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="22b86-123">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="22b86-124">**Versiones de .NET framework:** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="22b86-124">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="22b86-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="22b86-125">See also</span></span>

- [<span data-ttu-id="22b86-126">CorBindToRuntimeEx (función)</span><span class="sxs-lookup"><span data-stu-id="22b86-126">CorBindToRuntimeEx Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)
- [<span data-ttu-id="22b86-127">ICorRuntimeHost (interfaz)</span><span class="sxs-lookup"><span data-stu-id="22b86-127">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
