---
title: IMetaDataEmit::SetMethodProps (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetMethodProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetMethodProps
helpviewer_keywords:
- SetMethodProps method [.NET Framework metadata]
- IMetaDataEmit::SetMethodProps method [.NET Framework metadata]
ms.assetid: e0c6ac12-22ea-43f5-b799-8cda0faf3336
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a764aef9c485f7eb9d15bbb4fab667a3f254eb07
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57473779"
---
# <a name="imetadataemitsetmethodprops-method"></a><span data-ttu-id="85e95-102">IMetaDataEmit::SetMethodProps (Método)</span><span class="sxs-lookup"><span data-stu-id="85e95-102">IMetaDataEmit::SetMethodProps Method</span></span>
<span data-ttu-id="85e95-103">Establece o actualiza la característica, almacenada en la dirección virtual relativa especificada, de un método definido por una llamada anterior a [DefineMethod](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definemethod-method.md).</span><span class="sxs-lookup"><span data-stu-id="85e95-103">Sets or updates the feature, stored at the specified relative virtual address, of a method defined by a prior call to [IMetaDataEmit::DefineMethod](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definemethod-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="85e95-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="85e95-104">Syntax</span></span>  
  
```  
HRESULT SetMethodProps (   
    [in]  mdMethodDef md,   
    [in]  DWORD       dwMethodFlags,  
    [in]  ULONG       ulCodeRVA,   
    [in]  DWORD       dwImplFlags   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="85e95-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="85e95-105">Parameters</span></span>  
 `md`  
 <span data-ttu-id="85e95-106">[in] El token para el método que se puede cambiar.</span><span class="sxs-lookup"><span data-stu-id="85e95-106">[in] The token for the method to be changed.</span></span>  
  
 `dwMethodFlags`  
 <span data-ttu-id="85e95-107">[in] Los atributos de miembro.</span><span class="sxs-lookup"><span data-stu-id="85e95-107">[in] The member attributes.</span></span>  
  
 `ulCodeRVA`  
 <span data-ttu-id="85e95-108">[in] La dirección del código.</span><span class="sxs-lookup"><span data-stu-id="85e95-108">[in] The address of the code.</span></span>  
  
 `dwImplFlags`  
 <span data-ttu-id="85e95-109">[in] Las marcas de implementación para el método.</span><span class="sxs-lookup"><span data-stu-id="85e95-109">[in] The implementation flags for the method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="85e95-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="85e95-110">Requirements</span></span>  
 <span data-ttu-id="85e95-111">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="85e95-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="85e95-112">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="85e95-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="85e95-113">**Biblioteca:** Usar como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="85e95-113">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="85e95-114">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="85e95-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="85e95-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="85e95-115">See also</span></span>
- [<span data-ttu-id="85e95-116">IMetaDataEmit (interfaz)</span><span class="sxs-lookup"><span data-stu-id="85e95-116">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="85e95-117">IMetaDataEmit2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="85e95-117">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
