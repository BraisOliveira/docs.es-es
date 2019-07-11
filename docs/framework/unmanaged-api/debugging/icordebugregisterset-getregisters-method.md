---
title: ICorDebugRegisterSet::GetRegisters (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugRegisterSet.GetRegisters
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugRegisterSet::GetRegisters
helpviewer_keywords:
- GetRegisters method, ICorDebugRegisterSet interface [.NET Framework debugging]
- ICorDebugRegisterSet::GetRegisters method [.NET Framework debugging]
ms.assetid: fdf91864-48ea-4aa6-b70c-361b7a3184c7
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: daee6c46c247bcd21073f779cada8c843947a949
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67747251"
---
# <a name="icordebugregistersetgetregisters-method"></a><span data-ttu-id="de061-102">ICorDebugRegisterSet::GetRegisters (Método)</span><span class="sxs-lookup"><span data-stu-id="de061-102">ICorDebugRegisterSet::GetRegisters Method</span></span>
<span data-ttu-id="de061-103">Obtiene el valor de cada registro (en el equipo que está ejecutando el código) especificado por la máscara de bits.</span><span class="sxs-lookup"><span data-stu-id="de061-103">Gets the value of each register (on the computer that is currently executing code) that is specified by the bit mask.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="de061-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="de061-104">Syntax</span></span>  
  
```cpp  
HRESULT GetRegisters (  
    [in] ULONG64       mask,   
    [in] ULONG32       regCount,  
    [out, size_is(regCount), length_is(regCount)]  
        CORDB_REGISTER regBuffer[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="de061-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="de061-105">Parameters</span></span>  
 `mask`  
 <span data-ttu-id="de061-106">[in] Una máscara de bits que especifica qué registro son los valores van a recuperar.</span><span class="sxs-lookup"><span data-stu-id="de061-106">[in] A bit mask that specifies which register values are to be retrieved.</span></span> <span data-ttu-id="de061-107">Cada bit corresponde a un registro.</span><span class="sxs-lookup"><span data-stu-id="de061-107">Each bit corresponds to a register.</span></span> <span data-ttu-id="de061-108">Si un bit se establece en uno, se recupera el valor del registro; en caso contrario, no se recupera el valor del registro.</span><span class="sxs-lookup"><span data-stu-id="de061-108">If a bit is set to one, the register's value is retrieved; otherwise, the register's value is not retrieved.</span></span>  
  
 `regCount`  
 <span data-ttu-id="de061-109">[in] El número de valores de registro va a recuperar.</span><span class="sxs-lookup"><span data-stu-id="de061-109">[in] The number of register values to be retrieved.</span></span>  
  
 `regBuffer`  
 <span data-ttu-id="de061-110">[out] Una matriz de `CORDB_REGISTER` objetos, cada uno de los cuales recibe un valor de un registro.</span><span class="sxs-lookup"><span data-stu-id="de061-110">[out] An array of `CORDB_REGISTER` objects, each of which receives a value of a register.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="de061-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="de061-111">Remarks</span></span>  
 <span data-ttu-id="de061-112">El tamaño de la matriz debe ser igual al número de bits establecidos en 1 en la máscara de bits.</span><span class="sxs-lookup"><span data-stu-id="de061-112">The size of the array should be equal to the number of bits set to one in the bit mask.</span></span> <span data-ttu-id="de061-113">El `regCount` parámetro especifica el número de elementos en el búfer que recibirá los valores del registro.</span><span class="sxs-lookup"><span data-stu-id="de061-113">The `regCount` parameter specifies the number of elements in the buffer that will receive the register values.</span></span> <span data-ttu-id="de061-114">Si el `regCount` valor es demasiado pequeño para el número de registros indicado por la máscara, se truncarán los registros numerados más altos del conjunto.</span><span class="sxs-lookup"><span data-stu-id="de061-114">If the `regCount` value is too small for the number of registers indicated by the mask, the higher numbered registers will be truncated from the set.</span></span> <span data-ttu-id="de061-115">Si el `regCount` valor es demasiado grande, el sin usar `regBuffer` se modificarán los elementos.</span><span class="sxs-lookup"><span data-stu-id="de061-115">If the `regCount` value is too large, the unused `regBuffer` elements will be unmodified.</span></span>  
  
 <span data-ttu-id="de061-116">Si la máscara de bits especifica un registro que no está disponible, `GetRegisters` devuelve un valor indeterminado para ese registro.</span><span class="sxs-lookup"><span data-stu-id="de061-116">If the bit mask specifies a register that is unavailable, `GetRegisters` returns an indeterminate value for that register.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="de061-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="de061-117">Requirements</span></span>  
 <span data-ttu-id="de061-118">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="de061-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="de061-119">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="de061-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="de061-120">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="de061-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="de061-121">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="de061-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="de061-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="de061-122">See also</span></span>

- [<span data-ttu-id="de061-123">ICorDebugRegisterSet (interfaz)</span><span class="sxs-lookup"><span data-stu-id="de061-123">ICorDebugRegisterSet Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md)
- [<span data-ttu-id="de061-124">ICorDebugRegisterSet2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="de061-124">ICorDebugRegisterSet2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-interface.md)
