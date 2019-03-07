---
title: ICLRMetaHost::QueryLegacyV2RuntimeBinding (Método)
ms.date: 03/30/2017
api_name:
- ICLRMetaHost.RequestRuntimeLoadedNotification
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRMetaHost::QueryLegacyV2RuntimeBinding
helpviewer_keywords:
- QueryLegacyV2RuntimeBinding method [.NET Framework hosting]
- ICLRMetaHost::QueryLegacyV2RuntimeBinding method [.NET Framework hosting]
ms.assetid: 9929817e-acc9-40b7-960c-598664e04b60
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b21b86e9f5866626f72562f5105b214777e3d5bd
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57486908"
---
# <a name="iclrmetahostquerylegacyv2runtimebinding-method"></a><span data-ttu-id="9acc4-102">ICLRMetaHost::QueryLegacyV2RuntimeBinding (Método)</span><span class="sxs-lookup"><span data-stu-id="9acc4-102">ICLRMetaHost::QueryLegacyV2RuntimeBinding Method</span></span>
<span data-ttu-id="9acc4-103">Devuelve una interfaz que representa un tiempo de ejecución a la que la directiva de activación heredada se ha enlazado, por ejemplo, mediante el uso de la `useLegacyV2RuntimeActivationPolicy` atributo el [ \<Inicio > elemento](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md) entrada del archivo de configuración mediante el uso directo de la API de activación heredadas o llamando a la [ICLRRuntimeInfo:: Bindaslegacyv2runtime](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-bindaslegacyv2runtime-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="9acc4-103">Returns an interface that represents a runtime to which legacy activation policy has been bound, for example, by using the `useLegacyV2RuntimeActivationPolicy` attribute on the [\<startup> element](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md) configuration file entry, by direct use of the legacy activation APIs, or by calling the [ICLRRuntimeInfo::BindAsLegacyV2Runtime](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-bindaslegacyv2runtime-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9acc4-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9acc4-104">Syntax</span></span>  
  
```  
HRESULT QueryLegacyV2RuntimeBinding (  
    [in] REFIID riid,  
    [out, iid_is(riid), retval] LPVOID *ppUnk);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9acc4-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="9acc4-105">Parameters</span></span>  
 `riid`  
 <span data-ttu-id="9acc4-106">[in] El único valor válido para este parámetro es de Required.Currently `IID_ICLRRuntimeInfo`.</span><span class="sxs-lookup"><span data-stu-id="9acc4-106">[in] Required.Currently the only valid value for this parameter is `IID_ICLRRuntimeInfo`.</span></span>  
  
 `ppUnk`  
 <span data-ttu-id="9acc4-107">[out] Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="9acc4-107">[out] Required.</span></span> <span data-ttu-id="9acc4-108">Cuando este método finaliza, contiene un puntero a la [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interfaz que representa un tiempo de ejecución que se ha enlazado a la directiva de activación heredada.</span><span class="sxs-lookup"><span data-stu-id="9acc4-108">When this method returns, contains a pointer to the [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interface that represents a runtime that has been bound to legacy activation policy.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9acc4-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="9acc4-109">Return Value</span></span>  
 <span data-ttu-id="9acc4-110">Este método devuelve los siguientes HRESULT específicos y los errores HRESULT que indican un error del método.</span><span class="sxs-lookup"><span data-stu-id="9acc4-110">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="9acc4-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="9acc4-111">HRESULT</span></span>|<span data-ttu-id="9acc4-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="9acc4-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="9acc4-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="9acc4-113">S_OK</span></span>|<span data-ttu-id="9acc4-114">El método se completó correctamente y devolvió un tiempo de ejecución que se enlazó a la directiva de activación heredada.</span><span class="sxs-lookup"><span data-stu-id="9acc4-114">The method completed successfully and returned a runtime that was bound to legacy activation policy.</span></span>|  
|<span data-ttu-id="9acc4-115">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="9acc4-115">S_FALSE</span></span>|<span data-ttu-id="9acc4-116">El método se completó correctamente, pero un tiempo de ejecución heredado no se enlazó.</span><span class="sxs-lookup"><span data-stu-id="9acc4-116">The method completed successfully, but a legacy runtime has not yet been bound.</span></span>|  
|<span data-ttu-id="9acc4-117">E_NOINTERFACE</span><span class="sxs-lookup"><span data-stu-id="9acc4-117">E_NOINTERFACE</span></span>|<span data-ttu-id="9acc4-118">El método encontró un tiempo de ejecución que se enlazó a la directiva de activación heredada, pero ese tiempo de ejecución no admite `riid`.</span><span class="sxs-lookup"><span data-stu-id="9acc4-118">The method found a runtime that was bound to legacy activation policy, but `riid` is not supported by that runtime.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9acc4-119">Comentarios</span><span class="sxs-lookup"><span data-stu-id="9acc4-119">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9acc4-120">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9acc4-120">Requirements</span></span>  
 <span data-ttu-id="9acc4-121">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9acc4-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9acc4-122">**Encabezado**: MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="9acc4-122">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="9acc4-123">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="9acc4-123">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9acc4-124">**Versiones de .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9acc4-124">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9acc4-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="9acc4-125">See also</span></span>
- [<span data-ttu-id="9acc4-126">ICLRMetaHost (interfaz)</span><span class="sxs-lookup"><span data-stu-id="9acc4-126">ICLRMetaHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md)
- [<span data-ttu-id="9acc4-127">Hospedar aplicaciones de WPF</span><span class="sxs-lookup"><span data-stu-id="9acc4-127">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
