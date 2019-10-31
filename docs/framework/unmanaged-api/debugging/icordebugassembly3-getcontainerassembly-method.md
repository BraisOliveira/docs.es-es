---
title: Método ICorDebugAssembly3::GetContainerAssembly
ms.date: 03/30/2017
ms.assetid: f5fddeb6-b82e-4ebb-b432-849ce8513c77
ms.openlocfilehash: 39f8dd042ea785258dfe5c048ebc348852be6892
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73095389"
---
# <a name="icordebugassembly3getcontainerassembly-method"></a><span data-ttu-id="498ab-102">Método ICorDebugAssembly3::GetContainerAssembly</span><span class="sxs-lookup"><span data-stu-id="498ab-102">ICorDebugAssembly3::GetContainerAssembly Method</span></span>
<span data-ttu-id="498ab-103">Devuelve el ensamblado de contenedor de este objeto `ICorDebugAssembly3`.</span><span class="sxs-lookup"><span data-stu-id="498ab-103">Returns the container assembly of this `ICorDebugAssembly3` object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="498ab-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="498ab-104">Syntax</span></span>  
  
```cpp  
HRESULT GetContainerAssembly(  
    ICorDebugAssembly **ppAssembly  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="498ab-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="498ab-105">Parameters</span></span>  
 `ppAssembly`  
 <span data-ttu-id="498ab-106">Puntero a la dirección de un objeto ICorDebugAssembly que representa el ensamblado de contenedor, o **null** si se produce un error en la llamada al método.</span><span class="sxs-lookup"><span data-stu-id="498ab-106">A pointer to the address of an ICorDebugAssembly object that represents the container assembly, or **null** if the method call fails.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="498ab-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="498ab-107">Return Value</span></span>  
 <span data-ttu-id="498ab-108">`S_OK` si la llamada al método se realiza correctamente; de lo contrario, `S_FALSE`y `ppAssembly` es **null**.</span><span class="sxs-lookup"><span data-stu-id="498ab-108">`S_OK` if the method call succeeds; otherwise, `S_FALSE`, and `ppAssembly` is **null**.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="498ab-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="498ab-109">Remarks</span></span>  
 <span data-ttu-id="498ab-110">Si este ensamblado se ha combinado con otros dentro de un solo ensamblado de contenedor, este método devuelve el ensamblado de contenedor.</span><span class="sxs-lookup"><span data-stu-id="498ab-110">If this assembly has been merged with others inside a single container assembly, this method returns the container assembly.</span></span> <span data-ttu-id="498ab-111">Para obtener más información y terminología, vea el tema [método icordebugprocess6:: EnableVirtualModuleSplitting](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-enablevirtualmodulesplitting-method.md) .</span><span class="sxs-lookup"><span data-stu-id="498ab-111">For more information and terminology, see the [ICorDebugProcess6::EnableVirtualModuleSplitting](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-enablevirtualmodulesplitting-method.md) topic.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="498ab-112">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="498ab-112">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="498ab-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="498ab-113">Requirements</span></span>  
 <span data-ttu-id="498ab-114">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="498ab-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="498ab-115">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="498ab-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="498ab-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="498ab-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="498ab-117">**Versiones de .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="498ab-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="498ab-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="498ab-118">See also</span></span>

- [<span data-ttu-id="498ab-119">ICorDebugAssembly3 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="498ab-119">ICorDebugAssembly3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly3-interface.md)
- [<span data-ttu-id="498ab-120">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="498ab-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
