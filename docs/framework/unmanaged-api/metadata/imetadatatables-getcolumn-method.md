---
title: IMetaDataTables::GetColumn (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetColumn
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetColumn
helpviewer_keywords:
- IMetaDataTables::GetColumn method [.NET Framework metadata]
- GetColumn method [.NET Framework metadata]
ms.assetid: 1032055b-cabb-45c5-a50e-7e853201b175
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 22f9ceab2f01ac12762710f313c56f3f0ee4e6be
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67781544"
---
# <a name="imetadatatablesgetcolumn-method"></a><span data-ttu-id="45275-102">IMetaDataTables::GetColumn (Método)</span><span class="sxs-lookup"><span data-stu-id="45275-102">IMetaDataTables::GetColumn Method</span></span>
<span data-ttu-id="45275-103">Obtiene un puntero al valor incluido en la celda de la columna especificada y la fila en la tabla dada.</span><span class="sxs-lookup"><span data-stu-id="45275-103">Gets a pointer to the value contained in the cell of the specified column and row in the given table.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="45275-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="45275-104">Syntax</span></span>  
  
```cpp  
HRESULT GetColumn (   
    [in]  ULONG   ixTbl,  
    [in]  ULONG   ixCol,  
    [in]  ULONG   rid,  
    [out] ULONG   *pVal  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="45275-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="45275-105">Parameters</span></span>  
 `ixTbl`  
 <span data-ttu-id="45275-106">[in] El índice de la tabla.</span><span class="sxs-lookup"><span data-stu-id="45275-106">[in] The index of the table.</span></span>  
  
 `ixCol`  
 <span data-ttu-id="45275-107">[in] El índice de la columna en la tabla.</span><span class="sxs-lookup"><span data-stu-id="45275-107">[in] The index of the column in the table.</span></span>  
  
 `rid`  
 <span data-ttu-id="45275-108">[in] El índice de la fila en la tabla.</span><span class="sxs-lookup"><span data-stu-id="45275-108">[in] The index of the row in the table.</span></span>  
  
 `pVal`  
 <span data-ttu-id="45275-109">[out] Un puntero al valor de la celda.</span><span class="sxs-lookup"><span data-stu-id="45275-109">[out] A pointer to the value in the cell.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="45275-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="45275-110">Requirements</span></span>  
 <span data-ttu-id="45275-111">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="45275-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="45275-112">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="45275-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="45275-113">**Biblioteca:** Usar como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="45275-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="45275-114">**Versiones de .NET framework** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="45275-114">**.NET Framework Versions** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="45275-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="45275-115">See also</span></span>

- [<span data-ttu-id="45275-116">IMetaDataTables (interfaz)</span><span class="sxs-lookup"><span data-stu-id="45275-116">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="45275-117">IMetaDataTables2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="45275-117">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
