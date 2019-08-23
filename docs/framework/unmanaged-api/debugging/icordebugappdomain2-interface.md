---
title: Interfaz ICorDebugAppDomain2
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomain2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain2
helpviewer_keywords:
- ICorDebugAppDomain2 interface [.NET Framework debugging]
ms.assetid: 314d29f3-feb0-4a92-9530-b569c280cc31
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 63772c6642cc6f7f96a375beab4f7ef1b4884139
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69959843"
---
# <a name="icordebugappdomain2-interface"></a><span data-ttu-id="4d0ed-102">Interfaz ICorDebugAppDomain2</span><span class="sxs-lookup"><span data-stu-id="4d0ed-102">ICorDebugAppDomain2 Interface</span></span>

<span data-ttu-id="4d0ed-103">Proporciona métodos para trabajar con matrices, punteros, punteros de función y tipos de referencia.</span><span class="sxs-lookup"><span data-stu-id="4d0ed-103">Provides methods to work with arrays, pointers, function pointers, and reference types.</span></span> <span data-ttu-id="4d0ed-104">Esta interfaz es una extensión de la interfaz ICorDebugAppDomain.</span><span class="sxs-lookup"><span data-stu-id="4d0ed-104">This interface is an extension of the ICorDebugAppDomain interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="4d0ed-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="4d0ed-105">Methods</span></span>  
  
|<span data-ttu-id="4d0ed-106">Método</span><span class="sxs-lookup"><span data-stu-id="4d0ed-106">Method</span></span>|<span data-ttu-id="4d0ed-107">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="4d0ed-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="4d0ed-108">GetArrayOrPointerType (método)</span><span class="sxs-lookup"><span data-stu-id="4d0ed-108">GetArrayOrPointerType Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain2-getarrayorpointertype-method.md)|<span data-ttu-id="4d0ed-109">Obtiene una matriz del tipo especificado, o un puntero o una referencia al tipo especificado.</span><span class="sxs-lookup"><span data-stu-id="4d0ed-109">Gets an array of the specified type, or a pointer or reference to the specified type.</span></span>|  
|[<span data-ttu-id="4d0ed-110">GetFunctionPointerType</span><span class="sxs-lookup"><span data-stu-id="4d0ed-110">GetFunctionPointerType</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain2-getfunctionpointertype-method.md)|<span data-ttu-id="4d0ed-111">Obtiene un puntero a una función que tiene una firma especificada.</span><span class="sxs-lookup"><span data-stu-id="4d0ed-111">Gets a pointer to a function that has a given signature.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4d0ed-112">Comentarios</span><span class="sxs-lookup"><span data-stu-id="4d0ed-112">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="4d0ed-113">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="4d0ed-113">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4d0ed-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4d0ed-114">Requirements</span></span>  
 <span data-ttu-id="4d0ed-115">**Select** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4d0ed-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4d0ed-116">**Encabezado**: Cordebug. idl, Cordebug. h</span><span class="sxs-lookup"><span data-stu-id="4d0ed-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4d0ed-117">**Biblioteca** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4d0ed-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4d0ed-118">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4d0ed-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4d0ed-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="4d0ed-119">See also</span></span>

- [<span data-ttu-id="4d0ed-120">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="4d0ed-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
