---
title: IMetaDataImport::EnumTypeRefs (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumTypeRefs
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumTypeRefs
helpviewer_keywords:
- EnumTypeRefs method [.NET Framework metadata]
- IMetaDataImport::EnumTypeRefs method [.NET Framework metadata]
ms.assetid: b4896b8f-8e97-469c-8089-e72a025661b5
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: de0fe4a51fbb49e80377b6b434bf3b72ddb90f02
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59081628"
---
# <a name="imetadataimportenumtyperefs-method"></a><span data-ttu-id="738f5-102">IMetaDataImport::EnumTypeRefs (Método)</span><span class="sxs-lookup"><span data-stu-id="738f5-102">IMetaDataImport::EnumTypeRefs Method</span></span>
<span data-ttu-id="738f5-103">Enumera los tokens de TypeRef definidos en el ámbito de metadatos actual.</span><span class="sxs-lookup"><span data-stu-id="738f5-103">Enumerates TypeRef tokens defined in the current metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="738f5-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="738f5-104">Syntax</span></span>  
  
```  
HRESULT EnumTypeRefs (  
   [in, out] HCORENUM    *phEnum,   
   [out] mdTypeRef       rTypeRefs[],  
   [in]  ULONG           cMax,   
   [out] ULONG           *pcTypeRefs  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="738f5-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="738f5-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="738f5-106">[in, out] Un puntero en el enumerador.</span><span class="sxs-lookup"><span data-stu-id="738f5-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="738f5-107">Esto debe ser NULL para la primera llamada de este método.</span><span class="sxs-lookup"><span data-stu-id="738f5-107">This must be NULL for the first call of this method.</span></span>  
  
 `rTypeRefs`  
 <span data-ttu-id="738f5-108">[out] Matriz utilizada para almacenar los tokens de TypeRef.</span><span class="sxs-lookup"><span data-stu-id="738f5-108">[out] The array used to store the TypeRef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="738f5-109">[in] Tamaño máximo de la matriz `rTypeRefs`.</span><span class="sxs-lookup"><span data-stu-id="738f5-109">[in] The maximum size of the `rTypeRefs` array.</span></span>  
  
 `pcTypeRefs`  
 <span data-ttu-id="738f5-110">[out] Un puntero al número de tokens de TypeRef devuelto en `rTypeRefs`.</span><span class="sxs-lookup"><span data-stu-id="738f5-110">[out] A pointer to the number of TypeRef tokens returned in `rTypeRefs`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="738f5-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="738f5-111">Return Value</span></span>  
  
|<span data-ttu-id="738f5-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="738f5-112">HRESULT</span></span>|<span data-ttu-id="738f5-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="738f5-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|`EnumTypeRefs` <span data-ttu-id="738f5-114">se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="738f5-114">returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="738f5-115">No hay ningún token para enumerar.</span><span class="sxs-lookup"><span data-stu-id="738f5-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="738f5-116">En ese caso, `pcTypeRefs` es cero.</span><span class="sxs-lookup"><span data-stu-id="738f5-116">In that case, `pcTypeRefs` is zero.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="738f5-117">Comentarios</span><span class="sxs-lookup"><span data-stu-id="738f5-117">Remarks</span></span>  
 <span data-ttu-id="738f5-118">Un símbolo (token) de TypeRef representa una referencia a un tipo.</span><span class="sxs-lookup"><span data-stu-id="738f5-118">A TypeRef token represents a reference to a type.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="738f5-119">Requisitos</span><span class="sxs-lookup"><span data-stu-id="738f5-119">Requirements</span></span>  
 <span data-ttu-id="738f5-120">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="738f5-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="738f5-121">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="738f5-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="738f5-122">**Biblioteca:** Incluye como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="738f5-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="738f5-123">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="738f5-123">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="738f5-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="738f5-124">See also</span></span>

- [<span data-ttu-id="738f5-125">IMetaDataImport (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="738f5-125">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="738f5-126">IMetaDataImport2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="738f5-126">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
