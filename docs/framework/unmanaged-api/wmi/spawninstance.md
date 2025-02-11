---
title: Función SpawnInstance (referencia de la API no administrada)
description: La función SpawnInstance crea una nueva instancia de una clase.
ms.date: 11/06/2017
api_name:
- SpawnInstance
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- SpawnInstance
helpviewer_keywords:
- SpawnInstance function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: f93b4fbd5429ed2bdae8fb707e61df024cd8fd6e
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73107512"
---
# <a name="spawninstance-function"></a>SpawnInstance función)
Crea una instancia a partir de una clase.    
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT SpawnInstance (
   [in] int                  vFunc, 
   [in] IWbemClassObject*    ptr, 
   [in] LONG                 lFlags,
   [out] IWbemClassObject**  ppNewInstance); 
```  

## <a name="parameters"></a>Parámetros

`vFunc`  
de Este parámetro no se utiliza.

`ptr`  
de Puntero a una instancia de [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) .

`lFlags`  
[in] Reservado. Este parámetro debe ser 0.

`ppNewInstance`  
enuncia Recibe el puntero a la nueva instancia de la clase. Si se produce un error, no se devuelve un nuevo objeto y `ppNewInstance` se deja sin modificar.

## <a name="return-value"></a>Valor devuelto

Los siguientes valores devueltos por esta función se definen en el archivo de encabezado *WbemCli. h* , o bien se pueden definir como constantes en el código:

|Constante  |Valor  |Descripción  |
|---------|---------|---------|
| `WBEM_E_INCOMPLETE_CLASS` | 0x80041020 | `ptr` no es una definición de clase válida y no puede generar nuevas instancias. O bien está incompleto o no se ha registrado con la administración de Windows mediante una llamada a [PutClassWmi](putclasswmi.md). |
| `WBEM_E_OUT_OF_MEMORY` | 0x80041006 | No hay suficiente memoria disponible para completar la operación. |
| `WBEM_E_INVALID_PARAMETER` | 0x80041008 | El valor de `ppNewClass` es `null`. |
| `WBEM_S_NO_ERROR` | 0 | La llamada de función se realizó correctamente.  |
  
## <a name="remarks"></a>Comentarios

Esta función contiene una llamada al método [IWbemClassObject:: SpawnInstance](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-spawninstance) .

`ptr` debe ser una definición de clase obtenida de la administración de Windows. (Tenga en cuenta que se admite la generación de una instancia a partir de una instancia de, pero la instancia devuelta está vacía). A continuación, use esta definición de clase para crear nuevas instancias. Se requiere una llamada a la función [PutInstanceWmi](putinstancewmi.md) si desea escribir la instancia en la administración de Windows.

El nuevo objeto devuelto en `ppNewClass` se convierte automáticamente en una subclase del objeto actual. Este comportamiento no se puede invalidar. No hay ningún otro método por el que se puedan crear subclases (clases derivadas).

## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** WMINet_Utils. idl  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Vea también

- [WMI y contadores de rendimiento (referencia de la API no administrada)](index.md)
