---
title: ICorDebugDataTarget::GetThreadContext (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugDataTarget.GetThreadContext Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugDataTarget::GetThreadContext
helpviewer_keywords:
- ICorDebugDataTarget::GetThreadContext method [.NET Framework debugging]
- GetThreadContext method, ICorDebugDataTarget interface [.NET Framework debugging]
ms.assetid: c8954268-1821-4b23-b665-dbb55f2af31b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2db073f6bde3ded27f8e1aa41bfcb87e764745f1
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59174972"
---
# <a name="icordebugdatatargetgetthreadcontext-method"></a><span data-ttu-id="a9f06-102">ICorDebugDataTarget::GetThreadContext (Método)</span><span class="sxs-lookup"><span data-stu-id="a9f06-102">ICorDebugDataTarget::GetThreadContext Method</span></span>
<span data-ttu-id="a9f06-103">Devuelve el contexto del subproceso actual para el subproceso especificado.</span><span class="sxs-lookup"><span data-stu-id="a9f06-103">Returns the current thread context for the specified thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a9f06-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a9f06-104">Syntax</span></span>  
  
```  
HRESULT GetThreadContext(  
       [in] DWORD dwThreadID,  
       [in] ULONG32 contextFlags,  
       [in] ULONG32 contextSize,  
       [out, size_is(contextSize)] BYTE * pContext);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a9f06-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a9f06-105">Parameters</span></span>  
 `dwThreadID`  
 <span data-ttu-id="a9f06-106">[in] El identificador del subproceso cuyo contexto es va a recuperar.</span><span class="sxs-lookup"><span data-stu-id="a9f06-106">[in] The identifier of the thread whose context is to be retrieved.</span></span> <span data-ttu-id="a9f06-107">El identificador está definido por el sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="a9f06-107">The identifier is defined by the operating system.</span></span>  
  
 `contextFlags`  
 <span data-ttu-id="a9f06-108">[in] Una combinación bit a bit de marcas de depende de la plataforma que indican qué partes del contexto deben leerse.</span><span class="sxs-lookup"><span data-stu-id="a9f06-108">[in] A bitwise combination of platform-dependent flags that indicate which portions of the context should be read.</span></span>  
  
 `contextSize`  
 <span data-ttu-id="a9f06-109">[in] Tamaño de `pContext`.</span><span class="sxs-lookup"><span data-stu-id="a9f06-109">[in] The size of `pContext`.</span></span>  
  
 `pContext`  
 <span data-ttu-id="a9f06-110">[out] El búfer donde se almacenará el contexto del subproceso.</span><span class="sxs-lookup"><span data-stu-id="a9f06-110">[out] The buffer where the thread context will be stored.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a9f06-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a9f06-111">Remarks</span></span>  
 <span data-ttu-id="a9f06-112">En las plataformas Windows, `pContext` debe ser un `CONTEXT` estructura (definida en WinNT.h) que sea adecuada para el tipo de equipo especificado por el [ICorDebugDataTarget:: GetPlatform](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-getplatform-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="a9f06-112">On Windows platforms, `pContext` must be a `CONTEXT` structure (defined in WinNT.h) that is appropriate for the machine type specified by the [ICorDebugDataTarget::GetPlatform](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-getplatform-method.md) method.</span></span> <span data-ttu-id="a9f06-113">`contextFlags` debe tener los mismos valores que el `ContextFlags` campo de la `CONTEXT` estructura.</span><span class="sxs-lookup"><span data-stu-id="a9f06-113">`contextFlags` must have the same values as the `ContextFlags` field of the `CONTEXT` structure.</span></span> <span data-ttu-id="a9f06-114">El `CONTEXT` estructura es específico del procesador; consulte el archivo WinNT.h para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="a9f06-114">The `CONTEXT` structure is processor-specific; refer to the WinNT.h file for details.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a9f06-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a9f06-115">Requirements</span></span>  
 <span data-ttu-id="a9f06-116">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a9f06-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a9f06-117">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a9f06-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a9f06-118">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a9f06-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a9f06-119">**Versiones de .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a9f06-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a9f06-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="a9f06-120">See also</span></span>

- [<span data-ttu-id="a9f06-121">ICorDebugDataTarget (interfaz)</span><span class="sxs-lookup"><span data-stu-id="a9f06-121">ICorDebugDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md)
- [<span data-ttu-id="a9f06-122">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="a9f06-122">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="a9f06-123">Depuración</span><span class="sxs-lookup"><span data-stu-id="a9f06-123">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
