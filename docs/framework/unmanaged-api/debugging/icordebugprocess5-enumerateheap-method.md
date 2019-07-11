---
title: ICorDebugProcess5::EnumerateHeap (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugProcess5.EnumerateHeap
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess5::EnumerateHeap
helpviewer_keywords:
- EnumerateHeap method, ICorDebugProcess5 interface [.NET Framework debugging]
- ICorDebugProcess5::EnumerateHeap method [.NET Framework debugging]
ms.assetid: b0192104-6073-4089-a4df-dc29ee033074
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3d080145ac63882e04412b44c34d040a75746243
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67767526"
---
# <a name="icordebugprocess5enumerateheap-method"></a><span data-ttu-id="8bb12-102">ICorDebugProcess5::EnumerateHeap (Método)</span><span class="sxs-lookup"><span data-stu-id="8bb12-102">ICorDebugProcess5::EnumerateHeap Method</span></span>
<span data-ttu-id="8bb12-103">Obtiene un enumerador para los objetos del montón administrado.</span><span class="sxs-lookup"><span data-stu-id="8bb12-103">Gets an enumerator for the objects on the managed heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8bb12-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8bb12-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateHeap(  
    [out] ICorDebugHeapEnum **ppObjects  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8bb12-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="8bb12-105">Parameters</span></span>  
 `ppObject`  
 <span data-ttu-id="8bb12-106">[out] Un puntero a la dirección de un [ICorDebugHeapEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-interface.md) objeto de interfaz que es un enumerador para los objetos que residen en el montón administrado.</span><span class="sxs-lookup"><span data-stu-id="8bb12-106">[out] A pointer to the address of an [ICorDebugHeapEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-interface.md) interface object that is an enumerator for the objects that reside on the managed heap.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8bb12-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="8bb12-107">Remarks</span></span>  
 <span data-ttu-id="8bb12-108">Antes de llamar a la `ICorDebugProcess5::EnumerateHeap` método, debe llamar a la [Icordebugprocess5](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-getgcheapinformation-method.md) método y examinar el valor de la `areGCStructuresValid` campo devuelto del [COR_HEAPINFO](../../../../docs/framework/unmanaged-api/debugging/cor-heapinfo-structure.md) objeto para asegurarse de que el montón de elementos no utilizados en su estado actual es enumerable.</span><span class="sxs-lookup"><span data-stu-id="8bb12-108">Before calling the `ICorDebugProcess5::EnumerateHeap` method, you should call the [ICorDebugProcess5::GetGCHeapInformation](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-getgcheapinformation-method.md) method and examine the value of the `areGCStructuresValid` field of the returned [COR_HEAPINFO](../../../../docs/framework/unmanaged-api/debugging/cor-heapinfo-structure.md) object to ensure that the garbage collection heap in its current state is enumerable.</span></span> <span data-ttu-id="8bb12-109">Además, el `ICorDebugProcess5::EnumerateHeap` devuelve `E_FAIL` si adjuntar demasiado pronto en la duración del proceso, antes de la memoria para el montón administrado está asignado.</span><span class="sxs-lookup"><span data-stu-id="8bb12-109">In addition, the `ICorDebugProcess5::EnumerateHeap` returns `E_FAIL` if you attach too early in the lifetime of the process, before memory for the managed heap is allocated.</span></span>  
  
 <span data-ttu-id="8bb12-110">El [ICorDebugHeapEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-interface.md) objeto de interfaz es un enumerador estándar que se deriva de la interfaz ICorDebugEnum que le permite enumerar [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) objetos.</span><span class="sxs-lookup"><span data-stu-id="8bb12-110">The [ICorDebugHeapEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-interface.md) interface object is a standard enumerator derived from the ICorDebugEnum interface that allows you to enumerate [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) objects.</span></span> <span data-ttu-id="8bb12-111">Este método rellena el [ICorDebugHeapEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-interface.md) objeto de colección con [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) instancias que proporcionan información sobre todos los objetos.</span><span class="sxs-lookup"><span data-stu-id="8bb12-111">This method populates the [ICorDebugHeapEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-interface.md) collection object with [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) instances that provide information about all objects.</span></span> <span data-ttu-id="8bb12-112">También puede incluir la colección [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) instancias que proporcionan información acerca de los objetos que no se ha modificado por cualquier objeto pero aún no se han recopilado por el recolector de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="8bb12-112">The collection may also include [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) instances that provide information about objects that are not rooted by any object but have not yet been collected by the garbage collector.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8bb12-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8bb12-113">Requirements</span></span>  
 <span data-ttu-id="8bb12-114">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8bb12-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8bb12-115">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8bb12-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8bb12-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8bb12-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8bb12-117">**Versiones de .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8bb12-117">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8bb12-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="8bb12-118">See also</span></span>

- [<span data-ttu-id="8bb12-119">ICorDebugProcess5 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="8bb12-119">ICorDebugProcess5 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md)
- [<span data-ttu-id="8bb12-120">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="8bb12-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
