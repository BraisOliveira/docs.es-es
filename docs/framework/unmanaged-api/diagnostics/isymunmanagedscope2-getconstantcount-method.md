---
title: ISymUnmanagedScope2::GetConstantCount (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedScope2.GetConstantCount
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedScope2::GetConstantCount
helpviewer_keywords:
- ISymUnmanagedScope2::GetConstantCount method [.NET Framework debugging]
- GetConstantCount method [.NET Framework debugging]
ms.assetid: 1e1f0be6-c4e8-4d6c-98cd-d5fa9f686e87
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 2a063d25e180be466421c14ca65a5b4cea881fc8
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59127333"
---
# <a name="isymunmanagedscope2getconstantcount-method"></a><span data-ttu-id="39879-102">ISymUnmanagedScope2::GetConstantCount (Método)</span><span class="sxs-lookup"><span data-stu-id="39879-102">ISymUnmanagedScope2::GetConstantCount Method</span></span>
<span data-ttu-id="39879-103">Obtiene un recuento de las constantes definidas en este ámbito.</span><span class="sxs-lookup"><span data-stu-id="39879-103">Gets a count of the constants defined within this scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="39879-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="39879-104">Syntax</span></span>  
  
```  
HRESULT GetConstantCount(  
    [out, retval] ULONG32 *pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="39879-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="39879-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="39879-106">[out] Un puntero a un `ULONG32` que recibe el tamaño, en caracteres, del búfer necesario para contener las constantes.</span><span class="sxs-lookup"><span data-stu-id="39879-106">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the constants.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="39879-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="39879-107">Return Value</span></span>  
 <span data-ttu-id="39879-108">S_OK si el método se realiza correctamente; en caso contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="39879-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="39879-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="39879-109">Requirements</span></span>  
 <span data-ttu-id="39879-110">**Encabezado**: CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="39879-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="39879-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="39879-111">See also</span></span>

- [<span data-ttu-id="39879-112">ISymUnmanagedScope2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="39879-112">ISymUnmanagedScope2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope2-interface.md)
