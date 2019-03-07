---
title: IMetaDataEmit::Save (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.Save
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::Save
helpviewer_keywords:
- Save method, IMetaDataEmit interface [.NET Framework metadata]
- IMetaDataEmit::Save method [.NET Framework metadata]
ms.assetid: c1de8400-adfe-4a71-b828-a1d0cc1ea505
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 90ddc540115a60154953ac6e8cb931103a650752
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57492421"
---
# <a name="imetadataemitsave-method"></a><span data-ttu-id="a887a-102">IMetaDataEmit::Save (Método)</span><span class="sxs-lookup"><span data-stu-id="a887a-102">IMetaDataEmit::Save Method</span></span>
<span data-ttu-id="a887a-103">Guarda todos los metadatos en el ámbito actual en el archivo en la dirección especificada.</span><span class="sxs-lookup"><span data-stu-id="a887a-103">Saves all metadata in the current scope to the file at the specified address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a887a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a887a-104">Syntax</span></span>  
  
```  
HRESULT Save (   
    [in]  LPCWSTR     szFile,   
    [in]  DWORD       dwSaveFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a887a-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a887a-105">Parameters</span></span>  
 `wzFile`  
 <span data-ttu-id="a887a-106">[in] El nombre del archivo que se guarde en.</span><span class="sxs-lookup"><span data-stu-id="a887a-106">[in] The name of the file to save to.</span></span> <span data-ttu-id="a887a-107">Si este valor es null, la copia en memoria se guardará a la última ubicación que se usó.</span><span class="sxs-lookup"><span data-stu-id="a887a-107">If this value is null, the in-memory copy will be saved to the last location that was used.</span></span>  
  
 `dwSaveFlags`  
 <span data-ttu-id="a887a-108">[in] Reservado.</span><span class="sxs-lookup"><span data-stu-id="a887a-108">[in] Reserved.</span></span> <span data-ttu-id="a887a-109">Debe ser cero.</span><span class="sxs-lookup"><span data-stu-id="a887a-109">Must be zero.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a887a-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a887a-110">Requirements</span></span>  
 <span data-ttu-id="a887a-111">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a887a-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a887a-112">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="a887a-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a887a-113">**Biblioteca:** Usar como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a887a-113">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a887a-114">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a887a-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a887a-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="a887a-115">See also</span></span>
- [<span data-ttu-id="a887a-116">IMetaDataEmit (interfaz)</span><span class="sxs-lookup"><span data-stu-id="a887a-116">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="a887a-117">IMetaDataEmit2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="a887a-117">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
