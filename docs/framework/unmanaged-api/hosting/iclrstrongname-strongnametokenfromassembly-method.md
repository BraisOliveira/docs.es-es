---
title: ICLRStrongName::StrongNameTokenFromAssembly (Método)
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameTokenFromAssembly
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameTokenFromAssembly
helpviewer_keywords:
- ICLRStrongName::StrongNameTokenFromAssembly method [.NET Framework hosting]
- StrongNameTokenFromAssembly method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: fc725afb-b66b-4015-aa44-1c0d1304197f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8a2931c16e13d08c1e3e7d5b62e6583102a1b8cd
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59229256"
---
# <a name="iclrstrongnamestrongnametokenfromassembly-method"></a><span data-ttu-id="d5930-102">ICLRStrongName::StrongNameTokenFromAssembly (Método)</span><span class="sxs-lookup"><span data-stu-id="d5930-102">ICLRStrongName::StrongNameTokenFromAssembly Method</span></span>
<span data-ttu-id="d5930-103">Crea un token de nombre seguro desde el archivo de ensamblado especificado.</span><span class="sxs-lookup"><span data-stu-id="d5930-103">Creates a strong name token from the specified assembly file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d5930-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d5930-104">Syntax</span></span>  
  
```  
HRESULT StrongNameTokenFromAssembly (  
    [in]  LPCWSTR   wszFilePath,  
    [out] BYTE      **ppbStrongNameToken,  
    [out] ULONG     *pcbStrongNameToken  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d5930-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d5930-105">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="d5930-106">[in] La ruta de acceso al archivo ejecutable portable (PE) para el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="d5930-106">[in] The path to the portable executable (PE) file for the assembly.</span></span>  
  
 `ppbStrongNameToken`  
 <span data-ttu-id="d5930-107">[out] El token de nombre seguro devuelto.</span><span class="sxs-lookup"><span data-stu-id="d5930-107">[out] The returned strong name token.</span></span>  
  
 `pcbStrongNameToken`  
 <span data-ttu-id="d5930-108">[out] El tamaño, en bytes, del token de nombre seguro.</span><span class="sxs-lookup"><span data-stu-id="d5930-108">[out] The size, in bytes, of the strong name token.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d5930-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="d5930-109">Return Value</span></span>  
 `S_OK` <span data-ttu-id="d5930-110">Si el método se completó correctamente; en caso contrario, un valor HRESULT que indica un error (consulte [valores HRESULT comunes](https://go.microsoft.com/fwlink/?LinkId=213878) para obtener una lista).</span><span class="sxs-lookup"><span data-stu-id="d5930-110">if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](https://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d5930-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d5930-111">Remarks</span></span>  
 <span data-ttu-id="d5930-112">Un token de nombre seguro es la forma abreviada de una clave pública.</span><span class="sxs-lookup"><span data-stu-id="d5930-112">A strong name token is the shortened form of a public key.</span></span> <span data-ttu-id="d5930-113">El token es un hash de 64 bits que se crea a partir de la clave pública utilizada para firmar el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="d5930-113">The token is a 64-bit hash that is created from the public key used to sign the assembly.</span></span> <span data-ttu-id="d5930-114">El token es una parte del nombre seguro del ensamblado y se puede leer desde los metadatos del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="d5930-114">The token is a part of the strong name for the assembly, and can be read from the assembly metadata.</span></span>  
  
 <span data-ttu-id="d5930-115">Una vez creado el token, debe llamar a la [ICLRStrongName](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) método para liberar la memoria asignada.</span><span class="sxs-lookup"><span data-stu-id="d5930-115">After the token is created, you should call the [ICLRStrongName::StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) method to release the allocated memory.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d5930-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d5930-116">Requirements</span></span>  
 <span data-ttu-id="d5930-117">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d5930-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d5930-118">**Encabezado**: MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="d5930-118">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="d5930-119">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="d5930-119">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="d5930-120">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="d5930-120">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="d5930-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="d5930-121">See also</span></span>

- [<span data-ttu-id="d5930-122">Método StrongNameTokenFromAssemblyEx</span><span class="sxs-lookup"><span data-stu-id="d5930-122">StrongNameTokenFromAssemblyEx Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfromassemblyex-method.md)
- [<span data-ttu-id="d5930-123">ICLRStrongName (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="d5930-123">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
