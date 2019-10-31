---
title: CorDebugEHClause (Estructura)
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- CorDebugEHClause
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 0e350a1b-6997-46d0-bfc5-962a5011ef43
topic_type:
- apiref
ms.openlocfilehash: f35e979a5107064d2987a385a989075ef71283ff
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73098858"
---
# <a name="cordebugehclause-structure"></a><span data-ttu-id="c8e5c-102">CorDebugEHClause (Estructura)</span><span class="sxs-lookup"><span data-stu-id="c8e5c-102">CorDebugEHClause Structure</span></span>
<span data-ttu-id="c8e5c-103">[Compatible con .NET Framework 4.5.2 y versiones posteriores]</span><span class="sxs-lookup"><span data-stu-id="c8e5c-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="c8e5c-104">Representa una cláusula de control de excepciones (EH) para una parte determinada de código de lenguaje intermedio (IL).</span><span class="sxs-lookup"><span data-stu-id="c8e5c-104">Represents an exception handling (EH) clause for a given piece of intermediate language (IL) code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c8e5c-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c8e5c-105">Syntax</span></span>  
  
```cpp
typedef struct _CorDebugEHClause {  
   ULONG32 Flags;  
   ULONG32 TryOffset;  
   ULONG32 TryLength;  
   ULONG32 HandlerOffset;  
   ULONG32 HandlerLength;  
   ULONG32 ClassToken;  
   ULONG32 FilterOffset;  
} CorDebugEHClause;  
```  
  
## <a name="members"></a><span data-ttu-id="c8e5c-106">Miembros</span><span class="sxs-lookup"><span data-stu-id="c8e5c-106">Members</span></span>  
  
