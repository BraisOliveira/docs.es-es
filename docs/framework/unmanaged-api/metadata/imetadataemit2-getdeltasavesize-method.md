---
title: IMetaDataEmit2::GetDeltaSaveSize (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataEmit2.GetDeltaSaveSize
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit2::GetDeltaSaveSize
helpviewer_keywords:
- IMetaDataEmit2::GetDeltaSaveSize method [.NET Framework metadata]
- GetDeltaSaveSize method [.NET Framework metadata]
ms.assetid: 036db5e7-8211-4645-9a34-03d1a89be955
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 0b0a190ce57091434006421e6d8551c78cbe66b8
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67777175"
---
# <a name="imetadataemit2getdeltasavesize-method"></a><span data-ttu-id="884fd-102">IMetaDataEmit2::GetDeltaSaveSize (Método)</span><span class="sxs-lookup"><span data-stu-id="884fd-102">IMetaDataEmit2::GetDeltaSaveSize Method</span></span>
<span data-ttu-id="884fd-103">Obtiene un valor que indica cualquier cambio en el tamaño de los metadatos que da como resultado de la sesión actual de editar y continuar.</span><span class="sxs-lookup"><span data-stu-id="884fd-103">Gets a value indicating any change in metadata size that results from the current edit-and-continue session.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="884fd-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="884fd-104">Syntax</span></span>  
  
```cpp  
HRESULT GetDeltaSaveSize (  
    [in]  CorSaveSize  fSave,  
    [out] DWORD        *pdwSaveSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="884fd-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="884fd-105">Parameters</span></span>  
 `fSave`  
 <span data-ttu-id="884fd-106">[in] Uno de los [CorSaveSize](../../../../docs/framework/unmanaged-api/metadata/corsavesize-enumeration.md) valores, que indica el nivel de precisión deseado.</span><span class="sxs-lookup"><span data-stu-id="884fd-106">[in] One of the [CorSaveSize](../../../../docs/framework/unmanaged-api/metadata/corsavesize-enumeration.md) values, indicating the level of precision desired.</span></span> <span data-ttu-id="884fd-107">Para la versión 2.0 de .NET Framework, se omite este parámetro.</span><span class="sxs-lookup"><span data-stu-id="884fd-107">For the .NET Framework version 2.0, this parameter is ignored.</span></span>  
  
 `pdwSaveSize`  
 <span data-ttu-id="884fd-108">[out] El cambio en el tamaño de los metadatos.</span><span class="sxs-lookup"><span data-stu-id="884fd-108">[out] The change in the size of the metadata.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="884fd-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="884fd-109">Requirements</span></span>  
 <span data-ttu-id="884fd-110">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="884fd-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="884fd-111">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="884fd-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="884fd-112">**Biblioteca:** Usar como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="884fd-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="884fd-113">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="884fd-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="884fd-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="884fd-114">See also</span></span>

- [<span data-ttu-id="884fd-115">IMetaDataEmit2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="884fd-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
- [<span data-ttu-id="884fd-116">IMetaDataEmit (interfaz)</span><span class="sxs-lookup"><span data-stu-id="884fd-116">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
