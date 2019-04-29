---
title: ICorProfilerCallback::AppDomainCreationFinished (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.AppDomainCreationFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::AppDomainCreationFinished
helpviewer_keywords:
- AppDomainCreationFinished method [.NET Framework profiling]
- ICorProfilerCallback::AppDomainCreationFinished method [.NET Framework profiling]
ms.assetid: dbab7d90-d515-4dc9-8195-294d5d04bab6
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 35dac5fd000f5ae30af917e3813239b2e365e64a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61598564"
---
# <a name="icorprofilercallbackappdomaincreationfinished-method"></a><span data-ttu-id="faa79-102">ICorProfilerCallback::AppDomainCreationFinished (Método)</span><span class="sxs-lookup"><span data-stu-id="faa79-102">ICorProfilerCallback::AppDomainCreationFinished Method</span></span>
<span data-ttu-id="faa79-103">Notifica al generador de perfiles que se ha creado un dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="faa79-103">Notifies the profiler that an application domain has been created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="faa79-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="faa79-104">Syntax</span></span>  
  
```  
HRESULT AppDomainCreationFinished(  
    [in] AppDomainID appDomainId,  
    [in] HRESULT     hrStatus);   
```  
  
## <a name="parameters"></a><span data-ttu-id="faa79-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="faa79-105">Parameters</span></span>  
 `appDomainId`  
 <span data-ttu-id="faa79-106">[in] Identifica el dominio que se ha creado.</span><span class="sxs-lookup"><span data-stu-id="faa79-106">[in] Identifies the domain which has been created.</span></span>  
  
 `hrStatus`  
 <span data-ttu-id="faa79-107">[in] Un HRESULT que indica si se completó correctamente la creación del dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="faa79-107">[in] An HRESULT that indicates whether creation of the application domain completed successfully.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="faa79-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="faa79-108">Remarks</span></span>  
 <span data-ttu-id="faa79-109">El identificador de aplicación no es válido para cualquier solicitud de información hasta que el `AppDomainCreationFinished` se llama al método.</span><span class="sxs-lookup"><span data-stu-id="faa79-109">The application ID is not valid for any information request until the `AppDomainCreationFinished` method is called.</span></span>  
  
 <span data-ttu-id="faa79-110">Algunas partes de la carga del dominio de aplicación podrían continuar después de la `AppDomainCreationFinished` devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="faa79-110">Some parts of loading the application domain might continue after the `AppDomainCreationFinished` callback.</span></span> <span data-ttu-id="faa79-111">Un error HRESULT en `hrStatus` indica un error.</span><span class="sxs-lookup"><span data-stu-id="faa79-111">A failure HRESULT in `hrStatus` indicates a failure.</span></span> <span data-ttu-id="faa79-112">Sin embargo, un valor HRESULT correcto en `hrStatus` sólo indica que la primera parte de la creación del dominio de aplicación se ha realizado correctamente.</span><span class="sxs-lookup"><span data-stu-id="faa79-112">However, a success HRESULT in `hrStatus` indicates only that the first part of creating the application domain has succeeded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="faa79-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="faa79-113">Requirements</span></span>  
 <span data-ttu-id="faa79-114">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="faa79-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="faa79-115">**Encabezado**: CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="faa79-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="faa79-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="faa79-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="faa79-117">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="faa79-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="faa79-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="faa79-118">See also</span></span>

- [<span data-ttu-id="faa79-119">ICorProfilerCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="faa79-119">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
