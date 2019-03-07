---
title: Método ICorDebugDataTarget2::EnumerateThreadIDs
ms.date: 03/30/2017
ms.assetid: af02460f-2a45-496e-bc4e-a1ac4f80fe11
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1136b01aba5f2143c6d26388568df0b60a5db123
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57492184"
---
# <a name="icordebugdatatarget2enumeratethreadids-method"></a><span data-ttu-id="ae5c4-102">Método ICorDebugDataTarget2::EnumerateThreadIDs</span><span class="sxs-lookup"><span data-stu-id="ae5c4-102">ICorDebugDataTarget2::EnumerateThreadIDs Method</span></span>
<span data-ttu-id="ae5c4-103">Devuelve una lista de identificadores de subprocesos activos.</span><span class="sxs-lookup"><span data-stu-id="ae5c4-103">Returns a list of active thread IDs.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ae5c4-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ae5c4-104">Syntax</span></span>  
  
```  
HRESULT EnumerateThreadIDs(  
    [in] ULONG32 cThreadIds,   
    [out] ULONG32 *pcThreadIds,   
    [out, size_is(cThreadIds), length_is(*pcThreadIds)] ULONG32 pThreadIds[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ae5c4-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ae5c4-105">Parameters</span></span>  
 <span data-ttu-id="ae5c4-106">cThreadIDs</span><span class="sxs-lookup"><span data-stu-id="ae5c4-106">cThreadIDs</span></span>  
 <span data-ttu-id="ae5c4-107">[in] Número máximo de subprocesos cuyos identificadores se pueden devolver.</span><span class="sxs-lookup"><span data-stu-id="ae5c4-107">[in] The maximum number of threads whose IDs can be returned.</span></span>  
  
 <span data-ttu-id="ae5c4-108">pcThreadIds</span><span class="sxs-lookup"><span data-stu-id="ae5c4-108">pcThreadIds</span></span>  
 <span data-ttu-id="ae5c4-109">[out] Puntero a un `ULONG32` que indica el número real de identificadores de subproceso escritos en la matriz `pThreadIds`.</span><span class="sxs-lookup"><span data-stu-id="ae5c4-109">[out] A pointer to a `ULONG32` that indicates the actual number of thread IDs written to the `pThreadIds` array.</span></span>  
  
 <span data-ttu-id="ae5c4-110">pThreadIDs</span><span class="sxs-lookup"><span data-stu-id="ae5c4-110">pThreadIDs</span></span>  
 <span data-ttu-id="ae5c4-111">Matriz de identificadores de subproceso.</span><span class="sxs-lookup"><span data-stu-id="ae5c4-111">An array of thread identifiers.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ae5c4-112">Comentarios</span><span class="sxs-lookup"><span data-stu-id="ae5c4-112">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ae5c4-113">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="ae5c4-113">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ae5c4-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ae5c4-114">Requirements</span></span>  
 <span data-ttu-id="ae5c4-115">**Plataformas:** Consulte [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md). **Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ae5c4-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ae5c4-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ae5c4-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ae5c4-117">**Versiones de .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ae5c4-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae5c4-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="ae5c4-118">See also</span></span>
- [<span data-ttu-id="ae5c4-119">ICorDebugDataTarget2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ae5c4-119">ICorDebugDataTarget2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget2-interface.md)
- [<span data-ttu-id="ae5c4-120">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="ae5c4-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
