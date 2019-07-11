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
ms.openlocfilehash: 8298e7240052bdd859dbe414281d8e78984342e8
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67778248"
---
# <a name="isymunmanagedvariablegetname-method"></a><span data-ttu-id="2b270-102">ISymUnmanagedVariable::GetName (Método)</span><span class="sxs-lookup"><span data-stu-id="2b270-102">ISymUnmanagedVariable::GetName Method</span></span>
<span data-ttu-id="2b270-103">Obtiene el nombre de esta variable.</span><span class="sxs-lookup"><span data-stu-id="2b270-103">Gets the name of this variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2b270-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2b270-104">Syntax</span></span>  
  
```cpp  
HRESULT GetName(  
    [in]  ULONG32  cchName,  
    [out] ULONG32  *pcchName,  
    [out, size_is(cchName),  
        length_is(*pcchName)] WCHAR szName[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2b270-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="2b270-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="2b270-106">[in] La longitud del búfer que el `pcchName` parámetro señala.</span><span class="sxs-lookup"><span data-stu-id="2b270-106">[in] The length of the buffer that the `pcchName` parameter points to.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="2b270-107">[out] Un puntero a un `ULONG32` que recibe el tamaño, en caracteres, del búfer necesario para contener el nombre, incluida la terminación null.</span><span class="sxs-lookup"><span data-stu-id="2b270-107">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the name, including the null termination.</span></span>  
  
 `szName`  
 <span data-ttu-id="2b270-108">[out] Búfer que almacena el nombre.</span><span class="sxs-lookup"><span data-stu-id="2b270-108">[out] The buffer that stores the name.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2b270-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="2b270-109">Return Value</span></span>  
 <span data-ttu-id="2b270-110">S_OK si el método se realiza correctamente; en caso contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="2b270-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2b270-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2b270-111">Requirements</span></span>  
 <span data-ttu-id="2b270-112">**Encabezado**: CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="2b270-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2b270-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="2b270-113">See also</span></span>

- [<span data-ttu-id="2b270-114">ISymUnmanagedVariable (interfaz)</span><span class="sxs-lookup"><span data-stu-id="2b270-114">ISymUnmanagedVariable Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-interface.md)
