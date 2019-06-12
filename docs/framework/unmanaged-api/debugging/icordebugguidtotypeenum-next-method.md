---
title: ICorDebugGuidToTypeEnum::Next (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugGuidToTypeEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugGuidToTypeEnum::Next
helpviewer_keywords:
- ICorDebugGuidToTypeEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugGuidToTypeEnum interface [.NET Framework debugging]
ms.assetid: c9937666-8e18-484d-9fe0-b9ac95199530
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 160ddbf9be8eb9f3b99d159aa8b36a22b58a9f55
ms.sourcegitcommit: 5bc85ad81d96b8dc2a90ce53bada475ee5662c44
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/12/2019
ms.locfileid: "67025812"
---
# <a name="icordebugguidtotypeenumnext-method"></a><span data-ttu-id="a7544-102">ICorDebugGuidToTypeEnum::Next (Método)</span><span class="sxs-lookup"><span data-stu-id="a7544-102">ICorDebugGuidToTypeEnum::Next Method</span></span>
<span data-ttu-id="a7544-103">Obtiene el número especificado de [CorDebugGuidToTypeMapping](../../../../docs/framework/unmanaged-api/debugging/cordebugguidtotypemapping-structure.md) instancias que se asignan los GUID para escribir información.</span><span class="sxs-lookup"><span data-stu-id="a7544-103">Gets the specified number of [CorDebugGuidToTypeMapping](../../../../docs/framework/unmanaged-api/debugging/cordebugguidtotypemapping-structure.md) instances that map GUIDs to type information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a7544-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a7544-104">Syntax</span></span>  
  
```  
HRESULT Next(  
    [in] ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched] CorDebugGuidToTypeMapping values[  ],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a7544-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a7544-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="a7544-106">[in] El número de objetos de asignación del tipo de GUID va a recuperar.</span><span class="sxs-lookup"><span data-stu-id="a7544-106">[in] The number of GUID-to-type mapping objects to be retrieved.</span></span>  
  
 `values`  
 <span data-ttu-id="a7544-107">[out] Una matriz de punteros, cada uno de los cuales señala a un [CorDebugGuidToTypeMapping](../../../../docs/framework/unmanaged-api/debugging/cordebugguidtotypemapping-structure.md) objeto que asigna un GUID en tiempo de ejecución de Windows a su objeto ICorDebugType correspondiente.</span><span class="sxs-lookup"><span data-stu-id="a7544-107">[out] An array of pointers, each of which points to a [CorDebugGuidToTypeMapping](../../../../docs/framework/unmanaged-api/debugging/cordebugguidtotypemapping-structure.md) object that maps a Windows Runtime GUID to its corresponding ICorDebugType object.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="a7544-108">[out] Un puntero al número de [CorDebugGuidToTypeMapping](../../../../docs/framework/unmanaged-api/debugging/cordebugguidtotypemapping-structure.md) los objetos devueltos realmente en `values`.</span><span class="sxs-lookup"><span data-stu-id="a7544-108">[out] A pointer to the number of [CorDebugGuidToTypeMapping](../../../../docs/framework/unmanaged-api/debugging/cordebugguidtotypemapping-structure.md) objects actually returned in `values`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a7544-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a7544-109">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a7544-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a7544-110">Requirements</span></span>  
 <span data-ttu-id="a7544-111">**Plataformas:** Windows en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="a7544-111">**Platforms:** Windows Runtime</span></span>  
  
 <span data-ttu-id="a7544-112">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a7544-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a7544-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a7544-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a7544-114">**Versiones de .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a7544-114">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a7544-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="a7544-115">See also</span></span>

- [<span data-ttu-id="a7544-116">ICorDebugGuidToTypeEnum (interfaz)</span><span class="sxs-lookup"><span data-stu-id="a7544-116">ICorDebugGuidToTypeEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugguidtotypeenum-interface.md)
- [<span data-ttu-id="a7544-117">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="a7544-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
