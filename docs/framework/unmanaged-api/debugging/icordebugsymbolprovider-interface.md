---
title: Interfaz ICorDebugSymbolProvider
ms.date: 03/30/2017
ms.assetid: 85b24196-b6c6-4bda-9de3-47180bd6ff96
ms.openlocfilehash: fb947fec8f17fe13374251b4429be798a335eed6
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133662"
---
# <a name="icordebugsymbolprovider-interface"></a>Interfaz ICorDebugSymbolProvider
Proporciona métodos que pueden utilizarse para recuperar información de símbolos de depuración.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[GetAssemblyImageBytes (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-getassemblyimagebytes-method.md)|Lee datos de un ensamblado combinado a partir de una dirección virtual relativa (RVA) del ensamblado combinado.|  
|[GetAssemblyImageMetadata (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-getassemblyimagemetadata-method.md)|Devuelve los metadatos desde un ensamblado combinado.|  
|[GetCodeRange (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-getcoderange-method.md)|Obtiene el tamaño y la dirección de inicio del método a partir de una dirección virtual relativa (RVA) en un método.|  
|[GetInstanceFieldSymbols (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-getinstancefieldsymbols-method.md)|Obtiene los símbolos de campo de instancia que corresponden a una firma Typespec.|  
|[GetMergedAssemblyRecords (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-getmergedassemblyrecords-method.md)|Obtiene los registros de símbolos para todos los ensamblados combinados.|  
|[GetMethodLocalSymbols (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-getmethodlocalsymbols-method.md)|Obtiene los símbolos locales del método a partir de la dirección virtual relativa (RVA) de ese método.|  
|[GetMethodParameterSymbols (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-getmethodparametersymbols-method.md)|Obtiene los símbolos de parámetro del método a partir de la dirección virtual relativa (RVA) de ese método.|  
|[GetMethodProps (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-getmethodprops-method.md)|Devuelve información acerca de las propiedades del método, como el token de metadatos del método e información acerca de sus parámetros genéricos, a partir de una dirección virtual relativa (RVA) en ese método.|  
|[GetObjectSize (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-getobjectsize-method.md)|Devuelve el tamaño del objeto para un objeto basado en su firma Typespec.|  
|[GetStaticFieldSymbols (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-getstaticfieldsymbols-method.md)|Obtiene los símbolos de campo estáticos que corresponden a una firma Typespec.|  
|[GetTypeProps (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-gettypeprops-method.md)|Devuelve información acerca de las propiedades de un tipo, como el número de firmas de sus parámetros genéricos, dada una dirección virtual relativa (RVA) en una tabla virtual.|  
  
## <a name="remarks"></a>Comentarios  
  
> [!NOTE]
> Esta interfaz solo está disponible con .NET Native. Si implementa esta interfaz para escenarios de ICorDebug fuera de .NET Native, Common Language Runtime ignorará esta interfaz.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Interfaces de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [Depuración](../../../../docs/framework/unmanaged-api/debugging/index.md)
