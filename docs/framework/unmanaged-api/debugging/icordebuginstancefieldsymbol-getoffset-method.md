---
title: Método ICorDebugInstanceFieldSymbol::GetOffset
ms.date: 03/30/2017
ms.assetid: 7e470150-2b92-4425-989c-315f48964fd2
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a88de396d946c37b30688ab614d2bcc549c86873
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57468135"
---
# <a name="icordebuginstancefieldsymbolgetoffset-method"></a><span data-ttu-id="c6985-102">Método ICorDebugInstanceFieldSymbol::GetOffset</span><span class="sxs-lookup"><span data-stu-id="c6985-102">ICorDebugInstanceFieldSymbol::GetOffset Method</span></span>
<span data-ttu-id="c6985-103">Obtiene el desplazamiento en bytes de este campo de instancia en su clase primaria.</span><span class="sxs-lookup"><span data-stu-id="c6985-103">Gets the offset in bytes of this instance field in its parent class.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c6985-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c6985-104">Syntax</span></span>  
  
```  
HRESULT GetOffset(  
   [out] ULONG32 *pcbOffset  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c6985-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c6985-105">Parameters</span></span>  
 `pcbOffset`  
 <span data-ttu-id="c6985-106">Puntero al número de bytes que este campo de instancia compensa en su clase primaria.</span><span class="sxs-lookup"><span data-stu-id="c6985-106">A pointer to the number of bytes that this instance field is offset in its parent class.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c6985-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="c6985-107">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c6985-108">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="c6985-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c6985-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c6985-109">Requirements</span></span>  
 <span data-ttu-id="c6985-110">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c6985-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c6985-111">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c6985-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c6985-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c6985-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c6985-113">**Versiones de .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c6985-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c6985-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="c6985-114">See also</span></span>
- [<span data-ttu-id="c6985-115">ICorDebugInstanceFieldSymbol (interfaz)</span><span class="sxs-lookup"><span data-stu-id="c6985-115">ICorDebugInstanceFieldSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuginstancefieldsymbol-interface.md)
- [<span data-ttu-id="c6985-116">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="c6985-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
