---
title: Método ICorDebugDataTarget2::GetImageFromPointer
ms.date: 03/30/2017
ms.assetid: 939cabe1-b647-4090-b662-eeec23c6c58d
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c2371072261c9c75436ab86d742ce75423587765
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69969442"
---
# <a name="icordebugdatatarget2getimagefrompointer-method"></a><span data-ttu-id="11af2-102">Método ICorDebugDataTarget2::GetImageFromPointer</span><span class="sxs-lookup"><span data-stu-id="11af2-102">ICorDebugDataTarget2::GetImageFromPointer Method</span></span>
<span data-ttu-id="11af2-103">Devuelve el tamaño y dirección base del módulo a partir de una dirección de ese módulo.</span><span class="sxs-lookup"><span data-stu-id="11af2-103">Returns the module base address and size from an address in that module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="11af2-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="11af2-104">Syntax</span></span>  
  
```cpp  
HRESULT GetImageFromPointer(  
   [in] CORDB_ADDRESS addr,   
   [out] CORDB_ADDRESS *pImageBase,   
   [out] ULONG32 *pSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="11af2-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="11af2-105">Parameters</span></span>  
 `addr`  
 <span data-ttu-id="11af2-106">Valor de [CORDB_ADDRESS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md) que representa una dirección de un módulo.</span><span class="sxs-lookup"><span data-stu-id="11af2-106">A [CORDB_ADDRESS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md) value that represents an address in a module.</span></span>  
  
 `pImageBase`  
 <span data-ttu-id="11af2-107">enuncia Valor de [CORDB_ADDRESS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md) que representa la dirección base del módulo.</span><span class="sxs-lookup"><span data-stu-id="11af2-107">[out] A [CORDB_ADDRESS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md) value that represents the module's base address.</span></span>  
  
 `pSize`  
 <span data-ttu-id="11af2-108">Puntero al tamaño del módulo.</span><span class="sxs-lookup"><span data-stu-id="11af2-108">A pointer to the module size.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="11af2-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="11af2-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="11af2-110">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="11af2-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="11af2-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="11af2-111">Requirements</span></span>  
 <span data-ttu-id="11af2-112">**Select** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="11af2-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="11af2-113">**Encabezado**: Cordebug. idl, Cordebug. h</span><span class="sxs-lookup"><span data-stu-id="11af2-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="11af2-114">**Biblioteca** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="11af2-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="11af2-115">**Versiones de .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="11af2-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="11af2-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="11af2-116">See also</span></span>

- [<span data-ttu-id="11af2-117">ICorDebugDataTarget2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="11af2-117">ICorDebugDataTarget2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget2-interface.md)
- [<span data-ttu-id="11af2-118">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="11af2-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