|<span data-ttu-id="c8e5c-107">Miembro</span><span class="sxs-lookup"><span data-stu-id="c8e5c-107">Member</span></span>|<span data-ttu-id="c8e5c-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="c8e5c-108">Description</span></span>|  
|------------|-----------------|  
|`Flags`|<span data-ttu-id="c8e5c-109">Campo de bits que describe la información de la excepción en la cláusula EH.</span><span class="sxs-lookup"><span data-stu-id="c8e5c-109">A bit field that describes the exception information in the EH clause.</span></span> <span data-ttu-id="c8e5c-110">Para obtener más información, vea la sección Comentarios.</span><span class="sxs-lookup"><span data-stu-id="c8e5c-110">For more information, see the Remarks section.</span></span>|  
|`TryOffset`|<span data-ttu-id="c8e5c-111">Desplazamiento, en bytes, del bloque `try` desde el comienzo del cuerpo del método.</span><span class="sxs-lookup"><span data-stu-id="c8e5c-111">The offset, in bytes, of the `try` block from the start of the method body.</span></span>|  
|`TryLength`|<span data-ttu-id="c8e5c-112">Longitud, en bytes, del bloque `try`.</span><span class="sxs-lookup"><span data-stu-id="c8e5c-112">The length, in bytes, of the `try` block.</span></span>|  
|`HandlerOffset`|<span data-ttu-id="c8e5c-113">Ubicación del controlador para este bloque `try`.</span><span class="sxs-lookup"><span data-stu-id="c8e5c-113">The location of the handler for this `try` block.</span></span>|  
|`HandlerLength`|<span data-ttu-id="c8e5c-114">Tamaño del código de controlador, en bytes.</span><span class="sxs-lookup"><span data-stu-id="c8e5c-114">The size of the handler code in bytes.</span></span>|  
|`ClassToken`|<span data-ttu-id="c8e5c-115">Token de metadatos para un controlador de excepciones basado en tipos.</span><span class="sxs-lookup"><span data-stu-id="c8e5c-115">The metadata token for a type-based exception handler.</span></span>|  
|`FilterOffset`|<span data-ttu-id="c8e5c-116">Desplazamiento, en bytes, desde el principio del cuerpo del método para un controlador de excepciones basado en filtros.</span><span class="sxs-lookup"><span data-stu-id="c8e5c-116">The offset, in bytes, from the start of the method body for a filter-based exception handler.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c8e5c-117">Comentarios</span><span class="sxs-lookup"><span data-stu-id="c8e5c-117">Remarks</span></span>  
 <span data-ttu-id="c8e5c-118">El método [getehclauses (](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode-getehclauses-method.md) devuelve una matriz de valores `CoreDebugEHClause`.</span><span class="sxs-lookup"><span data-stu-id="c8e5c-118">An array of `CoreDebugEHClause` values is returned by the [GetEHClauses](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode-getehclauses-method.md) method.</span></span>  
  
 <span data-ttu-id="c8e5c-119">La información de la cláusula EH se define mediante la especificación de CLI.</span><span class="sxs-lookup"><span data-stu-id="c8e5c-119">The EH clause information is defined by the CLI specification.</span></span> <span data-ttu-id="c8e5c-120">Para obtener más información, consulte [el estándar ECMA-355: Common Language Infrastructure (CLI), 6ª edición](https://www.ecma-international.org/publications/standards/Ecma-335.htm).</span><span class="sxs-lookup"><span data-stu-id="c8e5c-120">For more information, see [Standard ECMA-355: Common Language Infrastructure (CLI), 6th Edition](https://www.ecma-international.org/publications/standards/Ecma-335.htm).</span></span>  
  
 <span data-ttu-id="c8e5c-121">El campo `flags` puede contener las siguientes marcas.</span><span class="sxs-lookup"><span data-stu-id="c8e5c-121">The `flags` field can contain the following flags.</span></span> <span data-ttu-id="c8e5c-122">Tenga en cuenta que no están definidas en CorDebug.idl ni en CorDebug.h.</span><span class="sxs-lookup"><span data-stu-id="c8e5c-122">Note that they are not defined in CorDebug.idl or CorDebug.h.</span></span>  
  
|<span data-ttu-id="c8e5c-123">Marcar</span><span class="sxs-lookup"><span data-stu-id="c8e5c-123">Flag</span></span>|<span data-ttu-id="c8e5c-124">Valor</span><span class="sxs-lookup"><span data-stu-id="c8e5c-124">Value</span></span>|<span data-ttu-id="c8e5c-125">Descripción</span><span class="sxs-lookup"><span data-stu-id="c8e5c-125">Description</span></span>|  
|----------|-----------|-----------------|  
|`COR_ILEXCEPTION_CLAUSE_EXCEPTION`|<span data-ttu-id="c8e5c-126">0x00000000</span><span class="sxs-lookup"><span data-stu-id="c8e5c-126">0x00000000</span></span>|<span data-ttu-id="c8e5c-127">Cláusula de excepción tipada.</span><span class="sxs-lookup"><span data-stu-id="c8e5c-127">A typed exception clause.</span></span>|  
|`COR_ILEXCEPTION_CLAUSE_FILTER`|<span data-ttu-id="c8e5c-128">0x00000001</span><span class="sxs-lookup"><span data-stu-id="c8e5c-128">0x00000001</span></span>|<span data-ttu-id="c8e5c-129">Filtro de excepción y cláusula de controlador.</span><span class="sxs-lookup"><span data-stu-id="c8e5c-129">An exception filter and handler clause.</span></span>|  
|`COR_ILEXCEPTION_CLAUSE_FINALLY`|<span data-ttu-id="c8e5c-130">0x00000002</span><span class="sxs-lookup"><span data-stu-id="c8e5c-130">0x00000002</span></span>|<span data-ttu-id="c8e5c-131">Cláusula `finally`.</span><span class="sxs-lookup"><span data-stu-id="c8e5c-131">A `finally` clause.</span></span>|  
|`COR_ILEXCEPTION_CLAUSE_FAULT`|<span data-ttu-id="c8e5c-132">0x00000004</span><span class="sxs-lookup"><span data-stu-id="c8e5c-132">0x00000004</span></span>|<span data-ttu-id="c8e5c-133">Cláusula fault (cláusula `finally` a la que se llama solo cuando se inicia una excepción).</span><span class="sxs-lookup"><span data-stu-id="c8e5c-133">A fault clause (a `finally` clause that is called only when an exception is thrown).</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c8e5c-134">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c8e5c-134">Requirements</span></span>  
 <span data-ttu-id="c8e5c-135">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c8e5c-135">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c8e5c-136">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c8e5c-136">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c8e5c-137">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c8e5c-137">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c8e5c-138">**Versiones de .NET Framework:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c8e5c-138">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c8e5c-139">Vea también</span><span class="sxs-lookup"><span data-stu-id="c8e5c-139">See also</span></span>

- [<span data-ttu-id="c8e5c-140">GetEHClauses (método)</span><span class="sxs-lookup"><span data-stu-id="c8e5c-140">GetEHClauses Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode-getehclauses-method.md)
- [<span data-ttu-id="c8e5c-141">Estructuras de depuración</span><span class="sxs-lookup"><span data-stu-id="c8e5c-141">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
