---
title: ISymUnmanagedVariable::GetAddressField3 (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedVariable.GetAddressField3
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedVariable::GetAddressField3
helpviewer_keywords:
- ISymUnmanagedVariable::GetAddressField3 method [.NET Framework debugging]
- GetAddressField3 method [.NET Framework debugging]
ms.assetid: 4d834721-ad8d-439d-b356-c6b4aef022fc
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 76199dd18799c9f51f37d5b92e589effd7f45a57
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67778302"
---
# <a name="isymunmanagedvariablegetaddressfield3-method"></a><span data-ttu-id="e7b7d-102">ISymUnmanagedVariable::GetAddressField3 (Método)</span><span class="sxs-lookup"><span data-stu-id="e7b7d-102">ISymUnmanagedVariable::GetAddressField3 Method</span></span>
<span data-ttu-id="e7b7d-103">Obtiene el tercer campo de dirección de esta variable.</span><span class="sxs-lookup"><span data-stu-id="e7b7d-103">Gets the third address field for this variable.</span></span> <span data-ttu-id="e7b7d-104">Su significado depende del tipo de dirección.</span><span class="sxs-lookup"><span data-stu-id="e7b7d-104">Its meaning depends on the kind of address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e7b7d-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e7b7d-105">Syntax</span></span>  
  
```cpp  
HRESULT GetAddressField3(  
    [out, retval] ULONG32* pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e7b7d-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e7b7d-106">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="e7b7d-107">[out] Un puntero a un `ULONG32` que recibe el tercer campo de dirección.</span><span class="sxs-lookup"><span data-stu-id="e7b7d-107">[out] A pointer to a `ULONG32` that receives the third address field.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e7b7d-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="e7b7d-108">Return Value</span></span>  
 <span data-ttu-id="e7b7d-109">S_OK si el método se realiza correctamente; en caso contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="e7b7d-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e7b7d-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e7b7d-110">Requirements</span></span>  
 <span data-ttu-id="e7b7d-111">**Encabezado**: CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="e7b7d-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e7b7d-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="e7b7d-112">See also</span></span>

- [<span data-ttu-id="e7b7d-113">ISymUnmanagedVariable (interfaz)</span><span class="sxs-lookup"><span data-stu-id="e7b7d-113">ISymUnmanagedVariable Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-interface.md)
- [<span data-ttu-id="e7b7d-114">GetAddressField1 (método)</span><span class="sxs-lookup"><span data-stu-id="e7b7d-114">GetAddressField1 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddressfield1-method.md)
- [<span data-ttu-id="e7b7d-115">GetAddressField2 (método)</span><span class="sxs-lookup"><span data-stu-id="e7b7d-115">GetAddressField2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddressfield2-method.md)
- [<span data-ttu-id="e7b7d-116">GetAddressKind (método)</span><span class="sxs-lookup"><span data-stu-id="e7b7d-116">GetAddressKind Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddresskind-method.md)
