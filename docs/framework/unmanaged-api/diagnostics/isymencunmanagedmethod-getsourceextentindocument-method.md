---
title: ISymENCUnmanagedMethod::GetSourceExtentInDocument (Método)
ms.date: 03/30/2017
api_name:
- ISymENCUnmanagedMethod.GetSourceExtentInDocument
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymENCUnmanagedMethod::GetSourceExtentInDocument
helpviewer_keywords:
- GetSourceExtentInDocument method [.NET Framework debugging]
- ISymENCUnmanagedMethod::GetSourceExtentInDocument method [.NET Framework debugging]
ms.assetid: 9c5566ab-4ec7-4b61-9753-839bb90ae78c
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 442584cffe4b4ae44702892587e261d41abf4e8a
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59150428"
---
# <a name="isymencunmanagedmethodgetsourceextentindocument-method"></a><span data-ttu-id="a1242-102">ISymENCUnmanagedMethod::GetSourceExtentInDocument (Método)</span><span class="sxs-lookup"><span data-stu-id="a1242-102">ISymENCUnmanagedMethod::GetSourceExtentInDocument Method</span></span>
<span data-ttu-id="a1242-103">Obtiene el valor más pequeño inicia línea y más grande fin de línea para el método en un documento específico.</span><span class="sxs-lookup"><span data-stu-id="a1242-103">Gets the smallest start line and largest end line for the method in a specific document.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a1242-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a1242-104">Syntax</span></span>  
  
```  
HRESULT GetSourceExtentInDocument(  
    [in]  ISymUnmanagedDocument *document,  
    [out] ULONG32* pstartLine,  
    [out] ULONG32* pendLine);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a1242-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a1242-105">Parameters</span></span>  
 `document`  
 <span data-ttu-id="a1242-106">[in] Un puntero al documento.</span><span class="sxs-lookup"><span data-stu-id="a1242-106">[in] A pointer to the document.</span></span>  
  
 `pstartLine`  
 <span data-ttu-id="a1242-107">[out] Un puntero a un `ULONG32` que recibe la línea de inicio.</span><span class="sxs-lookup"><span data-stu-id="a1242-107">[out] A pointer to a `ULONG32` that receives the start line.</span></span>  
  
 `pendLine`  
 <span data-ttu-id="a1242-108">[out] Un puntero a un `ULONG32` que recibe la línea final.</span><span class="sxs-lookup"><span data-stu-id="a1242-108">[out] A pointer to a `ULONG32` that receives the end line.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a1242-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="a1242-109">Return Value</span></span>  
 <span data-ttu-id="a1242-110">S_OK si el método se realiza correctamente; en caso contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="a1242-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a1242-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a1242-111">Requirements</span></span>  
 <span data-ttu-id="a1242-112">**Encabezado**: CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="a1242-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a1242-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="a1242-113">See also</span></span>

- [<span data-ttu-id="a1242-114">ISymENCUnmanagedMethod (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="a1242-114">ISymENCUnmanagedMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymencunmanagedmethod-interface.md)
