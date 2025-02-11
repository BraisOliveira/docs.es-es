---
title: WriteableMetadataUpdateMode (Enumeración)
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- WriteableMetadataUpdateMode
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 6758f4d3-6bc7-4c99-8582-e9be00566784
topic_type:
- apiref
ms.openlocfilehash: 98566176ff33000fc4b4587b5669a037c90268f5
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73139106"
---
# <a name="writeablemetadataupdatemode-enumeration"></a>WriteableMetadataUpdateMode (Enumeración)
[Compatible con .NET Framework 4.5.2 y versiones posteriores]  
  
 Proporciona valores que especifican si las actualizaciones en memoria de los metadatos son visibles para un depurador.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp
typedef enum WriteableMetadataUpdateMode {  
   LegacyCompatPolicy,  
   AlwaysShowUpdates  
} WriteableMetadataUpdateMode;  
```  
  
## <a name="members"></a>Miembros  
  
|Nombre de miembro|Descripción|  
|-----------------|-----------------|  
|`LegacyCompatPolicy`|Mantiene la compatibilidad con versiones anteriores de .NET Framework al hacer que las actualizaciones en memoria de los metadatos sean visibles. Vea la sección Comentarios para obtener más información.|  
|`AlwaysShowUpdates`|Hace que las actualizaciones en memoria de los metadatos sean visibles para el depurador.|  
  
## <a name="remarks"></a>Comentarios  
 Un miembro de la enumeración `WriteableMetadataUpdateMode` se puede pasar al método [setwriteablemetadataupdatemode (](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess7-setwriteablemetadataupdatemode-method.md) para controlar si las actualizaciones en memoria de los metadatos en el proceso de destino son visibles para el depurador.  
  
 La opción `LegacyCompatPolicy` aplica el mismo comportamiento que en las versiones de .NET Framework anteriores a la 4.5.2. Esto suele significar que los metadatos de las actualizaciones no son visibles. Sin embargo, las llamadas a varios métodos de depuración obligan implícitamente al depurador a hacer las actualizaciones visibles. Por ejemplo, si el depurador pasa [ICorDebugILFrame:: getlocalvariable (](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getlocalvariable-method.md) , el índice de una variable no se encuentra en los metadatos originales del método, todos los metadatos del módulo se actualizan a una instantánea que coincide con el estado actual del proceso. En otras palabras, con la opción `LegacyCompatPolicy`, el depurador podría ver ninguna, algunas o todas las actualizaciones de metadatos disponibles, según cómo use otras partes de la API de depuración no administrada.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Enumeraciones de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
- [SetWriteableMetadataUpdateMode (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess7-setwriteablemetadataupdatemode-method.md)
