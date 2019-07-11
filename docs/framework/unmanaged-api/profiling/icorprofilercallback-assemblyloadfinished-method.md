---
title: ICorProfilerCallback::AssemblyLoadFinished (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.AssemblyLoadFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::AssemblyLoadFinished
helpviewer_keywords:
- ICorProfilerCallback::AssemblyLoadFinished method [.NET Framework profiling]
- AssemblyLoadFinished method [.NET Framework profiling]
ms.assetid: 86d98f39-52e6-4c61-a625-9760f695ff12
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 174e71fca8c59dbd4842d0fc0b84bb9a3d7b10df
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67763045"
---
# <a name="icorprofilercallbackassemblyloadfinished-method"></a><span data-ttu-id="27e42-102">ICorProfilerCallback::AssemblyLoadFinished (Método)</span><span class="sxs-lookup"><span data-stu-id="27e42-102">ICorProfilerCallback::AssemblyLoadFinished Method</span></span>
<span data-ttu-id="27e42-103">Notifica al generador de perfiles que un ensamblado ha terminado de cargarse.</span><span class="sxs-lookup"><span data-stu-id="27e42-103">Notifies the profiler that an assembly has finished loading.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="27e42-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="27e42-104">Syntax</span></span>  
  
```cpp  
HRESULT AssemblyLoadFinished(  
    [in] AssemblyID assemblyId,  
    [in] HRESULT    hrStatus);  
```  
  
## <a name="parameters"></a><span data-ttu-id="27e42-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="27e42-105">Parameters</span></span>  
 `assemblyId`  
 <span data-ttu-id="27e42-106">[in] Identifica el ensamblado que se cargó.</span><span class="sxs-lookup"><span data-stu-id="27e42-106">[in] Identifies the assembly that was loaded.</span></span>  
  
 `hrStatus`  
 <span data-ttu-id="27e42-107">[in] Un HRESULT que indica si el ensamblado terminó de cargar correctamente.</span><span class="sxs-lookup"><span data-stu-id="27e42-107">[in] An HRESULT that indicates whether the assembly finished loading successfully.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="27e42-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="27e42-108">Remarks</span></span>  
 <span data-ttu-id="27e42-109">El valor de `assemblyId` no es válido para una solicitud de información hasta que el `AssemblyLoadFinished` se llama al método.</span><span class="sxs-lookup"><span data-stu-id="27e42-109">The value of `assemblyId` is not valid for an information request until the `AssemblyLoadFinished` method is called.</span></span>  
  
 <span data-ttu-id="27e42-110">Algunas partes de la carga del ensamblado podrían continuar después de la `AssemblyLoadFinished` devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="27e42-110">Some parts of loading the assembly might continue after the `AssemblyLoadFinished` callback.</span></span> <span data-ttu-id="27e42-111">Un error HRESULT en `hrStatus` indica un error.</span><span class="sxs-lookup"><span data-stu-id="27e42-111">A failure HRESULT in `hrStatus` indicates a failure.</span></span> <span data-ttu-id="27e42-112">Sin embargo, un valor HRESULT correcto en `hrStatus` sólo indica que la primera parte de la carga el ensamblado se ha realizado correctamente.</span><span class="sxs-lookup"><span data-stu-id="27e42-112">However, a success HRESULT in `hrStatus` indicates only that the first part of loading the assembly has succeeded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="27e42-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="27e42-113">Requirements</span></span>  
 <span data-ttu-id="27e42-114">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="27e42-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="27e42-115">**Encabezado**: CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="27e42-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="27e42-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="27e42-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="27e42-117">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="27e42-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="27e42-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="27e42-118">See also</span></span>

- [<span data-ttu-id="27e42-119">ICorProfilerCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="27e42-119">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
