---
title: ISymUnmanagedDocument::GetLanguageVendor (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedDocument.GetLanguageVendor
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedDocument::GetLanguageVendor
helpviewer_keywords:
- GetLanguageVendor method [.NET Framework debugging]
- ISymUnmanagedDocument::GetLanguageVendor method [.NET Framework debugging]
ms.assetid: 1d4b702e-4922-441d-8b44-03804284f70b
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 25797822fc147c973ee06a52669aa9bf3c25422e
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57496253"
---
# <a name="isymunmanageddocumentgetlanguagevendor-method"></a><span data-ttu-id="5148c-102">ISymUnmanagedDocument::GetLanguageVendor (Método)</span><span class="sxs-lookup"><span data-stu-id="5148c-102">ISymUnmanagedDocument::GetLanguageVendor Method</span></span>
<span data-ttu-id="5148c-103">Obtiene el proveedor de lenguaje de este documento.</span><span class="sxs-lookup"><span data-stu-id="5148c-103">Gets the language vendor of this document.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5148c-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5148c-104">Syntax</span></span>  
  
```  
HRESULT GetLanguageVendor(  
    [out, retval]  GUID*  pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5148c-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="5148c-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="5148c-106">[out] Un puntero a una variable que recibe el proveedor de lenguaje.</span><span class="sxs-lookup"><span data-stu-id="5148c-106">[out] A pointer to a variable that receives the language vendor.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5148c-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="5148c-107">Return Value</span></span>  
 <span data-ttu-id="5148c-108">S_OK si el método tiene éxito.</span><span class="sxs-lookup"><span data-stu-id="5148c-108">S_OK if the method succeeds.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5148c-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="5148c-109">See also</span></span>
- [<span data-ttu-id="5148c-110">ISymUnmanagedDocument (interfaz)</span><span class="sxs-lookup"><span data-stu-id="5148c-110">ISymUnmanagedDocument Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-interface.md)
