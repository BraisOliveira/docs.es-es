---
title: ICorRuntimeHost::MapFile (Método)
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost.MapFile
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::MapFile
helpviewer_keywords:
- ICorRuntimeHost::MapFile method [.NET Framework hosting]
- MapFile method [.NET Framework hosting]
ms.assetid: 45ae0502-0a31-4342-b7e3-f36e1cf738f3
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 956de98fca1caec0ac1b94afc7251f9741246f94
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57494784"
---
# <a name="icorruntimehostmapfile-method"></a><span data-ttu-id="f672e-102">ICorRuntimeHost::MapFile (Método)</span><span class="sxs-lookup"><span data-stu-id="f672e-102">ICorRuntimeHost::MapFile Method</span></span>
<span data-ttu-id="f672e-103">Asigna el archivo especificado en la memoria.</span><span class="sxs-lookup"><span data-stu-id="f672e-103">Maps the specified file into memory.</span></span> <span data-ttu-id="f672e-104">Este método está obsoleto.</span><span class="sxs-lookup"><span data-stu-id="f672e-104">This method is obsolete.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f672e-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f672e-105">Syntax</span></span>  
  
```  
HRESULT MapFile(  
    [in]  HANDLE    hFile,  
    [out] HMODULE*  hMapAddress  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f672e-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f672e-106">Parameters</span></span>  
 `hFile`  
 <span data-ttu-id="f672e-107">[in] El identificador del archivo que se puede asignar.</span><span class="sxs-lookup"><span data-stu-id="f672e-107">[in] The handle of the file to be mapped.</span></span>  
  
 `hMapAddress`  
 <span data-ttu-id="f672e-108">[out] La dirección de memoria de inicio donde comienza el archivo de asignación.</span><span class="sxs-lookup"><span data-stu-id="f672e-108">[out] The starting memory address at which to begin mapping the file.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f672e-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f672e-109">Requirements</span></span>  
 <span data-ttu-id="f672e-110">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f672e-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f672e-111">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="f672e-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f672e-112">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="f672e-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f672e-113">**Versión de .NET framework:** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="f672e-113">**.NET Framework Version:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f672e-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="f672e-114">See also</span></span>
- [<span data-ttu-id="f672e-115">ICorRuntimeHost (interfaz)</span><span class="sxs-lookup"><span data-stu-id="f672e-115">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
