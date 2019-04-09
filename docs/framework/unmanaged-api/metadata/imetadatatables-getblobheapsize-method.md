---
title: IMetaDataTables::GetBlobHeapSize (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetBlobHeapSize
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetBlobHeapSize
helpviewer_keywords:
- GetBlobHeapSize method [.NET Framework metadata]
- IMetaDataTables::GetBlobHeapSize method [.NET Framework metadata]
ms.assetid: 6330a9ee-8cd5-4299-86f1-b4de2c701a0d
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d22e61d28e0fbf06fa1cfe9e9ac18a534726f01d
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59076460"
---
# <a name="imetadatatablesgetblobheapsize-method"></a><span data-ttu-id="d6f53-102">IMetaDataTables::GetBlobHeapSize (Método)</span><span class="sxs-lookup"><span data-stu-id="d6f53-102">IMetaDataTables::GetBlobHeapSize Method</span></span>
<span data-ttu-id="d6f53-103">Obtiene el tamaño, en bytes, del montón de objeto binario grande (BLOB).</span><span class="sxs-lookup"><span data-stu-id="d6f53-103">Gets the size, in bytes, of the binary large object (BLOB) heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d6f53-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d6f53-104">Syntax</span></span>  
  
```  
HRESULT GetBlobHeapSize (  
    [out] ULONG     *pcbBlobs  
);   
```  
  
## <a name="parameters"></a><span data-ttu-id="d6f53-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d6f53-105">Parameters</span></span>  
 `pcbBlobs`  
 <span data-ttu-id="d6f53-106">[out] Un puntero al tamaño, en bytes, del montón de objetos binarios.</span><span class="sxs-lookup"><span data-stu-id="d6f53-106">[out] A pointer to the size, in bytes, of the BLOB heap.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d6f53-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d6f53-107">Requirements</span></span>  
 <span data-ttu-id="d6f53-108">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d6f53-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d6f53-109">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="d6f53-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d6f53-110">**Biblioteca:** Usar como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="d6f53-110">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="d6f53-111">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="d6f53-111">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="d6f53-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="d6f53-112">See also</span></span>

- [<span data-ttu-id="d6f53-113">IMetaDataTables (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="d6f53-113">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="d6f53-114">IMetaDataTables2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="d6f53-114">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
