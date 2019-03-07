---
title: ICorRuntimeHost::UnloadDomain (Método)
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost.UnloadDomain
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::UnloadDomain
helpviewer_keywords:
- ICorRuntimeHost::UnloadDomain method [.NET Framework hosting]
- UnloadDomain method [.NET Framework hosting]
ms.assetid: dd9e9204-a80d-44f3-8192-779224b35056
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6773d9387ae3b91125b413dee51b0c3fcbbb1edd
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57502025"
---
# <a name="icorruntimehostunloaddomain-method"></a><span data-ttu-id="b5687-102">ICorRuntimeHost::UnloadDomain (Método)</span><span class="sxs-lookup"><span data-stu-id="b5687-102">ICorRuntimeHost::UnloadDomain Method</span></span>
<span data-ttu-id="b5687-103">Descarga el dominio de aplicación especificado del proceso actual.</span><span class="sxs-lookup"><span data-stu-id="b5687-103">Unloads the specified application domain from the current process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b5687-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b5687-104">Syntax</span></span>  
  
```  
HRESULT UnloadDomain (  
    [in] IUnknown* pAppDomain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b5687-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="b5687-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="b5687-106">[in] Un puntero de tipo <xref:System._AppDomain?displayProperty=nameWithType> que representa el dominio a punto de descargarse.</span><span class="sxs-lookup"><span data-stu-id="b5687-106">[in] A pointer of type <xref:System._AppDomain?displayProperty=nameWithType> that represents the domain to be unloaded.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b5687-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="b5687-107">Return Value</span></span>  
  
|<span data-ttu-id="b5687-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="b5687-108">HRESULT</span></span>|<span data-ttu-id="b5687-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="b5687-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="b5687-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="b5687-110">S_OK</span></span>|<span data-ttu-id="b5687-111">La operación fue correcta.</span><span class="sxs-lookup"><span data-stu-id="b5687-111">The operation was successful.</span></span>|  
|<span data-ttu-id="b5687-112">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="b5687-112">S_FALSE</span></span>|<span data-ttu-id="b5687-113">No se pudo completar la operación.</span><span class="sxs-lookup"><span data-stu-id="b5687-113">The operation failed to complete.</span></span>|  
|<span data-ttu-id="b5687-114">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="b5687-114">E_FAIL</span></span>|<span data-ttu-id="b5687-115">Se ha producido un error catastrófico desconocido.</span><span class="sxs-lookup"><span data-stu-id="b5687-115">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="b5687-116">Si el método devuelve E_FAIL, common language runtime (CLR) ya no es utilizable en el proceso.</span><span class="sxs-lookup"><span data-stu-id="b5687-116">If a method returns E_FAIL, the common language runtime (CLR) is no longer usable in the process.</span></span> <span data-ttu-id="b5687-117">Las llamadas subsiguientes a cualquier API de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="b5687-117">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="b5687-118">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="b5687-118">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="b5687-119">El CLR no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="b5687-119">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b5687-120">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b5687-120">Requirements</span></span>  
 <span data-ttu-id="b5687-121">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b5687-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b5687-122">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="b5687-122">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b5687-123">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b5687-123">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b5687-124">**Versión de .NET framework:** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="b5687-124">**.NET Framework Version:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b5687-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="b5687-125">See also</span></span>
- <xref:System._AppDomain>
- <xref:System.AppDomain>
- [<span data-ttu-id="b5687-126">ICorRuntimeHost (interfaz)</span><span class="sxs-lookup"><span data-stu-id="b5687-126">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
