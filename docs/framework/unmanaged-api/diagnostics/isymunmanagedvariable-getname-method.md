---
title: ISymUnmanagedVariable::GetName (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedVariable.GetName
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedVariable::GetName
helpviewer_keywords:
- GetName method, ISymUnmanagedVariable interface [.NET Framework debugging]
- ISymUnmanagedVariable::GetName method [.NET Framework debugging]
ms.assetid: eedf1ef0-9d4a-4847-a201-4e99572dfe5e
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: e863640e18ca64de084331327e0fa39468b54b60
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59176246"
---
# <a name="isymunmanagedvariablegetname-method"></a><span data-ttu-id="b4fef-102">ISymUnmanagedVariable::GetName (Método)</span><span class="sxs-lookup"><span data-stu-id="b4fef-102">ISymUnmanagedVariable::GetName Method</span></span>
<span data-ttu-id="b4fef-103">Obtiene el nombre de esta variable.</span><span class="sxs-lookup"><span data-stu-id="b4fef-103">Gets the name of this variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b4fef-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b4fef-104">Syntax</span></span>  
  
```  
HRESULT GetName(  
    [in]  ULONG32  cchName,  
    [out] ULONG32  *pcchName,  
    [out, size_is(cchName),  
        length_is(*pcchName)] WCHAR szName[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b4fef-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="b4fef-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="b4fef-106">[in] La longitud del búfer que el `pcchName` parámetro señala.</span><span class="sxs-lookup"><span data-stu-id="b4fef-106">[in] The length of the buffer that the `pcchName` parameter points to.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="b4fef-107">[out] Un puntero a un `ULONG32` que recibe el tamaño, en caracteres, del búfer necesario para contener el nombre, incluida la terminación null.</span><span class="sxs-lookup"><span data-stu-id="b4fef-107">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the name, including the null termination.</span></span>  
  
 `szName`  
 <span data-ttu-id="b4fef-108">[out] Búfer que almacena el nombre.</span><span class="sxs-lookup"><span data-stu-id="b4fef-108">[out] The buffer that stores the name.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b4fef-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="b4fef-109">Return Value</span></span>  
 <span data-ttu-id="b4fef-110">S_OK si el método se realiza correctamente; en caso contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="b4fef-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b4fef-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b4fef-111">Requirements</span></span>  
 <span data-ttu-id="b4fef-112">**Encabezado**: CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="b4fef-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b4fef-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="b4fef-113">See also</span></span>

- [<span data-ttu-id="b4fef-114">ISymUnmanagedVariable (interfaz)</span><span class="sxs-lookup"><span data-stu-id="b4fef-114">ISymUnmanagedVariable Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-interface.md)
