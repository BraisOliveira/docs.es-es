---
title: Función get (referencia de la API no administrada)
description: La función get recupera el valor de propiedad especificado.
ms.date: 11/06/2017
api_name:
- Get
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- Get
helpviewer_keywords:
- Get function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: 60f29b91000fd3c07efea88dcc319eb283a4af78
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73120320"
---
# <a name="get-function"></a>Función Get

Recupera el valor de propiedad especificado si existe.

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a>Sintaxis

```cpp
HRESULT Get (
   [in] int               vFunc, 
   [in] IWbemClassObject* ptr, 
   [in] LPCWSTR           wszName,
   [in] LONG              lFlags,
   [out] VARIANT*         pVal,
   [out] CIMTYPE*         pvtType,
   [out] LONG*            plFlavor
); 
```

## <a name="parameters"></a>Parámetros

`vFunc`\
de Este parámetro no se utiliza.

`ptr`\
de Puntero a una instancia de [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) .

`wszName`\
de Nombre de la propiedad.

`lFlags`\
[in] Reservado. Este parámetro debe ser 0.

`pVal`\
enuncia Si la función se devuelve correctamente, contiene el valor de la propiedad `wszName`. Al argumento `pval` se le asigna el tipo y el valor correctos para el calificador.

`pvtType`\
enuncia Si la función se devuelve correctamente, contiene una [constante de tipo CIM](/windows/win32/api/wbemcli/ne-wbemcli-cimtype_enumeration) que indica el tipo de propiedad. Su valor también se puede `null`. 

`plFlavor`\
enuncia Si la función se devuelve correctamente, recibe información sobre el origen de la propiedad. Su valor puede ser `null`o una de las siguientes constantes WBEM_FLAVOR_TYPE definidas en el archivo de encabezado *WbemCli. h* : 

|Constante  |Valor  |Descripción  |
|---------|---------|---------|
| `WBEM_FLAVOR_ORIGIN_SYSTEM` | 0x40 | La propiedad es una propiedad estándar del sistema. |
| `WBEM_FLAVOR_ORIGIN_PROPAGATED` | 0x20 | Para una clase: la propiedad se hereda de la clase primaria. <br> Para una instancia: la propiedad, mientras que se hereda de la clase primaria, no ha sido modificada por la instancia de.  |
| `WBEM_FLAVOR_ORIGIN_LOCAL` | 0 | Para una clase: la propiedad pertenece a la clase derivada. <br> Para una instancia de: la propiedad es modificada por la instancia de; es decir, se ha proporcionado un valor o se ha agregado o modificado un calificador. |

## <a name="return-value"></a>Valor devuelto

Los siguientes valores devueltos por esta función se definen en el archivo de encabezado *WbemCli. h* , o bien se pueden definir como constantes en el código:

|Constante  |Valor  |Descripción  |
|---------|---------|---------|
|`WBEM_E_FAILED` | 0x80041001 | Se ha producido un error general. |
|`WBEM_E_INVALID_PARAMETER` | 0x80041008 | Uno o más parámetros no son válidos. |
|`WBEM_E_NOT_FOUND` | 0x80041002 | No se encontró la propiedad especificada. |
|`WBEM_E_OUT_OF_MEMORY` | 0x80041006 | No hay suficiente memoria disponible para completar la operación. |
|`WBEM_S_NO_ERROR` | 0 | La llamada de función se realizó correctamente.  |

## <a name="remarks"></a>Comentarios

Esta función contiene una llamada al método [IWbemClassObject:: get](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-get) .

La función `Get` también puede devolver propiedades del sistema.

Al argumento `pVal` se le asigna el tipo y el valor correctos para el calificador y la función [VariantInit](https://docs.microsoft.com/previous-versions/windows/desktop/api/oleauto/nf-oleauto-variantinit) de com.

## <a name="requirements"></a>Requisitos

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).

 **Encabezado:** WMINet_Utils. idl

 **Versiones de .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]

## <a name="see-also"></a>Vea también

- [WMI y contadores de rendimiento (referencia de la API no administrada)](index.md)
