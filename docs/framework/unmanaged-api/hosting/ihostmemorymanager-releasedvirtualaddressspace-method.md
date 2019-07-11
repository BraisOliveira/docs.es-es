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
ms.openlocfilehash: 5096eb1064485c02b599659cc9ae889e7151581c
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67767690"
---
# <a name="ihostmemorymanagerreleasedvirtualaddressspace-method"></a><span data-ttu-id="8e2aa-102">IHostMemoryManager::ReleasedVirtualAddressSpace (Método)</span><span class="sxs-lookup"><span data-stu-id="8e2aa-102">IHostMemoryManager::ReleasedVirtualAddressSpace Method</span></span>
<span data-ttu-id="8e2aa-103">Notifica al host que common language runtime (CLR) ha terminado de utilizar la memoria especificada.</span><span class="sxs-lookup"><span data-stu-id="8e2aa-103">Notifies the host that the common language runtime (CLR) has finished using the specified memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8e2aa-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8e2aa-104">Syntax</span></span>  
  
```cpp  
HRESULT ReleasedVirtualAddressSpace(  
    [in] LPVOID startAddress  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8e2aa-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="8e2aa-105">Parameters</span></span>  
 `startAddress`  
 <span data-ttu-id="8e2aa-106">[in] Puntero a la dirección inicial de la memoria que se va a liberar.</span><span class="sxs-lookup"><span data-stu-id="8e2aa-106">[in] Pointer to the starting address of the memory to be released.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8e2aa-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="8e2aa-107">Remarks</span></span>  
 <span data-ttu-id="8e2aa-108">El `ReleasedVirtualAddressSpace` es un método de devolución de llamada de método y debe ser implementada por el sistema de escritura de la aplicación de hospedaje.</span><span class="sxs-lookup"><span data-stu-id="8e2aa-108">The `ReleasedVirtualAddressSpace` method is a callback method and must be implemented by the writer of the hosting application.</span></span> <span data-ttu-id="8e2aa-109">Se llama a CLR.</span><span class="sxs-lookup"><span data-stu-id="8e2aa-109">It is called by the CLR.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8e2aa-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8e2aa-110">Requirements</span></span>  
 <span data-ttu-id="8e2aa-111">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8e2aa-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8e2aa-112">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="8e2aa-112">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="8e2aa-113">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="8e2aa-113">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8e2aa-114">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8e2aa-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8e2aa-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="8e2aa-115">See also</span></span>

- [<span data-ttu-id="8e2aa-116">IHostMemoryManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="8e2aa-116">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
