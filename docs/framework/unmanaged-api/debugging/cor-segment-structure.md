---
title: COR_SEGMENT (Estructura)
ms.date: 03/30/2017
api_name:
- COR_SEGMENT
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- COR_SEGMENT
helpviewer_keywords:
- COR_SEGMENT structure [.NET Framework debugging]
ms.assetid: 93aeecb9-7fef-4545-8daf-f566dfc47084
topic_type:
- apiref
ms.openlocfilehash: 0370c74bde9ca5bdbd0fd03515f4b174ddd0a39a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132320"
---
# <a name="cor_segment-structure"></a>COR_SEGMENT (Estructura)
Contiene información sobre una región de memoria en el montón administrado.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
typedef struct _COR_SEGMENT {  
    CORDB_ADDRESS start;            
    CORDB_ADDRESS end;              
    CorDebugGenerationTypes gen;    
    ULONG heap;                     
} COR_SEGMENT;  
```  
  
## <a name="members"></a>Miembros  
  
|Miembro|Descripción|  
|------------|-----------------|  
|`start`|La dirección de inicio de la región de memoria.|  
|`end`|La dirección final de la región de memoria.|  
|`gen`|Un miembro de la enumeración [CorDebugGenerationTypes](cordebuggenerationtypes-enumeration.md) que indica la generación de la región de memoria.|  
|`heap`|El número de montón en el que reside la región de memoria. Vea la sección Comentarios para obtener más información.|  
  
## <a name="remarks"></a>Comentarios  
 La estructura `COR_SEGMENTS` representa una región de memoria en el montón administrado.  Los objetos `COR_SEGMENTS` son miembros del objeto de colección [ICorDebugHeapRegionEnum](icordebugheapsegmentenum-interface.md), que se rellena mediante una llamada al método [ICorDebugProcess5::EnumerateHeapRegions](icordebugprocess5-enumerateheapregions-method.md).  
  
 El campo `heap` es el número de procesador, que se corresponde con el montón que se va a notificar. Para los recolectores de elementos no utilizados de la estación de trabajo, su valor siempre es cero, porque las estaciones de trabajo tienen solo un montón de recolección de elementos no utilizados. Para los recolectores de elementos no utilizados de servidor, su valor se corresponde con el procesador al que está vinculado el montón. Tenga en cuenta que podría haber más o menos montones de recolección de elementos no utilizados que procesadores reales debido a los detalles de implementación del recolector de elementos no utilizados.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Estructuras de depuración](debugging-structures.md)
- [Depuración](index.md)
