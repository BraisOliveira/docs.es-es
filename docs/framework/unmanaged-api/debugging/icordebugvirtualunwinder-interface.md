---
title: Interfaz de ICorDebugVirtualUnwinder
ms.date: 03/30/2017
ms.assetid: a09e9ccc-0b37-43e3-95c1-bc5fa7ee5f42
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 639cfc514d2a206f0de72db4b0bac02b53305ae3
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59083405"
---
# <a name="icordebugvirtualunwinder-interface"></a><span data-ttu-id="b8cba-102">Interfaz de ICorDebugVirtualUnwinder</span><span class="sxs-lookup"><span data-stu-id="b8cba-102">ICorDebugVirtualUnwinder Interface</span></span>
<span data-ttu-id="b8cba-103">Proporciona métodos que ayudan al desenredo de la pila.</span><span class="sxs-lookup"><span data-stu-id="b8cba-103">Provides methods to help in stack unwinding.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="b8cba-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="b8cba-104">Methods</span></span>  
  
|<span data-ttu-id="b8cba-105">Método</span><span class="sxs-lookup"><span data-stu-id="b8cba-105">Method</span></span>|<span data-ttu-id="b8cba-106">Name</span><span class="sxs-lookup"><span data-stu-id="b8cba-106">Name</span></span>|  
|------------|----------|  
|[<span data-ttu-id="b8cba-107">Método GetContext</span><span class="sxs-lookup"><span data-stu-id="b8cba-107">GetContext Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvirtualunwinder-getcontext-method.md)|<span data-ttu-id="b8cba-108">Obtiene el contexto actual de este responsable del desenredado.</span><span class="sxs-lookup"><span data-stu-id="b8cba-108">Gets the current context of this unwinder.</span></span>|  
|[<span data-ttu-id="b8cba-109">Método Next</span><span class="sxs-lookup"><span data-stu-id="b8cba-109">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvirtualunwinder-next-method.md)|<span data-ttu-id="b8cba-110">Avanza hasta el contexto del llamador.</span><span class="sxs-lookup"><span data-stu-id="b8cba-110">Advances to the caller's context.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b8cba-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="b8cba-111">Remarks</span></span>  
 <span data-ttu-id="b8cba-112">Los miembros de la interfaz `ICorDebugVirtualUnwinder` se implementan mediante el depurador para ayudar al desenredo de pila.</span><span class="sxs-lookup"><span data-stu-id="b8cba-112">The members of the `ICorDebugVirtualUnwinder` interface are implemented by the debugger to help in stack unwinding.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b8cba-113">Esta interfaz solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="b8cba-113">This interface is available with .NET Native only.</span></span> <span data-ttu-id="b8cba-114">Si implementa esta interfaz para escenarios de ICorDebug fuera de .NET Native, Common Language Runtime ignorará esta interfaz.</span><span class="sxs-lookup"><span data-stu-id="b8cba-114">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b8cba-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b8cba-115">Requirements</span></span>  
 <span data-ttu-id="b8cba-116">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b8cba-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b8cba-117">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b8cba-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b8cba-118">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b8cba-118">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="b8cba-119">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="b8cba-119">.NET Framework Versions:</span></span>** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="b8cba-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="b8cba-120">See also</span></span>

- [<span data-ttu-id="b8cba-121">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="b8cba-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="b8cba-122">Depuración</span><span class="sxs-lookup"><span data-stu-id="b8cba-122">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
