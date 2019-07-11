---
title: ICLRAssemblyIdentityManager::GetReferencedAssembliesFromStream (Método)
ms.date: 03/30/2017
api_name:
- ICLRAssemblyIdentityManager.GetReferencedAssembliesFromStream
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRAssemblyIdentityManager::GetReferencedAssembliesFromStream
helpviewer_keywords:
- ICLRAssemblyIdentityManager::GetReferencedAssembliesFromStream method [.NET Framework hosting]
- GetReferencedAssembliesFromStream method [.NET Framework hosting]
ms.assetid: fe9849c1-c3fc-477b-a31f-e8619f5516f5
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9655981bf7ca21a6f59b305f6ea3fa5ff47f608a
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67773400"
---
# <a name="iclrassemblyidentitymanagergetreferencedassembliesfromstream-method"></a><span data-ttu-id="84ce6-102">ICLRAssemblyIdentityManager::GetReferencedAssembliesFromStream (Método)</span><span class="sxs-lookup"><span data-stu-id="84ce6-102">ICLRAssemblyIdentityManager::GetReferencedAssembliesFromStream Method</span></span>
<span data-ttu-id="84ce6-103">Obtiene un puntero a un [ICLRReferenceAssemblyEnum](../../../../docs/framework/unmanaged-api/hosting/iclrreferenceassemblyenum-interface.md) objeto que contiene datos de identidad de ensamblado para los ensamblados que se hace referencia el ensamblado en la secuencia especificada.</span><span class="sxs-lookup"><span data-stu-id="84ce6-103">Gets a pointer to an [ICLRReferenceAssemblyEnum](../../../../docs/framework/unmanaged-api/hosting/iclrreferenceassemblyenum-interface.md) object that contains assembly identity data for the assemblies referenced by the assembly in the specified stream.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="84ce6-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="84ce6-104">Syntax</span></span>  
  
```cpp  
HRESULT GetReferencedAssembliesFromStream (  
    [in]  IStream *pStream,  
    [in]  DWORD    dwFlags,  
    [in]  ICLRAssemblyReferenceList  *pExcludeAssembliesList,  
    [out] ICLRReferenceAssemblyEnum **ppReferenceEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="84ce6-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="84ce6-105">Parameters</span></span>  
 `pStream`  
 <span data-ttu-id="84ce6-106">[in] Un puntero de interfaz a un `IStream` que contiene el ensamblado que se va a evaluar.</span><span class="sxs-lookup"><span data-stu-id="84ce6-106">[in] An interface pointer to an `IStream` containing the assembly to be evaluated.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="84ce6-107">[in] Se proporciona para extensibilidad futura.</span><span class="sxs-lookup"><span data-stu-id="84ce6-107">[in] Provided for future extensibility.</span></span> <span data-ttu-id="84ce6-108">CLR_ASSEMBLY_IDENTITY_FLAGS_DEFAULT es el único valor compatible con la versión actual de common language runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="84ce6-108">CLR_ASSEMBLY_IDENTITY_FLAGS_DEFAULT is the only value that the current version of the common language runtime (CLR) supports.</span></span>  
  
 `pExcludeAssembliesList`  
 <span data-ttu-id="84ce6-109">[in] Un puntero a un [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) objeto que contiene datos de identidad de ensamblado para los ensamblados que deben excluirse `ppReferenceEnum`.</span><span class="sxs-lookup"><span data-stu-id="84ce6-109">[in] A pointer to an [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) object that contains assembly identity data for the assemblies to be excluded from `ppReferenceEnum`.</span></span>  
  
 `ppReferenceEnum`  
 <span data-ttu-id="84ce6-110">[out] Un puntero a la dirección de un `ICLRReferenceAssemblyEnum` objeto que contiene datos de identidad de ensamblado para los ensamblados que se hace referencia el ensamblado en `pStream`, excluyendo los ensamblados de `pExcludeAssembliesList`.</span><span class="sxs-lookup"><span data-stu-id="84ce6-110">[out] A pointer to the address of an `ICLRReferenceAssemblyEnum` object that contains assembly identity data for the assemblies referenced by the assembly in `pStream`, excluding the assemblies in `pExcludeAssembliesList`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="84ce6-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="84ce6-111">Return Value</span></span>  
  
|<span data-ttu-id="84ce6-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="84ce6-112">HRESULT</span></span>|<span data-ttu-id="84ce6-113">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="84ce6-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="84ce6-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="84ce6-114">S_OK</span></span>|<span data-ttu-id="84ce6-115">El método se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="84ce6-115">The method returned successfully.</span></span>|  
|<span data-ttu-id="84ce6-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="84ce6-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="84ce6-117">El CLR no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="84ce6-117">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="84ce6-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="84ce6-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="84ce6-119">La llamada ha agotado el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="84ce6-119">The call timed out.</span></span>|  
|<span data-ttu-id="84ce6-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="84ce6-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="84ce6-121">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="84ce6-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="84ce6-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="84ce6-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="84ce6-123">Se canceló un evento mientras un subproceso bloqueado o fibra estaba esperando en ella.</span><span class="sxs-lookup"><span data-stu-id="84ce6-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="84ce6-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="84ce6-124">E_FAIL</span></span>|<span data-ttu-id="84ce6-125">Se ha producido un error irrecuperable desconocido.</span><span class="sxs-lookup"><span data-stu-id="84ce6-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="84ce6-126">Si el método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="84ce6-126">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="84ce6-127">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="84ce6-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="84ce6-128">Comentarios</span><span class="sxs-lookup"><span data-stu-id="84ce6-128">Remarks</span></span>  
 <span data-ttu-id="84ce6-129">El llamador puede excluir un conjunto de referencias de ensamblados conocidos de la lista devuelta.</span><span class="sxs-lookup"><span data-stu-id="84ce6-129">The caller can choose to exclude a set of known assembly references from the returned list.</span></span> <span data-ttu-id="84ce6-130">Este conjunto se define mediante `pExcludeAssembliesList`.</span><span class="sxs-lookup"><span data-stu-id="84ce6-130">This set is defined by `pExcludeAssembliesList`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="84ce6-131">Requisitos</span><span class="sxs-lookup"><span data-stu-id="84ce6-131">Requirements</span></span>  
 <span data-ttu-id="84ce6-132">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="84ce6-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="84ce6-133">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="84ce6-133">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="84ce6-134">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="84ce6-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="84ce6-135">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="84ce6-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="84ce6-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="84ce6-136">See also</span></span>

- [<span data-ttu-id="84ce6-137">ICLRAssemblyIdentityManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="84ce6-137">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="84ce6-138">ICLRAssemblyReferenceList (interfaz)</span><span class="sxs-lookup"><span data-stu-id="84ce6-138">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="84ce6-139">ICLRReferenceAssemblyEnum (interfaz)</span><span class="sxs-lookup"><span data-stu-id="84ce6-139">ICLRReferenceAssemblyEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrreferenceassemblyenum-interface.md)
