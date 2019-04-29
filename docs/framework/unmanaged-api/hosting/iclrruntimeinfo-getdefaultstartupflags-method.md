---
title: ICLRRuntimeInfo::GetDefaultStartupFlags (Método)
ms.date: 03/30/2017
api_name:
- ICLRRuntimeInfo.GetDefaultStartupFlags
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeInfo::GetDefaultStartupFlags
helpviewer_keywords:
- ICLRRuntimeInfo::GetDefaultStartupFlags method [.NET Framework hosting]
- GetDefaultStartupFlags method [.NET Framework hosting]
ms.assetid: 35c2173e-3b0b-4b2a-950d-e0a01c6df052
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9c39ad4638c7db45c481bd3dfccb0a82759397aa
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61771753"
---
# <a name="iclrruntimeinfogetdefaultstartupflags-method"></a><span data-ttu-id="ae9f4-102">ICLRRuntimeInfo::GetDefaultStartupFlags (Método)</span><span class="sxs-lookup"><span data-stu-id="ae9f4-102">ICLRRuntimeInfo::GetDefaultStartupFlags Method</span></span>
<span data-ttu-id="ae9f4-103">Obtiene las marcas de inicio y el archivo de configuración de host que se usará para iniciar el tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="ae9f4-103">Gets the startup flags and host configuration file that will be used to start the runtime.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ae9f4-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ae9f4-104">Syntax</span></span>  
  
```  
HRESULT GetDefaultStartupFlags(  
     [out]  DWORD *pdwStartupFlags,  
     [out, size_is(*pcchHostConfigFile)] LPWSTR pwzHostConfigFile,  
     [in, out]  DWORD *pcchHostConfigFile);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ae9f4-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ae9f4-105">Parameters</span></span>  
 `pdwStartupFlags`  
 <span data-ttu-id="ae9f4-106">[out] Un puntero a las marcas de inicio del host que están establecidas actualmente.</span><span class="sxs-lookup"><span data-stu-id="ae9f4-106">[out] A pointer to the host startup flags that are currently set.</span></span>  
  
 `pwzHostConfigFile`  
 <span data-ttu-id="ae9f4-107">[out] Un puntero a la ruta del directorio del archivo de configuración de host actual.</span><span class="sxs-lookup"><span data-stu-id="ae9f4-107">[out] A pointer to the directory path of the current host configuration file.</span></span>  
  
 `pcchHostConfigFile`  
 <span data-ttu-id="ae9f4-108">[in, out] En la entrada, el tamaño de `pwzHostConfigFile`, para evitar saturaciones de búfer.</span><span class="sxs-lookup"><span data-stu-id="ae9f4-108">[in, out] On input, the size of `pwzHostConfigFile`, to avoid buffer overruns.</span></span> <span data-ttu-id="ae9f4-109">Si `pwzHostConfigFile` es null, el método devuelve el tamaño necesario de `pwzHostConfigFile` para la asignación previa.</span><span class="sxs-lookup"><span data-stu-id="ae9f4-109">If `pwzHostConfigFile` is null, the method returns the required size of `pwzHostConfigFile` for pre-allocation.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ae9f4-110">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="ae9f4-110">Return Value</span></span>  
 <span data-ttu-id="ae9f4-111">Este método devuelve los siguientes HRESULT específicos, así como los errores HRESULT que indican un error del método.</span><span class="sxs-lookup"><span data-stu-id="ae9f4-111">This method returns the following specific HRESULT as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="ae9f4-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ae9f4-112">HRESULT</span></span>|<span data-ttu-id="ae9f4-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="ae9f4-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ae9f4-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="ae9f4-114">S_OK</span></span>|<span data-ttu-id="ae9f4-115">El método se completó correctamente.</span><span class="sxs-lookup"><span data-stu-id="ae9f4-115">The method completed successfully.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ae9f4-116">Comentarios</span><span class="sxs-lookup"><span data-stu-id="ae9f4-116">Remarks</span></span>  
 <span data-ttu-id="ae9f4-117">Este método devuelve los valores de marca predeterminada (`STARTUP_CONCURRENT_GC` y `NULL`), o los valores proporcionados por una llamada anterior a la [SetDefaultStartupFlags (método)](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-setdefaultstartupflags-method.md), o los valores establecidos por cualquiera de los `CorBind*` métodos si están enlazados a este entorno de ejecución.</span><span class="sxs-lookup"><span data-stu-id="ae9f4-117">This method returns the default flag values (`STARTUP_CONCURRENT_GC` and `NULL`), or the values provided by a previous call to the [ICLRRuntimeInfo::SetDefaultStartupFlags method](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-setdefaultstartupflags-method.md), or the values set by any of the `CorBind*` methods if they are bound to this runtime.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ae9f4-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ae9f4-118">Requirements</span></span>  
 <span data-ttu-id="ae9f4-119">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ae9f4-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ae9f4-120">**Encabezado**: MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="ae9f4-120">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="ae9f4-121">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="ae9f4-121">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ae9f4-122">**Versiones de .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ae9f4-122">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae9f4-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="ae9f4-123">See also</span></span>

- [<span data-ttu-id="ae9f4-124">ICLRRuntimeInfo (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ae9f4-124">ICLRRuntimeInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)
- [<span data-ttu-id="ae9f4-125">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="ae9f4-125">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="ae9f4-126">Hospedar aplicaciones de WPF</span><span class="sxs-lookup"><span data-stu-id="ae9f4-126">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
