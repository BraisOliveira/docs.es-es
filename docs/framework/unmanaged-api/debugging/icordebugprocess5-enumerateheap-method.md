---
title: ICorDebugProcess5::EnumerateHeap (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugProcess5.EnumerateHeap
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess5::EnumerateHeap
helpviewer_keywords:
- EnumerateHeap method, ICorDebugProcess5 interface [.NET Framework debugging]
- ICorDebugProcess5::EnumerateHeap method [.NET Framework debugging]
ms.assetid: b0192104-6073-4089-a4df-dc29ee033074
topic_type:
- apiref
ms.openlocfilehash: c8cfc9cdf6580a002f6ac15080012a9e8c63be20
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129647"
---
# <a name="icordebugprocess5enumerateheap-method"></a>ICorDebugProcess5::EnumerateHeap (Método)
Obtiene un enumerador para los objetos en el montón administrado.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT EnumerateHeap(  
    [out] ICorDebugHeapEnum **ppObjects  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `ppObject`  
 enuncia Puntero a la dirección de un objeto de interfaz [icordebugheapenum (](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-interface.md) que es un enumerador para los objetos que residen en el montón administrado.  
  
## <a name="remarks"></a>Comentarios  
 Antes de llamar al método `ICorDebugProcess5::EnumerateHeap`, debe llamar al método [ICorDebugProcess5:: getgcheapinformation (](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-getgcheapinformation-method.md) y examinar el valor del campo `areGCStructuresValid` del objeto [COR_HEAPINFO](../../../../docs/framework/unmanaged-api/debugging/cor-heapinfo-structure.md) devuelto para asegurarse de que el montón de recolección de elementos no utilizados en su el estado actual es Enumerable. Además, el `ICorDebugProcess5::EnumerateHeap` devuelve `E_FAIL` si se adjunta demasiado pronto en la duración del proceso, antes de que se asigne la memoria para el montón administrado.  
  
 El objeto de interfaz [icordebugheapenum (](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-interface.md) es un enumerador estándar derivado de la interfaz ICorDebugEnum que le permite enumerar objetos [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) . Este método rellena el objeto de colección [icordebugheapenum (](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-interface.md) con instancias [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) que proporcionan información acerca de todos los objetos. La colección también puede incluir instancias de [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) que proporcionan información sobre los objetos que no están raíz de ningún objeto pero que el recolector de elementos no utilizados aún no ha recopilado.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorDebugProcess5 (interfaz)](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md)
- [Interfaces de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
