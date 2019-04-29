---
title: COR_PRF_GC_GENERATION (Enumeración)
ms.date: 03/30/2017
api_name:
- COR_PRF_GC_GENERATION
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_GC_GENERATION
helpviewer_keywords:
- COR_GC_GENERATION_FLAGS enumeration [.NET Framework profiling]
ms.assetid: d6ece160-26ad-4d39-abd7-05acd6f78c48
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 0178e2a7877803644bb25e6700306d7ac2ef2d4f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61775081"
---
# <a name="corprfgcgeneration-enumeration"></a><span data-ttu-id="19d85-102">COR_PRF_GC_GENERATION (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="19d85-102">COR_PRF_GC_GENERATION Enumeration</span></span>
<span data-ttu-id="19d85-103">Identifica una colección de elementos no utilizados de generación.</span><span class="sxs-lookup"><span data-stu-id="19d85-103">Identifies a garbage-collection generation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="19d85-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="19d85-104">Syntax</span></span>  
  
```  
typedef enum {  
    COR_PRF_GC_GEN_0 = 0,  
    COR_PRF_GC_GEN_1 = 1,  
    COR_PRF_GC_GEN_2 = 2,  
    COR_PRF_GC_LARGE_OBJECT_HEAP = 3  
} COR_PRF_GC_GENERATION;  
```  
  
## <a name="members"></a><span data-ttu-id="19d85-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="19d85-105">Members</span></span>  
  
|<span data-ttu-id="19d85-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="19d85-106">Member</span></span>|<span data-ttu-id="19d85-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="19d85-107">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_GC_GEN_0`|<span data-ttu-id="19d85-108">El objeto se almacena como generación 0.</span><span class="sxs-lookup"><span data-stu-id="19d85-108">The object is stored as generation 0.</span></span>|  
|`COR_PRF_GC_GEN_1`|<span data-ttu-id="19d85-109">El objeto se almacena como generación 1.</span><span class="sxs-lookup"><span data-stu-id="19d85-109">The object is stored as generation 1.</span></span>|  
|`COR_PRF_GC_GEN_2`|<span data-ttu-id="19d85-110">El objeto se almacena como generación 2.</span><span class="sxs-lookup"><span data-stu-id="19d85-110">The object is stored as generation 2.</span></span>|  
|`COR_PRF_GC_LARGE_OBJECT_HEAP`|<span data-ttu-id="19d85-111">El objeto se almacena en el montón de objetos grandes.</span><span class="sxs-lookup"><span data-stu-id="19d85-111">The object is stored in the large-object heap.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="19d85-112">Comentarios</span><span class="sxs-lookup"><span data-stu-id="19d85-112">Remarks</span></span>  
 <span data-ttu-id="19d85-113">El recolector de elementos no utilizados mejora el rendimiento de la administración de memoria dividiendo los objetos en las generaciones según la edad.</span><span class="sxs-lookup"><span data-stu-id="19d85-113">The garbage collector improves memory management performance by dividing objects into generations based on age.</span></span> <span data-ttu-id="19d85-114">El recolector de elementos no utilizados utiliza actualmente tres generaciones, numeradas de 0, 1 y 2, además de un segmento de montón especial que se usa para los objetos grandes.</span><span class="sxs-lookup"><span data-stu-id="19d85-114">The garbage collector currently uses three generations, numbered 0, 1, and 2, plus a special heap segment that is used for large objects.</span></span> <span data-ttu-id="19d85-115">Los objetos cuyo tamaño es mayor que un valor determinado se almacenan en el montón de objetos grandes.</span><span class="sxs-lookup"><span data-stu-id="19d85-115">Objects whose size is larger than a particular value are stored in the large-object heap.</span></span> <span data-ttu-id="19d85-116">Para empezar otros objetos asignados que pertenecen a la generación 0.</span><span class="sxs-lookup"><span data-stu-id="19d85-116">Other allocated objects start out belonging to generation 0.</span></span> <span data-ttu-id="19d85-117">Todos los objetos que existen después de que se produce una recolección en la generación 0 se promueven a la generación 1.</span><span class="sxs-lookup"><span data-stu-id="19d85-117">All objects that exist after garbage collection occurs in generation 0 are promoted to generation 1.</span></span> <span data-ttu-id="19d85-118">Mueven los objetos que existen después de que se produce una recolección de generación 1 a la generación 2.</span><span class="sxs-lookup"><span data-stu-id="19d85-118">Objects that exist after garbage collection occurs in generation 1 move into generation 2.</span></span>  
  
 <span data-ttu-id="19d85-119">El uso de las generaciones significa que el recolector de elementos no utilizados tiene que trabajar con solo un subconjunto de los objetos asignados en cualquier momento.</span><span class="sxs-lookup"><span data-stu-id="19d85-119">The use of generations means that the garbage collector has to work with only a subset of the allocated objects at any one time.</span></span>  
  
 <span data-ttu-id="19d85-120">El `COR_PRF_GC_GENERATION` enumeración la utiliza el [COR_PRF_GC_GENERATION_RANGE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-generation-range-structure.md) estructura.</span><span class="sxs-lookup"><span data-stu-id="19d85-120">The `COR_PRF_GC_GENERATION` enumeration is used by the [COR_PRF_GC_GENERATION_RANGE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-generation-range-structure.md) structure.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="19d85-121">Requisitos</span><span class="sxs-lookup"><span data-stu-id="19d85-121">Requirements</span></span>  
 <span data-ttu-id="19d85-122">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="19d85-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="19d85-123">**Encabezado**: CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="19d85-123">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="19d85-124">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="19d85-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="19d85-125">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="19d85-125">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="19d85-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="19d85-126">See also</span></span>

- [<span data-ttu-id="19d85-127">Enumeraciones para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="19d85-127">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
