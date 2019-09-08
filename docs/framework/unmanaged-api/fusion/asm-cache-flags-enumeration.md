---
title: ASM_CACHE_FLAGS (Enumeración)
ms.date: 03/30/2017
api_name:
- ASM_CACHE_FLAGS
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- ASM_CACHE_FLAGS
helpviewer_keywords:
- ASM_CACHE_FLAGS enumeration [.NET Framework fusion]
ms.assetid: 82e9a7da-321b-48b8-b239-52eaffda6be8
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0e3e9da3db71d3e24b2a60ff032a631680055b88
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70795275"
---
# <a name="asm_cache_flags-enumeration"></a><span data-ttu-id="715f2-102">ASM_CACHE_FLAGS (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="715f2-102">ASM_CACHE_FLAGS Enumeration</span></span>
<span data-ttu-id="715f2-103">Indica el origen de un ensamblado representado por [IAssemblyCacheItem](iassemblycacheitem-interface.md) en la caché global de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="715f2-103">Indicates the source of an assembly that is represented by [IAssemblyCacheItem](iassemblycacheitem-interface.md) in the global assembly cache.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="715f2-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="715f2-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    ASM_CACHE_ZAP       = 0x01,  
    ASM_CACHE_GAC       = 0x02,  
    ASM_CACHE_DOWNLOAD  = 0x04,  
    ASM_CACHE_ROOT      = 0x08,  
    ASM_CACHE_ROOT_EX   = 0x80  
} ASM_CACHE_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="715f2-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="715f2-105">Members</span></span>  
  
|<span data-ttu-id="715f2-106">Member</span><span class="sxs-lookup"><span data-stu-id="715f2-106">Member</span></span>|<span data-ttu-id="715f2-107">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="715f2-107">Description</span></span>|  
|------------|-----------------|  
|`ASM_CACHE_ZAP`|<span data-ttu-id="715f2-108">Enumera la memoria caché de ensamblados precompilados mediante Ngen. exe.</span><span class="sxs-lookup"><span data-stu-id="715f2-108">Enumerates the cache of precompiled assemblies by using Ngen.exe.</span></span>|  
|`ASM_CACHE_GAC`|<span data-ttu-id="715f2-109">Enumera la caché global de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="715f2-109">Enumerates the global assembly cache.</span></span>|  
|`ASM_CACHE_DOWNLOAD`|<span data-ttu-id="715f2-110">Enumera los ensamblados que se han descargado a petición o que se han copiado de la instantánea.</span><span class="sxs-lookup"><span data-stu-id="715f2-110">Enumerates the assemblies that have been downloaded on demand or that have been shadow-copied.</span></span>|  
|`ASM_CACHE_ROOT`|<span data-ttu-id="715f2-111">Indica que la función [GetCachePath (](getcachepath-function.md) debe devolver la ruta de acceso a la caché global de ensamblados para la versión 2,0 de Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="715f2-111">Indicates that the [GetCachePath](getcachepath-function.md) function should return the path to the global assembly cache for the common language runtime (CLR) version 2.0.</span></span> <span data-ttu-id="715f2-112">Solo es significativo en el contexto de una llamada a [GetCachePath (](getcachepath-function.md).</span><span class="sxs-lookup"><span data-stu-id="715f2-112">Meaningful only in the context of a call to [GetCachePath](getcachepath-function.md).</span></span>|  
|`ASM_CACHE_ROOT_EX`|<span data-ttu-id="715f2-113">Indica que la función [GetCachePath (](getcachepath-function.md) debe devolver la ruta de acceso a la caché global de ensamblados para la versión 4 de CLR.</span><span class="sxs-lookup"><span data-stu-id="715f2-113">Indicates that the [GetCachePath](getcachepath-function.md) function should return the path to the global assembly cache for CLR version 4.</span></span> <span data-ttu-id="715f2-114">Solo es significativo en el contexto de una llamada a [GetCachePath (](getcachepath-function.md).</span><span class="sxs-lookup"><span data-stu-id="715f2-114">Meaningful only in the context of a call to [GetCachePath](getcachepath-function.md).</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="715f2-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="715f2-115">Requirements</span></span>  
 <span data-ttu-id="715f2-116">**Select** Consulte [Requisitos del sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="715f2-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="715f2-117">**Encabezado**: Fusion. h</span><span class="sxs-lookup"><span data-stu-id="715f2-117">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="715f2-118">**Biblioteca** Se incluye como recurso en MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="715f2-118">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="715f2-119">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="715f2-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="715f2-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="715f2-120">See also</span></span>

- [<span data-ttu-id="715f2-121">GetCachePath (Función)</span><span class="sxs-lookup"><span data-stu-id="715f2-121">GetCachePath Function</span></span>](getcachepath-function.md)
- [<span data-ttu-id="715f2-122">IAssemblyCacheItem (interfaz)</span><span class="sxs-lookup"><span data-stu-id="715f2-122">IAssemblyCacheItem Interface</span></span>](iassemblycacheitem-interface.md)
- [<span data-ttu-id="715f2-123">Enumeraciones de fusión</span><span class="sxs-lookup"><span data-stu-id="715f2-123">Fusion Enumerations</span></span>](fusion-enumerations.md)
