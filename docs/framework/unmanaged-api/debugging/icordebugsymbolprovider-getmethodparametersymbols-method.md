---
title: ICorDebugSymbolProvider::GetMethodParameterSymbols (método)
ms.date: 03/30/2017
ms.assetid: 58b7c0b9-f6ad-4b49-b92d-0e421cfd0ec6
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d016007d09a06e923bef78fa8ead99e1e1ce9420
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67771374"
---
# <a name="icordebugsymbolprovidergetmethodparametersymbols-method"></a><span data-ttu-id="6ed6f-102">ICorDebugSymbolProvider::GetMethodParameterSymbols (método)</span><span class="sxs-lookup"><span data-stu-id="6ed6f-102">ICorDebugSymbolProvider::GetMethodParameterSymbols Method</span></span>
<span data-ttu-id="6ed6f-103">Obtiene los símbolos de parámetro del método a partir de la dirección virtual relativa (RVA) de ese método.</span><span class="sxs-lookup"><span data-stu-id="6ed6f-103">Gets a method's parameter symbols given the relative virtual address (RVA) of that method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6ed6f-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6ed6f-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMethodParameterSymbols(  
   [in] ULONG32 nativeRVA,  
   [in] ULONG32 cRequestedSymbols,  
   [out] ULONG32 *pcFetchedSymbols,  
   [out, size_is(cRequestedSymbols), length_is(*pcFetchedSymbols)] ICorDebugVariableSymbol *pSymbols[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6ed6f-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="6ed6f-105">Parameters</span></span>  
 `nativeRVA`  
 <span data-ttu-id="6ed6f-106">[in] Dirección virtual relativa nativa del método.</span><span class="sxs-lookup"><span data-stu-id="6ed6f-106">[in] The native relative virtual address of the method.</span></span>  
  
 `cRequestedSymbols`  
 <span data-ttu-id="6ed6f-107">[in] Número de símbolos locales solicitado.</span><span class="sxs-lookup"><span data-stu-id="6ed6f-107">[in] The number of local symbols requested.</span></span>  
  
 `pcFetchedSymbols`  
 <span data-ttu-id="6ed6f-108">[out] Puntero al número de símbolos recuperados por el método.</span><span class="sxs-lookup"><span data-stu-id="6ed6f-108">[out] A pointer to the number of symbols retrieved by the method.</span></span>  
  
 `pcFetchedSymbols`  
 <span data-ttu-id="6ed6f-109">[out] Un puntero a un [ICorDebugVariableSymbol](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablesymbol-interface.md) matriz que contiene los símbolos locales del método.</span><span class="sxs-lookup"><span data-stu-id="6ed6f-109">[out] A pointer to an [ICorDebugVariableSymbol](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablesymbol-interface.md) array that contains the method's local symbols.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6ed6f-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="6ed6f-110">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6ed6f-111">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="6ed6f-111">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6ed6f-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="6ed6f-112">Requirements</span></span>  
 <span data-ttu-id="6ed6f-113">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6ed6f-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6ed6f-114">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6ed6f-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6ed6f-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6ed6f-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6ed6f-116">**Versiones de .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6ed6f-116">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6ed6f-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="6ed6f-117">See also</span></span>

- [<span data-ttu-id="6ed6f-118">GetMethodLocalSymbols (método)</span><span class="sxs-lookup"><span data-stu-id="6ed6f-118">GetMethodLocalSymbols Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-getmethodlocalsymbols-method.md)
- [<span data-ttu-id="6ed6f-119">ICorDebugSymbolProvider (interfaz)</span><span class="sxs-lookup"><span data-stu-id="6ed6f-119">ICorDebugSymbolProvider Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md)
- [<span data-ttu-id="6ed6f-120">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="6ed6f-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
