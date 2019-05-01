---
title: ICorDebugThread3::CreateStackWalk (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugThread3.CreateStackWalk Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread3::CreateStackWalk
helpviewer_keywords:
- CreateStackWalk method [.NET Framework debugging]
- ICorDebugThread3::CreateStackWalk method [.NET Framework debugging]
ms.assetid: c55e35d9-f9aa-4268-94b5-dce44c61acf2
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7969d8482970b13951938203262f6ce8f9bf574a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61993959"
---
# <a name="icordebugthread3createstackwalk-method"></a><span data-ttu-id="87413-102">ICorDebugThread3::CreateStackWalk (Método)</span><span class="sxs-lookup"><span data-stu-id="87413-102">ICorDebugThread3::CreateStackWalk Method</span></span>
<span data-ttu-id="87413-103">Crea un [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) objeto para el subproceso cuya pila desea desenredar.</span><span class="sxs-lookup"><span data-stu-id="87413-103">Creates an [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) object for the thread whose stack you want to unwind.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="87413-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="87413-104">Syntax</span></span>  
  
```  
HRESULT CreateStackWalk([out] ICorDebugStackWalk **ppStackWalk);  
```  
  
## <a name="parameters"></a><span data-ttu-id="87413-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="87413-105">Parameters</span></span>  
 `ppStackWalk`  
 <span data-ttu-id="87413-106">[out] Un puntero a la dirección de la [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) objeto para el subproceso cuya pila desea desenredar.</span><span class="sxs-lookup"><span data-stu-id="87413-106">[out] A pointer to address of the [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) object for the thread whose stack you want to unwind.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="87413-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="87413-107">Return Value</span></span>  
 <span data-ttu-id="87413-108">Este método devuelve los siguientes HRESULT específicos y los errores HRESULT que indican un error del método.</span><span class="sxs-lookup"><span data-stu-id="87413-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="87413-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="87413-109">HRESULT</span></span>|<span data-ttu-id="87413-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="87413-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="87413-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="87413-111">S_OK</span></span>|<span data-ttu-id="87413-112">La `ICorDebugStackWalk` objeto se creó correctamente.</span><span class="sxs-lookup"><span data-stu-id="87413-112">The `ICorDebugStackWalk` object was successfully created.</span></span>|  
|<span data-ttu-id="87413-113">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="87413-113">E_FAIL</span></span>|<span data-ttu-id="87413-114">El `ICorDebugStackWalk` no se creó el objeto.</span><span class="sxs-lookup"><span data-stu-id="87413-114">The `ICorDebugStackWalk` object was not created.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="87413-115">Excepciones</span><span class="sxs-lookup"><span data-stu-id="87413-115">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="87413-116">Comentarios</span><span class="sxs-lookup"><span data-stu-id="87413-116">Remarks</span></span>  
 <span data-ttu-id="87413-117">Si el `CreateStackWalk` método tiene éxito, el valor devuelto `ICorDebugStackWalk` contexto del objeto se establece en el contexto del subproceso actual.</span><span class="sxs-lookup"><span data-stu-id="87413-117">If the `CreateStackWalk` method succeeds, the returned `ICorDebugStackWalk` object's context is set to the thread's current context.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="87413-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="87413-118">Requirements</span></span>  
 <span data-ttu-id="87413-119">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="87413-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="87413-120">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="87413-120">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="87413-121">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="87413-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="87413-122">**Versiones de .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="87413-122">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="87413-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="87413-123">See also</span></span>

- [<span data-ttu-id="87413-124">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="87413-124">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="87413-125">Depuración</span><span class="sxs-lookup"><span data-stu-id="87413-125">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
