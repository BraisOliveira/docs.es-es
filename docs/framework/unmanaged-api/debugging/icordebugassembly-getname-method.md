---
title: ICorDebugAssembly::GetName (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugAssembly.GetName
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAssembly::GetName
helpviewer_keywords:
- ICorDebugAssembly::GetName method [.NET Framework debugging]
- GetName method, ICorDebugAssembly interface [.NET Framework debugging]
ms.assetid: cdeda721-b214-4503-a291-c70b68b5f36b
topic_type:
- apiref
ms.openlocfilehash: 5e3619d12b9377a8482254703d3d97d0348a013b
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73127170"
---
# <a name="icordebugassemblygetname-method"></a><span data-ttu-id="f8ebd-102">ICorDebugAssembly::GetName (Método)</span><span class="sxs-lookup"><span data-stu-id="f8ebd-102">ICorDebugAssembly::GetName Method</span></span>
<span data-ttu-id="f8ebd-103">Obtiene el nombre del ensamblado que esta instancia de `ICorDebugAssembly` representa.</span><span class="sxs-lookup"><span data-stu-id="f8ebd-103">Gets the name of the assembly that this `ICorDebugAssembly` instance represents.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f8ebd-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f8ebd-104">Syntax</span></span>  
  
```cpp  
HRESULT GetName (  
    [in] ULONG32  cchName,  
    [out] ULONG32 *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)] WCHAR szName[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f8ebd-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f8ebd-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="f8ebd-106">[in] Tamaño de la matriz `szName`.</span><span class="sxs-lookup"><span data-stu-id="f8ebd-106">[in] The size of the `szName` array.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="f8ebd-107">enuncia Puntero a un entero que especifica la longitud real del nombre.</span><span class="sxs-lookup"><span data-stu-id="f8ebd-107">[out] A pointer to an integer that specifies the actual length of the name.</span></span>  
  
 `szName`  
 <span data-ttu-id="f8ebd-108">enuncia Matriz que almacena el nombre.</span><span class="sxs-lookup"><span data-stu-id="f8ebd-108">[out] An array that stores the name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f8ebd-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f8ebd-109">Remarks</span></span>  
 <span data-ttu-id="f8ebd-110">El método `GetName` devuelve la ruta de acceso completa y el nombre de archivo del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="f8ebd-110">The `GetName` method returns the full path and file name of the assembly.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f8ebd-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f8ebd-111">Requirements</span></span>  
 <span data-ttu-id="f8ebd-112">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f8ebd-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f8ebd-113">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f8ebd-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f8ebd-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f8ebd-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f8ebd-115">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f8ebd-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
