---
title: CoreClrDebugProcInfo (Estructura)
ms.date: 03/30/2017
api_name:
- CoreClrDebugProcInfo
api_location:
- mscordbi_macx86.dll
api_type:
- COM
f1_keywords:
- CoreClrDebugProcInfo
helpviewer_keywords:
- remote debugging API [Silverlight]
- CoreClrDebugProcInfo structure
- Silverlight, remote debugging
ms.assetid: 4ddc37da-5c94-4beb-b61c-b54071c0e749
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 21fc34add4038d25d60e4728847e0d84914a14e3
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67739415"
---
# <a name="coreclrdebugprocinfo-structure"></a><span data-ttu-id="4f3f9-102">CoreClrDebugProcInfo (Estructura)</span><span class="sxs-lookup"><span data-stu-id="4f3f9-102">CoreClrDebugProcInfo Structure</span></span>
<span data-ttu-id="4f3f9-103">Representa un proceso que se ejecuta en un equipo remoto.</span><span class="sxs-lookup"><span data-stu-id="4f3f9-103">Represents a process that is running on a remote machine.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4f3f9-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4f3f9-104">Syntax</span></span>  
  
```cpp  
struct  CoreClrDebugProcInfo {  
    DWORD m_dwPID;  
    DWORD m_dwInternalID;  
    WCHAR m_wszName[256];  
};  
```  
  
## <a name="members"></a><span data-ttu-id="4f3f9-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="4f3f9-105">Members</span></span>  
  
|<span data-ttu-id="4f3f9-106">Member</span><span class="sxs-lookup"><span data-stu-id="4f3f9-106">Member</span></span>|<span data-ttu-id="4f3f9-107">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="4f3f9-107">Description</span></span>|  
|------------|-----------------|  
|`m_dwPID`|<span data-ttu-id="4f3f9-108">Identificador del proceso asignado por el sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="4f3f9-108">OS-assigned process identifier.</span></span>|  
|`m_dwInternalID`|<span data-ttu-id="4f3f9-109">Identificador del proceso asignado por el proxy de depuración remota que se ejecuta en el equipo de destino.</span><span class="sxs-lookup"><span data-stu-id="4f3f9-109">Process identifier that is assigned by the remote debugging proxy running on the target machine.</span></span> <span data-ttu-id="4f3f9-110">Este identificador se recicla con menos frecuencia que el identificador del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="4f3f9-110">This identifier recycles less often than the OS identifier.</span></span>|  
|`m_wszName`|<span data-ttu-id="4f3f9-111">Línea de comandos del proceso.</span><span class="sxs-lookup"><span data-stu-id="4f3f9-111">Command-line of the process.</span></span> <span data-ttu-id="4f3f9-112">Este miembro puede truncarse.</span><span class="sxs-lookup"><span data-stu-id="4f3f9-112">This member may be truncated.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="4f3f9-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4f3f9-113">Requirements</span></span>  
 <span data-ttu-id="4f3f9-114">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4f3f9-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4f3f9-115">**Encabezado**: CoreClrRemoteDebuggingInterfaces.h</span><span class="sxs-lookup"><span data-stu-id="4f3f9-115">**Header:** CoreClrRemoteDebuggingInterfaces.h</span></span>  
  
 <span data-ttu-id="4f3f9-116">**Library:** mscordbi_macx86.dll</span><span class="sxs-lookup"><span data-stu-id="4f3f9-116">**Library:** mscordbi_macx86.dll</span></span>  
  
 <span data-ttu-id="4f3f9-117">**Versiones de .NET framework:** 3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="4f3f9-117">**.NET Framework Versions:** 3.5 SP1</span></span>
