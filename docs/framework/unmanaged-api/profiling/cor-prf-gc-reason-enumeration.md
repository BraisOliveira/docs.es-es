---
title: COR_PRF_GC_REASON (Enumeración)
ms.date: 03/30/2017
api_name:
- COR_PRF_GC_REASON
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_GC_REASON
helpviewer_keywords:
- COR_PRF_GC_REASON enumeration [.NET Framework profiling]
ms.assetid: 72822b95-a7fb-485e-9d55-1cb016d9a458
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: daf97f25b1adc30b173fcd81812a4b197915cdd1
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59196949"
---
# <a name="corprfgcreason-enumeration"></a><span data-ttu-id="8ccf3-102">COR_PRF_GC_REASON (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="8ccf3-102">COR_PRF_GC_REASON Enumeration</span></span>
<span data-ttu-id="8ccf3-103">Indica el motivo por el que se está produciendo la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="8ccf3-103">Indicates the reason that garbage collection is occurring.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8ccf3-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8ccf3-104">Syntax</span></span>  
  
```  
typedef enum {  
    COR_PRF_GC_INDUCED = 1,  
    COR_PRF_GC_OTHER = 0  
} COR_PRF_GC_REASON;  
```  
  
## <a name="members"></a><span data-ttu-id="8ccf3-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="8ccf3-105">Members</span></span>  
  
|<span data-ttu-id="8ccf3-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="8ccf3-106">Member</span></span>|<span data-ttu-id="8ccf3-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="8ccf3-107">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_GC_INDUCED`|<span data-ttu-id="8ccf3-108">Indujo la recolección de elementos mediante un <xref:System.GC.Collect%2A> método.</span><span class="sxs-lookup"><span data-stu-id="8ccf3-108">The garbage collection was induced by a <xref:System.GC.Collect%2A> method.</span></span>|  
|`COR_PRF_GC_OTHER`|<span data-ttu-id="8ccf3-109">No se especifica el motivo.</span><span class="sxs-lookup"><span data-stu-id="8ccf3-109">The reason is unspecified.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="8ccf3-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8ccf3-110">Requirements</span></span>  
 <span data-ttu-id="8ccf3-111">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8ccf3-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8ccf3-112">**Encabezado**: CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="8ccf3-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="8ccf3-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8ccf3-113">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="8ccf3-114">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="8ccf3-114">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="8ccf3-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="8ccf3-115">See also</span></span>

- [<span data-ttu-id="8ccf3-116">Enumeraciones para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="8ccf3-116">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
