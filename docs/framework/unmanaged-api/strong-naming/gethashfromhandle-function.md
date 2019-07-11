---
title: GetHashFromHandle (Función)
ms.date: 03/30/2017
api_name:
- GetHashFromHandle
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- GetHashFromHandle
helpviewer_keywords:
- GetHashFromHandle function [.NET Framework strong naming]
ms.assetid: 9e00337f-b307-4602-9bc3-965a8dbf02cd
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: aa5d5ee469d41cca46ea05fa4111ce3abff808d4
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67771905"
---
# <a name="gethashfromhandle-function"></a><span data-ttu-id="f81be-102">GetHashFromHandle (Función)</span><span class="sxs-lookup"><span data-stu-id="f81be-102">GetHashFromHandle Function</span></span>
<span data-ttu-id="f81be-103">Genera un hash a partir del contenido del archivo con el identificador de archivos especificado mediante un algoritmo hash concreto.</span><span class="sxs-lookup"><span data-stu-id="f81be-103">Generates a hash over the contents of the file with the specified file handle, using the specified hash algorithm.</span></span>  
  
 <span data-ttu-id="f81be-104">Esta función está desusada.</span><span class="sxs-lookup"><span data-stu-id="f81be-104">This function has been deprecated.</span></span> <span data-ttu-id="f81be-105">Use la [ICLRStrongName](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromhandle-method.md) método en su lugar.</span><span class="sxs-lookup"><span data-stu-id="f81be-105">Use the [ICLRStrongName::GetHashFromHandle](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromhandle-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f81be-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f81be-106">Syntax</span></span>  
  
```cpp  
HRESULT GetHashFromHandle (  
    [in]  HANDLE   hFile,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE     *pbHash,  
    [in]  DWORD    cchHash,  
    [out] DWORD    *pchHash  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f81be-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f81be-107">Parameters</span></span>  
 `hFile`  
 <span data-ttu-id="f81be-108">[in] El identificador del archivo que se aplica un algoritmo hash.</span><span class="sxs-lookup"><span data-stu-id="f81be-108">[in] The handle of the file to be hashed.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="f81be-109">[in, out] Una constante que especifica el algoritmo hash.</span><span class="sxs-lookup"><span data-stu-id="f81be-109">[in, out] A constant that specifies the hash algorithm.</span></span> <span data-ttu-id="f81be-110">Usar cero para el algoritmo predeterminado.</span><span class="sxs-lookup"><span data-stu-id="f81be-110">Use zero for the default algorithm.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="f81be-111">[out] El búfer hash devuelto.</span><span class="sxs-lookup"><span data-stu-id="f81be-111">[out] The returned hash buffer.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="f81be-112">[in] El tamaño máximo solicitado de `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="f81be-112">[in] The requested maximum size of `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="f81be-113">[out] El tamaño, en bytes, del devuelto `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="f81be-113">[out] The size, in bytes, of the returned `pbHash`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f81be-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f81be-114">Requirements</span></span>  
 <span data-ttu-id="f81be-115">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f81be-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f81be-116">**Encabezado**: StrongName.h</span><span class="sxs-lookup"><span data-stu-id="f81be-116">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="f81be-117">**Biblioteca:** Incluye como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="f81be-117">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="f81be-118">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f81be-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f81be-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="f81be-119">See also</span></span>

- [<span data-ttu-id="f81be-120">GetHashFromHandle (método)</span><span class="sxs-lookup"><span data-stu-id="f81be-120">GetHashFromHandle Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromhandle-method.md)
- [<span data-ttu-id="f81be-121">ICLRStrongName (interfaz)</span><span class="sxs-lookup"><span data-stu-id="f81be-121">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
