---
title: GetFileVersion (Función)
ms.date: 03/30/2017
api_name:
- GetFileVersion
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- GetFileVersion
helpviewer_keywords:
- GetFileVersion function [.NET Framework hosting]
ms.assetid: b3222c85-da88-4485-97d7-3a6ee3e8d358
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 214f16f970cfb2c319f3a26afc882e6102c1be71
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57498268"
---
# <a name="getfileversion-function"></a><span data-ttu-id="0ceb7-102">GetFileVersion (Función)</span><span class="sxs-lookup"><span data-stu-id="0ceb7-102">GetFileVersion Function</span></span>
<span data-ttu-id="0ceb7-103">Obtiene la información de versión de common language runtime (CLR) del archivo especificado, utilizando el búfer especificado.</span><span class="sxs-lookup"><span data-stu-id="0ceb7-103">Gets the common language runtime (CLR) version information of the specified file, using the specified buffer.</span></span>  
  
 <span data-ttu-id="0ceb7-104">Esta función está en desuso en [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0ceb7-104">This function has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0ceb7-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0ceb7-105">Syntax</span></span>  
  
```  
HRESULT GetFileVersion (  
    [in]  LPCWSTR      szFilename,   
    [in, out] LPWSTR   szBuffer,   
    [in]  DWORD        cchBuffer,   
    [out] DWORD        *dwLength  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0ceb7-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="0ceb7-106">Parameters</span></span>  
 `szFilename`  
 <span data-ttu-id="0ceb7-107">[in] La ruta de acceso del archivo se va a examinar.</span><span class="sxs-lookup"><span data-stu-id="0ceb7-107">[in] The path of the file to be examined.</span></span>  
  
 `szBuffer`  
 <span data-ttu-id="0ceb7-108">[in, out] El búfer asignado para la información de versión que se devuelve.</span><span class="sxs-lookup"><span data-stu-id="0ceb7-108">[in, out] The buffer allocated for the version information that is returned.</span></span>  
  
 `cchBuffer`  
 <span data-ttu-id="0ceb7-109">[in] El tamaño, en caracteres anchos, de `szBuffer`.</span><span class="sxs-lookup"><span data-stu-id="0ceb7-109">[in] The size, in wide characters, of `szBuffer`.</span></span>  
  
 `dwLength`  
 <span data-ttu-id="0ceb7-110">[out] El tamaño, en bytes, del devuelto `szBuffer`.</span><span class="sxs-lookup"><span data-stu-id="0ceb7-110">[out] The size, in bytes, of the returned `szBuffer`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0ceb7-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0ceb7-111">Requirements</span></span>  
 <span data-ttu-id="0ceb7-112">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0ceb7-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0ceb7-113">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="0ceb7-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="0ceb7-114">**Versiones de .NET Framework:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0ceb7-114">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0ceb7-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="0ceb7-115">See also</span></span>
- [<span data-ttu-id="0ceb7-116">Funciones de hospedaje de CLR en desuso</span><span class="sxs-lookup"><span data-stu-id="0ceb7-116">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
