---
title: ISymUnmanagedENCUpdate::GetLocalVariableCount (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedENCUpdate.GetLocalVariableCount
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedENCUpdate::GetLocalVariableCount
helpviewer_keywords:
- ISymUnmanagedENCUpdate::GetLocalVariableCount method [.NET Framework debugging]
- GetLocalVariableCount method [.NET Framework debugging]
ms.assetid: 9777d8bb-4abc-4be8-aa7c-34f853eceb9c
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 11a75ca89a3537ce8ee72e8ba24401800eacff20
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61939742"
---
# <a name="isymunmanagedencupdategetlocalvariablecount-method"></a><span data-ttu-id="78f0c-102">ISymUnmanagedENCUpdate::GetLocalVariableCount (Método)</span><span class="sxs-lookup"><span data-stu-id="78f0c-102">ISymUnmanagedENCUpdate::GetLocalVariableCount Method</span></span>
<span data-ttu-id="78f0c-103">Obtiene el número de variables locales.</span><span class="sxs-lookup"><span data-stu-id="78f0c-103">Gets the number of local variables.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="78f0c-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="78f0c-104">Syntax</span></span>  
  
```  
HRESULT GetLocalVariableCount(  
    [in]  mdMethodDef  mdMethodToken,  
    [out] ULONG        *pcLocals);  
```  
  
## <a name="parameters"></a><span data-ttu-id="78f0c-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="78f0c-105">Parameters</span></span>  
 `mdMethodToken`  
 <span data-ttu-id="78f0c-106">[in] El token de metadatos de los métodos.</span><span class="sxs-lookup"><span data-stu-id="78f0c-106">[in] The metadata token of methods.</span></span>  
  
 `pcLocals`  
 <span data-ttu-id="78f0c-107">[out] Un puntero a un `ULONG32` que recibe el tamaño, en caracteres, del búfer necesario para contener el número de variables locales.</span><span class="sxs-lookup"><span data-stu-id="78f0c-107">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the number of local variables.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="78f0c-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="78f0c-108">Return Value</span></span>  
 <span data-ttu-id="78f0c-109">S_OK si el método se realiza correctamente; en caso contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="78f0c-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="78f0c-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="78f0c-110">Requirements</span></span>  
 <span data-ttu-id="78f0c-111">**Encabezado**: CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="78f0c-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="78f0c-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="78f0c-112">See also</span></span>

- [<span data-ttu-id="78f0c-113">ISymUnmanagedENCUpdate (interfaz)</span><span class="sxs-lookup"><span data-stu-id="78f0c-113">ISymUnmanagedENCUpdate Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-interface.md)
