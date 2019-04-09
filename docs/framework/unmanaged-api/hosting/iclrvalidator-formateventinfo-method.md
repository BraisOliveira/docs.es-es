---
title: ICLRValidator::FormatEventInfo (Método)
ms.date: 03/30/2017
api_name:
- ICLRValidator.FormatEventInfo
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRValidator::FormatEventInfo
helpviewer_keywords:
- FormatEventInfo method, ICLRValidator interface [.NET Framework hosting]
- ICLRValidator::FormatEventInfo method [.NET Framework hosting]
ms.assetid: 808e1f1d-52f4-47c4-83cc-dcf47d075219
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9117a82dff48dcda8d96f0feb7b8c4a001fa17f1
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59205880"
---
# <a name="iclrvalidatorformateventinfo-method"></a><span data-ttu-id="52d9e-102">ICLRValidator::FormatEventInfo (Método)</span><span class="sxs-lookup"><span data-stu-id="52d9e-102">ICLRValidator::FormatEventInfo Method</span></span>
<span data-ttu-id="52d9e-103">Obtiene un mensaje detallado sobre el error de validación especificado.</span><span class="sxs-lookup"><span data-stu-id="52d9e-103">Gets a detailed message about the specified validation error.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="52d9e-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="52d9e-104">Syntax</span></span>  
  
```  
HRESULT FormatEventInfo (  
    [in] HRESULT            hVECode,  
    [in] VEContext          Context,  
    [in, out] LPWSTR        msg,  
    [in] unsigned long      ulMaxLength,  
    [in] SAFEARRAY(VARIANT) psa  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="52d9e-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="52d9e-105">Parameters</span></span>  
 `hVECode`  
 <span data-ttu-id="52d9e-106">[in] El valor HRESULT que se pasó al controlador de errores de validación.</span><span class="sxs-lookup"><span data-stu-id="52d9e-106">[in] The HRESULT value that was passed to the validation error handler.</span></span>  
  
 `Context`  
 <span data-ttu-id="52d9e-107">[in] Un `VEContext` instancia que contiene información de contexto sobre los errores de validación.</span><span class="sxs-lookup"><span data-stu-id="52d9e-107">[in] A `VEContext` instance that contains context information about the validation errors.</span></span>  
  
 `msg`  
 <span data-ttu-id="52d9e-108">[in, out] El mensaje de error descriptivo.</span><span class="sxs-lookup"><span data-stu-id="52d9e-108">[in, out] The friendly error message.</span></span>  
  
 `ulMaxLength`  
 <span data-ttu-id="52d9e-109">[in] La longitud máxima del mensaje de error.</span><span class="sxs-lookup"><span data-stu-id="52d9e-109">[in] The maximum length of the error message.</span></span>  
  
 `psa`  
 <span data-ttu-id="52d9e-110">[in] Una matriz segura de parámetros adicionales que se usarán en el mensaje.</span><span class="sxs-lookup"><span data-stu-id="52d9e-110">[in] A safe array of additional parameters to be used in the message.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="52d9e-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="52d9e-111">Return Value</span></span>  
  
|<span data-ttu-id="52d9e-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="52d9e-112">HRESULT</span></span>|<span data-ttu-id="52d9e-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="52d9e-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="52d9e-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="52d9e-114">S_OK</span></span>|`FormatEventInfo` <span data-ttu-id="52d9e-115">se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="52d9e-115">returned successfully.</span></span>|  
|<span data-ttu-id="52d9e-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="52d9e-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="52d9e-117">Common language runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="52d9e-117">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="52d9e-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="52d9e-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="52d9e-119">La llamada ha agotado el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="52d9e-119">The call timed out.</span></span>|  
|<span data-ttu-id="52d9e-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="52d9e-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="52d9e-121">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="52d9e-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="52d9e-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="52d9e-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="52d9e-123">Se canceló un evento mientras un subproceso bloqueado o fibra estaba esperando en ella.</span><span class="sxs-lookup"><span data-stu-id="52d9e-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="52d9e-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="52d9e-124">E_FAIL</span></span>|<span data-ttu-id="52d9e-125">Se ha producido un error irrecuperable desconocido.</span><span class="sxs-lookup"><span data-stu-id="52d9e-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="52d9e-126">Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="52d9e-126">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="52d9e-127">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="52d9e-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="52d9e-128">Requisitos</span><span class="sxs-lookup"><span data-stu-id="52d9e-128">Requirements</span></span>  
 <span data-ttu-id="52d9e-129">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="52d9e-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="52d9e-130">**Encabezado**: IValidator.idl, IValidator.h</span><span class="sxs-lookup"><span data-stu-id="52d9e-130">**Header:** IValidator.idl, IValidator.h</span></span>  
  
 <span data-ttu-id="52d9e-131">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="52d9e-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="52d9e-132">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="52d9e-132">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="52d9e-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="52d9e-133">See also</span></span>

- [<span data-ttu-id="52d9e-134">ICLRErrorReportingManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="52d9e-134">ICLRErrorReportingManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-interface.md)
- [<span data-ttu-id="52d9e-135">ICLRValidator (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="52d9e-135">ICLRValidator Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrvalidator-interface.md)
