---
title: CorDebugMappingResult (Enumeración)
ms.date: 03/30/2017
api_name:
- CorDebugMappingResult
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugMappingResult
helpviewer_keywords:
- CorDebugMappingResult enumeration [.NET Framework debugging]
ms.assetid: 701281dd-2936-45c8-a1f0-3bf7332b093b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c2fecc7160cb41e31bf88f1a461265ad8fdce166
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61792709"
---
# <a name="cordebugmappingresult-enumeration"></a><span data-ttu-id="24208-102">CorDebugMappingResult (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="24208-102">CorDebugMappingResult Enumeration</span></span>
<span data-ttu-id="24208-103">Proporciona información detallada sobre cómo se obtuvo el valor del puntero de instrucción (IP).</span><span class="sxs-lookup"><span data-stu-id="24208-103">Provides the details of how the value of the instruction pointer (IP) was obtained.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="24208-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="24208-104">Syntax</span></span>  
  
```  
typedef enum CorDebugMappingResult {  
    MAPPING_PROLOG              = 0x1,  
    MAPPING_EPILOG              = 0x2,  
    MAPPING_NO_INFO             = 0x4,  
    MAPPING_UNMAPPED_ADDRESS    = 0x8,  
    MAPPING_EXACT               = 0x10,  
    MAPPING_APPROXIMATE         = 0x20,  
} CorDebugMappingResult;  
```  
  
## <a name="members"></a><span data-ttu-id="24208-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="24208-105">Members</span></span>  
  
|<span data-ttu-id="24208-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="24208-106">Member</span></span>|<span data-ttu-id="24208-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="24208-107">Description</span></span>|  
|------------|-----------------|  
|`MAPPING_PROLOG`|<span data-ttu-id="24208-108">El código nativo está en el prólogo, por lo que el valor de la dirección IP es 0.</span><span class="sxs-lookup"><span data-stu-id="24208-108">The native code is in the prolog, so the value of the IP is 0.</span></span>|  
|`MAPPING_EPILOG`|<span data-ttu-id="24208-109">El código nativo está en un epílogo, por lo que el valor de la dirección IP es la dirección de la última instrucción del método.</span><span class="sxs-lookup"><span data-stu-id="24208-109">The native code is in an epilog, so the value of the IP is the address of the last instruction of the method.</span></span>|  
|`MAPPING_NO_INFO`|<span data-ttu-id="24208-110">No hay información de asignación está disponible para el método, por lo que el valor de la dirección IP es 0.</span><span class="sxs-lookup"><span data-stu-id="24208-110">No mapping information is available for the method, so the value of the IP is 0.</span></span>|  
|`MAPPING_UNMAPPED_ADDRESS`|<span data-ttu-id="24208-111">Aunque no hay información de asignación para el método, no se puede asignar la dirección actual al código de lenguaje intermedio (MSIL) de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="24208-111">Although there is mapping information for the method, the current address cannot be mapped to Microsoft intermediate language (MSIL) code.</span></span> <span data-ttu-id="24208-112">El valor de la dirección IP es 0.</span><span class="sxs-lookup"><span data-stu-id="24208-112">The value of the IP is 0.</span></span>|  
|`MAPPING_EXACT`|<span data-ttu-id="24208-113">El método se asigna exactamente a código MSIL o interpreta el marco, por lo que el valor de la dirección IP es preciso.</span><span class="sxs-lookup"><span data-stu-id="24208-113">Either the method maps exactly to MSIL code or the frame has been interpreted, so the value of the IP is accurate.</span></span>|  
|`MAPPING_APPROXIMATE`|<span data-ttu-id="24208-114">El método se ha asignado correctamente, pero el valor de la dirección IP puede ser aproximado.</span><span class="sxs-lookup"><span data-stu-id="24208-114">The method was successfully mapped, but the value of the IP may be approximate.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="24208-115">Comentarios</span><span class="sxs-lookup"><span data-stu-id="24208-115">Remarks</span></span>  
 <span data-ttu-id="24208-116">Puede usar el [ICorDebugILFrame:: GetIP](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getip-method.md) método para obtener el valor del puntero de instrucción.</span><span class="sxs-lookup"><span data-stu-id="24208-116">You can use the [ICorDebugILFrame::GetIP](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getip-method.md) method to obtain the value of the instruction pointer.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="24208-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="24208-117">Requirements</span></span>  
 <span data-ttu-id="24208-118">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="24208-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="24208-119">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="24208-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="24208-120">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="24208-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="24208-121">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="24208-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="24208-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="24208-122">See also</span></span>

- [<span data-ttu-id="24208-123">Enumeraciones de depuración</span><span class="sxs-lookup"><span data-stu-id="24208-123">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
