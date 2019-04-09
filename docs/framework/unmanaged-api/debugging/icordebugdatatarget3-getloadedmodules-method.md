---
title: Método de ICorDebugDataTarget3::GetLoadedModules
ms.date: 03/30/2017
ms.assetid: 9a48c05b-1949-416e-933c-52549b6fcf5e
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 464fd9ac44d6ba5717dbc4ecfbe03b6e6ad52276
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59138663"
---
# <a name="icordebugdatatarget3getloadedmodules-method"></a><span data-ttu-id="31f11-102">Método de ICorDebugDataTarget3::GetLoadedModules</span><span class="sxs-lookup"><span data-stu-id="31f11-102">ICorDebugDataTarget3::GetLoadedModules Method</span></span>
<span data-ttu-id="31f11-103">Obtiene una lista de los módulos que se han cargado hasta ahora.</span><span class="sxs-lookup"><span data-stu-id="31f11-103">Gets a list of the modules that have been loaded so far.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="31f11-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="31f11-104">Syntax</span></span>  
  
```  
HRESULT GetLoadedModules(  
   [in] ULONG32 cRequestedModules,  
   [out] ULONG32 *pcFetchedModules,  
   [out, size_is(cRequestedModules), length_is(*pcFetchedModules)] ICorDebugLoadedModule *pLoadedModules[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="31f11-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="31f11-105">Parameters</span></span>  
 `cRequestedModules`  
 <span data-ttu-id="31f11-106">[in] Número de módulos para los que se solicita información.</span><span class="sxs-lookup"><span data-stu-id="31f11-106">[in] The number of modules for which information is requested.</span></span>  
  
 `pcFetchedModules`  
 <span data-ttu-id="31f11-107">[out] Puntero al número de módulos sobre qué información se devolvió.</span><span class="sxs-lookup"><span data-stu-id="31f11-107">[out] A pointer to the number of modules about which information was returned.</span></span>  
  
 `pLoadedModules`  
 <span data-ttu-id="31f11-108">[out] Un puntero a una matriz de [ICorDebugLoadedModule](../../../../docs/framework/unmanaged-api/debugging/icordebugloadedmodule-interface.md) objetos que proporcionan información acerca de los módulos cargan.</span><span class="sxs-lookup"><span data-stu-id="31f11-108">[out] A pointer to an array of [ICorDebugLoadedModule](../../../../docs/framework/unmanaged-api/debugging/icordebugloadedmodule-interface.md) objects that provide information about loaded modules.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="31f11-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="31f11-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="31f11-110">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="31f11-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="31f11-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="31f11-111">Requirements</span></span>  
 <span data-ttu-id="31f11-112">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="31f11-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="31f11-113">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="31f11-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="31f11-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="31f11-114">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="31f11-115">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="31f11-115">.NET Framework Versions:</span></span>** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="31f11-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="31f11-116">See also</span></span>

- [<span data-ttu-id="31f11-117">Interfaz de ICorDebugDataTarget3</span><span class="sxs-lookup"><span data-stu-id="31f11-117">ICorDebugDataTarget3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget3-interface.md)
- [<span data-ttu-id="31f11-118">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="31f11-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
