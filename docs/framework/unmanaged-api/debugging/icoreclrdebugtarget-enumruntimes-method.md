---
title: ICoreClrDebugTarget::EnumRuntimes (Método)
ms.date: 03/30/2017
api_name:
- ICoreClrDebugTarget.EnumRuntimes
api_location:
- mscordbi_macx86.dll
api_type:
- COM
f1_keywords:
- ICoreClrDebugTarget::EnumRuntimes
helpviewer_keywords:
- remote debugging API [Silverlight]
- ICorClrDebugTarget::EnumRuntimes method [Silverlight debugging]
- EnumRuntimes method, ICoreClrDebugTarget interface [Silverlight debugging]
- Silverlight, remote debugging
ms.assetid: 316df866-442d-40cc-b049-45e8adcb65d1
topic_type:
- apiref
ms.openlocfilehash: 2579bed9ae432a2b9460c421c6ee5bdc40d1e149
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73121830"
---
# <a name="icoreclrdebugtargetenumruntimes-method"></a>ICoreClrDebugTarget::EnumRuntimes (Método)
Enumera los Common Language Runtime(CLR) del proceso especificado que se están ejecutando en un equipo remoto.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT EnumRuntimes (  
      [in] DWORD       dwInternalProcessID,  
      [out] DWORD*     pcRuntimes,  
      [out] CoreClrDebugRuntimeInfo**    ppRuntimes  
    );  
```  
  
## <a name="parameters"></a>Parámetros  
 `dwInternalProcessID`  
 [in] Identificador de proceso interno del proceso para el que desea enumerar los tiempos de ejecución. Se `m_dwInternalID`rá desde el [coreclrdebugprocinfo (](../../../../docs/framework/unmanaged-api/debugging/coreclrdebugprocinfo-structure.md)correspondiente.  
  
 `pcRuntimes`  
 [out] Número de tiempos de ejecución que se devuelve en `ppRuntimes`. Este valor puede ser 0 (cero).  
  
 `ppRuntimes`  
 enuncia Matriz de estructuras [coreclrdebugruntimeinfo (](../../../../docs/framework/unmanaged-api/debugging/coreclrdebugruntimeinfo-structure.md) que representan los tiempos de ejecución cargados en el proceso de destino remoto.  
  
## <a name="return-value"></a>Valor devuelto  
 S_OK  
 Correcto.  
  
 S_FALSE  
 `dwInternalProcessID` no coincide con ningún proceso que se esté ejecutando en el equipo, probablemente porque finalizó el proceso. `pcRuntimes` y `ppRuntimes` serán nulos.  
  
 E_OUTOFMEMORY  
 No se puede asignar memoria suficiente para `ppRuntimes`.  
  
 E_FAIL (u otros códigos devueltos de E_)  
 Otros errores.  
  
## <a name="remarks"></a>Comentarios  
 Para liberar la memoria asignada por este método, llame al método [ICoreClrDebugTarget:: FreeMemory (](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-freememory-method.md) .  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CoreClrRemoteDebuggingInterfaces. h  
  
 **Biblioteca:** mscordbi_macx86. dll  
  
 **.NET Framework versiones:** 3,5 SP1  
  
## <a name="see-also"></a>Vea también

- [ICoreClrDebugTarget (interfaz)](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-interface.md)
