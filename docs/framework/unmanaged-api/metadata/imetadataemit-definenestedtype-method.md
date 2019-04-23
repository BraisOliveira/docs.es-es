---
title: IMetaDataEmit::DefineNestedType (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineNestedType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineNestedType
helpviewer_keywords:
- IMetaDataEmit::DefineNestedType method [.NET Framework metadata]
- DefineNestedType method [.NET Framework metadata]
ms.assetid: 1e994de6-4628-459c-b967-b34be1e9fe4f
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 4ebd4e9beca315ef8284c915800afec6bdb78c78
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59183240"
---
# <a name="imetadataemitdefinenestedtype-method"></a><span data-ttu-id="bb305-102">IMetaDataEmit::DefineNestedType (Método)</span><span class="sxs-lookup"><span data-stu-id="bb305-102">IMetaDataEmit::DefineNestedType Method</span></span>
<span data-ttu-id="bb305-103">Crea la firma de metadatos de una definición de tipo, se devuelve un `mdTypeDef` para ese tipo de token y especifica que el tipo definido es un miembro del tipo al que hace referencia el `tdEncloser` parámetro.</span><span class="sxs-lookup"><span data-stu-id="bb305-103">Creates the metadata signature of a type definition, returns an `mdTypeDef` token for that type, and specifies that the defined type is a member of the type referenced by the `tdEncloser` parameter.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bb305-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="bb305-104">Syntax</span></span>  
  
```  
HRESULT DefineNestedType (   
    [in]  LPCWSTR     szTypeDef,  
    [in]  DWORD       dwTypeDefFlags,   
    [in]  mdToken     tkExtends,   
    [in]  mdToken     rtkImplements[],   
    [in]  mdTypeDef   tdEncloser,   
    [out] mdTypeDef   *ptd  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bb305-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="bb305-105">Parameters</span></span>  
 `szTypeDef`  
 <span data-ttu-id="bb305-106">[in] El nombre del tipo en formato Unicode.</span><span class="sxs-lookup"><span data-stu-id="bb305-106">[in] The name of the type in Unicode.</span></span>  
  
 `dwTypeDefFlags`  
 <span data-ttu-id="bb305-107">[in] `TypeDef` atributos.</span><span class="sxs-lookup"><span data-stu-id="bb305-107">[in] `TypeDef` attributes.</span></span> <span data-ttu-id="bb305-108">Se trata de una máscara de bits de `CorTypeAttr` valores.</span><span class="sxs-lookup"><span data-stu-id="bb305-108">This is a bitmask of `CorTypeAttr` values.</span></span>  
  
 `tkExtends`  
 <span data-ttu-id="bb305-109">[in] El token de la clase base.</span><span class="sxs-lookup"><span data-stu-id="bb305-109">[in] The token of the base class.</span></span> <span data-ttu-id="bb305-110">Puede ser un `mdTypeDef` o un `mdTypeRef` token.</span><span class="sxs-lookup"><span data-stu-id="bb305-110">This is either a `mdTypeDef` or a `mdTypeRef` token.</span></span>  
  
 <span data-ttu-id="bb305-111">`rtkImplements`[]</span><span class="sxs-lookup"><span data-stu-id="bb305-111">`rtkImplements`[]</span></span>  
 <span data-ttu-id="bb305-112">[in] Una matriz de los tokens que especifican las interfaces que implementa esta clase o interfaz.</span><span class="sxs-lookup"><span data-stu-id="bb305-112">[in] An array of tokens that specify the interfaces that this class or interface implements.</span></span>  
  
 `tdEncloser`  
 <span data-ttu-id="bb305-113">[in] El token del tipo envolvente.</span><span class="sxs-lookup"><span data-stu-id="bb305-113">[in] The token of the enclosing type.</span></span> <span data-ttu-id="bb305-114">Debe ser el último elemento de la matriz `mdTokenNil`.</span><span class="sxs-lookup"><span data-stu-id="bb305-114">The last element of the array must be `mdTokenNil`.</span></span>  
  
 `ptd`  
 <span data-ttu-id="bb305-115">[out] El `mdTypeDef` token asignado.</span><span class="sxs-lookup"><span data-stu-id="bb305-115">[out] The `mdTypeDef` token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bb305-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="bb305-116">Requirements</span></span>  
 <span data-ttu-id="bb305-117">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bb305-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bb305-118">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="bb305-118">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="bb305-119">**Biblioteca:** Usar como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="bb305-119">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="bb305-120">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bb305-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb305-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="bb305-121">See also</span></span>

- [<span data-ttu-id="bb305-122">IMetaDataEmit (interfaz)</span><span class="sxs-lookup"><span data-stu-id="bb305-122">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="bb305-123">IMetaDataEmit2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="bb305-123">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
