---
title: Interfaz ICorDebugModule2
ms.date: 03/30/2017
api_name:
- ICorDebugModule2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule2
helpviewer_keywords:
- ICorDebugModule2 interface [.NET Framework debugging]
ms.assetid: 0847e64f-fdbe-4c96-8168-da20fdc84d80
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d8fe1a25c4bc1f5e19f49f0d660d0aad5a180ea2
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69911887"
---
# <a name="icordebugmodule2-interface"></a><span data-ttu-id="01705-102">Interfaz ICorDebugModule2</span><span class="sxs-lookup"><span data-stu-id="01705-102">ICorDebugModule2 Interface</span></span>

<span data-ttu-id="01705-103">Actúa como una extensión lógica de la interfaz ICorDebugModule.</span><span class="sxs-lookup"><span data-stu-id="01705-103">Serves as a logical extension to the ICorDebugModule interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="01705-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="01705-104">Methods</span></span>  
  
|<span data-ttu-id="01705-105">Método</span><span class="sxs-lookup"><span data-stu-id="01705-105">Method</span></span>|<span data-ttu-id="01705-106">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="01705-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="01705-107">ApplyChanges (método)</span><span class="sxs-lookup"><span data-stu-id="01705-107">ApplyChanges Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-applychanges-method.md)|<span data-ttu-id="01705-108">Aplica los cambios en los metadatos y los cambios en el código del lenguaje intermedio de Microsoft (MSIL) al proceso en ejecución.</span><span class="sxs-lookup"><span data-stu-id="01705-108">Applies the changes in the metadata and the changes in the Microsoft intermediate language (MSIL) code to the running process.</span></span>|  
|[<span data-ttu-id="01705-109">GetJITCompilerFlags (método)</span><span class="sxs-lookup"><span data-stu-id="01705-109">GetJITCompilerFlags Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-getjitcompilerflags-method.md)|<span data-ttu-id="01705-110">Obtiene las marcas que controlan la compilación Just-in-Time (JIT) para `ICorDebugModule2`este.</span><span class="sxs-lookup"><span data-stu-id="01705-110">Gets the flags that control the just-in-time (JIT) compilation for this `ICorDebugModule2`.</span></span>|  
|[<span data-ttu-id="01705-111">ResolveAssembly (método)</span><span class="sxs-lookup"><span data-stu-id="01705-111">ResolveAssembly Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-resolveassembly-method.md)|<span data-ttu-id="01705-112">Resuelve el ensamblado al que hace referencia el token de metadatos especificado.</span><span class="sxs-lookup"><span data-stu-id="01705-112">Resolves the assembly referenced by the specified metadata token.</span></span>|  
|[<span data-ttu-id="01705-113">SetJITCompilerFlags (método)</span><span class="sxs-lookup"><span data-stu-id="01705-113">SetJITCompilerFlags Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-setjitcompilerflags-method.md)|<span data-ttu-id="01705-114">Establece las marcas que controlan la compilación JIT para `ICorDebugModule2`este.</span><span class="sxs-lookup"><span data-stu-id="01705-114">Sets the flags that control the JIT compilation for this `ICorDebugModule2`.</span></span>|  
|[<span data-ttu-id="01705-115">SetJMCStatus (método)</span><span class="sxs-lookup"><span data-stu-id="01705-115">SetJMCStatus Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-setjmcstatus-method.md)|<span data-ttu-id="01705-116">Establece el estado solo mi código (JMC) de todos los métodos de todas las clases de `ICorDebugModule2` este en el valor especificado, excepto los de `pTokens` la matriz, que establece en el valor opuesto.</span><span class="sxs-lookup"><span data-stu-id="01705-116">Sets the Just My Code (JMC) status of all methods of all the classes in this `ICorDebugModule2` to the specified value, except those in the `pTokens` array, which it sets to the opposite value.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="01705-117">Comentarios</span><span class="sxs-lookup"><span data-stu-id="01705-117">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="01705-118">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="01705-118">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="01705-119">Requisitos</span><span class="sxs-lookup"><span data-stu-id="01705-119">Requirements</span></span>  
 <span data-ttu-id="01705-120">**Select** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="01705-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="01705-121">**Encabezado**: Cordebug. idl, Cordebug. h</span><span class="sxs-lookup"><span data-stu-id="01705-121">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="01705-122">**Biblioteca** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="01705-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="01705-123">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="01705-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="01705-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="01705-124">See also</span></span>

- [<span data-ttu-id="01705-125">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="01705-125">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
