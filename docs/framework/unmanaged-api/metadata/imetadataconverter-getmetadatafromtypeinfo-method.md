---
title: IMetaDataConverter::GetMetaDataFromTypeInfo (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataConverter.GetMetaDataFromTypeInfo
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataConverter::GetMetaDataFromTypeInfo
helpviewer_keywords:
- GetMetaDataFromTypeInfo method [.NET Framework metadata]
- IMetaDataConverter::GetMetaDataFromTypeInfo method [.NET Framework metadata]
ms.assetid: d44484bb-23a3-49c3-9e46-69d0d9ab4f0f
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b87bc814179b35f594ec8fab812055ff0182c5c3
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59145852"
---
# <a name="imetadataconvertergetmetadatafromtypeinfo-method"></a><span data-ttu-id="bf39e-102">IMetaDataConverter::GetMetaDataFromTypeInfo (Método)</span><span class="sxs-lookup"><span data-stu-id="bf39e-102">IMetaDataConverter::GetMetaDataFromTypeInfo Method</span></span>
<span data-ttu-id="bf39e-103">Obtiene un puntero a un [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) instancia que representa la firma de metadatos de la biblioteca de tipos al que hace referencia especificado `ITypeInfo` instancia.</span><span class="sxs-lookup"><span data-stu-id="bf39e-103">Gets a pointer to an [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) instance that represents the metadata signature of the type library referenced by the specified `ITypeInfo` instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bf39e-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="bf39e-104">Syntax</span></span>  
  
```  
HRESULT GetMetaDataFromTypeInfo (  
    [in]  ITypeInfo         *pITI,  
    [out] IMetaDataImport   **ppMDI  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bf39e-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="bf39e-105">Parameters</span></span>  
 `pITI`  
 <span data-ttu-id="bf39e-106">[in] Un puntero a un `ITypeInfo` objeto que hace referencia a la biblioteca de tipos.</span><span class="sxs-lookup"><span data-stu-id="bf39e-106">[in] A pointer to an `ITypeInfo` object that refers to the type library.</span></span>  
  
 `ppMDI`  
 <span data-ttu-id="bf39e-107">[out] Un puntero a una ubicación que recibe la dirección de la `IMetaDataImport` instancia que representa la firma de metadatos.</span><span class="sxs-lookup"><span data-stu-id="bf39e-107">[out] A pointer to a location that receives the address of the `IMetaDataImport` instance that represents the metadata signature.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bf39e-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="bf39e-108">Requirements</span></span>  
 <span data-ttu-id="bf39e-109">**Plataforma:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bf39e-109">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bf39e-110">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="bf39e-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="bf39e-111">**Biblioteca:** Usar como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="bf39e-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="bf39e-112">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bf39e-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bf39e-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="bf39e-113">See also</span></span>

- [<span data-ttu-id="bf39e-114">IMetaDataEmit (interfaz)</span><span class="sxs-lookup"><span data-stu-id="bf39e-114">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="bf39e-115">IMetaDataImport (interfaz)</span><span class="sxs-lookup"><span data-stu-id="bf39e-115">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
