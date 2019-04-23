---
title: ICLRStrongName::GetHashFromFile (Método)
ms.date: 03/30/2017
api_name:
- ICLRStrongName.GetHashFromFile
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::GetHashFromFile
helpviewer_keywords:
- ICLRStrongName::GetHashFromFile method [.NET Framework hosting]
- GetHashFromFile method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: 9e50480a-8ada-4044-b2a5-97bb14ed3525
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f410e38d846969bbd23ff5b0a6751a5202088254
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59157500"
---
# <a name="iclrstrongnamegethashfromfile-method"></a><span data-ttu-id="49387-102">ICLRStrongName::GetHashFromFile (Método)</span><span class="sxs-lookup"><span data-stu-id="49387-102">ICLRStrongName::GetHashFromFile Method</span></span>
<span data-ttu-id="49387-103">Genera un hash a partir del contenido del archivo especificado.</span><span class="sxs-lookup"><span data-stu-id="49387-103">Generates a hash over the contents of the specified file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="49387-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="49387-104">Syntax</span></span>  
  
```  
HRESULT GetHashFromFile (  
    [in]  LPCSTR   szFilePath,  
    [in, out] unsigned int   *piHashAlg,   
    [out] BYTE     *pbHash,      
    [in]  DWORD    cchHash,      
    [out] DWORD    *pchHash  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="49387-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="49387-105">Parameters</span></span>  
 `szFilePath`  
 <span data-ttu-id="49387-106">[in] El nombre del archivo a hash.</span><span class="sxs-lookup"><span data-stu-id="49387-106">[in] The name of the file to hash.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="49387-107">[in, out] El algoritmo que se utilizará al generar el código hash.</span><span class="sxs-lookup"><span data-stu-id="49387-107">[in, out] The algorithm to use when generating the hash.</span></span> <span data-ttu-id="49387-108">Los algoritmos válidos son los definidos por CryptoAPI de Win32.</span><span class="sxs-lookup"><span data-stu-id="49387-108">Valid algorithms are those defined by the Win32 CryptoAPI.</span></span> <span data-ttu-id="49387-109">Si `piHashAlg` se establece en 0, el algoritmo predeterminado CALG_SHA-1 se utiliza.</span><span class="sxs-lookup"><span data-stu-id="49387-109">If `piHashAlg` is set to 0, the default algorithm CALG_SHA-1 is used.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="49387-110">[out] Una matriz de bytes que contiene el código hash generado.</span><span class="sxs-lookup"><span data-stu-id="49387-110">[out] A byte array containing the generated hash.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="49387-111">[in] El tamaño máximo del búfer que `pbHash` apunta a.</span><span class="sxs-lookup"><span data-stu-id="49387-111">[in] The maximum size of the buffer that `pbHash` points to.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="49387-112">[out] El tamaño, en bytes, del devuelto `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="49387-112">[out] The size, in bytes, of the returned `pbHash`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="49387-113">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="49387-113">Return Value</span></span>  
 <span data-ttu-id="49387-114">`S_OK` Si el método se completó correctamente; en caso contrario, un valor HRESULT que indica un error (consulte [valores HRESULT comunes](https://go.microsoft.com/fwlink/?LinkId=213878) para obtener una lista).</span><span class="sxs-lookup"><span data-stu-id="49387-114">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](https://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="49387-115">Comentarios</span><span class="sxs-lookup"><span data-stu-id="49387-115">Remarks</span></span>  
 <span data-ttu-id="49387-116">Este método es el mismo que el [ICLRStrongName](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfilew-method.md) método, salvo que el nombre del archivo especificación es ANSI en lugar de Unicode.</span><span class="sxs-lookup"><span data-stu-id="49387-116">This method is the same as the [ICLRStrongName::GetHashFromFileW](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfilew-method.md) method, except that the file name specification is ANSI instead of Unicode.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="49387-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="49387-117">Requirements</span></span>  
 <span data-ttu-id="49387-118">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="49387-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="49387-119">**Encabezado**: MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="49387-119">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="49387-120">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="49387-120">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="49387-121">**Versiones de .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="49387-121">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="49387-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="49387-122">See also</span></span>

- [<span data-ttu-id="49387-123">GetHashFromFileW (método)</span><span class="sxs-lookup"><span data-stu-id="49387-123">GetHashFromFileW Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfilew-method.md)
- [<span data-ttu-id="49387-124">ICLRStrongName (interfaz)</span><span class="sxs-lookup"><span data-stu-id="49387-124">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
