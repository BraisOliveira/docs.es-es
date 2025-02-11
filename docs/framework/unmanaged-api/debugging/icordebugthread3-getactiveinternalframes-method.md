---
title: ICorDebugThread3::GetActiveInternalFrames (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugThread3.GetActiveInternalFrames Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread3::GetActiveInternalFrames
helpviewer_keywords:
- ICorDebugThread3::GetActiveInternalFrames method [.NET Framework debugging]
- GetActiveInternalFrames method [.NET Framework debugging]
ms.assetid: d69796b4-5b6d-457c-85f6-2cf42e8a8773
topic_type:
- apiref
ms.openlocfilehash: b4f228d55c9ffd6b85ebd0b430a7f5db404320f6
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73124348"
---
# <a name="icordebugthread3getactiveinternalframes-method"></a>ICorDebugThread3::GetActiveInternalFrames (Método)
Devuelve una matriz de Marcos internos (objetos[ICorDebugInternalFrame2](../../../../docs/framework/unmanaged-api/debugging/icordebuginternalframe2-interface.md) ) en la pila.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp 
HRESULT GetActiveInternalFrames  
      (  
      [in] ULONG32 cInternalFrames,  
      [out] ULONG32 *pcInternalFrames,  
      [in, out,size_is(cInternalFrames), length_is(*pcInternalFrames)]  
            ICorDebugInternalFrame2 * ppInternalFrames[]  
      );  
```  
  
## <a name="parameters"></a>Parámetros  
 `cInternalFrames`  
 de Número de fotogramas internos esperados en `ppInternalFrames`.  
  
 `pcInternalFrames`  
 enuncia Puntero a una `ULONG32` que contiene el número de Marcos internos de la pila.  
  
 `ppInternalFrames`  
 [in, out] Puntero a la dirección de una matriz de Marcos internos de la pila.  
  
## <a name="return-value"></a>Valor devuelto  
 Este método devuelve los siguientes HRESULT específicos y los errores HRESULT que indican un error del método.  
  
|HRESULT|Descripción|  
|-------------|-----------------|  
|S_OK|El objeto [ICorDebugInternalFrame2](../../../../docs/framework/unmanaged-api/debugging/icordebuginternalframe2-interface.md) se ha creado correctamente.|  
|E_INVALIDARG|`cInternalFrames` no es cero y `ppInternalFrames` es `null`o `pcInternalFrames` es `null`.|  
|HRESULT_FROM_WIN32(ERROR_INSUFFICIENT_BUFFER)|`ppInternalFrames` es menor que el número de Marcos internos.|  
  
## <a name="exceptions"></a>Excepciones  
  
## <a name="remarks"></a>Comentarios  
 Los marcos internos son estructuras de datos insertadas en la pila por el motor en tiempo de ejecución para almacenar datos temporales.  
  
 Cuando llame por primera vez a `GetActiveInternalFrames`, debe establecer el parámetro `cInternalFrames` en 0 (cero) y el parámetro `ppInternalFrames` en NULL. Cuando `GetActiveInternalFrames` devuelve primero, `pcInternalFrames` contiene el recuento de los marcos internos en la pila.  
  
 a continuación, se debe llamar a `GetActiveInternalFrames` por segunda vez. Debe pasar el recuento adecuado (`pcInternalFrames`) en el parámetro `cInternalFrames` y especificar un puntero a una matriz de tamaño adecuado en `ppInternalFrames`.  
  
 Use el método [ICorDebugStackWalk:: GetFrame](../../../../docs/framework/unmanaged-api/debugging/icordebugthread3-getactiveinternalframes-method.md) para devolver los marcos de pila reales.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Interfaces de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [Depuración](../../../../docs/framework/unmanaged-api/debugging/index.md)
