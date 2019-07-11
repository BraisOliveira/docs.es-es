---
title: IMetaDataImport::EnumProperties (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumProperties
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumProperties
helpviewer_keywords:
- IMetaDataImport::EnumProperties method [.NET Framework metadata]
- EnumProperties method [.NET Framework metadata]
ms.assetid: 60573ad7-8821-4721-a068-3f7a6d25926a
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3c63797b60354b461891f44d32cf1840f7fdcf3d
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67756491"
---
# <a name="imetadataimportenumproperties-method"></a><span data-ttu-id="af1a2-102">IMetaDataImport::EnumProperties (Método)</span><span class="sxs-lookup"><span data-stu-id="af1a2-102">IMetaDataImport::EnumProperties Method</span></span>
<span data-ttu-id="af1a2-103">Enumera los tokens de PropertyDef que representan las propiedades del tipo al que hace referencia el token de TypeDef especificado.</span><span class="sxs-lookup"><span data-stu-id="af1a2-103">Enumerates PropertyDef tokens representing the properties of the type referenced by the specified TypeDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="af1a2-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="af1a2-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumProperties (  
   [in, out] HCORENUM    *phEnum,  
   [in]      mdTypeDef   td,  
   [out]     mdProperty  rProperties[],  
   [in]      ULONG       cMax,  
   [out]     ULONG       *pcProperties  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="af1a2-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="af1a2-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="af1a2-106">[in, out] Un puntero en el enumerador.</span><span class="sxs-lookup"><span data-stu-id="af1a2-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="af1a2-107">Esto debe ser NULL para la primera llamada de este método.</span><span class="sxs-lookup"><span data-stu-id="af1a2-107">This must be NULL for the first call of this method.</span></span>  
  
 `td`  
 <span data-ttu-id="af1a2-108">[in] Un token de TypeDef que representa el tipo con propiedades a enumerar.</span><span class="sxs-lookup"><span data-stu-id="af1a2-108">[in] A TypeDef token representing the type with properties to enumerate.</span></span>  
  
 `rProperties`  
 <span data-ttu-id="af1a2-109">[out] Matriz utilizada para almacenar los tokens de PropertyDef.</span><span class="sxs-lookup"><span data-stu-id="af1a2-109">[out] The array used to store the PropertyDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="af1a2-110">[in] Tamaño máximo de la matriz `rProperties`.</span><span class="sxs-lookup"><span data-stu-id="af1a2-110">[in] The maximum size of the `rProperties` array.</span></span>  
  
 `pcProperties`  
 <span data-ttu-id="af1a2-111">[out] El número de tokens de PropertyDef devueltos en `rProperties`.</span><span class="sxs-lookup"><span data-stu-id="af1a2-111">[out] The number of PropertyDef tokens returned in `rProperties`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="af1a2-112">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="af1a2-112">Return Value</span></span>  
  
|<span data-ttu-id="af1a2-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="af1a2-113">HRESULT</span></span>|<span data-ttu-id="af1a2-114">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="af1a2-114">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="af1a2-115">`EnumProperties` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="af1a2-115">`EnumProperties` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="af1a2-116">No hay ningún token para enumerar.</span><span class="sxs-lookup"><span data-stu-id="af1a2-116">There are no tokens to enumerate.</span></span> <span data-ttu-id="af1a2-117">En ese caso, `pcProperties` es cero.</span><span class="sxs-lookup"><span data-stu-id="af1a2-117">In that case, `pcProperties` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="af1a2-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="af1a2-118">Requirements</span></span>  
 <span data-ttu-id="af1a2-119">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="af1a2-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="af1a2-120">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="af1a2-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="af1a2-121">**Biblioteca:** Incluye como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="af1a2-121">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="af1a2-122">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="af1a2-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="af1a2-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="af1a2-123">See also</span></span>

- [<span data-ttu-id="af1a2-124">IMetaDataImport (interfaz)</span><span class="sxs-lookup"><span data-stu-id="af1a2-124">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="af1a2-125">IMetaDataImport2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="af1a2-125">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
