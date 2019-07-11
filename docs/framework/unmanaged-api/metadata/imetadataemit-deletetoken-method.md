---
title: IMetaDataEmit::DeleteToken (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DeleteToken
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DeleteToken
helpviewer_keywords:
- DeleteToken method [.NET Framework metadata]
- IMetaDataEmit::DeleteToken method [.NET Framework metadata]
ms.assetid: a4926d0a-261b-46b1-9994-82633661a64b
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 1c734801fd5629d8ed6bf4bccd81cf6b6de246f4
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67777400"
---
# <a name="imetadataemitdeletetoken-method"></a><span data-ttu-id="e93fc-102">IMetaDataEmit::DeleteToken (Método)</span><span class="sxs-lookup"><span data-stu-id="e93fc-102">IMetaDataEmit::DeleteToken Method</span></span>
<span data-ttu-id="e93fc-103">Elimina el token especificado de ámbito de metadatos actual.</span><span class="sxs-lookup"><span data-stu-id="e93fc-103">Deletes the specified token from the current metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e93fc-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e93fc-104">Syntax</span></span>  
  
```cpp  
HRESULT DeleteToken (   
    [in]  mdToken     tkObj   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e93fc-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e93fc-105">Parameters</span></span>  
 `tkObj`  
 <span data-ttu-id="e93fc-106">[in] Token que se va a eliminar.</span><span class="sxs-lookup"><span data-stu-id="e93fc-106">[in] The token to be deleted.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e93fc-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e93fc-107">Requirements</span></span>  
 <span data-ttu-id="e93fc-108">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e93fc-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e93fc-109">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="e93fc-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="e93fc-110">**Biblioteca:** Usar como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="e93fc-110">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e93fc-111">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e93fc-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e93fc-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="e93fc-112">See also</span></span>

- [<span data-ttu-id="e93fc-113">IMetaDataEmit (interfaz)</span><span class="sxs-lookup"><span data-stu-id="e93fc-113">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="e93fc-114">IMetaDataEmit2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="e93fc-114">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
