---
title: ISymUnmanagedMethod::GetToken (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedMethod.GetToken
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedMethod::GetToken
helpviewer_keywords:
- ISymUnmanagedMethod::GetToken method [.NET Framework debugging]
- GetToken method, ISymUnmanagedMethod interface [.NET Framework debugging]
ms.assetid: 4effbe95-c36e-4a45-8b2a-ee21339415fb
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 7ec6e25452a40ae67570badde8a883878d103f95
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59187412"
---
# <a name="isymunmanagedmethodgettoken-method"></a><span data-ttu-id="42f1b-102">ISymUnmanagedMethod::GetToken (Método)</span><span class="sxs-lookup"><span data-stu-id="42f1b-102">ISymUnmanagedMethod::GetToken Method</span></span>
<span data-ttu-id="42f1b-103">Devuelve el token de metadatos para este método.</span><span class="sxs-lookup"><span data-stu-id="42f1b-103">Returns the metadata token for this method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="42f1b-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="42f1b-104">Syntax</span></span>  
  
```  
HRESULT GetToken(  
   [out, retval]  mdMethodDef  *pToken);  
```  
  
## <a name="parameters"></a><span data-ttu-id="42f1b-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="42f1b-105">Parameters</span></span>  
 `pToken`  
 <span data-ttu-id="42f1b-106">[out] Un puntero a un `mdMethodDef` que recibe el tamaño, en caracteres, del búfer necesario para contener los metadatos.</span><span class="sxs-lookup"><span data-stu-id="42f1b-106">[out] A pointer to a `mdMethodDef` that receives the size, in characters, of the buffer required to contain the metadata.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="42f1b-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="42f1b-107">Return Value</span></span>  
 <span data-ttu-id="42f1b-108">S_OK si el método se realiza correctamente; en caso contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="42f1b-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="42f1b-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="42f1b-109">Requirements</span></span>  
 <span data-ttu-id="42f1b-110">**Encabezado**: CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="42f1b-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="42f1b-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="42f1b-111">See also</span></span>

- [<span data-ttu-id="42f1b-112">ISymUnmanagedMethod (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="42f1b-112">ISymUnmanagedMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md)
