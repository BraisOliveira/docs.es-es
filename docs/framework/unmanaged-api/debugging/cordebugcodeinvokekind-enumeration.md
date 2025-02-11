---
title: Enumeración CorDebugCodeInvokeKind
ms.date: 03/30/2017
api_name:
- CorDebugCodeInvokeKind
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: e795e6a2-1008-4a81-af88-d777888e942e
topic_type:
- apiref
ms.openlocfilehash: cc839e9b2a28dc428ae7cc87c9d080c4b7612a9d
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73098875"
---
# <a name="cordebugcodeinvokekind-enumeration"></a>Enumeración CorDebugCodeInvokeKind
Describe cómo una función exportada invoca a código administrado.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
typedef enum CorDebugCodeInvokeKind  
{  
    CODE_INVOKE_KIND_NONE,       
    CODE_INVOKE_KIND_RETURN,     
    CODE_INVOKE_KIND_TAILCALL,   
} CorDebugCodeInvokeKind;  
```  
  
## <a name="members"></a>Miembros  
  
|Miembro|Descripción|  
|------------|-----------------|  
|`CODE_INVOKE_KIND_NONE`|Si algún código administrado se invoca mediante este método, tendrá que encontrarse más adelante mediante eventos explícitos o puntos de interrupción.<br /><br /> O bien<br /><br /> Puede que falte parte del código administrado al que este método llama porque no hay forma fácil de detenerse en él.<br /><br /> O bien<br /><br /> El método no puede invocar nunca código administrado.|  
|`CODE_INVOKE_KIND_RETURN`|Este método llamará a código administrado mediante una instrucción de devolución. El paso a paso para salir debe llegar en el siguiente código administrado.|  
|`CODE_INVOKE_KIND_TAILCALL`|Este método invocará código administrado mediante una llamada de cola. El paso a paso y el paso a paso por procedimientos sobre instrucciones de llamada deben llegar en el código administrado.|  
  
## <a name="remarks"></a>Comentarios  
 El método [método icordebugprocess6:: GetExportStepInfo](icordebugprocess6-getexportstepinfo-method.md) usa esta enumeración para proporcionar información sobre la ejecución paso a paso a través del código administrado.  
  
> [!NOTE]
> Esta enumeración está pensada solo para su uso en escenarios de depuración .NET Native.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Enumeraciones de depuración](debugging-enumerations.md)
- [Depuración](index.md)
