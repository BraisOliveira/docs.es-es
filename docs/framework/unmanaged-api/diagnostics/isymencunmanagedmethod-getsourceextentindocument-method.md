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
ms.openlocfilehash: e4948a853434b14845983addb0e6fa4012279084
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67776871"
---
# <a name="isymencunmanagedmethodgetsourceextentindocument-method"></a><span data-ttu-id="a4aa6-102">ISymENCUnmanagedMethod::GetSourceExtentInDocument (Método)</span><span class="sxs-lookup"><span data-stu-id="a4aa6-102">ISymENCUnmanagedMethod::GetSourceExtentInDocument Method</span></span>
<span data-ttu-id="a4aa6-103">Obtiene el valor más pequeño inicia línea y más grande fin de línea para el método en un documento específico.</span><span class="sxs-lookup"><span data-stu-id="a4aa6-103">Gets the smallest start line and largest end line for the method in a specific document.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a4aa6-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a4aa6-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSourceExtentInDocument(  
    [in]  ISymUnmanagedDocument *document,  
    [out] ULONG32* pstartLine,  
    [out] ULONG32* pendLine);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a4aa6-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a4aa6-105">Parameters</span></span>  
 `document`  
 <span data-ttu-id="a4aa6-106">[in] Un puntero al documento.</span><span class="sxs-lookup"><span data-stu-id="a4aa6-106">[in] A pointer to the document.</span></span>  
  
 `pstartLine`  
 <span data-ttu-id="a4aa6-107">[out] Un puntero a un `ULONG32` que recibe la línea de inicio.</span><span class="sxs-lookup"><span data-stu-id="a4aa6-107">[out] A pointer to a `ULONG32` that receives the start line.</span></span>  
  
 `pendLine`  
 <span data-ttu-id="a4aa6-108">[out] Un puntero a un `ULONG32` que recibe la línea final.</span><span class="sxs-lookup"><span data-stu-id="a4aa6-108">[out] A pointer to a `ULONG32` that receives the end line.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a4aa6-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="a4aa6-109">Return Value</span></span>  
 <span data-ttu-id="a4aa6-110">S_OK si el método se realiza correctamente; en caso contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="a4aa6-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a4aa6-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a4aa6-111">Requirements</span></span>  
 <span data-ttu-id="a4aa6-112">**Encabezado**: CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="a4aa6-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a4aa6-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="a4aa6-113">See also</span></span>

- [<span data-ttu-id="a4aa6-114">ISymENCUnmanagedMethod (interfaz)</span><span class="sxs-lookup"><span data-stu-id="a4aa6-114">ISymENCUnmanagedMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymencunmanagedmethod-interface.md)
