---
title: Interfaz ICorDebugGenericValue
ms.date: 03/30/2017
api_name:
- ICorDebugGenericValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugGenericValue
helpviewer_keywords:
- ICorDebugGenericValue interface [.NET Framework debugging]
ms.assetid: bc14f408-b359-4c8c-ade2-888ccdf7261b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ad2209c6e28c7749bd149902e5b696955ee7f13f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61988681"
---
# <a name="icordebuggenericvalue-interface"></a><span data-ttu-id="7fea5-102">Interfaz ICorDebugGenericValue</span><span class="sxs-lookup"><span data-stu-id="7fea5-102">ICorDebugGenericValue Interface</span></span>

<span data-ttu-id="7fea5-103">Una subclase de "ICorDebugValue" que se aplica a todos los valores.</span><span class="sxs-lookup"><span data-stu-id="7fea5-103">A subclass of "ICorDebugValue" that applies to all values.</span></span> <span data-ttu-id="7fea5-104">Esta interfaz proporciona métodos Get y Set para el valor.</span><span class="sxs-lookup"><span data-stu-id="7fea5-104">This interface provides Get and Set methods for the value.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="7fea5-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="7fea5-105">Methods</span></span>  
  
|<span data-ttu-id="7fea5-106">Método</span><span class="sxs-lookup"><span data-stu-id="7fea5-106">Method</span></span>|<span data-ttu-id="7fea5-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="7fea5-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="7fea5-108">GetValue (método)</span><span class="sxs-lookup"><span data-stu-id="7fea5-108">GetValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuggenericvalue-getvalue-method.md)|<span data-ttu-id="7fea5-109">Copia el valor en el búfer especificado.</span><span class="sxs-lookup"><span data-stu-id="7fea5-109">Copies the value into the specified buffer.</span></span>|  
|[<span data-ttu-id="7fea5-110">SetValue (método)</span><span class="sxs-lookup"><span data-stu-id="7fea5-110">SetValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuggenericvalue-setvalue-method.md)|<span data-ttu-id="7fea5-111">Copia un nuevo valor del búfer especificado.</span><span class="sxs-lookup"><span data-stu-id="7fea5-111">Copies a new value from the specified buffer.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7fea5-112">Comentarios</span><span class="sxs-lookup"><span data-stu-id="7fea5-112">Remarks</span></span>  
 <span data-ttu-id="7fea5-113">`ICorDebugGenericValue` es una subinterfaz porque es que no son utilizables de forma remota.</span><span class="sxs-lookup"><span data-stu-id="7fea5-113">`ICorDebugGenericValue` is a sub-interface because it is non-remotable.</span></span>  
  
 <span data-ttu-id="7fea5-114">Tipos de referencia, el valor es la referencia en lugar de con el contenido de la referencia.</span><span class="sxs-lookup"><span data-stu-id="7fea5-114">For reference types, the value is the reference rather than the contents of the reference.</span></span>  
  
 <span data-ttu-id="7fea5-115">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="7fea5-115">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7fea5-116">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="7fea5-116">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7fea5-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7fea5-117">Requirements</span></span>  
 <span data-ttu-id="7fea5-118">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7fea5-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7fea5-119">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7fea5-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7fea5-120">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7fea5-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7fea5-121">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7fea5-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7fea5-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="7fea5-122">See also</span></span>

- [<span data-ttu-id="7fea5-123">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="7fea5-123">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
