---
title: ICorDebugAppDomain3::GetCachedWinRTTypes (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomain3.GetCachedWinRTTypes
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain3::GetCachedWinRTTypes
helpviewer_keywords:
- ICorDebugAppDomain3::GetCachedWinRTTypes method [.NET Framework debugging]
- GetCachedWinRTTypes method, ICorDebugAppDomain3 interface [.NET Framework debugging]
ms.assetid: 9afd0e04-a403-41e2-9528-a6dcbcdcbd4d
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4ba981d86f90af449820ce13aa847169ca877429
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67737772"
---
# <a name="icordebugappdomain3getcachedwinrttypes-method"></a><span data-ttu-id="74e93-102">ICorDebugAppDomain3::GetCachedWinRTTypes (Método)</span><span class="sxs-lookup"><span data-stu-id="74e93-102">ICorDebugAppDomain3::GetCachedWinRTTypes Method</span></span>
<span data-ttu-id="74e93-103">Obtiene un enumerador para todos los tipos en tiempo de ejecución de Windows almacenado en caché.</span><span class="sxs-lookup"><span data-stu-id="74e93-103">Gets an enumerator for all cached Windows Runtime types.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="74e93-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="74e93-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCachedWinRTTypes (   
    [out] ICorDebugGuidToTypeEnum **ppGuidToTypeEnum)  
;  
```  
  
## <a name="parameters"></a><span data-ttu-id="74e93-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="74e93-105">Parameters</span></span>  
 `ppGuidToTypeEnum`  
 <span data-ttu-id="74e93-106">[out] Un puntero a un [ICorDebugGuidToTypeEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugguidtotypeenum-interface.md) objeto de interfaz que puede enumerar las representaciones de tipos de Windows Runtime administradas actualmente cargado en el dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="74e93-106">[out] A pointer to an [ICorDebugGuidToTypeEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugguidtotypeenum-interface.md) interface object that can enumerate the managed representations of Windows Runtime types currently loaded in the application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="74e93-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="74e93-107">Requirements</span></span>  
 <span data-ttu-id="74e93-108">**Plataformas:** Windows en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="74e93-108">**Platforms:** Windows Runtime</span></span>  
  
 <span data-ttu-id="74e93-109">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="74e93-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="74e93-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="74e93-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="74e93-111">**Versiones de .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="74e93-111">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="74e93-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="74e93-112">See also</span></span>

- [<span data-ttu-id="74e93-113">ICorDebugAppDomain3 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="74e93-113">ICorDebugAppDomain3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain3-interface.md)
