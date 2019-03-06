---
title: Función GetPropertyQualifierSet (referencia de API no administrada)
description: La función GetPropertyQualifierSet recupera el calificador establecido para una propiedad.
ms.date: 11/06/2017
api_name:
- GetPropertyQualifierSet
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- GetPropertyQualifierSet
helpviewer_keywords:
- GetPropertyQualifierSet function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cdb9f748279e4e74c0dbd1ced1f48e3a24b9904d
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2019
ms.locfileid: "57358423"
---
# <a name="getpropertyqualifierset-function"></a><span data-ttu-id="cfada-103">Función GetPropertyQualifierSet</span><span class="sxs-lookup"><span data-stu-id="cfada-103">GetPropertyQualifierSet function</span></span>

<span data-ttu-id="cfada-104">Recupera el calificador establecido para una propiedad específica.</span><span class="sxs-lookup"><span data-stu-id="cfada-104">Retrieves the qualifier set for a particular property.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="cfada-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="cfada-105">Syntax</span></span>

```cpp
HRESULT GetPropertyQualifierSet (
   [in] int                 vFunc,
   [in] IWbemClassObject*   ptr,
   [in] LPCWSTR             wszProperty,
   [out] IWbemQualifierSet  **ppQualSet
);
```

## <a name="parameters"></a><span data-ttu-id="cfada-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="cfada-106">Parameters</span></span>

`vFunc`\
<span data-ttu-id="cfada-107">[in] Este parámetro se usa.</span><span class="sxs-lookup"><span data-stu-id="cfada-107">[in] This parameter is unused.</span></span>

