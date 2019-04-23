---
title: Interfaz ICorDebugType2
ms.date: 03/30/2017
api_name:
- ICorDebugType2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugType2
helpviewer_keywords:
- ICorDebugType2 interface
ms.assetid: 376fb03f-f1ef-4107-baa4-4d9d55884862
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 878941f7af71fa5e3de8e38c4a68a66cb964983d
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59223165"
---
# <a name="icordebugtype2-interface"></a><span data-ttu-id="a036f-102">Interfaz ICorDebugType2</span><span class="sxs-lookup"><span data-stu-id="a036f-102">ICorDebugType2 Interface</span></span>
<span data-ttu-id="a036f-103">Extiende la interfaz ICorDebugType para recuperar el identificador de tipo de un tipo base o un tipo complejo (definido por el usuario).</span><span class="sxs-lookup"><span data-stu-id="a036f-103">Extends the ICorDebugType interface to retrieve the type identifier  of a base type or complex (user-defined) type.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a036f-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="a036f-104">Methods</span></span>  
  
|<span data-ttu-id="a036f-105">Método</span><span class="sxs-lookup"><span data-stu-id="a036f-105">Method</span></span>||  
|------------|-|  
|[<span data-ttu-id="a036f-106">GetTypeID (método)</span><span class="sxs-lookup"><span data-stu-id="a036f-106">GetTypeID Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugtype2-gettypeid-method.md)|<span data-ttu-id="a036f-107">Obtiene un [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) para este tipo.</span><span class="sxs-lookup"><span data-stu-id="a036f-107">Gets a [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) for this type.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a036f-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a036f-108">Remarks</span></span>  
 <span data-ttu-id="a036f-109">Esta interfaz es una extensión lógica de ICorDebugType (interfaz).</span><span class="sxs-lookup"><span data-stu-id="a036f-109">This interface is a logical extension of the ICorDebugType interface.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a036f-110">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="a036f-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a036f-111">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a036f-111">Example</span></span>  
 <span data-ttu-id="a036f-112">El fragmento de código siguiente muestra el uso de la [icordebugtype2:: GetTypeId](../../../../docs/framework/unmanaged-api/debugging/icordebugtype2-gettypeid-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="a036f-112">The following code fragment illustrates the use of the [ICorDebugType2::GetTypeID](../../../../docs/framework/unmanaged-api/debugging/icordebugtype2-gettypeid-method.md) method.</span></span>  
  
```  
// (error checking omitted for brevity)  
// given an ICorDebugType *pType  
  
ICorDebugType2 *pType2 = NULL;  
pType->QueryInterface(IID_ICorDebugType2, &pType);  
  
COR_TYPEID id;  
pType2->GetTypeID(&id);  
  
// now we can use existing APIs to get information about this COR_TYPEID  
```  
  
## <a name="requirements"></a><span data-ttu-id="a036f-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a036f-113">Requirements</span></span>  
 <span data-ttu-id="a036f-114">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a036f-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a036f-115">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a036f-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a036f-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a036f-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a036f-117">**Versiones de .NET Framework:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a036f-117">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a036f-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="a036f-118">See also</span></span>

- [<span data-ttu-id="a036f-119">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="a036f-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
