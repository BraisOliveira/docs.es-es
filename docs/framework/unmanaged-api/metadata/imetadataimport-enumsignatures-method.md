---
title: IMetaDataImport::EnumSignatures (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumSignatures
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumSignatures
helpviewer_keywords:
- EnumSignatures method [.NET Framework metadata]
- IMetaDataImport::EnumSignatures method [.NET Framework metadata]
ms.assetid: d0d65060-6f90-42a2-95cf-6ffb04352996
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 193abe173b259ff2679642e229fce96151e37872
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59179691"
---
# <a name="imetadataimportenumsignatures-method"></a><span data-ttu-id="25e91-102">IMetaDataImport::EnumSignatures (Método)</span><span class="sxs-lookup"><span data-stu-id="25e91-102">IMetaDataImport::EnumSignatures Method</span></span>
<span data-ttu-id="25e91-103">Enumera los tokens de firma que representan las firmas independientes en el ámbito actual.</span><span class="sxs-lookup"><span data-stu-id="25e91-103">Enumerates Signature tokens representing stand-alone signatures in the current scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="25e91-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="25e91-104">Syntax</span></span>  
  
```  
HRESULT EnumSignatures (  
   [in, out] HCORENUM     *phEnum,  
   [out]     mdSignature  rSignatures[],  
   [in]      ULONG        cMax,  
   [out]     ULONG        *pcSignatures  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="25e91-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="25e91-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="25e91-106">[in, out] Un puntero en el enumerador.</span><span class="sxs-lookup"><span data-stu-id="25e91-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="25e91-107">Esto debe ser NULL para la primera llamada de este método.</span><span class="sxs-lookup"><span data-stu-id="25e91-107">This must be NULL for the first call of this method.</span></span>  
  
 `rSignatures`  
 <span data-ttu-id="25e91-108">[out] Matriz utilizada para almacenar los tokens de firma.</span><span class="sxs-lookup"><span data-stu-id="25e91-108">[out] The array used to store the Signature tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="25e91-109">[in] Tamaño máximo de la matriz `rSignatures`.</span><span class="sxs-lookup"><span data-stu-id="25e91-109">[in] The maximum size of the `rSignatures` array.</span></span>  
  
 `pcSignatures`  
 <span data-ttu-id="25e91-110">[out] El número de tokens de firma que se devuelven en `rSignatures`.</span><span class="sxs-lookup"><span data-stu-id="25e91-110">[out] The number of Signature tokens returned in `rSignatures`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="25e91-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="25e91-111">Return Value</span></span>  
  
|<span data-ttu-id="25e91-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="25e91-112">HRESULT</span></span>|<span data-ttu-id="25e91-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="25e91-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="25e91-114">`EnumSignatures` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="25e91-114">`EnumSignatures` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="25e91-115">No hay ningún token para enumerar.</span><span class="sxs-lookup"><span data-stu-id="25e91-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="25e91-116">En ese caso, `pcSignatures` es cero.</span><span class="sxs-lookup"><span data-stu-id="25e91-116">In that case, `pcSignatures` is zero.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="25e91-117">Comentarios</span><span class="sxs-lookup"><span data-stu-id="25e91-117">Remarks</span></span>  
 <span data-ttu-id="25e91-118">Los tokens de firma se crean mediante el [GetTokenFromSig](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-gettokenfromsig-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="25e91-118">The Signature tokens are created by the [IMetaDataEmit::GetTokenFromSig](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-gettokenfromsig-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="25e91-119">Requisitos</span><span class="sxs-lookup"><span data-stu-id="25e91-119">Requirements</span></span>  
 <span data-ttu-id="25e91-120">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="25e91-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="25e91-121">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="25e91-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="25e91-122">**Biblioteca:** Incluye como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="25e91-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="25e91-123">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="25e91-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="25e91-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="25e91-124">See also</span></span>

- [<span data-ttu-id="25e91-125">IMetaDataImport (interfaz)</span><span class="sxs-lookup"><span data-stu-id="25e91-125">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="25e91-126">IMetaDataImport2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="25e91-126">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
