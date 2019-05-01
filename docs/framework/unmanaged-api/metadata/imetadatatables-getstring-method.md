---
title: IMetaDataTables::GetString (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetString
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetString
helpviewer_keywords:
- IMetaDataTables::GetString method [.NET Framework metadata]
- GetString method, IMetaDataTables interface [.NET Framework metadata]
ms.assetid: 895c35cf-b95d-4e3b-93b5-cfc1cf9044fc
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 8fed98521c0609ebd8b5f65885d69c77814e9e85
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62042294"
---
# <a name="imetadatatablesgetstring-method"></a><span data-ttu-id="ebf3b-102">IMetaDataTables::GetString (Método)</span><span class="sxs-lookup"><span data-stu-id="ebf3b-102">IMetaDataTables::GetString Method</span></span>
<span data-ttu-id="ebf3b-103">Obtiene la cadena en el índice especificado de la columna de tabla en el ámbito de referencia actual.</span><span class="sxs-lookup"><span data-stu-id="ebf3b-103">Gets the string at the specified index from the table column in the current reference scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ebf3b-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ebf3b-104">Syntax</span></span>  
  
```  
HRESULT GetString (   
    [in]  ULONG       ixString,  
    [out] const char  **ppString  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ebf3b-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ebf3b-105">Parameters</span></span>  
 `ixString`  
 <span data-ttu-id="ebf3b-106">[in] Índice en el que se va a empezar a buscar el valor siguiente.</span><span class="sxs-lookup"><span data-stu-id="ebf3b-106">[in] The index at which to start to search for the next value.</span></span>  
  
 `ppString`  
 <span data-ttu-id="ebf3b-107">[out] Un puntero a un puntero al valor de cadena devuelta.</span><span class="sxs-lookup"><span data-stu-id="ebf3b-107">[out] A pointer to a pointer to the returned string value.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ebf3b-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ebf3b-108">Requirements</span></span>  
 <span data-ttu-id="ebf3b-109">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ebf3b-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ebf3b-110">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="ebf3b-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ebf3b-111">**Biblioteca:** Usar como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="ebf3b-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="ebf3b-112">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ebf3b-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ebf3b-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="ebf3b-113">See also</span></span>

- [<span data-ttu-id="ebf3b-114">IMetaDataTables (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ebf3b-114">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="ebf3b-115">IMetaDataTables2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ebf3b-115">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
