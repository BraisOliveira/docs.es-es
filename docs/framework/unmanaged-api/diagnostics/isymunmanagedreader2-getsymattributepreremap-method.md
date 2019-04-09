---
title: ISymUnmanagedReader2::GetSymAttributePreRemap (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader2.GetSymAttributePreRemap
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader2::GetSymAttributePreRemap
helpviewer_keywords:
- GetSymAttributePreRemap method [.NET Framework debugging]
- ISymUnmanagedReader2::GetSymAttributePreRemap method [.NET Framework debugging]
ms.assetid: 7580d546-a709-40c5-ad02-aa70d774fd0b
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 543a8015e944333942b619060059273577902a74
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59110297"
---
# <a name="isymunmanagedreader2getsymattributepreremap-method"></a><span data-ttu-id="25fa7-102">ISymUnmanagedReader2::GetSymAttributePreRemap (Método)</span><span class="sxs-lookup"><span data-stu-id="25fa7-102">ISymUnmanagedReader2::GetSymAttributePreRemap Method</span></span>
<span data-ttu-id="25fa7-103">Obtiene un atributo personalizado basándose en su nombre.</span><span class="sxs-lookup"><span data-stu-id="25fa7-103">Gets a custom attribute based upon its name.</span></span> <span data-ttu-id="25fa7-104">A diferencia de los atributos personalizados de los metadatos, estos atributos se encuentran en el almacén de símbolos.</span><span class="sxs-lookup"><span data-stu-id="25fa7-104">Unlike metadata custom attributes, these attributes are held in the symbol store.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="25fa7-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="25fa7-105">Syntax</span></span>  
  
```  
HRESULT GetSymAttributePreRemap(  
    [in]  mdToken  parent,  
    [in]  WCHAR    *name,  
    [in]  ULONG32  cBuffer,  
    [out] ULONG32  *pcBuffer,  
    [out, size_is(cBuffer),  
        length_is(*pcBuffer)] BYTE buffer[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="25fa7-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="25fa7-106">Parameters</span></span>  
 `parent`  
 <span data-ttu-id="25fa7-107">[in] El token de metadatos del elemento primario.</span><span class="sxs-lookup"><span data-stu-id="25fa7-107">[in] The metadata token of the parent.</span></span>  
  
 `name`  
 <span data-ttu-id="25fa7-108">[in] Un puntero a un `WCHAR` que contiene el nombre.</span><span class="sxs-lookup"><span data-stu-id="25fa7-108">[in] A pointer to a `WCHAR` that contains the name.</span></span>  
  
 `cBuffer`  
 <span data-ttu-id="25fa7-109">[in] Un `ULONG32` que indica el tamaño de la `buffer` matriz.</span><span class="sxs-lookup"><span data-stu-id="25fa7-109">[in] A `ULONG32` that indicates the size of the `buffer` array.</span></span>  
  
 `pcBuffer`  
 <span data-ttu-id="25fa7-110">[out] Un puntero a un `ULONG32` que recibe el tamaño del búfer necesario para contener los bytes del atributo.</span><span class="sxs-lookup"><span data-stu-id="25fa7-110">[out] A pointer to a `ULONG32` that receives the size of the buffer required to contain the attribute bytes.</span></span>  
  
 `buffer`  
 <span data-ttu-id="25fa7-111">[out] Un puntero al búfer que recibe los bytes del atributo.</span><span class="sxs-lookup"><span data-stu-id="25fa7-111">[out] A pointer to the buffer that receives the attribute bytes.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="25fa7-112">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="25fa7-112">Return Value</span></span>  
 <span data-ttu-id="25fa7-113">S_OK si el método se realiza correctamente; en caso contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="25fa7-113">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="25fa7-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="25fa7-114">Requirements</span></span>  
 <span data-ttu-id="25fa7-115">**Encabezado**: CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="25fa7-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="25fa7-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="25fa7-116">See also</span></span>

- [<span data-ttu-id="25fa7-117">ISymUnmanagedReader2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="25fa7-117">ISymUnmanagedReader2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader2-interface.md)
