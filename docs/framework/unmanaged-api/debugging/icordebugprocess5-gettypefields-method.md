---
title: ICorDebugProcess5::GetTypeFields (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugProcess5.GetTypeFields
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess5::GetTypeFields
helpviewer_keywords:
- GetTypeFields method, ICorDebugProcess5 interface [.NET Framework debugging]
- ICorDebugProcess5::GetTypeFields method [.NET Framework debugging]
ms.assetid: 6a0ad3ee-dacb-47e9-abae-4536bcc4804b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7c2725c62105e92996bb2d8e79e8ff504904e9c7
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59107957"
---
# <a name="icordebugprocess5gettypefields-method"></a><span data-ttu-id="bcb09-102">ICorDebugProcess5::GetTypeFields (Método)</span><span class="sxs-lookup"><span data-stu-id="bcb09-102">ICorDebugProcess5::GetTypeFields Method</span></span>
<span data-ttu-id="bcb09-103">Proporciona información sobre los campos que pertenecen a un tipo.</span><span class="sxs-lookup"><span data-stu-id="bcb09-103">Provides information about the fields that belong to a type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bcb09-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="bcb09-104">Syntax</span></span>  
  
```  
HRESULT GetTypeFields(  
    [in] COR_TYPEID id,  
    [in] ULONG32 celt,  
    [out] COR_FIELD fields[],   
    [out] ULONG32 *pceltNeeded  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bcb09-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="bcb09-105">Parameters</span></span>  
 `id`  
 <span data-ttu-id="bcb09-106">[in] El identificador del tipo cuya información de campo se recupera.</span><span class="sxs-lookup"><span data-stu-id="bcb09-106">[in] The identifier of the type whose field information is retrieved.</span></span>  
  
 `celt`  
 <span data-ttu-id="bcb09-107">[in] El número de [COR_FIELD](../../../../docs/framework/unmanaged-api/debugging/cor-field-structure.md) objetos cuya información de campo que se va a recuperar.</span><span class="sxs-lookup"><span data-stu-id="bcb09-107">[in] The number of [COR_FIELD](../../../../docs/framework/unmanaged-api/debugging/cor-field-structure.md) objects whose field information is to be retrieved.</span></span>  
  
 `fields`  
 <span data-ttu-id="bcb09-108">[out] Una matriz de [COR_FIELD](../../../../docs/framework/unmanaged-api/debugging/cor-field-structure.md) objetos que proporcionan información sobre los campos que pertenecen al tipo.</span><span class="sxs-lookup"><span data-stu-id="bcb09-108">[out] An array of [COR_FIELD](../../../../docs/framework/unmanaged-api/debugging/cor-field-structure.md) objects that provide information about the fields that belong to the type.</span></span>  
  
 `pceltNeeded`  
 <span data-ttu-id="bcb09-109">[out] Un puntero al número de [COR_FIELD](../../../../docs/framework/unmanaged-api/debugging/cor-field-structure.md) objetos incluidos en `fields`.</span><span class="sxs-lookup"><span data-stu-id="bcb09-109">[out] A pointer to the number of [COR_FIELD](../../../../docs/framework/unmanaged-api/debugging/cor-field-structure.md) objects included in `fields`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bcb09-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="bcb09-110">Remarks</span></span>  
 <span data-ttu-id="bcb09-111">El `celt` parámetro, que especifica el número de campos cuya información de campo, el método se usa para rellenar `fields`, debe corresponder al valor de la `COR_TYPE_LAYOUT::numFields` campo.</span><span class="sxs-lookup"><span data-stu-id="bcb09-111">The `celt` parameter, which specifies the number of fields whose field information the method uses to populate `fields`, should correspond to the value of the `COR_TYPE_LAYOUT::numFields` field.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bcb09-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="bcb09-112">Requirements</span></span>  
 <span data-ttu-id="bcb09-113">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bcb09-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bcb09-114">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="bcb09-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="bcb09-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bcb09-115">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="bcb09-116">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="bcb09-116">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="bcb09-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="bcb09-117">See also</span></span>

- [<span data-ttu-id="bcb09-118">ICorDebugProcess5 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="bcb09-118">ICorDebugProcess5 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md)
- [<span data-ttu-id="bcb09-119">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="bcb09-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
