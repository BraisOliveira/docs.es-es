---
title: ICorDebugAppDomain3 (Interfaz)
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomain3
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain3
helpviewer_keywords:
- ICorDebugAppDomain3 interface [.NET Framework debugging]
ms.assetid: 875ef5be-c1e7-4d95-97e9-d3a667aeaba0
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7c141ca9a8e1c74015883f45cb2eaa9183bb3d89
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59177533"
---
# <a name="icordebugappdomain3-interface"></a><span data-ttu-id="6b237-102">ICorDebugAppDomain3 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="6b237-102">ICorDebugAppDomain3 Interface</span></span>
<span data-ttu-id="6b237-103">Proporciona métodos para recuperar información acerca de las representaciones administradas de [!INCLUDE[wrt](../../../../includes/wrt-md.md)] tipos cargados actualmente en un dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="6b237-103">Provides methods to retrieve information about the managed representations of [!INCLUDE[wrt](../../../../includes/wrt-md.md)] types currently loaded in an application domain.</span></span> <span data-ttu-id="6b237-104">Esta interfaz es una extensión de las interfaces ICorDebugAppDomain y ICorDebugAppDomain2.</span><span class="sxs-lookup"><span data-stu-id="6b237-104">This interface is an extension of the ICorDebugAppDomain and ICorDebugAppDomain2 interfaces.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="6b237-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="6b237-105">Methods</span></span>  
  
|<span data-ttu-id="6b237-106">Método</span><span class="sxs-lookup"><span data-stu-id="6b237-106">Method</span></span>|<span data-ttu-id="6b237-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="6b237-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="6b237-108">ICorDebugAppDomain3::GetCachedWinRTTypes</span><span class="sxs-lookup"><span data-stu-id="6b237-108">ICorDebugAppDomain3::GetCachedWinRTTypes</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain3-getcachedwinrttypes-method.md)|<span data-ttu-id="6b237-109">Obtiene un enumerador para todos los almacena en caché [!INCLUDE[wrt](../../../../includes/wrt-md.md)] tipos.</span><span class="sxs-lookup"><span data-stu-id="6b237-109">Gets an enumerator for all cached [!INCLUDE[wrt](../../../../includes/wrt-md.md)] types.</span></span>|  
|[<span data-ttu-id="6b237-110">ICorDebugAppDomain3::GetCachedWinRTTypesForIIDs</span><span class="sxs-lookup"><span data-stu-id="6b237-110">ICorDebugAppDomain3::GetCachedWinRTTypesForIIDs</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain3-getcachedwinrttypesforiids-method.md)|<span data-ttu-id="6b237-111">Obtiene un enumerador para almacenar en caché [!INCLUDE[wrt](../../../../includes/wrt-md.md)] tipos en un dominio de aplicación en función de sus identificadores de interfaz.</span><span class="sxs-lookup"><span data-stu-id="6b237-111">Gets an enumerator for cached [!INCLUDE[wrt](../../../../includes/wrt-md.md)] types in an application domain based on their interface identifiers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6b237-112">Comentarios</span><span class="sxs-lookup"><span data-stu-id="6b237-112">Remarks</span></span>  
 <span data-ttu-id="6b237-113">Esta interfaz está pensada para utilizarse por un depurador junto con una llamada a evaluación de función `M:System.Runtime.InteropServices.Marshal.GetInspectableIIDs(System.Object)`.</span><span class="sxs-lookup"><span data-stu-id="6b237-113">This interface is meant to be used by a debugger in conjunction with a function evaluation call to `M:System.Runtime.InteropServices.Marshal.GetInspectableIIDs(System.Object)`.</span></span> <span data-ttu-id="6b237-114">Cuando el método recupera los identificadores de interfaz compatibles con un [!INCLUDE[wrt](../../../../includes/wrt-md.md)] objeto de servidor, el depurador puede usar los métodos definidos en esta interfaz para asignarlas a tipos administrados correspondientes a esas interfaces.</span><span class="sxs-lookup"><span data-stu-id="6b237-114">When the method retrieves the interface identifiers supported by a [!INCLUDE[wrt](../../../../includes/wrt-md.md)] server object, the debugger may use the methods defined in this interface to map them to managed types that correspond to those interfaces.</span></span>  
  
 <span data-ttu-id="6b237-115">Para recuperar una instancia de esta interfaz, ejecute `QueryInterface` en una instancia de la interfaz ICorDebugAppDomain o ICorDebugAppDomain2.</span><span class="sxs-lookup"><span data-stu-id="6b237-115">To retrieve an instance of this interface, run `QueryInterface` on an instance of the ICorDebugAppDomain or ICorDebugAppDomain2 interface.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6b237-116">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="6b237-116">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6b237-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="6b237-117">Requirements</span></span>  
 **<span data-ttu-id="6b237-118">Plataformas:</span><span class="sxs-lookup"><span data-stu-id="6b237-118">Platforms:</span></span>** [!INCLUDE[wrt](../../../../includes/wrt-md.md)]  
  
 <span data-ttu-id="6b237-119">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6b237-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6b237-120">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6b237-120">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="6b237-121">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="6b237-121">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="6b237-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="6b237-122">See also</span></span>

- [<span data-ttu-id="6b237-123">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="6b237-123">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