`ptr`\
<span data-ttu-id="cfada-108">[in] Un puntero a un [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instancia.</span><span class="sxs-lookup"><span data-stu-id="cfada-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`wszMethod`\
<span data-ttu-id="cfada-109">[in] El nombre de propiedad.</span><span class="sxs-lookup"><span data-stu-id="cfada-109">[in] The property  name.</span></span> <span data-ttu-id="cfada-110">`wszProperty` debe apuntar a una `LPCWSTR`.</span><span class="sxs-lookup"><span data-stu-id="cfada-110">`wszProperty` must point to a valid `LPCWSTR`.</span></span>

`ppQualSet`\
<span data-ttu-id="cfada-111">[out] Recibe el puntero de interfaz que permite el acceso a los calificadores de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="cfada-111">[out] Receives the interface pointer that allows access to the qualifiers of the property.</span></span> <span data-ttu-id="cfada-112">El valor de `ppQualSet` no puede ser `null`.</span><span class="sxs-lookup"><span data-stu-id="cfada-112">`ppQualSet` cannot be `null`.</span></span> <span data-ttu-id="cfada-113">Si se produce un error, no se devuelve un nuevo objeto y el puntero se establece para que apunte a `null`.</span><span class="sxs-lookup"><span data-stu-id="cfada-113">If an error occurs, a new object is not returned, and the pointer is set to point to `null`.</span></span>

## <a name="return-value"></a><span data-ttu-id="cfada-114">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="cfada-114">Return value</span></span>

<span data-ttu-id="cfada-115">Los siguientes valores devueltos por esta función se definen en el *WbemCli.h* archivo de encabezado, también puede definir como constantes en el código:</span><span class="sxs-lookup"><span data-stu-id="cfada-115">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="cfada-116">Constante</span><span class="sxs-lookup"><span data-stu-id="cfada-116">Constant</span></span>  |<span data-ttu-id="cfada-117">Valor</span><span class="sxs-lookup"><span data-stu-id="cfada-117">Value</span></span>  |<span data-ttu-id="cfada-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="cfada-118">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_FAILED` | <span data-ttu-id="cfada-119">0x80041001</span><span class="sxs-lookup"><span data-stu-id="cfada-119">0x80041001</span></span> | <span data-ttu-id="cfada-120">Ha habido un error general.</span><span class="sxs-lookup"><span data-stu-id="cfada-120">There has been a general failure.</span></span> |
| `WBEM_E_NOT_FOUND` | <span data-ttu-id="cfada-121">0x80041002</span><span class="sxs-lookup"><span data-stu-id="cfada-121">0x80041002</span></span> | <span data-ttu-id="cfada-122">El método especificado no existe.</span><span class="sxs-lookup"><span data-stu-id="cfada-122">The specified method does not exist.</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="cfada-123">0x80041006</span><span class="sxs-lookup"><span data-stu-id="cfada-123">0x80041006</span></span> | <span data-ttu-id="cfada-124">No hay suficiente memoria disponible para completar la operación.</span><span class="sxs-lookup"><span data-stu-id="cfada-124">Not enough memory is available to complete the operation.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="cfada-125">0x80041008</span><span class="sxs-lookup"><span data-stu-id="cfada-125">0x80041008</span></span> | <span data-ttu-id="cfada-126">Es un parámetro `null`.</span><span class="sxs-lookup"><span data-stu-id="cfada-126">A parameter is `null`.</span></span> |
| `WBEM_E_SYSTEM_PROPERTY` | <span data-ttu-id="cfada-127">0x80041030</span><span class="sxs-lookup"><span data-stu-id="cfada-127">0x80041030</span></span> | <span data-ttu-id="cfada-128">La función intenta obtener calificadores de una propiedad del sistema.</span><span class="sxs-lookup"><span data-stu-id="cfada-128">The function attempts to get qualifiers of a system property.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="cfada-129">0</span><span class="sxs-lookup"><span data-stu-id="cfada-129">0</span></span> | <span data-ttu-id="cfada-130">La llamada de función fue correcta.</span><span class="sxs-lookup"><span data-stu-id="cfada-130">The function call was successful.</span></span>  |

## <a name="remarks"></a><span data-ttu-id="cfada-131">Comentarios</span><span class="sxs-lookup"><span data-stu-id="cfada-131">Remarks</span></span>

<span data-ttu-id="cfada-132">Esta función contiene una llamada a la [IWbemClassObject::GetPropertyQualifierSet](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getpropertyqualifierset) método.</span><span class="sxs-lookup"><span data-stu-id="cfada-132">This function wraps a call to the [IWbemClassObject::GetPropertyQualifierSet](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getpropertyqualifierset) method.</span></span>

<span data-ttu-id="cfada-133">Una llamada a esta función solo se admite si el objeto actual es una definición de clase CIM.</span><span class="sxs-lookup"><span data-stu-id="cfada-133">A call to this function is supported only if the current object is a CIM class definition.</span></span> <span data-ttu-id="cfada-134">No está disponible para la manipulación de los métodos [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) punteros que señalan a las instancias CIM.</span><span class="sxs-lookup"><span data-stu-id="cfada-134">Method manipulation is not available for [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) pointers that point to CIM instances.</span></span>

<span data-ttu-id="cfada-135">Dado que cada método puede tener su propio calificadores, el [IWbemQualifierSet puntero](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) permite al llamador agregar, editar o eliminar estos calificadores.</span><span class="sxs-lookup"><span data-stu-id="cfada-135">Because each method may have its own qualifiers, the [IWbemQualifierSet pointer](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) lets the caller add, edit, or delete these qualifiers.</span></span>

<span data-ttu-id="cfada-136">Dado que las propiedades del sistema no tengan ningún calificador, la función devuelve `WBEM_E_SYSTEM_PROPERTY` si se intenta obtener un [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) puntero para una propiedad del sistema.</span><span class="sxs-lookup"><span data-stu-id="cfada-136">Because system properties have no qualifiers, the function returns `WBEM_E_SYSTEM_PROPERTY` if you attempt to obtain a [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) pointer for a system property.</span></span>

## <a name="requirements"></a><span data-ttu-id="cfada-137">Requisitos</span><span class="sxs-lookup"><span data-stu-id="cfada-137">Requirements</span></span>

<span data-ttu-id="cfada-138">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cfada-138">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="cfada-139">**Encabezado**: WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="cfada-139">**Header:** WMINet_Utils.idl</span></span>

<span data-ttu-id="cfada-140">**Versiones de .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="cfada-140">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="cfada-141">Vea también</span><span class="sxs-lookup"><span data-stu-id="cfada-141">See also</span></span>

- [<span data-ttu-id="cfada-142">WMI y contadores de rendimiento (referencia de API no administrada)</span><span class="sxs-lookup"><span data-stu-id="cfada-142">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)