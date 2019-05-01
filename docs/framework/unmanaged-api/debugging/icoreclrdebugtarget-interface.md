---
title: ICoreClrDebugTarget (Interfaz)
ms.date: 03/30/2017
api_name:
- ICoreClrDebugTarget
api_location:
- mscordbi_macx86.dll
api_type:
- COM
f1_keywords:
- ICoreClrDebugTarget
helpviewer_keywords:
- remote debugging API [Silverlight]
- ICorClrDebugTarget interface
- Silverlight, remote debugging
ms.assetid: 7cfaee76-e284-4a66-a431-8e33f0f60038
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2972b87b2d0136f182f8e8223988953e1896f2bd
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61986692"
---
# <a name="icoreclrdebugtarget-interface"></a><span data-ttu-id="21ec6-102">ICoreClrDebugTarget (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="21ec6-102">ICoreClrDebugTarget Interface</span></span>
<span data-ttu-id="21ec6-103">Proporciona métodos que controlan los recuentos de referencias, enumerar procesos y liberen la memoria asociada con un depurador que se adjunta a un destino remoto de Silverlight de Macintosh.</span><span class="sxs-lookup"><span data-stu-id="21ec6-103">Provides methods that control reference counts, enumerate processes, and free the memory associated with a debugger that is attached to a remote Macintosh Silverlight target.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="21ec6-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="21ec6-104">Syntax</span></span>  
  
```  
class ICoreClrDebugTarget {  
      HRESULT EnumProcesses (  
          [out] DWORD*                    pcProcs,  
          [out] CoreClrDebugProcInfo**    ppProcs  
      );  
  
      HRESULT EnumRuntimes (  
      [in]  DWORD                      dwInternalProcessID,  
      [out] DWORD*                     pcRuntimes,  
      [out] CoreClrDebugRuntimeInfo**  ppRuntimes  
      );  
  
      void FreeMemory (  
      [in] void*      pMemory  
    );  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="21ec6-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="21ec6-105">Methods</span></span>  
  
|<span data-ttu-id="21ec6-106">Método</span><span class="sxs-lookup"><span data-stu-id="21ec6-106">Method</span></span>|<span data-ttu-id="21ec6-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="21ec6-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="21ec6-108">ICoreClrDebugTarget::EnumProcesses (método)</span><span class="sxs-lookup"><span data-stu-id="21ec6-108">ICoreClrDebugTarget::EnumProcesses Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-enumprocesses-method.md)|<span data-ttu-id="21ec6-109">Enumera los procesos que se ejecutan en un equipo remoto.</span><span class="sxs-lookup"><span data-stu-id="21ec6-109">Enumerates the processes that are running on a remote computer.</span></span>|  
|[<span data-ttu-id="21ec6-110">ICoreClrDebugTarget::EnumRuntimes (método)</span><span class="sxs-lookup"><span data-stu-id="21ec6-110">ICoreClrDebugTarget::EnumRuntimes Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-enumruntimes-method.md)|<span data-ttu-id="21ec6-111">Enumera los common language Runtime (CLR) en el proceso especificado en un equipo remoto.</span><span class="sxs-lookup"><span data-stu-id="21ec6-111">Enumerates the common language runtimes (CLRs) in the specified process on a remote computer.</span></span>|  
|[<span data-ttu-id="21ec6-112">ICoreClrDebugTarget::FreeMemory (método)</span><span class="sxs-lookup"><span data-stu-id="21ec6-112">ICoreClrDebugTarget::FreeMemory Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-freememory-method.md)|<span data-ttu-id="21ec6-113">Libera la memoria asignada por los métodos de enumeración de esta clase.</span><span class="sxs-lookup"><span data-stu-id="21ec6-113">Frees the memory that is allocated by the enumeration methods in this class.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="21ec6-114">Comentarios</span><span class="sxs-lookup"><span data-stu-id="21ec6-114">Remarks</span></span>  
 <span data-ttu-id="21ec6-115">Actualmente, esta funcionalidad solo se admite para la depuración de un destino de la aplicación basada en Silverlight que se ejecuta en un equipo remoto de Macintosh.</span><span class="sxs-lookup"><span data-stu-id="21ec6-115">Currently, this functionality is supported only for debugging a Silverlight-based application target that is running on a remote Macintosh computer.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="21ec6-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="21ec6-116">Requirements</span></span>  
 <span data-ttu-id="21ec6-117">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="21ec6-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="21ec6-118">**Encabezado**: CoreClrRemoteDebuggingInterfaces.h</span><span class="sxs-lookup"><span data-stu-id="21ec6-118">**Header:** CoreClrRemoteDebuggingInterfaces.h</span></span>  
  
 <span data-ttu-id="21ec6-119">**Library:** mscordbi_macx86.dll</span><span class="sxs-lookup"><span data-stu-id="21ec6-119">**Library:** mscordbi_macx86.dll</span></span>  
  
 <span data-ttu-id="21ec6-120">**Versiones de .NET framework:** 3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="21ec6-120">**.NET Framework Versions:** 3.5 SP1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="21ec6-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="21ec6-121">See also</span></span>

- [<span data-ttu-id="21ec6-122">ICorDebugRemoteTarget (interfaz)</span><span class="sxs-lookup"><span data-stu-id="21ec6-122">ICorDebugRemoteTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugremotetarget-interface.md)
- [<span data-ttu-id="21ec6-123">ICorDebug (interfaz)</span><span class="sxs-lookup"><span data-stu-id="21ec6-123">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)

- [<span data-ttu-id="21ec6-124">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="21ec6-124">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
