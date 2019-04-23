---
title: Método ICorDebugCode4::EnumerateVariableHomes
ms.date: 03/30/2017
api_name:
- ICorDebugCode4.EnumerateVariableHomes
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode4::EnumerateVariableHomes
helpviewer_keywords:
- EnumerateVariableHomes method [.NET Framework debugging]
- ICorDebugCode4::EnumerateVariableHomes method [.NET Framework debugging]
ms.assetid: 802c01ff-8b80-4733-b6dd-03ab6ff7fa11
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8a6e4f6e7e3107516476b179b0ed718ca44bb114
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59103404"
---
# <a name="icordebugcode4enumeratevariablehomes-method"></a><span data-ttu-id="0c1fe-102">Método ICorDebugCode4::EnumerateVariableHomes</span><span class="sxs-lookup"><span data-stu-id="0c1fe-102">ICorDebugCode4::EnumerateVariableHomes Method</span></span>
<span data-ttu-id="0c1fe-103">Obtiene un enumerador para los argumentos y variables locales en una función.</span><span class="sxs-lookup"><span data-stu-id="0c1fe-103">Gets an enumerator to the local variables and arguments in a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0c1fe-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0c1fe-104">Syntax</span></span>  
  
```  
HRESULT EnumerateVariableHomes(  
    [out] ICorDebugVariableHomeEnum **ppEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0c1fe-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="0c1fe-105">Parameters</span></span>  
 `ppEnum`  
 <span data-ttu-id="0c1fe-106">Un puntero a la dirección de un [ICorDebugVariableHomeEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehomeenum-interface.md) objeto de interfaz que es un enumerador para los argumentos en una función y las variables locales.</span><span class="sxs-lookup"><span data-stu-id="0c1fe-106">A pointer to the address of an [ICorDebugVariableHomeEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehomeenum-interface.md) interface object that is an enumerator for the local variables and arguments in a function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0c1fe-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="0c1fe-107">Remarks</span></span>  
 <span data-ttu-id="0c1fe-108">El [ICorDebugVariableHomeEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehomeenum-interface.md) objeto de interfaz es un enumerador estándar que se deriva de la interfaz "ICorDebugEnum" que permite enumerar [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) objetos.</span><span class="sxs-lookup"><span data-stu-id="0c1fe-108">The [ICorDebugVariableHomeEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehomeenum-interface.md) interface object is a standard enumerator derived from the "ICorDebugEnum" interface that allows you to enumerate [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) objects.</span></span> <span data-ttu-id="0c1fe-109">La colección puede incluir varios [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) de objetos para el mismo índice de ranura o argumento si tienen las casas diferentes en distintos puntos de la función.</span><span class="sxs-lookup"><span data-stu-id="0c1fe-109">The collection may include multiple [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) objects for the same slot or      argument index if they have different homes at different points in the      function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0c1fe-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0c1fe-110">Requirements</span></span>  
 <span data-ttu-id="0c1fe-111">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0c1fe-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0c1fe-112">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0c1fe-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0c1fe-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0c1fe-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0c1fe-114">**Versiones de .NET Framework:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0c1fe-114">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0c1fe-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="0c1fe-115">See also</span></span>

- [<span data-ttu-id="0c1fe-116">ICorDebugCode4 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="0c1fe-116">ICorDebugCode4 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode4-interface.md)
- [<span data-ttu-id="0c1fe-117">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="0c1fe-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
