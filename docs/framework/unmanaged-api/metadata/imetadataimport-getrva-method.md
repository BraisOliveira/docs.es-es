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
ms.openlocfilehash: d305aa59c1b9e9e1225b30f12e36fc689d584db1
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67778886"
---
# <a name="imetadataimportgetrva-method"></a><span data-ttu-id="c0148-102">IMetaDataImport::GetRVA (Método)</span><span class="sxs-lookup"><span data-stu-id="c0148-102">IMetaDataImport::GetRVA Method</span></span>
<span data-ttu-id="c0148-103">Obtiene la dirección virtual relativa (RVA) y las marcas de implementación del método o campo representado por el token especificado.</span><span class="sxs-lookup"><span data-stu-id="c0148-103">Gets the relative virtual address (RVA) and the implementation flags of the method or field represented by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c0148-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c0148-104">Syntax</span></span>  
  
```cpp  
HRESULT GetRVA (  
   [in]  mdToken     tk,   
   [out] ULONG       *pulCodeRVA,   
   [out]  DWORD      *pdwImplFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c0148-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c0148-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="c0148-106">[in] Un token de metadatos MethodDef o FieldDef que representa el objeto de código para devolver la RVA.</span><span class="sxs-lookup"><span data-stu-id="c0148-106">[in] A MethodDef or FieldDef metadata token that represents the code object to return the RVA for.</span></span> <span data-ttu-id="c0148-107">Si el token es un FieldDef, el campo debe ser una variable global.</span><span class="sxs-lookup"><span data-stu-id="c0148-107">If the token is a FieldDef, the field must be a global variable.</span></span>  
  
 `pulCodeRVA`  
 <span data-ttu-id="c0148-108">[out] Un puntero a la dirección virtual relativa del objeto de código representado por el token.</span><span class="sxs-lookup"><span data-stu-id="c0148-108">[out] A pointer to the relative virtual address of the code object represented by the token.</span></span>  
  
 `pdwImplFlags`  
 <span data-ttu-id="c0148-109">[out] Un puntero a los marcadores de implementación para el método.</span><span class="sxs-lookup"><span data-stu-id="c0148-109">[out] A pointer to the implementation flags for the method.</span></span> <span data-ttu-id="c0148-110">Este valor es una máscara de bits desde el [CorMethodImpl](../../../../docs/framework/unmanaged-api/metadata/cormethodimpl-enumeration.md) enumeración.</span><span class="sxs-lookup"><span data-stu-id="c0148-110">This value is a bitmask from the [CorMethodImpl](../../../../docs/framework/unmanaged-api/metadata/cormethodimpl-enumeration.md) enumeration.</span></span> <span data-ttu-id="c0148-111">El valor de `pdwImplFlags` es válido únicamente si `tk` es un token de MethodDef.</span><span class="sxs-lookup"><span data-stu-id="c0148-111">The value of `pdwImplFlags` is valid only if `tk` is a MethodDef token.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c0148-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c0148-112">Requirements</span></span>  
 <span data-ttu-id="c0148-113">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c0148-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c0148-114">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="c0148-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="c0148-115">**Biblioteca:** Incluye como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="c0148-115">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="c0148-116">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c0148-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c0148-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="c0148-117">See also</span></span>

- [<span data-ttu-id="c0148-118">IMetaDataImport (interfaz)</span><span class="sxs-lookup"><span data-stu-id="c0148-118">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="c0148-119">IMetaDataImport2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="c0148-119">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
