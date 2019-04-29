---
title: EClrFailure (Enumeración)
ms.date: 03/30/2017
api_name:
- EClrFailure
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- EClrFailure
helpviewer_keywords:
- EClrFailure enumeration [.NET Framework hosting]
ms.assetid: 37b95cce-9bfb-4ecf-a00b-33dcba782c67
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 19dacae05766566521f563d0d24980c01dfb7a0b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61796155"
---
# <a name="eclrfailure-enumeration"></a><span data-ttu-id="4acd5-102">EClrFailure (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="4acd5-102">EClrFailure Enumeration</span></span>
<span data-ttu-id="4acd5-103">Describe el conjunto de errores para el que un host puede establecer acciones de directiva.</span><span class="sxs-lookup"><span data-stu-id="4acd5-103">Describes the set of failures for which a host can set policy actions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4acd5-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4acd5-104">Syntax</span></span>  
  
```  
typedef enum {  
    FAIL_NonCriticalResource,  
    FAIL_CriticalResource,  
    FAIL_FatalRuntime,  
    FAIL_OrphanedLock  
    FAIL_StackOverflow  
    FAIL_AccessViolation  
    FAIL_CodeContract  
} EClrFailure;  
```  
  
## <a name="members"></a><span data-ttu-id="4acd5-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="4acd5-105">Members</span></span>  
  
|<span data-ttu-id="4acd5-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="4acd5-106">Member</span></span>|<span data-ttu-id="4acd5-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="4acd5-107">Description</span></span>|  
|------------|-----------------|  
|`FAIL_NonCriticalResource`|<span data-ttu-id="4acd5-108">Error al intentar asignar un recurso (por ejemplo, un subproceso, un bloque de memoria o un bloqueo) en una región no crítica del código.</span><span class="sxs-lookup"><span data-stu-id="4acd5-108">A failure occurred during an attempt to allocate a resource (such as a thread, a block of memory, or a lock) in a non-critical region of code.</span></span>|  
|`FAIL_CriticalResource`|<span data-ttu-id="4acd5-109">Error al intentar asignar un recurso (por ejemplo, un subproceso, un bloque de memoria o un bloqueo) en una región crítica del código.</span><span class="sxs-lookup"><span data-stu-id="4acd5-109">A failure occurred during an attempt to allocate a resource (such as a thread, a block of memory, or a lock) in a critical region of code.</span></span>|  
|`FAIL_FatalRuntime`|<span data-ttu-id="4acd5-110">Common language runtime (CLR) ya no es capaz de ejecutar código administrado en el proceso.</span><span class="sxs-lookup"><span data-stu-id="4acd5-110">The common language runtime (CLR) is no longer able to run managed code in the process.</span></span> <span data-ttu-id="4acd5-111">Aquí en adelante, las llamadas a las funciones de hospedaje devuelven un valor HRESULT de HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="4acd5-111">Henceforth, calls to any hosting functions return an HRESULT value of HOST_E_CLRNOTAVAILABLE.</span></span>|  
|`FAIL_OrphanedLock`|<span data-ttu-id="4acd5-112">Un subproceso no pudo liberar un bloqueo al volver de un <xref:System.AppDomain> objeto.</span><span class="sxs-lookup"><span data-stu-id="4acd5-112">A thread has failed to release a lock upon returning from an <xref:System.AppDomain> object.</span></span> <span data-ttu-id="4acd5-113">El host no puede establecer este error para hacer que un subproceso se anule.</span><span class="sxs-lookup"><span data-stu-id="4acd5-113">The host cannot set this failure to cause a thread to abort.</span></span>|  
|`FAIL_StackOverflow`|<span data-ttu-id="4acd5-114">Se ha producido un desbordamiento de pila.</span><span class="sxs-lookup"><span data-stu-id="4acd5-114">A stack overflow has occurred.</span></span>|  
|`FAIL_AccessViolation`|<span data-ttu-id="4acd5-115">Se intentó leer o escribir en la memoria protegida.</span><span class="sxs-lookup"><span data-stu-id="4acd5-115">An attempt was made to read or write protected memory.</span></span> <span data-ttu-id="4acd5-116">No se admite en el [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4acd5-116">Not supported in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>|  
|`FAIL_CodeContract`|<span data-ttu-id="4acd5-117">Se ha producido un error de contrato de código.</span><span class="sxs-lookup"><span data-stu-id="4acd5-117">A code contract failure occurred.</span></span> <span data-ttu-id="4acd5-118">Consulte [contratos de código](../../../../docs/framework/debug-trace-profile/code-contracts.md).</span><span class="sxs-lookup"><span data-stu-id="4acd5-118">See [Code Contracts](../../../../docs/framework/debug-trace-profile/code-contracts.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4acd5-119">Comentarios</span><span class="sxs-lookup"><span data-stu-id="4acd5-119">Remarks</span></span>  
 <span data-ttu-id="4acd5-120">Consulte la [ICLRPolicyManager:: SetActionOnFailure](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactiononfailure-method.md) método para obtener una lista de [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) valores el host puede utilizar para especificar las acciones de directiva para las condiciones de error.</span><span class="sxs-lookup"><span data-stu-id="4acd5-120">See the [ICLRPolicyManager::SetActionOnFailure](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactiononfailure-method.md) method for a list of [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) values the host can use to specify the policy actions for failure conditions.</span></span> <span data-ttu-id="4acd5-121">Para obtener más información acerca de las regiones que no son críticas y de código, vea [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md).</span><span class="sxs-lookup"><span data-stu-id="4acd5-121">For more information about critical and non-critical regions of code, see [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4acd5-122">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4acd5-122">Requirements</span></span>  
 <span data-ttu-id="4acd5-123">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4acd5-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4acd5-124">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="4acd5-124">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="4acd5-125">**Biblioteca:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="4acd5-125">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4acd5-126">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4acd5-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4acd5-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="4acd5-127">See also</span></span>

- [<span data-ttu-id="4acd5-128">ICLRPolicyManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="4acd5-128">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)
- [<span data-ttu-id="4acd5-129">SetActionOnFailure (método)</span><span class="sxs-lookup"><span data-stu-id="4acd5-129">SetActionOnFailure Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactiononfailure-method.md)
- [<span data-ttu-id="4acd5-130">IHostPolicyManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="4acd5-130">IHostPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-interface.md)
- [<span data-ttu-id="4acd5-131">Enumeraciones para hosts</span><span class="sxs-lookup"><span data-stu-id="4acd5-131">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
