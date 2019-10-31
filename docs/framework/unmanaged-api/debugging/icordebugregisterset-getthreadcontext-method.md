---
title: ICorDebugRegisterSet::GetThreadContext (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugRegisterSet.GetThreadContext
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugRegisterSet::GetThreadContext
helpviewer_keywords:
- GetThreadContext method, ICorDebugRegisterSet interface [.NET Framework debugging]
- ICorDebugRegisterSet::GetThreadContext method [.NET Framework debugging]
ms.assetid: 0f63400b-dc1c-48d6-b51a-75c3f7f28e03
topic_type:
- apiref
ms.openlocfilehash: db4f9bc6277015055cbcdb509628f2862a71dbc4
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73127153"
---
# <a name="icordebugregistersetgetthreadcontext-method"></a><span data-ttu-id="a1e25-102">ICorDebugRegisterSet::GetThreadContext (Método)</span><span class="sxs-lookup"><span data-stu-id="a1e25-102">ICorDebugRegisterSet::GetThreadContext Method</span></span>
<span data-ttu-id="a1e25-103">Obtiene el contexto del subproceso actual.</span><span class="sxs-lookup"><span data-stu-id="a1e25-103">Gets the context of the current thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a1e25-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a1e25-104">Syntax</span></span>  
  
```cpp  
HRESULT GetThreadContext(  
    [in] ULONG32 contextSize,  
    [in, out, length_is(contextSize),  
        size_is(contextSize)] BYTE context[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a1e25-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a1e25-105">Parameters</span></span>  
 `contextSize`  
 <span data-ttu-id="a1e25-106">de Tamaño, en bytes, de la matriz de `context`.</span><span class="sxs-lookup"><span data-stu-id="a1e25-106">[in] The size, in bytes, of the `context` array.</span></span>  
  
 `context`  
 <span data-ttu-id="a1e25-107">[in, out] Matriz de bytes que componen la estructura de `CONTEXT` Win32 para la plataforma actual.</span><span class="sxs-lookup"><span data-stu-id="a1e25-107">[in, out] An array of bytes that compose the Win32 `CONTEXT` structure for the current platform.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a1e25-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a1e25-108">Remarks</span></span>  
 <span data-ttu-id="a1e25-109">El depurador debe llamar a esta función en lugar de a la función `GetThreadContext` de Win32, porque el subproceso puede estar en un estado "secuestrado" donde su contexto ha cambiado temporalmente.</span><span class="sxs-lookup"><span data-stu-id="a1e25-109">The debugger should call this function instead of the Win32 `GetThreadContext` function, because the thread may be in a "hijacked" state where its context has been temporarily changed.</span></span> <span data-ttu-id="a1e25-110">Los datos devueltos son una estructura de `CONTEXT` Win32 para la plataforma actual.</span><span class="sxs-lookup"><span data-stu-id="a1e25-110">The data returned is a Win32 `CONTEXT` structure for the current platform.</span></span>  
  
 <span data-ttu-id="a1e25-111">En el caso de los marcos no hoja, los clientes deben comprobar qué registros son válidos mediante [ICorDebugRegisterSet:: getregistersavailable (](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-getregistersavailable-method.md).</span><span class="sxs-lookup"><span data-stu-id="a1e25-111">For non-leaf frames, clients should check which registers are valid by using [ICorDebugRegisterSet::GetRegistersAvailable](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-getregistersavailable-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a1e25-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a1e25-112">Requirements</span></span>  
 <span data-ttu-id="a1e25-113">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a1e25-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a1e25-114">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a1e25-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a1e25-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a1e25-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a1e25-116">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a1e25-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a1e25-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="a1e25-117">See also</span></span>

- [<span data-ttu-id="a1e25-118">ICorDebugRegisterSet (interfaz)</span><span class="sxs-lookup"><span data-stu-id="a1e25-118">ICorDebugRegisterSet Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md)
- [<span data-ttu-id="a1e25-119">ICorDebugRegisterSet2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="a1e25-119">ICorDebugRegisterSet2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-interface.md)
