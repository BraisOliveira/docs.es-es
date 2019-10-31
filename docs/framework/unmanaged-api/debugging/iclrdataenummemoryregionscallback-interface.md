---
title: ICLRDataEnumMemoryRegionsCallback (Interfaz)
ms.date: 03/30/2017
api_name:
- ICLRDataEnumMemoryRegionsCallback
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataEnumMemoryRegionsCallback
helpviewer_keywords:
- ICLRDataEnumMemoryRegionsCallback interface [.NET Framework debugging]
ms.assetid: 3f1af8b0-8478-48e0-a7ec-3e90e0b97649
topic_type:
- apiref
ms.openlocfilehash: cf46133095d1345ffbe0356d3ab486c11ae6dbd6
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73122912"
---
# <a name="iclrdataenummemoryregionscallback-interface"></a><span data-ttu-id="b0695-102">ICLRDataEnumMemoryRegionsCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="b0695-102">ICLRDataEnumMemoryRegionsCallback Interface</span></span>
<span data-ttu-id="b0695-103">Proporciona un método de devolución de llamada para [ICLRDataEnumMemoryRegions:: EnumMemoryRegions](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregions-enummemoryregions-method.md) con el fin de notificar al depurador el resultado de un intento de enumerar un área de memoria especificada.</span><span class="sxs-lookup"><span data-stu-id="b0695-103">Provides a callback method for [ICLRDataEnumMemoryRegions::EnumMemoryRegions](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregions-enummemoryregions-method.md) to report to the debugger the result of an attempt to enumerate a specified region of memory.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="b0695-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="b0695-104">Methods</span></span>  
  
|<span data-ttu-id="b0695-105">Método</span><span class="sxs-lookup"><span data-stu-id="b0695-105">Method</span></span>|<span data-ttu-id="b0695-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="b0695-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="b0695-107">EnumMemoryRegion (método)</span><span class="sxs-lookup"><span data-stu-id="b0695-107">EnumMemoryRegion Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregionscallback-enummemoryregion-method.md)|<span data-ttu-id="b0695-108">Lo llama `ICLRDataEnumMemoryRegions::EnumMemoryRegions` para notificar al depurador el resultado de un intento de enumerar un área de memoria especificada.</span><span class="sxs-lookup"><span data-stu-id="b0695-108">Called by `ICLRDataEnumMemoryRegions::EnumMemoryRegions` to report to the debugger the result of an attempt to enumerate a specified region of memory.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b0695-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b0695-109">Requirements</span></span>  
 <span data-ttu-id="b0695-110">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b0695-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b0695-111">**Encabezado:** ClrData. idl, ClrData. h</span><span class="sxs-lookup"><span data-stu-id="b0695-111">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="b0695-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b0695-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b0695-113">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b0695-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b0695-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="b0695-114">See also</span></span>

- [<span data-ttu-id="b0695-115">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="b0695-115">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
