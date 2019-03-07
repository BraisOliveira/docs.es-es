---
title: ICorDebugMemoryBuffer::GetStartAddress (método)
ms.date: 03/30/2017
ms.assetid: f804d9ab-8c88-44f0-b278-5fcca7f87726
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0f4f51c087112053aa7b76bff1f7c55016c8ff57
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57474753"
---
# <a name="icordebugmemorybuffergetstartaddress-method"></a><span data-ttu-id="611dd-102">ICorDebugMemoryBuffer::GetStartAddress (método)</span><span class="sxs-lookup"><span data-stu-id="611dd-102">ICorDebugMemoryBuffer::GetStartAddress Method</span></span>
<span data-ttu-id="611dd-103">Obtiene la dirección de inicio del búfer de memoria.</span><span class="sxs-lookup"><span data-stu-id="611dd-103">Gets the starting address of the memory buffer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="611dd-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="611dd-104">Syntax</span></span>  
  
```  
HRESULT GetStartAddress(  
   [out] LPCVOID *address  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="611dd-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="611dd-105">Parameters</span></span>  
 `address`  
 <span data-ttu-id="611dd-106">[out] Puntero a la dirección de inicio del búfer de memoria.</span><span class="sxs-lookup"><span data-stu-id="611dd-106">[out] A pointer to the starting address of the memory buffer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="611dd-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="611dd-107">Remarks</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="611dd-108">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="611dd-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="611dd-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="611dd-109">Requirements</span></span>  
 <span data-ttu-id="611dd-110">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="611dd-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="611dd-111">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="611dd-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="611dd-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="611dd-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="611dd-113">**Versiones de .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="611dd-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="611dd-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="611dd-114">See also</span></span>
- [<span data-ttu-id="611dd-115">ICorDebugMemoryBuffer (interfaz)</span><span class="sxs-lookup"><span data-stu-id="611dd-115">ICorDebugMemoryBuffer Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmemorybuffer-interface.md)
- [<span data-ttu-id="611dd-116">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="611dd-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
