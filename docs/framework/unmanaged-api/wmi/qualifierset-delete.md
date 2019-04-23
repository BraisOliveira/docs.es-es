---
title: Función QualifierSet_Delete (referencia de API no administrada)
description: La función QualifierSet_Delete elimina un calificador por su nombre.
ms.date: 11/06/2017
api_name:
- QualifierSet_Delete
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- QualifierSet_Delete
helpviewer_keywords:
- QualifierSet_Delete function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 543cc63b3e2188c11a6a8bf1eaa846461375be99
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59180081"
---
# <a name="qualifiersetdelete-function"></a><span data-ttu-id="f09fb-103">QualifierSet_Delete function</span><span class="sxs-lookup"><span data-stu-id="f09fb-103">QualifierSet_Delete function</span></span>
<span data-ttu-id="f09fb-104">Elimina un calificador específico por el nombre.</span><span class="sxs-lookup"><span data-stu-id="f09fb-104">Deletes a specified qualifier by name.</span></span>  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="f09fb-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f09fb-105">Syntax</span></span>  
  
```  
HRESULT QualifierSet_Delete (
   [in] int                  vFunc, 
   [in] IWbemQualifierSet*   ptr, 
   [in] LPCWSTR              wszName
); 
```  

## <a name="parameters"></a><span data-ttu-id="f09fb-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f09fb-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="f09fb-107">[in] Este parámetro se usa.</span><span class="sxs-lookup"><span data-stu-id="f09fb-107">[in] This parameter is unused.</span></span>

`ptr`   
<span data-ttu-id="f09fb-108">[in] Un puntero a un [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) instancia.</span><span class="sxs-lookup"><span data-stu-id="f09fb-108">[in] A pointer to an [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) instance.</span></span>

`wszName`   
<span data-ttu-id="f09fb-109">[in] El nombre del calificador que se va a eliminar.</span><span class="sxs-lookup"><span data-stu-id="f09fb-109">[in] The name of the qualifier to delete.</span></span>

## <a name="return-value"></a><span data-ttu-id="f09fb-110">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="f09fb-110">Return value</span></span>

<span data-ttu-id="f09fb-111">Los siguientes valores devueltos por esta función se definen en el *WbemCli.h* archivo de encabezado, también puede definir como constantes en el código:</span><span class="sxs-lookup"><span data-stu-id="f09fb-111">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="f09fb-112">Constante</span><span class="sxs-lookup"><span data-stu-id="f09fb-112">Constant</span></span>  |<span data-ttu-id="f09fb-113">Valor</span><span class="sxs-lookup"><span data-stu-id="f09fb-113">Value</span></span>  |<span data-ttu-id="f09fb-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="f09fb-114">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="f09fb-115">0x80041008</span><span class="sxs-lookup"><span data-stu-id="f09fb-115">0x80041008</span></span> | <span data-ttu-id="f09fb-116">El parámetro `wszName` no es válido.</span><span class="sxs-lookup"><span data-stu-id="f09fb-116">The `wszName` parameter is not valid.</span></span> |
|`WBEM_E_INVALID_OPERATION` | <span data-ttu-id="f09fb-117">0x80041016</span><span class="sxs-lookup"><span data-stu-id="f09fb-117">0x80041016</span></span> | <span data-ttu-id="f09fb-118">Eliminar este calificador no es válido.</span><span class="sxs-lookup"><span data-stu-id="f09fb-118">Deleting this qualifier is illegal.</span></span> |
|`WBEM_E_NOT_FOUND` | <span data-ttu-id="f09fb-119">0x80041002</span><span class="sxs-lookup"><span data-stu-id="f09fb-119">0x80041002</span></span> | <span data-ttu-id="f09fb-120">No se encontró el calificador especificado.</span><span class="sxs-lookup"><span data-stu-id="f09fb-120">The specified qualifier was not found.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="f09fb-121">0</span><span class="sxs-lookup"><span data-stu-id="f09fb-121">0</span></span> | <span data-ttu-id="f09fb-122">La llamada de función fue correcta.</span><span class="sxs-lookup"><span data-stu-id="f09fb-122">The function call was successful.</span></span>  |
| `WBEM_S_RESET_TO_DEFAULT` | <span data-ttu-id="f09fb-123">0x40002</span><span class="sxs-lookup"><span data-stu-id="f09fb-123">0x40002</span></span> | <span data-ttu-id="f09fb-124">Se eliminó la invalidación local y el calificador del objeto primario original ha reanudado el ámbito.</span><span class="sxs-lookup"><span data-stu-id="f09fb-124">The local override was deleted and the original qualifier from the parent object has resumed scope.</span></span> |

## <a name="remarks"></a><span data-ttu-id="f09fb-125">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f09fb-125">Remarks</span></span>

<span data-ttu-id="f09fb-126">Esta función contiene una llamada a la [IWbemQualifierSet::Delete](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-delete) método.</span><span class="sxs-lookup"><span data-stu-id="f09fb-126">This function wraps a call to the [IWbemQualifierSet::Delete](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-delete) method.</span></span>

<span data-ttu-id="f09fb-127">Debido a las reglas de propagación de calificador, un calificador determinado puede haberse se hereda de otro objeto y simplemente se reemplaza en la clase o instancia actual.</span><span class="sxs-lookup"><span data-stu-id="f09fb-127">Due to qualifier propagation rules, a particular qualifier may have been inherited from another object and merely overridden in the current class or instance.</span></span> <span data-ttu-id="f09fb-128">En este caso, el `QualifierSet_Delete` método restablece el calificador a su valor original heredado.</span><span class="sxs-lookup"><span data-stu-id="f09fb-128">In this case, the `QualifierSet_Delete` method resets the qualifier to its original inherited value.</span></span> <span data-ttu-id="f09fb-129">En este caso, la función devuelve el código de estado `WBEM_S_RESET_TO_DEFAULT`.</span><span class="sxs-lookup"><span data-stu-id="f09fb-129">The function in this case returns the status code `WBEM_S_RESET_TO_DEFAULT`.</span></span>

## <a name="requirements"></a><span data-ttu-id="f09fb-130">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f09fb-130">Requirements</span></span>  
 <span data-ttu-id="f09fb-131">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f09fb-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f09fb-132">**Encabezado**: WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="f09fb-132">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="f09fb-133">**Versiones de .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="f09fb-133">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f09fb-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="f09fb-134">See also</span></span>

- [<span data-ttu-id="f09fb-135">WMI y contadores de rendimiento (referencia de API no administrada)</span><span class="sxs-lookup"><span data-stu-id="f09fb-135">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
