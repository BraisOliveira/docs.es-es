---
title: ICLRAppDomainResourceMonitor::GetCurrentAllocated (Método)
ms.date: 03/30/2017
api_name:
- ICLRAppDomainResourceMonitor.GetCurrentAllocated
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRAppDomainResourceMonitor::GetCurrentAllocated
helpviewer_keywords:
- GetCurrentAllocated method [.NET Framework hosting]
- ICLRAppDomainResourceMonitor::GetCurrentAllocated method [.NET Framework hosting]
ms.assetid: 7bab209c-efd4-44c2-af30-61abab0ae2fc
topic_type:
- apiref
ms.openlocfilehash: f19ac39737d08c10c23ce0bde03131f52b660cac
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73126815"
---
# <a name="iclrappdomainresourcemonitorgetcurrentallocated-method"></a><span data-ttu-id="9d92b-102">ICLRAppDomainResourceMonitor::GetCurrentAllocated (Método)</span><span class="sxs-lookup"><span data-stu-id="9d92b-102">ICLRAppDomainResourceMonitor::GetCurrentAllocated Method</span></span>
<span data-ttu-id="9d92b-103">Obtiene el tamaño total, en bytes, de todas las asignaciones de memoria realizadas por el dominio de aplicación desde que se creó, sin restar la memoria que se ha recolectado como elemento no utilizado.</span><span class="sxs-lookup"><span data-stu-id="9d92b-103">Gets the total size, in bytes, of all memory allocations that have been made by the application domain since it was created, without subtracting memory that has been garbage-collected.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9d92b-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9d92b-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCurrentAllocated([in]  DWORD dwAppDomainId,  
                            [out] ULONGLONG* pBytesAllocated);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9d92b-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="9d92b-105">Parameters</span></span>  
 `dwAppDomainId`  
 <span data-ttu-id="9d92b-106">de IDENTIFICADOR del dominio de aplicación solicitado.</span><span class="sxs-lookup"><span data-stu-id="9d92b-106">[in] The ID of the requested application domain.</span></span>  
  
 `pBytesAllocated`  
 <span data-ttu-id="9d92b-107">enuncia Puntero al tamaño total de todas las asignaciones de memoria.</span><span class="sxs-lookup"><span data-stu-id="9d92b-107">[out] A pointer to the total size of all memory allocations.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9d92b-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="9d92b-108">Return Value</span></span>  
 <span data-ttu-id="9d92b-109">Este método devuelve los siguientes HRESULT específicos y los errores HRESULT que indican un error del método.</span><span class="sxs-lookup"><span data-stu-id="9d92b-109">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="9d92b-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="9d92b-110">HRESULT</span></span>|<span data-ttu-id="9d92b-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="9d92b-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="9d92b-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="9d92b-112">S_OK</span></span>|<span data-ttu-id="9d92b-113">El método se completó correctamente.</span><span class="sxs-lookup"><span data-stu-id="9d92b-113">The method completed successfully.</span></span>|  
|<span data-ttu-id="9d92b-114">COR_E_APPDOMAINUNLOADED</span><span class="sxs-lookup"><span data-stu-id="9d92b-114">COR_E_APPDOMAINUNLOADED</span></span>|<span data-ttu-id="9d92b-115">El dominio de aplicación se ha descargado o no existe.</span><span class="sxs-lookup"><span data-stu-id="9d92b-115">The application domain has been unloaded or does not exist.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9d92b-116">Comentarios</span><span class="sxs-lookup"><span data-stu-id="9d92b-116">Remarks</span></span>  
 <span data-ttu-id="9d92b-117">Este método es el equivalente no administrado de la propiedad <xref:System.AppDomain.MonitoringTotalAllocatedMemorySize%2A?displayProperty=nameWithType> administrada.</span><span class="sxs-lookup"><span data-stu-id="9d92b-117">This method is the unmanaged equivalent of the managed <xref:System.AppDomain.MonitoringTotalAllocatedMemorySize%2A?displayProperty=nameWithType> property.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9d92b-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9d92b-118">Requirements</span></span>  
 <span data-ttu-id="9d92b-119">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9d92b-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9d92b-120">**Encabezado:** Metahost. h</span><span class="sxs-lookup"><span data-stu-id="9d92b-120">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="9d92b-121">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="9d92b-121">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9d92b-122">**Versiones de .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9d92b-122">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9d92b-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="9d92b-123">See also</span></span>

- [<span data-ttu-id="9d92b-124">ICLRAppDomainResourceMonitor (interfaz)</span><span class="sxs-lookup"><span data-stu-id="9d92b-124">ICLRAppDomainResourceMonitor Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrappdomainresourcemonitor-interface.md)
- [<span data-ttu-id="9d92b-125">Supervisión de recursos de dominio de aplicación</span><span class="sxs-lookup"><span data-stu-id="9d92b-125">Application Domain Resource Monitoring</span></span>](../../../standard/garbage-collection/app-domain-resource-monitoring.md)
- [<span data-ttu-id="9d92b-126">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="9d92b-126">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="9d92b-127">Hospedar aplicaciones de WPF</span><span class="sxs-lookup"><span data-stu-id="9d92b-127">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
