---
title: StrongNameGetBlob (Función)
ms.date: 03/30/2017
api_name:
- StrongNameGetBlob
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameGetBlob
helpviewer_keywords:
- StrongNameGetBlob function [.NET Framework strong naming]
ms.assetid: 15d09166-be00-4696-913f-2c1fbc7ac2e1
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: af2fa38bab8b22f86429dbcd95c842cec9ae73c3
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57484840"
---
# <a name="strongnamegetblob-function"></a><span data-ttu-id="ea5f3-102">StrongNameGetBlob (Función)</span><span class="sxs-lookup"><span data-stu-id="ea5f3-102">StrongNameGetBlob Function</span></span>
<span data-ttu-id="ea5f3-103">Llena el búfer especificado con la representación binaria del archivo ejecutable en la dirección especificada.</span><span class="sxs-lookup"><span data-stu-id="ea5f3-103">Fills the specified buffer with the binary representation of the executable file at the specified address.</span></span>  
  
 <span data-ttu-id="ea5f3-104">Esta función está desusada.</span><span class="sxs-lookup"><span data-stu-id="ea5f3-104">This function has been deprecated.</span></span> <span data-ttu-id="ea5f3-105">Use la [ICLRStrongName](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetblob-method.md) método en su lugar.</span><span class="sxs-lookup"><span data-stu-id="ea5f3-105">Use the [ICLRStrongName::StrongNameGetBLob](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetblob-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ea5f3-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ea5f3-106">Syntax</span></span>  
  
```  
BOOLEAN StrongNameGetBlob (  
    [in]  LPCWSTR    wszFilePath,  
    [in]  BYTE       *pbBlob,  
    [in, out] DWORD  *pcbBlob  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ea5f3-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ea5f3-107">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="ea5f3-108">[in] Una ruta de acceso válida para el archivo ejecutable que se va a cargar.</span><span class="sxs-lookup"><span data-stu-id="ea5f3-108">[in] A valid path to the executable file to be loaded.</span></span>  
  
 `pbBlob`  
 <span data-ttu-id="ea5f3-109">[in] Búfer en el que se va a cargar el archivo ejecutable.</span><span class="sxs-lookup"><span data-stu-id="ea5f3-109">[in] The buffer into which to load the executable file.</span></span>  
  
 `pcbBlob`  
 <span data-ttu-id="ea5f3-110">[in, out] El solicita el tamaño máximo, en bytes, de `pbBlob`.</span><span class="sxs-lookup"><span data-stu-id="ea5f3-110">[in, out] The requested maximum size, in bytes, of `pbBlob`.</span></span> <span data-ttu-id="ea5f3-111">Cuando se devuelve, el tamaño real, en bytes, de `pbBlob`.</span><span class="sxs-lookup"><span data-stu-id="ea5f3-111">Upon return, the actual size, in bytes, of `pbBlob`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ea5f3-112">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="ea5f3-112">Return Value</span></span>  
 <span data-ttu-id="ea5f3-113">`true` Cuando se finaliza correctamente; en caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="ea5f3-113">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ea5f3-114">Comentarios</span><span class="sxs-lookup"><span data-stu-id="ea5f3-114">Remarks</span></span>  
 <span data-ttu-id="ea5f3-115">Si el `StrongNameGetBlob` función no se completa correctamente, llame a la [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) función para recuperar el último error generado.</span><span class="sxs-lookup"><span data-stu-id="ea5f3-115">If the `StrongNameGetBlob` function does not complete successfully, call the [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ea5f3-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ea5f3-116">Requirements</span></span>  
 <span data-ttu-id="ea5f3-117">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ea5f3-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ea5f3-118">**Encabezado**: StrongName.h</span><span class="sxs-lookup"><span data-stu-id="ea5f3-118">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="ea5f3-119">**Biblioteca:** Incluye como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="ea5f3-119">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="ea5f3-120">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ea5f3-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ea5f3-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="ea5f3-121">See also</span></span>
- [<span data-ttu-id="ea5f3-122">StrongNameGetBlob (método)</span><span class="sxs-lookup"><span data-stu-id="ea5f3-122">StrongNameGetBlob Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetblob-method.md)
- [<span data-ttu-id="ea5f3-123">StrongNameGetBlobFromImage (método)</span><span class="sxs-lookup"><span data-stu-id="ea5f3-123">StrongNameGetBlobFromImage Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetblobfromimage-method.md)
- [<span data-ttu-id="ea5f3-124">ICLRStrongName (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ea5f3-124">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
