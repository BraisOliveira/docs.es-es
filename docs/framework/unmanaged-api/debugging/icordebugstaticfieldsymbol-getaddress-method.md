---
title: ICorDebugStaticFieldSymbol::GetAddress (método)
ms.date: 03/30/2017
ms.assetid: 5a6c9a5a-ec72-4c40-a9c3-cee7baa63687
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e233fe78f6b2c721114f0307a8ca414625a0087e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59160425"
---
# <a name="icordebugstaticfieldsymbolgetaddress-method"></a><span data-ttu-id="fa6b6-102">ICorDebugStaticFieldSymbol::GetAddress (método)</span><span class="sxs-lookup"><span data-stu-id="fa6b6-102">ICorDebugStaticFieldSymbol::GetAddress Method</span></span>
<span data-ttu-id="fa6b6-103">Obtiene la dirección de un campo estático.</span><span class="sxs-lookup"><span data-stu-id="fa6b6-103">Gets the address of a static field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fa6b6-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="fa6b6-104">Syntax</span></span>  
  
```  
HRESULT GetAddress(  
   [out] CORDB_ADDRESS *pRVA  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fa6b6-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="fa6b6-105">Parameters</span></span>  
 <span data-ttu-id="fa6b6-106">pRVA</span><span class="sxs-lookup"><span data-stu-id="fa6b6-106">pRVA</span></span>  
 <span data-ttu-id="fa6b6-107">[out] Puntero a la dirección virtual relativa (RVA) del campo estático.</span><span class="sxs-lookup"><span data-stu-id="fa6b6-107">[out] A pointer to the relative virtual address (RVA) of the static field.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fa6b6-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="fa6b6-108">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fa6b6-109">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="fa6b6-109">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fa6b6-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="fa6b6-110">Requirements</span></span>  
 <span data-ttu-id="fa6b6-111">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fa6b6-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fa6b6-112">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fa6b6-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fa6b6-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fa6b6-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fa6b6-114">**Versiones de .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fa6b6-114">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa6b6-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="fa6b6-115">See also</span></span>

- [<span data-ttu-id="fa6b6-116">ICorDebugStaticFieldSymbol (interfaz)</span><span class="sxs-lookup"><span data-stu-id="fa6b6-116">ICorDebugStaticFieldSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstaticfieldsymbol-interface.md)
- [<span data-ttu-id="fa6b6-117">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="fa6b6-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
