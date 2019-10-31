---
title: CodeChunkInfo (Estructura)
ms.date: 03/30/2017
api_name:
- CodeChunkInfo
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CodeChunkInfo
helpviewer_keywords:
- CodeChunkInfo structure [.NET Framework debugging]
ms.assetid: 0f482454-8517-48de-ba7a-d7aedab13bb5
topic_type:
- apiref
ms.openlocfilehash: d33c8b31473e389e07fb24076dc32272e9dde387
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132399"
---
# <a name="codechunkinfo-structure"></a><span data-ttu-id="b0d69-102">CodeChunkInfo (Estructura)</span><span class="sxs-lookup"><span data-stu-id="b0d69-102">CodeChunkInfo Structure</span></span>

<span data-ttu-id="b0d69-103">Representa un único fragmento de código en la memoria.</span><span class="sxs-lookup"><span data-stu-id="b0d69-103">Represents a single chunk of code in memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b0d69-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b0d69-104">Syntax</span></span>  
  
```cpp  
typedef struct _CodeChunkInfo {  
    CORDB_ADDRESS startAddr;  
    ULONG32       length;  
} CodeChunkInfo;  
```  
  
## <a name="members"></a><span data-ttu-id="b0d69-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="b0d69-105">Members</span></span>  
  
|<span data-ttu-id="b0d69-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="b0d69-106">Member</span></span>|<span data-ttu-id="b0d69-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="b0d69-107">Description</span></span>|  
|------------|-----------------|  
|`startAddr`|<span data-ttu-id="b0d69-108">`CORDB_ADDRESS` valor que especifica la dirección inicial del fragmento.</span><span class="sxs-lookup"><span data-stu-id="b0d69-108">A `CORDB_ADDRESS` value that specifies the starting address of the chunk.</span></span>|  
|`length`|<span data-ttu-id="b0d69-109">Tamaño, en bytes, del fragmento.</span><span class="sxs-lookup"><span data-stu-id="b0d69-109">The size, in bytes, of the chunk.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b0d69-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="b0d69-110">Remarks</span></span>  
 <span data-ttu-id="b0d69-111">El único fragmento de código es una región de código nativo que forma parte de un objeto de código como una función.</span><span class="sxs-lookup"><span data-stu-id="b0d69-111">The single chunk of code is a region of native code that is part of a code object such as a function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b0d69-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b0d69-112">Requirements</span></span>  
 <span data-ttu-id="b0d69-113">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b0d69-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b0d69-114">**Encabezado:** Cordebug. idl</span><span class="sxs-lookup"><span data-stu-id="b0d69-114">**Header:** CorDebug.idl</span></span>  
  
 <span data-ttu-id="b0d69-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b0d69-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b0d69-116">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b0d69-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b0d69-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="b0d69-117">See also</span></span>

- [<span data-ttu-id="b0d69-118">GetCodeChunks (método)</span><span class="sxs-lookup"><span data-stu-id="b0d69-118">GetCodeChunks Method</span></span>](icordebugcode2-getcodechunks-method.md)
- [<span data-ttu-id="b0d69-119">Estructuras de depuración</span><span class="sxs-lookup"><span data-stu-id="b0d69-119">Debugging Structures</span></span>](debugging-structures.md)
- [<span data-ttu-id="b0d69-120">Depuración</span><span class="sxs-lookup"><span data-stu-id="b0d69-120">Debugging</span></span>](index.md)
