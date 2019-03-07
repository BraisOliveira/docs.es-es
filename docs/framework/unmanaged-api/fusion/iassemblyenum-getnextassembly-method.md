---
title: IAssemblyEnum::GetNextAssembly (Método)
ms.date: 03/30/2017
api_name:
- IAssemblyEnum.GetNextAssembly
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyEnum::GetNextAssembly
helpviewer_keywords:
- GetNextAssembly method [.NET Framework fusion]
- IAssemblyEnum::GetNextAssembly method [.NET Framework fusion]
ms.assetid: 5d7a4ca2-5f46-4ef1-a9a2-257884e9dc11
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 39e6cbdf683ad59be93c88d87ba7a7194ac83992
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57502402"
---
# <a name="iassemblyenumgetnextassembly-method"></a><span data-ttu-id="3412b-102">IAssemblyEnum::GetNextAssembly (Método)</span><span class="sxs-lookup"><span data-stu-id="3412b-102">IAssemblyEnum::GetNextAssembly Method</span></span>
<span data-ttu-id="3412b-103">Obtiene un puntero a la siguiente [IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md) incluidos en este [IAssemblyEnum](../../../../docs/framework/unmanaged-api/fusion/iassemblyenum-interface.md) objeto.</span><span class="sxs-lookup"><span data-stu-id="3412b-103">Gets a pointer to the next [IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md) contained in this [IAssemblyEnum](../../../../docs/framework/unmanaged-api/fusion/iassemblyenum-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3412b-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3412b-104">Syntax</span></span>  
  
```  
HRESULT GetNextAssembly (  
    [in]  LPVOID          pvReserved,  
    [out] IAssemblyName   **ppName,  
    [in]  DWORD           dwFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3412b-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="3412b-105">Parameters</span></span>  
 `pvReserved`  
 <span data-ttu-id="3412b-106">[in] Reservado para extensibilidad futura.</span><span class="sxs-lookup"><span data-stu-id="3412b-106">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="3412b-107">`pvReserved` debe ser una referencia nula.</span><span class="sxs-lookup"><span data-stu-id="3412b-107">`pvReserved` must be a null reference.</span></span>  
  
 `ppName`  
 <span data-ttu-id="3412b-108">[out] El valor devuelto `IAssemblyName` puntero.</span><span class="sxs-lookup"><span data-stu-id="3412b-108">[out] The returned `IAssemblyName` pointer.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="3412b-109">[in] Reservado para extensibilidad futura.</span><span class="sxs-lookup"><span data-stu-id="3412b-109">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="3412b-110">`dwFlags` debe ser 0 (cero).</span><span class="sxs-lookup"><span data-stu-id="3412b-110">`dwFlags` must be 0 (zero).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3412b-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3412b-111">Requirements</span></span>  
 <span data-ttu-id="3412b-112">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3412b-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3412b-113">**Encabezado**: Fusion.h</span><span class="sxs-lookup"><span data-stu-id="3412b-113">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="3412b-114">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3412b-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3412b-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="3412b-115">See also</span></span>
- [<span data-ttu-id="3412b-116">IAssemblyName (interfaz)</span><span class="sxs-lookup"><span data-stu-id="3412b-116">IAssemblyName Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)
- [<span data-ttu-id="3412b-117">IAssemblyEnum (interfaz)</span><span class="sxs-lookup"><span data-stu-id="3412b-117">IAssemblyEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyenum-interface.md)
