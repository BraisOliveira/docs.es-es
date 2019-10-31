---
title: IAssemblyName::GetProperty (Método)
ms.date: 03/30/2017
api_name:
- IAssemblyName.GetProperty
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyName::GetProperty
helpviewer_keywords:
- IAssemblyName::GetProperty method [.NET Framework fusion]
- GetProperty method [.NET Framework fusion]
ms.assetid: e59fda62-77d5-4e37-89cb-ce7ae4627975
topic_type:
- apiref
ms.openlocfilehash: b86828e01fb00b12feff2ed451793c240e16e240
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134387"
---
# <a name="iassemblynamegetproperty-method"></a><span data-ttu-id="fa0cf-102">IAssemblyName::GetProperty (Método)</span><span class="sxs-lookup"><span data-stu-id="fa0cf-102">IAssemblyName::GetProperty Method</span></span>
<span data-ttu-id="fa0cf-103">Obtiene un puntero a la propiedad a la que hace referencia el identificador de propiedad especificado.</span><span class="sxs-lookup"><span data-stu-id="fa0cf-103">Gets a pointer to the property referenced by the specified property identifier.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fa0cf-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="fa0cf-104">Syntax</span></span>  
  
```cpp  
HRESULT GetProperty (  
    [in]      DWORD    PropertyId,  
    [out]     LPVOID   pvProperty,  
    [in, out] LPDWORD  pcbProperty  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fa0cf-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="fa0cf-105">Parameters</span></span>  
 `PropertyId`  
 <span data-ttu-id="fa0cf-106">de Identificador único de la propiedad solicitada.</span><span class="sxs-lookup"><span data-stu-id="fa0cf-106">[in] The unique identifier for the requested property.</span></span>  
  
 `pvProperty`  
 <span data-ttu-id="fa0cf-107">enuncia Datos de propiedad devueltos.</span><span class="sxs-lookup"><span data-stu-id="fa0cf-107">[out] The returned property data.</span></span>  
  
 `pcbProperty`  
 <span data-ttu-id="fa0cf-108">[in, out] Tamaño, en bytes, de `pvProperty`.</span><span class="sxs-lookup"><span data-stu-id="fa0cf-108">[in, out] The size, in bytes, of `pvProperty`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fa0cf-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="fa0cf-109">Requirements</span></span>  
 <span data-ttu-id="fa0cf-110">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fa0cf-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fa0cf-111">**Encabezado:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="fa0cf-111">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="fa0cf-112">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fa0cf-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa0cf-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="fa0cf-113">See also</span></span>

- [<span data-ttu-id="fa0cf-114">IAssemblyName (interfaz)</span><span class="sxs-lookup"><span data-stu-id="fa0cf-114">IAssemblyName Interface</span></span>](iassemblyname-interface.md)
