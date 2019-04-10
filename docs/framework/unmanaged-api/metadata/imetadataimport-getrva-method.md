---
title: IMetaDataImport::GetRVA (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetRVA
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetRVA
helpviewer_keywords:
- GetRVA method [.NET Framework metadata]
- IMetaDataImport::GetRVA method [.NET Framework metadata]
ms.assetid: ea422217-988b-4acd-b2db-c55357938275
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 96c013cd3e45e4ede0cbc9f42bf511a2eb3fc12d
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59223594"
---
# <a name="imetadataimportgetrva-method"></a><span data-ttu-id="34383-102">IMetaDataImport::GetRVA (Método)</span><span class="sxs-lookup"><span data-stu-id="34383-102">IMetaDataImport::GetRVA Method</span></span>
<span data-ttu-id="34383-103">Obtiene la dirección virtual relativa (RVA) y las marcas de implementación del método o campo representado por el token especificado.</span><span class="sxs-lookup"><span data-stu-id="34383-103">Gets the relative virtual address (RVA) and the implementation flags of the method or field represented by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="34383-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="34383-104">Syntax</span></span>  
  
```  
HRESULT GetRVA (  
   [in]  mdToken     tk,   
   [out] ULONG       *pulCodeRVA,   
   [out]  DWORD      *pdwImplFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="34383-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="34383-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="34383-106">[in] Un token de metadatos MethodDef o FieldDef que representa el objeto de código para devolver la RVA.</span><span class="sxs-lookup"><span data-stu-id="34383-106">[in] A MethodDef or FieldDef metadata token that represents the code object to return the RVA for.</span></span> <span data-ttu-id="34383-107">Si el token es un FieldDef, el campo debe ser una variable global.</span><span class="sxs-lookup"><span data-stu-id="34383-107">If the token is a FieldDef, the field must be a global variable.</span></span>  
  
 `pulCodeRVA`  
 <span data-ttu-id="34383-108">[out] Un puntero a la dirección virtual relativa del objeto de código representado por el token.</span><span class="sxs-lookup"><span data-stu-id="34383-108">[out] A pointer to the relative virtual address of the code object represented by the token.</span></span>  
  
 `pdwImplFlags`  
 <span data-ttu-id="34383-109">[out] Un puntero a los marcadores de implementación para el método.</span><span class="sxs-lookup"><span data-stu-id="34383-109">[out] A pointer to the implementation flags for the method.</span></span> <span data-ttu-id="34383-110">Este valor es una máscara de bits desde el [CorMethodImpl](../../../../docs/framework/unmanaged-api/metadata/cormethodimpl-enumeration.md) enumeración.</span><span class="sxs-lookup"><span data-stu-id="34383-110">This value is a bitmask from the [CorMethodImpl](../../../../docs/framework/unmanaged-api/metadata/cormethodimpl-enumeration.md) enumeration.</span></span> <span data-ttu-id="34383-111">El valor de `pdwImplFlags` es válido únicamente si `tk` es un token de MethodDef.</span><span class="sxs-lookup"><span data-stu-id="34383-111">The value of `pdwImplFlags` is valid only if `tk` is a MethodDef token.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="34383-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="34383-112">Requirements</span></span>  
 <span data-ttu-id="34383-113">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="34383-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="34383-114">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="34383-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="34383-115">**Biblioteca:** Incluye como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="34383-115">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="34383-116">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="34383-116">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="34383-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="34383-117">See also</span></span>

- [<span data-ttu-id="34383-118">IMetaDataImport (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="34383-118">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="34383-119">IMetaDataImport2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="34383-119">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
