---
title: GetHashFromFile (Función)
ms.date: 03/30/2017
api_name:
- GetHashFromFile
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- GetHashFromFile
helpviewer_keywords:
- GetHashFromFile function [.NET Framework strong naming]
ms.assetid: b3c526a4-8fb4-4ad6-b6af-42ce9c06492e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 38c663bc2db780c89ca666702534a75525ae189b
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67771956"
---
# <a name="gethashfromfile-function"></a><span data-ttu-id="3dfa0-102">GetHashFromFile (Función)</span><span class="sxs-lookup"><span data-stu-id="3dfa0-102">GetHashFromFile Function</span></span>
<span data-ttu-id="3dfa0-103">Genera un hash a partir del contenido del archivo especificado.</span><span class="sxs-lookup"><span data-stu-id="3dfa0-103">Generates a hash over the contents of the specified file.</span></span>  
  
 <span data-ttu-id="3dfa0-104">Esta función está desusada.</span><span class="sxs-lookup"><span data-stu-id="3dfa0-104">This function has been deprecated.</span></span> <span data-ttu-id="3dfa0-105">Use la [ICLRStrongName](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfile-method.md) método en su lugar.</span><span class="sxs-lookup"><span data-stu-id="3dfa0-105">Use the [ICLRStrongName::GetHashFromFile](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfile-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3dfa0-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3dfa0-106">Syntax</span></span>  
  
```cpp  
HRESULT GetHashFromFile (  
    [in]  LPCSTR   szFilePath,  
    [in, out] unsigned int   *piHashAlg,   
    [out] BYTE     *pbHash,      
    [in]  DWORD    cchHash,      
    [out] DWORD    *pchHash  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3dfa0-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="3dfa0-107">Parameters</span></span>  
 `szFilePath`  
 <span data-ttu-id="3dfa0-108">[in] El nombre del archivo a hash.</span><span class="sxs-lookup"><span data-stu-id="3dfa0-108">[in] The name of the file to hash.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="3dfa0-109">[in, out] El algoritmo que se utilizará al generar el código hash.</span><span class="sxs-lookup"><span data-stu-id="3dfa0-109">[in, out] The algorithm to use when generating the hash.</span></span> <span data-ttu-id="3dfa0-110">Los algoritmos válidos son los definidos por CryptoAPI de Win32.</span><span class="sxs-lookup"><span data-stu-id="3dfa0-110">Valid algorithms are those defined by the Win32 CryptoAPI.</span></span> <span data-ttu-id="3dfa0-111">Si `piHashAlg` se establece en 0, el algoritmo predeterminado CALG_SHA-1 se utiliza.</span><span class="sxs-lookup"><span data-stu-id="3dfa0-111">If `piHashAlg` is set to 0, the default algorithm CALG_SHA-1 is used.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="3dfa0-112">[out] Una matriz de bytes que contiene el código hash generado.</span><span class="sxs-lookup"><span data-stu-id="3dfa0-112">[out] A byte array containing the generated hash.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="3dfa0-113">[in] El tamaño máximo del búfer que `pbHash` apunta a.</span><span class="sxs-lookup"><span data-stu-id="3dfa0-113">[in] The maximum size of the buffer that `pbHash` points to.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="3dfa0-114">[out] El tamaño, en bytes, del devuelto `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="3dfa0-114">[out] The size, in bytes, of the returned `pbHash`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3dfa0-115">Comentarios</span><span class="sxs-lookup"><span data-stu-id="3dfa0-115">Remarks</span></span>  
 <span data-ttu-id="3dfa0-116">Esta función es el mismo que [GetHashFromFileW](../../../../docs/framework/unmanaged-api/strong-naming/gethashfromfilew-function.md), salvo que la especificación del nombre de archivo es ANSI en lugar de Unicode.</span><span class="sxs-lookup"><span data-stu-id="3dfa0-116">This function is the same as [GetHashFromFileW](../../../../docs/framework/unmanaged-api/strong-naming/gethashfromfilew-function.md), except that the file name specification is ANSI instead of Unicode.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3dfa0-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3dfa0-117">Requirements</span></span>  
 <span data-ttu-id="3dfa0-118">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3dfa0-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3dfa0-119">**Encabezado**: StrongName.h</span><span class="sxs-lookup"><span data-stu-id="3dfa0-119">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="3dfa0-120">**Biblioteca:** Incluye como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="3dfa0-120">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="3dfa0-121">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3dfa0-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3dfa0-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="3dfa0-122">See also</span></span>

- [<span data-ttu-id="3dfa0-123">GetHashFromFile (método)</span><span class="sxs-lookup"><span data-stu-id="3dfa0-123">GetHashFromFile Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfile-method.md)
- [<span data-ttu-id="3dfa0-124">GetHashFromFileW (método)</span><span class="sxs-lookup"><span data-stu-id="3dfa0-124">GetHashFromFileW Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfilew-method.md)
- [<span data-ttu-id="3dfa0-125">ICLRStrongName (interfaz)</span><span class="sxs-lookup"><span data-stu-id="3dfa0-125">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
