---
title: ICorProfilerCallback::AssemblyUnloadFinished (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.AssemblyUnloadFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::AssemblyUnloadFinished
helpviewer_keywords:
- AssemblyUnloadFinished method [.NET Framework profiling]
- ICorProfilerCallback::AssemblyUnloadFinished method [.NET Framework profiling]
ms.assetid: 53fca564-84b1-44d4-9e21-17a492d2aae7
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a75d31f0a2c844895363bb4693dbcb5aba4cce1f
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67775509"
---
# <a name="icorprofilercallbackassemblyunloadfinished-method"></a>ICorProfilerCallback::AssemblyUnloadFinished (Método)
Notifica al generador de perfiles que se ha descargado un ensamblado.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT AssemblyUnloadFinished(  
    [in] AssemblyID assemblyId,  
    [in] HRESULT    hrStatus);  
```  
  
## <a name="parameters"></a>Parámetros  
 `assemblyId`  
 [in] Identifica el ensamblado que se está descargando.  
  
 `hrStatus`  
 [in] Un HRESULT que indica si el ensamblado se descargó correctamente.  
  
## <a name="remarks"></a>Comentarios  
 El valor de `assemblyId` no es válido para una solicitud de información después de la [AssemblyUnloadStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-assemblyunloadstarted-method.md) devuelve del método.  
  
 Algunas partes de la descarga del ensamblado podrían continuar después de la `AssemblyUnloadFinished` devolución de llamada. Un error HRESULT en `hrStatus` indica un error. Sin embargo, un valor HRESULT correcto en `hrStatus` sólo indica que la primera parte de la descarga del ensamblado se ha realizado correctamente.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorProfilerCallback (interfaz)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
