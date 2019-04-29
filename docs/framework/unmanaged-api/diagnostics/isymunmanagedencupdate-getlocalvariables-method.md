---
title: ISymUnmanagedENCUpdate::GetLocalVariables (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedENCUpdate.GetLocalVariables
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedENCUpdate::GetLocalVariables
helpviewer_keywords:
- ISymUnmanagedENCUpdate::GetLocalVariables method [.NET Framework debugging]
- GetLocalVariables method [.NET Framework debugging]
ms.assetid: 5c8840be-ffea-447f-9c8d-178f1eaf8d06
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 16e91a0c748e5b148e79dc73cf213b03c68c5021
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61939729"
---
# <a name="isymunmanagedencupdategetlocalvariables-method"></a><span data-ttu-id="a814a-102">ISymUnmanagedENCUpdate::GetLocalVariables (Método)</span><span class="sxs-lookup"><span data-stu-id="a814a-102">ISymUnmanagedENCUpdate::GetLocalVariables Method</span></span>
<span data-ttu-id="a814a-103">Obtiene las variables locales.</span><span class="sxs-lookup"><span data-stu-id="a814a-103">Gets the local variables.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a814a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a814a-104">Syntax</span></span>  
  
```  
HRESULT GetLocalVariables(  
    [in]  mdMethodDef  mdMethodToken,  
    [in]  ULONG        cLocals,  
    [out, size_is(cLocals), length_is(*pceltFetched)]  
        ISymUnmanagedVariable *rgLocals[],  
    [out] ULONG        *pceltFetched);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a814a-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a814a-105">Parameters</span></span>  
 `mdMethodToken`  
 <span data-ttu-id="a814a-106">[in] El token de metadatos del método.</span><span class="sxs-lookup"><span data-stu-id="a814a-106">[in] The metadata token of the method.</span></span>  
  
 `cLocals`  
 <span data-ttu-id="a814a-107">[in] Un `ULONG` que indica el tamaño de la `rgLocals` parámetro.</span><span class="sxs-lookup"><span data-stu-id="a814a-107">[in] A `ULONG` that indicates the size of the `rgLocals` parameter.</span></span>  
  
 `rgLocals`  
 <span data-ttu-id="a814a-108">[out] La matriz devuelta de [ISymUnmanagedVariable](isymunmanagedvariable-interface.md) instancias.</span><span class="sxs-lookup"><span data-stu-id="a814a-108">[out] The returned array of [ISymUnmanagedVariable](isymunmanagedvariable-interface.md) instances.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="a814a-109">[out] Un puntero a un `ULONG` que recibe el tamaño de la `rgLocals` búfer necesario para contener las variables locales.</span><span class="sxs-lookup"><span data-stu-id="a814a-109">[out] A pointer to a `ULONG` that receives the size of the `rgLocals` buffer required to contain the locals.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a814a-110">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="a814a-110">Return Value</span></span>  
 <span data-ttu-id="a814a-111">S_OK si el método se realiza correctamente; en caso contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="a814a-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a814a-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a814a-112">Requirements</span></span>  
 <span data-ttu-id="a814a-113">**Encabezado**: CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="a814a-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a814a-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="a814a-114">See also</span></span>

- [<span data-ttu-id="a814a-115">ISymUnmanagedENCUpdate (interfaz)</span><span class="sxs-lookup"><span data-stu-id="a814a-115">ISymUnmanagedENCUpdate Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-interface.md)
