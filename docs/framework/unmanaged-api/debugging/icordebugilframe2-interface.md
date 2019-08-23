---
title: Interfaz ICorDebugILFrame2
ms.date: 03/30/2017
api_name:
- ICorDebugILFrame2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugILFrame2
helpviewer_keywords:
- ICorDebugILFrame2 interface [.NET Framework debugging]
ms.assetid: f94b9d53-d8f8-4424-a95e-53a1bfd26e4a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d02dab01eca3bd4f8ce3ae7ace7f9d4be8233dca
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69917002"
---
# <a name="icordebugilframe2-interface"></a><span data-ttu-id="26e35-102">Interfaz ICorDebugILFrame2</span><span class="sxs-lookup"><span data-stu-id="26e35-102">ICorDebugILFrame2 Interface</span></span>

<span data-ttu-id="26e35-103">Extensión lógica de la interfaz ICorDebugILFrame.</span><span class="sxs-lookup"><span data-stu-id="26e35-103">A logical extension of the ICorDebugILFrame interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="26e35-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="26e35-104">Methods</span></span>  
  
|<span data-ttu-id="26e35-105">Método</span><span class="sxs-lookup"><span data-stu-id="26e35-105">Method</span></span>|<span data-ttu-id="26e35-106">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="26e35-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="26e35-107">EnumerateTypeParameters (método)</span><span class="sxs-lookup"><span data-stu-id="26e35-107">EnumerateTypeParameters Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe2-enumeratetypeparameters-method.md)|<span data-ttu-id="26e35-108">Obtiene un objeto ICorDebugTypeEnum que contiene los <xref:System.Type> parámetros de este marco.</span><span class="sxs-lookup"><span data-stu-id="26e35-108">Gets an ICorDebugTypeEnum object that contains the <xref:System.Type> parameters in this frame.</span></span>|  
|[<span data-ttu-id="26e35-109">RemapFunction (método)</span><span class="sxs-lookup"><span data-stu-id="26e35-109">RemapFunction Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe2-remapfunction-method.md)|<span data-ttu-id="26e35-110">Vuelve a asignar una función editada especificando el nuevo desplazamiento de MSIL.</span><span class="sxs-lookup"><span data-stu-id="26e35-110">Remaps an edited function by specifying the new MSIL offset.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="26e35-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="26e35-111">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="26e35-112">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="26e35-112">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="26e35-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="26e35-113">Requirements</span></span>  
 <span data-ttu-id="26e35-114">**Select** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="26e35-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="26e35-115">**Encabezado**: Cordebug. idl, Cordebug. h</span><span class="sxs-lookup"><span data-stu-id="26e35-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="26e35-116">**Biblioteca** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="26e35-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="26e35-117">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="26e35-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="26e35-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="26e35-118">See also</span></span>

- [<span data-ttu-id="26e35-119">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="26e35-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
