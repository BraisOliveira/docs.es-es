---
title: IMetaDataEmit::SetTypeDefProps (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetTypeDefProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetTypeDefProps
helpviewer_keywords:
- SetTypeDefProps method [.NET Framework metadata]
- IMetaDataEmit::SetTypeDefProps method [.NET Framework metadata]
ms.assetid: 480d596a-759f-4d29-ac1a-3dbff8f3544d
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 596888a8eb4a55c4cfe594b1911f17f6d32f56d2
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61992438"
---
# <a name="imetadataemitsettypedefprops-method"></a><span data-ttu-id="7f185-102">IMetaDataEmit::SetTypeDefProps (Método)</span><span class="sxs-lookup"><span data-stu-id="7f185-102">IMetaDataEmit::SetTypeDefProps Method</span></span>
<span data-ttu-id="7f185-103">Establece las características de un tipo definido por una llamada anterior a [DefineTypeDef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md).</span><span class="sxs-lookup"><span data-stu-id="7f185-103">Sets features of a type defined by a prior call to [IMetaDataEmit::DefineTypeDef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7f185-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7f185-104">Syntax</span></span>  
  
```  
HRESULT SetTypeDefProps (  
    [in]  mdTypeDef   td,   
    [in]  DWORD       dwTypeDefFlags,   
    [in]  mdToken     tkExtends,   
    [in]  mdToken     rtkImplements[]   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7f185-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="7f185-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="7f185-106">[in] Un `mdTypeDef` token obtenido de la llamada original a [DefineTypeDef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md).</span><span class="sxs-lookup"><span data-stu-id="7f185-106">[in] An `mdTypeDef` token obtained from original call to [IMetaDataEmit::DefineTypeDef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md).</span></span>  
  
 `dwTypeDefFlags`  
 <span data-ttu-id="7f185-107">[in] `TypeDef` atributos.</span><span class="sxs-lookup"><span data-stu-id="7f185-107">[in] `TypeDef` attributes.</span></span> <span data-ttu-id="7f185-108">Se trata de una máscara de bits de `CorTypeAttr` valores.</span><span class="sxs-lookup"><span data-stu-id="7f185-108">This is a bitmask of `CorTypeAttr` values.</span></span>  
  
 `tkExtends`  
 <span data-ttu-id="7f185-109">[in] El `mdToken` de la clase base.</span><span class="sxs-lookup"><span data-stu-id="7f185-109">[in] The `mdToken` of the base class.</span></span> <span data-ttu-id="7f185-110">Obtenido de una llamada anterior a [DefineImportType](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimporttype-method.md), o `null`.</span><span class="sxs-lookup"><span data-stu-id="7f185-110">Obtained from a previous call to [IMetaDataEmit::DefineImportType](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimporttype-method.md), or `null`.</span></span>  
  
 `rtkImplements[]`  
 <span data-ttu-id="7f185-111">[in] Una matriz de tokens para las interfaces que implementa este tipo.</span><span class="sxs-lookup"><span data-stu-id="7f185-111">[in] An array of tokens for the interfaces that this type implements.</span></span> <span data-ttu-id="7f185-112">Estos `mdTypeRef` los tokens se obtengan mediante [DefineImportType](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimporttype-method.md).</span><span class="sxs-lookup"><span data-stu-id="7f185-112">These `mdTypeRef` tokens are obtained using [IMetaDataEmit::DefineImportType](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimporttype-method.md).</span></span> <span data-ttu-id="7f185-113">Debe ser el último elemento de la matriz es `mdTokenNil`.</span><span class="sxs-lookup"><span data-stu-id="7f185-113">The last element of the array is must be `mdTokenNil`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7f185-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7f185-114">Requirements</span></span>  
 <span data-ttu-id="7f185-115">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7f185-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7f185-116">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="7f185-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="7f185-117">**Biblioteca:** Usar como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="7f185-117">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7f185-118">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7f185-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7f185-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="7f185-119">See also</span></span>

- [<span data-ttu-id="7f185-120">IMetaDataEmit (interfaz)</span><span class="sxs-lookup"><span data-stu-id="7f185-120">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="7f185-121">IMetaDataEmit2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="7f185-121">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
