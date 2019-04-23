---
title: IHostAssemblyManager (Interfaz)
ms.date: 03/30/2017
api_name:
- IHostAssemblyManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostAssemblyManager
helpviewer_keywords:
- IHostAssemblyManager interface [.NET Framework hosting]
ms.assetid: dfec05bb-3cd7-4bd5-b396-a4f097c3a636
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2e300d4645939a131ceb8206999d95056b96a678
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59118955"
---
# <a name="ihostassemblymanager-interface"></a><span data-ttu-id="a0474-102">IHostAssemblyManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="a0474-102">IHostAssemblyManager Interface</span></span>
<span data-ttu-id="a0474-103">Proporciona métodos que permiten a un host especificar conjuntos de ensamblados que se deben cargar common language runtime (CLR) o el host.</span><span class="sxs-lookup"><span data-stu-id="a0474-103">Provides methods that allow a host to specify sets of assemblies that should be loaded by the common language runtime (CLR) or by the host.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a0474-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="a0474-104">Methods</span></span>  
  
|<span data-ttu-id="a0474-105">Método</span><span class="sxs-lookup"><span data-stu-id="a0474-105">Method</span></span>|<span data-ttu-id="a0474-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="a0474-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a0474-107">GetAssemblyStore (método)</span><span class="sxs-lookup"><span data-stu-id="a0474-107">GetAssemblyStore Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-getassemblystore-method.md)|<span data-ttu-id="a0474-108">Obtiene un puntero de interfaz a un [IHostAssemblyStore](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md) que representa la lista de ensamblados cargados por el host.</span><span class="sxs-lookup"><span data-stu-id="a0474-108">Gets an interface pointer to an [IHostAssemblyStore](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md) that represents the list of assemblies loaded by the host.</span></span>|  
|[<span data-ttu-id="a0474-109">GetNonHostStoreAssemblies (método)</span><span class="sxs-lookup"><span data-stu-id="a0474-109">GetNonHostStoreAssemblies Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-getnonhoststoreassemblies-method.md)|<span data-ttu-id="a0474-110">Obtiene un puntero de interfaz a un [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) que representa la lista de ensamblados que el host espera que CLR cargue.</span><span class="sxs-lookup"><span data-stu-id="a0474-110">Gets an interface pointer to an [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) that represents the list of assemblies that the host expects the CLR to load.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a0474-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a0474-111">Remarks</span></span>  
 <span data-ttu-id="a0474-112">El host no es necesario implementar `IHostAssemblyManager` o `IHostAssemblyStore`.</span><span class="sxs-lookup"><span data-stu-id="a0474-112">The host is not required to implement `IHostAssemblyManager` or `IHostAssemblyStore`.</span></span> <span data-ttu-id="a0474-113">Si el host implementa `IHostAssemblyManager`, también debe implementar `IHostAssemblyStore`.</span><span class="sxs-lookup"><span data-stu-id="a0474-113">If the host does implement `IHostAssemblyManager`, it must also implement `IHostAssemblyStore`.</span></span>  
  
 <span data-ttu-id="a0474-114">El tiempo de ejecución de consultas para un `IHostAssemblyManager` mediante una llamada a [IHostControl](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-gethostmanager-method.md) tras la inicialización con una `IID` de IID_IHostAssemblyManager.</span><span class="sxs-lookup"><span data-stu-id="a0474-114">The runtime queries for an `IHostAssemblyManager` by calling [IHostControl::GetHostManager](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-gethostmanager-method.md) upon initialization with an `IID` of IID_IHostAssemblyManager.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a0474-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a0474-115">Requirements</span></span>  
 <span data-ttu-id="a0474-116">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a0474-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a0474-117">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="a0474-117">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a0474-118">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a0474-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a0474-119">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a0474-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a0474-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="a0474-120">See also</span></span>

- [<span data-ttu-id="a0474-121">ICLRAssemblyReferenceList (interfaz)</span><span class="sxs-lookup"><span data-stu-id="a0474-121">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="a0474-122">IHostAssemblyStore (interfaz)</span><span class="sxs-lookup"><span data-stu-id="a0474-122">IHostAssemblyStore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)
- [<span data-ttu-id="a0474-123">IHostControl (interfaz)</span><span class="sxs-lookup"><span data-stu-id="a0474-123">IHostControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)
- [<span data-ttu-id="a0474-124">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="a0474-124">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
