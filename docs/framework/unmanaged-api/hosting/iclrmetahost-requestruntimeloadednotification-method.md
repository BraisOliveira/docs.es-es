---
title: ICLRMetaHost::RequestRuntimeLoadedNotification (Método)
ms.date: 03/30/2017
api_name:
- ICLRMetaHost.RequestRuntimeLoadedNotification
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRMetaHost::RequestRuntimeLoadedNotification
helpviewer_keywords:
- RequestRuntimeLoadedNotification method [.NET Framework hosting]
- ICLRMetaHost::RequestRuntimeLoadedNotification method [.NET Framework hosting]
ms.assetid: 0d5ccc4d-0193-41f5-af54-45d7b70d5321
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 539f69c33b67ad1a8a514062c5d777deaced1599
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69965005"
---
# <a name="iclrmetahostrequestruntimeloadednotification-method"></a><span data-ttu-id="f8f54-102">ICLRMetaHost::RequestRuntimeLoadedNotification (Método)</span><span class="sxs-lookup"><span data-stu-id="f8f54-102">ICLRMetaHost::RequestRuntimeLoadedNotification Method</span></span>
<span data-ttu-id="f8f54-103">Proporciona una función de devolución de llamada que se garantiza que se llamará cuando una versión de Common Language Runtime (CLR) se cargue por primera vez, pero no se haya iniciado todavía.</span><span class="sxs-lookup"><span data-stu-id="f8f54-103">Provides a callback function that is guaranteed to be called when a common language runtime (CLR) version is first loaded, but not yet started.</span></span> <span data-ttu-id="f8f54-104">Este método reemplaza a la función [LockClrVersion](../../../../docs/framework/unmanaged-api/hosting/lockclrversion-function.md) .</span><span class="sxs-lookup"><span data-stu-id="f8f54-104">This method supersedes the [LockClrVersion](../../../../docs/framework/unmanaged-api/hosting/lockclrversion-function.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f8f54-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f8f54-105">Syntax</span></span>  
  
```cpp  
HRESULT RequestRuntimeLoadedNotification (  
    [in] RuntimeLoadedCallbackFnPtr pCallbackFunction);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f8f54-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f8f54-106">Parameters</span></span>  
 `pCallbackFunction`  
 <span data-ttu-id="f8f54-107">de Función de devolución de llamada que se invoca cuando se ha cargado un nuevo tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="f8f54-107">[in] The callback function that is invoked when a new runtime has been loaded.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f8f54-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="f8f54-108">Return Value</span></span>  
 <span data-ttu-id="f8f54-109">Este método devuelve los siguientes HRESULT específicos y los errores HRESULT que indican un error del método.</span><span class="sxs-lookup"><span data-stu-id="f8f54-109">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="f8f54-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="f8f54-110">HRESULT</span></span>|<span data-ttu-id="f8f54-111">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="f8f54-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="f8f54-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="f8f54-112">S_OK</span></span>|<span data-ttu-id="f8f54-113">El método se completó correctamente.</span><span class="sxs-lookup"><span data-stu-id="f8f54-113">The method completed successfully.</span></span>|  
|<span data-ttu-id="f8f54-114">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="f8f54-114">E_POINTER</span></span>|<span data-ttu-id="f8f54-115">`pCallbackFunction` es null.</span><span class="sxs-lookup"><span data-stu-id="f8f54-115">`pCallbackFunction` is null.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f8f54-116">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f8f54-116">Remarks</span></span>  
 <span data-ttu-id="f8f54-117">La devolución de llamada funciona de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="f8f54-117">The callback works in the following way:</span></span>  
  
- <span data-ttu-id="f8f54-118">La devolución de llamada se invoca solo cuando se carga por primera vez un tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="f8f54-118">The callback is invoked only when a runtime is loaded for the first time.</span></span>  
  
- <span data-ttu-id="f8f54-119">No se invoca la devolución de llamada para las cargas reentrantes del mismo tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="f8f54-119">The callback is not invoked for reentrant loads of the same runtime.</span></span>  
  
- <span data-ttu-id="f8f54-120">En el caso de las cargas de tiempo de ejecución no reentrantes, se serializan las llamadas a la función de devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="f8f54-120">For non-reentrant runtime loads, calls to the callback function are serialized.</span></span>  
  
 <span data-ttu-id="f8f54-121">La función de devolución de llamada tiene el prototipo siguiente:</span><span class="sxs-lookup"><span data-stu-id="f8f54-121">The callback function has the following prototype:</span></span>  
  
```cpp  
typedef void (__stdcall *RuntimeLoadedCallbackFnPtr)(  
                     ICLRRuntimeInfo *pRuntimeInfo,  
                     CallbackThreadSetFnPtr pfnCallbackThreadSet,  
                     CallbackThreadUnsetFnPtr pfnCallbackThreadUnset);  
```  
  
 <span data-ttu-id="f8f54-122">Los prototipos de función de devolución de llamada son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="f8f54-122">The callback function prototypes are as follows:</span></span>  
  
- <span data-ttu-id="f8f54-123">`pfnCallbackThreadSet`:</span><span class="sxs-lookup"><span data-stu-id="f8f54-123">`pfnCallbackThreadSet`:</span></span>  
  
    ```cpp  
    typedef HRESULT (__stdcall *CallbackThreadSetFnPtr)();  
    ```  
  
- <span data-ttu-id="f8f54-124">`pfnCallbackThreadUnset`:</span><span class="sxs-lookup"><span data-stu-id="f8f54-124">`pfnCallbackThreadUnset`:</span></span>  
  
    ```cpp  
    typedef HRESULT (__stdcall *CallbackThreadUnsetFnPtr)();  
    ```  
  
 <span data-ttu-id="f8f54-125">Si el host intenta cargar o hacer que otro Runtime se cargue de forma reentrante, los `pfnCallbackThreadSet` parámetros y `pfnCallbackThreadUnset` que se proporcionan en la función de devolución de llamada deben usarse de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="f8f54-125">If the host intends to load or cause another runtime to be loaded in a reentrant manner, the `pfnCallbackThreadSet` and `pfnCallbackThreadUnset` parameters that are provided in the callback function must be used in the following way:</span></span>  
  
- <span data-ttu-id="f8f54-126">`pfnCallbackThreadSet`debe ser invocado por el subproceso que puede producir una carga en tiempo de ejecución antes de que se intente una carga de este tipo.</span><span class="sxs-lookup"><span data-stu-id="f8f54-126">`pfnCallbackThreadSet` must be called by the thread that might cause a runtime load before such a load is attempted.</span></span>  
  
- <span data-ttu-id="f8f54-127">`pfnCallbackThreadUnset`se debe llamar a cuando el subproceso ya no producirá una carga de este tipo en tiempo de ejecución (y antes de devolver desde la devolución de llamada inicial).</span><span class="sxs-lookup"><span data-stu-id="f8f54-127">`pfnCallbackThreadUnset` must be called when the thread will no longer cause such a runtime load (and before returning from the initial callback).</span></span>  
  
- <span data-ttu-id="f8f54-128">`pfnCallbackThreadSet`y `pfnCallbackThreadUnset` son no reentrantes.</span><span class="sxs-lookup"><span data-stu-id="f8f54-128">`pfnCallbackThreadSet` and `pfnCallbackThreadUnset` are both non-reentrant.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f8f54-129">Las aplicaciones host no deben `pfnCallbackThreadSet` llamar `pfnCallbackThreadUnset` a y `pCallbackFunction` fuera del ámbito del parámetro.</span><span class="sxs-lookup"><span data-stu-id="f8f54-129">Host applications must not call `pfnCallbackThreadSet` and `pfnCallbackThreadUnset` outside the scope of the `pCallbackFunction` parameter.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f8f54-130">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f8f54-130">Requirements</span></span>  
 <span data-ttu-id="f8f54-131">**Select** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f8f54-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f8f54-132">**Encabezado**: Metahost. h</span><span class="sxs-lookup"><span data-stu-id="f8f54-132">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="f8f54-133">**Biblioteca** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="f8f54-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f8f54-134">**Versiones de .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f8f54-134">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f8f54-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="f8f54-135">See also</span></span>

- [<span data-ttu-id="f8f54-136">ICLRMetaHost (interfaz)</span><span class="sxs-lookup"><span data-stu-id="f8f54-136">ICLRMetaHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md)
- [<span data-ttu-id="f8f54-137">Hospedar aplicaciones de WPF</span><span class="sxs-lookup"><span data-stu-id="f8f54-137">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
