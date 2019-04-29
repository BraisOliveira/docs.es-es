---
title: IMetaDataTables::GetUserStringHeapSize (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetUserStringHeapSize
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetUserStringHeapSize
helpviewer_keywords:
- IMetaDataTables::GetUserStringHeapSize method [.NET Framework metadata]
- GetUserStringHeapSize method [.NET Framework metadata]
ms.assetid: cba9e4d6-9461-4420-9614-96ff7039ec9c
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d35231e4c36639722635796891056a8902b95940
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61645193"
---
# <a name="imetadatatablesgetuserstringheapsize-method"></a><span data-ttu-id="daadd-102">IMetaDataTables::GetUserStringHeapSize (Método)</span><span class="sxs-lookup"><span data-stu-id="daadd-102">IMetaDataTables::GetUserStringHeapSize Method</span></span>
<span data-ttu-id="daadd-103">Obtiene el tamaño, en bytes, del montón de cadenas de usuario.</span><span class="sxs-lookup"><span data-stu-id="daadd-103">Gets the size, in bytes, of the user string heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="daadd-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="daadd-104">Syntax</span></span>  
  
```  
HRESULT GetUserStringHeapSize (  
    [out] ULONG   *pcbBlobs  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="daadd-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="daadd-105">Parameters</span></span>  
 `pcbBlobs`  
 <span data-ttu-id="daadd-106">[out] Un puntero al tamaño, en bytes, del montón de cadenas de usuario.</span><span class="sxs-lookup"><span data-stu-id="daadd-106">[out] A pointer to the size, in bytes, of the user string heap.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="daadd-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="daadd-107">Requirements</span></span>  
 <span data-ttu-id="daadd-108">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="daadd-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="daadd-109">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="daadd-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="daadd-110">**Biblioteca:** Usar como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="daadd-110">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="daadd-111">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="daadd-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="daadd-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="daadd-112">See also</span></span>

- [<span data-ttu-id="daadd-113">IMetaDataTables (interfaz)</span><span class="sxs-lookup"><span data-stu-id="daadd-113">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="daadd-114">IMetaDataTables2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="daadd-114">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
