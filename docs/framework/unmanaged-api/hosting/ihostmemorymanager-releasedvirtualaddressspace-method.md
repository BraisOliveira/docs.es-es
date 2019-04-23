---
title: IHostMemoryManager::ReleasedVirtualAddressSpace (Método)
ms.date: 03/30/2017
api_name:
- IHostMemoryManager.ReleasedVirtualAddressSpace
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostMemoryManager::ReleasedVirtualAddressSpace
helpviewer_keywords:
- ReleasedVirtualAddressSpace method [.NET Framework hosting]
- IHostMemoryManager::ReleasedVirtualAddressSpace method [.NET Framework hosting]
ms.assetid: d1876601-6ab9-48e1-8ebd-184af1d0cd76
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0acbf4163e98b1171510260c4fac72c3d6f6fb1d
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59189292"
---
# <a name="ihostmemorymanagerreleasedvirtualaddressspace-method"></a><span data-ttu-id="3b75d-102">IHostMemoryManager::ReleasedVirtualAddressSpace (Método)</span><span class="sxs-lookup"><span data-stu-id="3b75d-102">IHostMemoryManager::ReleasedVirtualAddressSpace Method</span></span>
<span data-ttu-id="3b75d-103">Notifica al host que common language runtime (CLR) ha terminado de utilizar la memoria especificada.</span><span class="sxs-lookup"><span data-stu-id="3b75d-103">Notifies the host that the common language runtime (CLR) has finished using the specified memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3b75d-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3b75d-104">Syntax</span></span>  
  
```  
HRESULT ReleasedVirtualAddressSpace(  
    [in] LPVOID startAddress  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3b75d-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="3b75d-105">Parameters</span></span>  
 `startAddress`  
 <span data-ttu-id="3b75d-106">[in] Puntero a la dirección inicial de la memoria que se va a liberar.</span><span class="sxs-lookup"><span data-stu-id="3b75d-106">[in] Pointer to the starting address of the memory to be released.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3b75d-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="3b75d-107">Remarks</span></span>  
 <span data-ttu-id="3b75d-108">El `ReleasedVirtualAddressSpace` es un método de devolución de llamada de método y debe ser implementada por el sistema de escritura de la aplicación de hospedaje.</span><span class="sxs-lookup"><span data-stu-id="3b75d-108">The `ReleasedVirtualAddressSpace` method is a callback method and must be implemented by the writer of the hosting application.</span></span> <span data-ttu-id="3b75d-109">Se llama a CLR.</span><span class="sxs-lookup"><span data-stu-id="3b75d-109">It is called by the CLR.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3b75d-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3b75d-110">Requirements</span></span>  
 <span data-ttu-id="3b75d-111">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3b75d-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3b75d-112">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="3b75d-112">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="3b75d-113">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="3b75d-113">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3b75d-114">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3b75d-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3b75d-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="3b75d-115">See also</span></span>

- [<span data-ttu-id="3b75d-116">IHostMemoryManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="3b75d-116">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
