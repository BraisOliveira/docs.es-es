---
title: ICorDebugDataTarget::GetPlatform (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugDataTarget.GetPlatform Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugDataTarget::GetPlatform
helpviewer_keywords:
- GetPlatform method [.NET Framework debugging]
- ICorDebugDataTarget::GetPlatform method [.NET Framework debugging]
ms.assetid: 9ee96c9d-7a3d-4129-a6cc-7675c7f2dda4
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1065c8d710ddbd6088ee0db694a43e098564e707
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67750377"
---
# <a name="icordebugdatatargetgetplatform-method"></a><span data-ttu-id="29fc8-102">ICorDebugDataTarget::GetPlatform (Método)</span><span class="sxs-lookup"><span data-stu-id="29fc8-102">ICorDebugDataTarget::GetPlatform Method</span></span>
<span data-ttu-id="29fc8-103">Proporciona información acerca de la plataforma, incluida la arquitectura de procesador y del sistema operativo, en el que se está ejecutando el proceso de destino.</span><span class="sxs-lookup"><span data-stu-id="29fc8-103">Provides information about the platform, including processor architecture and operating system, on which the target process is running.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="29fc8-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="29fc8-104">Syntax</span></span>  
  
```cpp  
HRESULT GetPlatform([out] CorDebugPlatform * pTargetPlatform);  
```  
  
## <a name="parameters"></a><span data-ttu-id="29fc8-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="29fc8-105">Parameters</span></span>  
 `pTargetPlatform`  
 <span data-ttu-id="29fc8-106">[out] Un puntero a un [CorDebugPlatformEnum](../../../../docs/framework/unmanaged-api/debugging/cordebugplatform-enumeration.md) enumeración que describe la plataforma de destino.</span><span class="sxs-lookup"><span data-stu-id="29fc8-106">[out] A pointer to a [CorDebugPlatformEnum](../../../../docs/framework/unmanaged-api/debugging/cordebugplatform-enumeration.md) enumeration that describes the target platform.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="29fc8-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="29fc8-107">Remarks</span></span>  
 <span data-ttu-id="29fc8-108">El `CorDebugPlatformEnum` se usa el valor de enumeración devuelto por la [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) interfaz para determinar los detalles del proceso de destino, como su tamaño de puntero, el diseño del espacio de direcciones, conjunto de registros, formato de instrucción, el diseño de contexto, y convenciones de llamada.</span><span class="sxs-lookup"><span data-stu-id="29fc8-108">The `CorDebugPlatformEnum` enumeration return value is used by the [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) interface to determine details of the target process such as its pointer size, address space layout, register set, instruction format, context layout, and calling conventions.</span></span>  
  
 <span data-ttu-id="29fc8-109">El `pTargetPlatform` valor puede hacer referencia a una plataforma que se está emulando para el destino en lugar de especificar el hardware real en uso.</span><span class="sxs-lookup"><span data-stu-id="29fc8-109">The `pTargetPlatform` value may refer to a platform that is being emulated for the target instead of specifying the actual hardware in use.</span></span> <span data-ttu-id="29fc8-110">Por ejemplo, debe usar un proceso que se ejecuta en el Windows en el entorno de Windows (WOW) en una edición de 64 bits del sistema operativo Windows la `CORDB_PLATFORM_WINDOWS_X86` valor de la [CorDebugPlatformEnum](../../../../docs/framework/unmanaged-api/debugging/cordebugplatform-enumeration.md) enumeración.</span><span class="sxs-lookup"><span data-stu-id="29fc8-110">For example, a process that is running in the Windows on Windows (WOW) environment on a 64-bit edition of the Windows operating system should use the `CORDB_PLATFORM_WINDOWS_X86` value of the [CorDebugPlatformEnum](../../../../docs/framework/unmanaged-api/debugging/cordebugplatform-enumeration.md) enumeration.</span></span>  
  
 <span data-ttu-id="29fc8-111">Este método debe ejecutarse correctamente.</span><span class="sxs-lookup"><span data-stu-id="29fc8-111">This method must succeed.</span></span> <span data-ttu-id="29fc8-112">Si se produce un error, la plataforma de destino es inutilizable.</span><span class="sxs-lookup"><span data-stu-id="29fc8-112">If it fails, the target platform is unusable.</span></span> <span data-ttu-id="29fc8-113">El método puede producir un error por las razones siguientes:</span><span class="sxs-lookup"><span data-stu-id="29fc8-113">The method may fail for the following reasons:</span></span>  
  
- <span data-ttu-id="29fc8-114">La plataforma que se está emulando para el destino es inutilizable.</span><span class="sxs-lookup"><span data-stu-id="29fc8-114">The platform that is being emulated for the target is unusable.</span></span>  
  
- <span data-ttu-id="29fc8-115">El hardware real de la plataforma de destino es inutilizable.</span><span class="sxs-lookup"><span data-stu-id="29fc8-115">The actual hardware on the target platform is unusable.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="29fc8-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="29fc8-116">Requirements</span></span>  
 <span data-ttu-id="29fc8-117">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="29fc8-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="29fc8-118">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="29fc8-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="29fc8-119">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="29fc8-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="29fc8-120">**Versiones de .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="29fc8-120">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="29fc8-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="29fc8-121">See also</span></span>

- [<span data-ttu-id="29fc8-122">ICorDebugDataTarget (interfaz)</span><span class="sxs-lookup"><span data-stu-id="29fc8-122">ICorDebugDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md)
- [<span data-ttu-id="29fc8-123">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="29fc8-123">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="29fc8-124">Depuración</span><span class="sxs-lookup"><span data-stu-id="29fc8-124">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
