---
title: ICLRRuntimeHost::ExecuteInDefaultAppDomain (Método)
ms.date: 03/30/2017
api_name:
- ICLRRuntimeHost.ExecuteInDefaultAppDomain
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeHost::ExecuteInDefaultAppDomain
helpviewer_keywords:
- ICLRRuntimeHost::ExecuteInDefaultAppDomain method [.NET Framework hosting]
- ExecuteInDefaultAppDomain method [.NET Framework hosting]
ms.assetid: 30b5cf9a-a762-4bd4-be12-d6c1442b78b1
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5b7540f166311bbc9e5efa21d136132cc72b7c12
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67768739"
---
# <a name="iclrruntimehostexecuteindefaultappdomain-method"></a><span data-ttu-id="f6882-102">ICLRRuntimeHost::ExecuteInDefaultAppDomain (Método)</span><span class="sxs-lookup"><span data-stu-id="f6882-102">ICLRRuntimeHost::ExecuteInDefaultAppDomain Method</span></span>
<span data-ttu-id="f6882-103">Llama al método especificado del tipo especificado en el ensamblado administrado especificado.</span><span class="sxs-lookup"><span data-stu-id="f6882-103">Calls the specified method of the specified type in the specified managed assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f6882-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f6882-104">Syntax</span></span>  
  
```cpp  
HRESULT ExecuteInDefaultAppDomain (  
    [in] LPCWSTR pwzAssemblyPath,  
    [in] LPCWSTR pwzTypeName,   
    [in] LPCWSTR pwzMethodName,  
    [in] LPCWSTR pwzArgument,  
    [out] DWORD *pReturnValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f6882-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f6882-105">Parameters</span></span>  
 `pwzAssemblyPath`  
 <span data-ttu-id="f6882-106">[in] La ruta de acceso a la <xref:System.Reflection.Assembly> que define el <xref:System.Type> cuyo método es que se debe invocar.</span><span class="sxs-lookup"><span data-stu-id="f6882-106">[in] The path to the <xref:System.Reflection.Assembly> that defines the <xref:System.Type> whose method is to be invoked.</span></span>  
  
 `pwzTypeName`  
 <span data-ttu-id="f6882-107">[in] El nombre de la <xref:System.Type> que define el método que se invoca.</span><span class="sxs-lookup"><span data-stu-id="f6882-107">[in] The name of the <xref:System.Type> that defines the method to invoke.</span></span>  
  
 `pwzMethodName`  
 <span data-ttu-id="f6882-108">[in] El nombre del método que se va a invocar.</span><span class="sxs-lookup"><span data-stu-id="f6882-108">[in] The name of the method to invoke.</span></span>  
  
 `pwzArgument`  
 <span data-ttu-id="f6882-109">[in] El parámetro de cadena para pasar al método.</span><span class="sxs-lookup"><span data-stu-id="f6882-109">[in] The string parameter to pass to the method.</span></span>  
  
 `pReturnValue`  
 <span data-ttu-id="f6882-110">[out] El valor entero devuelto por el método invocado.</span><span class="sxs-lookup"><span data-stu-id="f6882-110">[out] The integer value returned by the invoked method.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f6882-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="f6882-111">Return Value</span></span>  
  
|<span data-ttu-id="f6882-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="f6882-112">HRESULT</span></span>|<span data-ttu-id="f6882-113">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="f6882-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="f6882-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="f6882-114">S_OK</span></span>|<span data-ttu-id="f6882-115">`ExecuteInDefaultAppDomain` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="f6882-115">`ExecuteInDefaultAppDomain` returned successfully.</span></span>|  
|<span data-ttu-id="f6882-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="f6882-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="f6882-117">Common language runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="f6882-117">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="f6882-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="f6882-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="f6882-119">La llamada ha agotado el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="f6882-119">The call timed out.</span></span>|  
|<span data-ttu-id="f6882-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="f6882-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="f6882-121">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="f6882-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="f6882-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="f6882-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="f6882-123">Se canceló un evento mientras un subproceso bloqueado o fibra estaba esperando en ella.</span><span class="sxs-lookup"><span data-stu-id="f6882-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="f6882-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="f6882-124">E_FAIL</span></span>|<span data-ttu-id="f6882-125">Se ha producido un error irrecuperable desconocido.</span><span class="sxs-lookup"><span data-stu-id="f6882-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="f6882-126">Si el método devuelve E_FAIL, ya no es utilizable dentro del proceso de la CRL.</span><span class="sxs-lookup"><span data-stu-id="f6882-126">If a method returns E_FAIL, the CRL is no longer usable within the process.</span></span> <span data-ttu-id="f6882-127">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="f6882-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f6882-128">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f6882-128">Remarks</span></span>  
 <span data-ttu-id="f6882-129">El método invocado debe tener la siguiente firma:</span><span class="sxs-lookup"><span data-stu-id="f6882-129">The invoked method must have the following signature:</span></span>  
  
```cpp  
static int pwzMethodName (String pwzArgument)  
```  
  
 <span data-ttu-id="f6882-130">donde `pwzMethodName` representa el nombre del método invocado, y `pwzArgument` representa el valor de cadena se pasa como parámetro a ese método.</span><span class="sxs-lookup"><span data-stu-id="f6882-130">where `pwzMethodName` represents the name of the invoked method, and `pwzArgument` represents the string value passed as a parameter to that method.</span></span> <span data-ttu-id="f6882-131">Si se establece el valor HRESULT a S_OK, `pReturnValue` se establece en el valor entero devuelto por el método invocado.</span><span class="sxs-lookup"><span data-stu-id="f6882-131">If the HRESULT value is set to S_OK, `pReturnValue` is set to the integer value returned by the invoked method.</span></span> <span data-ttu-id="f6882-132">En caso contrario, `pReturnValue` no está establecida.</span><span class="sxs-lookup"><span data-stu-id="f6882-132">Otherwise, `pReturnValue` is not set.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f6882-133">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f6882-133">Requirements</span></span>  
 <span data-ttu-id="f6882-134">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f6882-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f6882-135">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="f6882-135">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f6882-136">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="f6882-136">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f6882-137">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f6882-137">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f6882-138">Vea también</span><span class="sxs-lookup"><span data-stu-id="f6882-138">See also</span></span>

- [<span data-ttu-id="f6882-139">ICLRRuntimeHost (interfaz)</span><span class="sxs-lookup"><span data-stu-id="f6882-139">ICLRRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)
