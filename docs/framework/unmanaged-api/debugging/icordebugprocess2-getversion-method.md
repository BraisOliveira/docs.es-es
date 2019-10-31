---
title: ICorDebugProcess2::GetVersion (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugProcess2.GetVersion
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess2::GetVersion
helpviewer_keywords:
- GetVersion method, ICorDebugProcess2 interface [.NET Framework debugging]
- ICorDebugProcess2::GetVersion method [.NET Framework debugging]
ms.assetid: e11d5a75-61d9-4548-aedf-79c26079bd17
topic_type:
- apiref
ms.openlocfilehash: 5f618f6779f6931785bba18f70fb1ac9baf46753
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73137191"
---
# <a name="icordebugprocess2getversion-method"></a><span data-ttu-id="45c96-102">ICorDebugProcess2::GetVersion (Método)</span><span class="sxs-lookup"><span data-stu-id="45c96-102">ICorDebugProcess2::GetVersion Method</span></span>

<span data-ttu-id="45c96-103">Obtiene el número de versión del Common Language Runtime (CLR) que se ejecuta en este proceso.</span><span class="sxs-lookup"><span data-stu-id="45c96-103">Gets the version number of the common language runtime (CLR) that is running in this process.</span></span>

## <a name="syntax"></a><span data-ttu-id="45c96-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="45c96-104">Syntax</span></span>

```cpp
HRESULT GetVersion (
    [out] COR_VERSION     *version
);
```

## <a name="parameters"></a><span data-ttu-id="45c96-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="45c96-105">Parameters</span></span>

`version`\
<span data-ttu-id="45c96-106">enuncia Puntero a una estructura COR_VERSION que almacena el número de versión del Runtime.</span><span class="sxs-lookup"><span data-stu-id="45c96-106">[out] A pointer to a COR_VERSION structure that stores the version number of the runtime.</span></span>

## <a name="remarks"></a><span data-ttu-id="45c96-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="45c96-107">Remarks</span></span>

<span data-ttu-id="45c96-108">El método `GetVersion` devuelve un código de error si no se ha cargado ningún tiempo de ejecución en el proceso.</span><span class="sxs-lookup"><span data-stu-id="45c96-108">The `GetVersion` method returns an error code if no runtime has been loaded in the process.</span></span>

## <a name="requirements"></a><span data-ttu-id="45c96-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="45c96-109">Requirements</span></span>

<span data-ttu-id="45c96-110">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="45c96-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="45c96-111">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="45c96-111">**Header:** CorDebug.idl, CorDebug.h</span></span>

<span data-ttu-id="45c96-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="45c96-112">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="45c96-113">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="45c96-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
