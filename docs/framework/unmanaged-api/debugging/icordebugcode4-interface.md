---
title: Interfaz ICorDebugCode4
ms.date: 03/30/2017
api_name:
- ICorDebugCode4
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode4
helpviewer_keywords:
- ICorDebugCode4 interface [.NET Framework debugging]
ms.assetid: a3fdf523-274a-449c-920b-9fcb0aed1d97
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d23f588b46eb452b7670085249938f7d10cea1ba
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59108184"
---
# <a name="icordebugcode4-interface"></a><span data-ttu-id="c4e3c-102">Interfaz ICorDebugCode4</span><span class="sxs-lookup"><span data-stu-id="c4e3c-102">ICorDebugCode4 Interface</span></span>
<span data-ttu-id="c4e3c-103">Proporciona un método que permite a un depurador enumerar las variables locales y los argumentos en una función.</span><span class="sxs-lookup"><span data-stu-id="c4e3c-103">Provides a method that enables a debugger to enumerate the local variables and arguments in a function.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="c4e3c-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="c4e3c-104">Methods</span></span>  
  
|<span data-ttu-id="c4e3c-105">Método</span><span class="sxs-lookup"><span data-stu-id="c4e3c-105">Method</span></span>|<span data-ttu-id="c4e3c-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="c4e3c-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="c4e3c-107">Método EnumerateVariableHomes</span><span class="sxs-lookup"><span data-stu-id="c4e3c-107">EnumerateVariableHomes Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode4-enumeratevariablehomes-method.md)|<span data-ttu-id="c4e3c-108">Obtiene un enumerador para los argumentos y variables locales en una función.</span><span class="sxs-lookup"><span data-stu-id="c4e3c-108">Gets an enumerator to the local variables and arguments in a function.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c4e3c-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="c4e3c-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c4e3c-110">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="c4e3c-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c4e3c-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c4e3c-111">Requirements</span></span>  
 <span data-ttu-id="c4e3c-112">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c4e3c-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c4e3c-113">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c4e3c-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c4e3c-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c4e3c-114">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="c4e3c-115">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="c4e3c-115">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="c4e3c-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="c4e3c-116">See also</span></span>

- [<span data-ttu-id="c4e3c-117">ICorDebugCode3 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="c4e3c-117">ICorDebugCode3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode3-interface.md)
- [<span data-ttu-id="c4e3c-118">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="c4e3c-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
