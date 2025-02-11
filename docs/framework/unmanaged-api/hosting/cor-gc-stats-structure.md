---
title: COR_GC_STATS (Estructura)
ms.date: 03/30/2017
api_name:
- COR_GC_STATS
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- COR_GC_STATS
helpviewer_keywords:
- COR_GC_STATS structure [.NET Framework hosting]
ms.assetid: 8d4ff73e-739b-40f6-9349-359fbc99c2f9
topic_type:
- apiref
ms.openlocfilehash: 12c00ed009e0e57436a71aed256b07a58ba68a32
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73138349"
---
# <a name="cor_gc_stats-structure"></a>COR_GC_STATS (Estructura)
Proporciona estadísticas sobre el mecanismo de recolección de elementos no utilizados del Common Language Runtime (CLR).  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
typedef struct _COR_GC_STATS {  
    ULONG   Flags;   
    SIZE_T  ExplicitGCCount;  
    SIZE_T  GenCollectionsTaken[3];  
    SIZE_T  CommittedKBytes;   
    SIZE_T  ReservedKBytes;  
    SIZE_T  Gen0HeapSizeKBytes;  
    SIZE_T  Gen1HeapSizeKBytes;  
    SIZE_T  Gen2HeapSizeKBytes;  
    SIZE_T  LargeObjectHeapSizeKBytes;  
    SIZE_T  KBytesPromotedFromGen0;  
    SIZE_T  KBytesPromotedFromGen1;  
} COR_GC_STATS;  
```  
  
## <a name="members"></a>Miembros  
  
|Miembro|Descripción|  
|------------|-----------------|  
|`Flags`|Indica qué valores de campo deben calcularse y devolverse.|  
|`ExplicitGCCount`|Indica el número de recolecciones de elementos no utilizados forzadas por la solicitud externa.|  
|`GenCollectionsTaken`|Indica el número de recolecciones de elementos no utilizados realizadas para cada generación.|  
|`CommittedKBytes`|Número total de kilobytes confirmados en todos los montones.|  
|`ReservedKBytes`|Número total de kilobytes reservados en todos los montones.|  
|`Gen0HeapSizeKBytes`|Tamaño, en kilobytes, del montón de generación cero.|  
|`Gen1HeapSizeKBytes`|Tamaño, en kilobytes, del montón de generación uno.|  
|`Gen2HeapSizeKBytes`|Tamaño, en kilobytes, del montón de generación 2.|  
|`LargeObjectHeapSizeKBytes`|Tamaño, en kilobytes, del montón de objetos grandes.|  
|`KBytesPromotedFromGen0`|Tamaño, en kilobytes, de los objetos promovidos de la generación cero a la generación uno.|  
|`KBytesPromotedFromGen1`|Tamaño, en kilobytes, de los objetos promovidos de la generación de uno a la generación dos.|  
  
## <a name="remarks"></a>Comentarios  
 El método [ICLRGCManager:: getstats (](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-getstats-method.md) requiere que el campo `Flags` de la estructura `COR_GC_STATS` se establezca en uno o más valores de la enumeración [COR_GC_STAT_TYPES](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stat-types-enumeration.md) para especificar qué estadísticas se van a establecer.  
  
 En la tabla siguiente se asignan las estadísticas proporcionadas por esta estructura a los dos valores de enumeración [COR_GC_STAT_TYPES](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stat-types-enumeration.md) , `COR_GC_COUNTS` y `COR_GC_MEMORYUSAGE`.  
  
|Especificado por COR_GC_COUNTS|Especificado por COR_GC_MEMORYUSAGE|  
|----------------------------------|---------------------------------------|  
|`ExplicitGCCount`<br /><br /> `GenCollectionsTaken`|`CommittedKBytes`<br /><br /> `ReservedKBytes`<br /><br /> `Gen0HeapSizeKBytes`<br /><br /> `Gen1HeapSizeKBytes`<br /><br /> `Gen2HeapSizeKBytes`<br /><br /> `LargeObjectHeapSizeKBytes`<br /><br /> `KBytesPromotedFromGen0`<br /><br /> `KBytesPromotedFromGen1`|  
  
 A continuación se muestra un ejemplo de uso:  
  
```cpp  
COR_GC_STATS GCStats;  
GCStats.Flags = COR_GC_COUNTS | COR_GC_MEMORYUSAGE;  
pCLRGCManager->GetStats(&GCStats);  
```  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** GCHost. idl  
  
 **Biblioteca:** Se incluye como recurso en MSCorEE. dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Estructuras de hospedaje](../../../../docs/framework/unmanaged-api/hosting/hosting-structures.md)
- [Administración automática de la memoria](../../../standard/automatic-memory-management.md)
- [Recolección de elementos no utilizados](../../../standard/garbage-collection/index.md)
