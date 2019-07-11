---
title: ICLRStrongName::GetHashFromHandle (Método)
ms.date: 03/30/2017
api_name:
- ICLRStrongName.GetHashFromHandle
- ICLRStrongName.StrongNameCompareAssemblies
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::GetHashFromHandle
helpviewer_keywords:
- GetHashFromHandle method, ICLRStrongName interface [.NET Framework hosting]
- ICLRStrongName::GetHashFromHandle method [.NET Framework hosting]
ms.assetid: 3bedbb7d-3cdd-4175-b370-10ae734062db
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a8f6878d714704370c3f43451c9995a7c5adb5d1
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67748141"
---
# <a name="iclrstrongnamegethashfromhandle-method"></a><span data-ttu-id="19929-102">ICLRStrongName::GetHashFromHandle (Método)</span><span class="sxs-lookup"><span data-stu-id="19929-102">ICLRStrongName::GetHashFromHandle Method</span></span>
<span data-ttu-id="19929-103">Genera un hash del contenido del archivo que tiene el identificador de archivo especificado, utilizando el algoritmo hash especificado.</span><span class="sxs-lookup"><span data-stu-id="19929-103">Generates a hash over the contents of the file that has the specified file handle, using the specified hash algorithm.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="19929-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="19929-104">Syntax</span></span>  
  
```cpp  
HRESULT GetHashFromHandle (  
    [in]  HANDLE   hFile,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE     *pbHash,  
    [in]  DWORD    cchHash,  
    [out] DWORD    *pchHash  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="19929-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="19929-105">Parameters</span></span>  
 `hFile`  
 <span data-ttu-id="19929-106">[in] El identificador del archivo que se aplica un algoritmo hash.</span><span class="sxs-lookup"><span data-stu-id="19929-106">[in] The handle of the file to be hashed.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="19929-107">[in, out] Una constante que especifica el algoritmo hash.</span><span class="sxs-lookup"><span data-stu-id="19929-107">[in, out] A constant that specifies the hash algorithm.</span></span> <span data-ttu-id="19929-108">Usar cero para el algoritmo predeterminado.</span><span class="sxs-lookup"><span data-stu-id="19929-108">Use zero for the default algorithm.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="19929-109">[out] El búfer hash devuelto.</span><span class="sxs-lookup"><span data-stu-id="19929-109">[out] The returned hash buffer.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="19929-110">[in] El tamaño máximo solicitado de `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="19929-110">[in] The requested maximum size of `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="19929-111">[out] El tamaño, en bytes, del devuelto `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="19929-111">[out] The size, in bytes, of the returned `pbHash`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="19929-112">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="19929-112">Return Value</span></span>  
 <span data-ttu-id="19929-113">`S_OK` Si el método se completó correctamente; en caso contrario, un valor HRESULT que indica un error (consulte [valores HRESULT comunes](https://go.microsoft.com/fwlink/?LinkId=213878) para obtener una lista).</span><span class="sxs-lookup"><span data-stu-id="19929-113">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](https://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="19929-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="19929-114">Requirements</span></span>  
 <span data-ttu-id="19929-115">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="19929-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="19929-116">**Encabezado**: MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="19929-116">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="19929-117">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="19929-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="19929-118">**Versiones de .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="19929-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="19929-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="19929-119">See also</span></span>

- [<span data-ttu-id="19929-120">ICLRStrongName (interfaz)</span><span class="sxs-lookup"><span data-stu-id="19929-120">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
