---
title: ICorProfilerInfo::EndInprocDebugging (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.EndInprocDebugging
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::EndInprocDebugging
helpviewer_keywords:
- ICorProfilerInfo::EndInprocDebugging method [.NET Framework profiling]
- EndInprocDebugging method [.NET Framework profiling]
ms.assetid: 35bc1188-9767-4141-8038-60ea015b99ac
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f86c680a10a3dcb1009b4f0cedd777ab9da5ac1f
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57501752"
---
# <a name="icorprofilerinfoendinprocdebugging-method"></a><span data-ttu-id="5fa12-102">ICorProfilerInfo::EndInprocDebugging (Método)</span><span class="sxs-lookup"><span data-stu-id="5fa12-102">ICorProfilerInfo::EndInprocDebugging Method</span></span>
<span data-ttu-id="5fa12-103">Se cierra una sesión de depuración en proceso.</span><span class="sxs-lookup"><span data-stu-id="5fa12-103">Shuts down an in-process debugging session.</span></span> <span data-ttu-id="5fa12-104">Este método está obsoleto en .NET Framework versión 2.0.</span><span class="sxs-lookup"><span data-stu-id="5fa12-104">This method is obsolete in the .NET Framework version 2.0.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5fa12-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5fa12-105">Syntax</span></span>  
  
```  
HRESULT EndInprocDebugging(  
    [in]  DWORD dwProfilerContext);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5fa12-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="5fa12-106">Parameters</span></span>  
 `dwProfilerContext`  
 <span data-ttu-id="5fa12-107">[in] Un valor que identifica la sesión de depuración.</span><span class="sxs-lookup"><span data-stu-id="5fa12-107">[in] A value that identifies the debugging session.</span></span> <span data-ttu-id="5fa12-108">Este valor debe ser el mismo que recibió en el [BeginInprocDebugging](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-begininprocdebugging-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="5fa12-108">This value must be the same as that received in the [ICorProfilerInfo::BeginInprocDebugging](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-begininprocdebugging-method.md) method.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5fa12-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="5fa12-109">Remarks</span></span>  
 <span data-ttu-id="5fa12-110">Debe llamar a [BeginInprocDebugging](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-begininprocdebugging-method.md) y `EndInprocDebugging` en el mismo método de devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="5fa12-110">You must call [ICorProfilerInfo::BeginInprocDebugging](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-begininprocdebugging-method.md) and `EndInprocDebugging` within the same callback method.</span></span>  
  
 <span data-ttu-id="5fa12-111">Los servicios de depuración de CLR admiten la depuración en proceso de forma limitada en las versiones 1.0 y 1.1 de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="5fa12-111">The CLR debugging services supported limited in-process debugging in the .NET Framework versions 1.0 and 1.1.</span></span> <span data-ttu-id="5fa12-112">Depuración en proceso habilitado un generador de perfiles usar las partes de inspección de la API de depuración.</span><span class="sxs-lookup"><span data-stu-id="5fa12-112">In-process debugging enabled a profiler to use the inspection portions of the debugging API.</span></span> <span data-ttu-id="5fa12-113">Sin embargo, debido a los comentarios de los clientes, la depuración en proceso tiene ha quitado de la versión 2.0 de .NET Framework y reemplaza con un conjunto de funciones que está más en consonancia con la API de generación de perfiles.</span><span class="sxs-lookup"><span data-stu-id="5fa12-113">However, due to customer feedback, in-process debugging has been removed from the .NET Framework in version 2.0, and replaced with a set of functionality that is more in line with the profiling API.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5fa12-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5fa12-114">Requirements</span></span>  
 <span data-ttu-id="5fa12-115">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5fa12-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5fa12-116">**Encabezado**: CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="5fa12-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="5fa12-117">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5fa12-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5fa12-118">**Versión de .NET framework:** 1.0</span><span class="sxs-lookup"><span data-stu-id="5fa12-118">**.NET Framework Version:** 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5fa12-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="5fa12-119">See also</span></span>
- [<span data-ttu-id="5fa12-120">ICorProfilerInfo (interfaz)</span><span class="sxs-lookup"><span data-stu-id="5fa12-120">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
