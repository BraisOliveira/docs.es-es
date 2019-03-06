---
title: Función QualifierSet_GetNames (referencia de API no administrada)
description: La función QualifierSet_GetNames recupera los nombres de los calificadores de un objeto o propiedad.
ms.date: 11/06/2017
api_name:
- QualifierSet_GetNames
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- QualifierSet_GetNames
helpviewer_keywords:
- QualifierSet_GetNames function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: da6321e50082c3f73477b8187cc5bf671655df21
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2019
ms.locfileid: "57365950"
---
# <a name="qualifiersetgetnames-function"></a><span data-ttu-id="99253-103">Función QualifierSet_GetNames</span><span class="sxs-lookup"><span data-stu-id="99253-103">QualifierSet_GetNames function</span></span>

<span data-ttu-id="99253-104">Recupera los nombres de todos los calificadores o de ciertos calificadores que están disponibles en el objeto actual o la propiedad.</span><span class="sxs-lookup"><span data-stu-id="99253-104">Retrieves the names of all the qualifiers or of certain qualifiers that are available from the current object or property.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="99253-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="99253-105">Syntax</span></span>

```cpp
HRESULT QualifierSet_GetNames (
   [in] int                  vFunc,
   [in] IWbemQualifierSet*   ptr,
   [in] LONG                 lFlags,
   [out] SAFEARRAY (BSTR)**  pstrNames
);
```

## <a name="parameters"></a><span data-ttu-id="99253-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="99253-106">Parameters</span></span>

`vFunc`\
<span data-ttu-id="99253-107">[in] Este parámetro se usa.</span><span class="sxs-lookup"><span data-stu-id="99253-107">[in] This parameter is unused.</span></span>

`ptr`\
<span data-ttu-id="99253-108">[in] Un puntero a un [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) instancia.</span><span class="sxs-lookup"><span data-stu-id="99253-108">[in] A pointer to an [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) instance.</span></span>

`lFlags`\
<span data-ttu-id="99253-109">[in] Uno de los siguientes indicadores o valores que especifica los nombres que se va a incluir en la enumeración.</span><span class="sxs-lookup"><span data-stu-id="99253-109">[in] One of the following flags or values that specifies which names to include in the enumeration.</span></span>

|<span data-ttu-id="99253-110">Constante</span><span class="sxs-lookup"><span data-stu-id="99253-110">Constant</span></span>  |<span data-ttu-id="99253-111">Valor</span><span class="sxs-lookup"><span data-stu-id="99253-111">Value</span></span>  |<span data-ttu-id="99253-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="99253-112">Description</span></span>  |
|---------|---------|---------|
|  | <span data-ttu-id="99253-113">0</span><span class="sxs-lookup"><span data-stu-id="99253-113">0</span></span> | <span data-ttu-id="99253-114">Devuelve los nombres de todos los calificadores.</span><span class="sxs-lookup"><span data-stu-id="99253-114">Return the names of all qualifiers.</span></span> |
| `WBEM_FLAG_LOCAL_ONLY` | <span data-ttu-id="99253-115">0x10</span><span class="sxs-lookup"><span data-stu-id="99253-115">0x10</span></span> | <span data-ttu-id="99253-116">Devolver solo los nombres de los calificadores específicos que el objeto o propiedad actual.</span><span class="sxs-lookup"><span data-stu-id="99253-116">Return only the names of qualifiers specific to the current property or object.</span></span> <br/> <span data-ttu-id="99253-117">Para una propiedad: Devolver solo los calificadores específicos de la propiedad (incluidas las invalidaciones) y no los calificadores propagados desde la definición de clase.</span><span class="sxs-lookup"><span data-stu-id="99253-117">For a property: Return only the qualifiers specific to the property (including overrides), and not those qualifiers propagated from the class definition.</span></span> <br/> <span data-ttu-id="99253-118">Para una instancia: Devolver solo los nombres de calificador específicos de la instancia.</span><span class="sxs-lookup"><span data-stu-id="99253-118">For an instance: Return only instance-specific qualifier names.</span></span> <br/> <span data-ttu-id="99253-119">Para una clase: Devolver solo los calificadores específica a la clase que se deriva.</span><span class="sxs-lookup"><span data-stu-id="99253-119">For a class: Return only qualifiers specific to the class being derived.</span></span>
|`WBEM_FLAG_PROPAGATED_ONLY` | <span data-ttu-id="99253-120">0x20</span><span class="sxs-lookup"><span data-stu-id="99253-120">0x20</span></span> | <span data-ttu-id="99253-121">Si la devolución propagan los nombres de los calificadores de otro objeto.</span><span class="sxs-lookup"><span data-stu-id="99253-121">Return only the names of qualifiers propagated from another object.</span></span> <br/> <span data-ttu-id="99253-122">Para una propiedad: Si la devolución solo los calificadores se propagan a esta propiedad desde la definición de clase y no los de la propiedad propiamente dicha.</span><span class="sxs-lookup"><span data-stu-id="99253-122">For a property: Return only the qualifiers propagated to this property from the class definition, and not those from the property itself.</span></span> <br/> <span data-ttu-id="99253-123">Para una instancia: Si la devolución solo esos calificadores se propagan desde la definición de clase.</span><span class="sxs-lookup"><span data-stu-id="99253-123">For an instance: Return only those qualifiers propagated from the class definition.</span></span> <br/> <span data-ttu-id="99253-124">Para una clase: Si la devolución solo esos nombres calificador heredados de las clases principales.</span><span class="sxs-lookup"><span data-stu-id="99253-124">For a class: Return only those qualifier names inherited from the parent classes.</span></span> |

`pstrNames`\
<span data-ttu-id="99253-125">[out] Un nuevo `SAFEARRAY` que contiene los nombres solicitados.</span><span class="sxs-lookup"><span data-stu-id="99253-125">[out] A new `SAFEARRAY` that contains the requested names.</span></span> <span data-ttu-id="99253-126">La matriz puede tener 0 elementos.</span><span class="sxs-lookup"><span data-stu-id="99253-126">The array can have 0 elements.</span></span> <span data-ttu-id="99253-127">Si se produce un error, un nuevo `SAFEARRAY` no se devuelve.</span><span class="sxs-lookup"><span data-stu-id="99253-127">If an error occurs, a new `SAFEARRAY` is not returned.</span></span>

## <a name="return-value"></a><span data-ttu-id="99253-128">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="99253-128">Return value</span></span>

<span data-ttu-id="99253-129">Los siguientes valores devueltos por esta función se definen en el *WbemCli.h* archivo de encabezado, también puede definir como constantes en el código:</span><span class="sxs-lookup"><span data-stu-id="99253-129">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="99253-130">Constante</span><span class="sxs-lookup"><span data-stu-id="99253-130">Constant</span></span>  |<span data-ttu-id="99253-131">Valor</span><span class="sxs-lookup"><span data-stu-id="99253-131">Value</span></span>  |<span data-ttu-id="99253-132">Descripción</span><span class="sxs-lookup"><span data-stu-id="99253-132">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="99253-133">0x80041008</span><span class="sxs-lookup"><span data-stu-id="99253-133">0x80041008</span></span> | <span data-ttu-id="99253-134">Un parámetro no es válido.</span><span class="sxs-lookup"><span data-stu-id="99253-134">A parameter is not valid.</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="99253-135">0x80041006</span><span class="sxs-lookup"><span data-stu-id="99253-135">0x80041006</span></span> | <span data-ttu-id="99253-136">No hay suficiente memoria disponible para comenzar una nueva enumeración.</span><span class="sxs-lookup"><span data-stu-id="99253-136">Not enough memory is available to begin a new enumeration.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="99253-137">0</span><span class="sxs-lookup"><span data-stu-id="99253-137">0</span></span> | <span data-ttu-id="99253-138">La llamada de función fue correcta.</span><span class="sxs-lookup"><span data-stu-id="99253-138">The function call was successful.</span></span>  |

## <a name="remarks"></a><span data-ttu-id="99253-139">Comentarios</span><span class="sxs-lookup"><span data-stu-id="99253-139">Remarks</span></span>

<span data-ttu-id="99253-140">Esta función contiene una llamada a la [IWbemQualifierSet::GetNames](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-getnames) método.</span><span class="sxs-lookup"><span data-stu-id="99253-140">This function wraps a call to the [IWbemQualifierSet::GetNames](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-getnames) method.</span></span>

<span data-ttu-id="99253-141">Una vez que haya recuperado los nombres de calificador, puede acceder a cada calificador por nombre mediante una llamada a la [QualifierSet_Get](qualifierset-get.md) función.</span><span class="sxs-lookup"><span data-stu-id="99253-141">Once you've retrieved the qualifier names, you can access each qualifier by name by calling the [QualifierSet_Get](qualifierset-get.md) function.</span></span>

<span data-ttu-id="99253-142">No es un error para un objeto determinado tener calificadores de cero, por lo que el número de cadenas en `pstrNames` en el valor devuelto puede ser 0, aunque la función devuelve `WBEM_S_NO_ERROR`.</span><span class="sxs-lookup"><span data-stu-id="99253-142">It is not an error for a given object to have zero qualifiers, so the number of strings in `pstrNames` on return can be 0, even though the function returns `WBEM_S_NO_ERROR`.</span></span>

## <a name="requirements"></a><span data-ttu-id="99253-143">Requisitos</span><span class="sxs-lookup"><span data-stu-id="99253-143">Requirements</span></span>

<span data-ttu-id="99253-144">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="99253-144">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="99253-145">**Encabezado**: WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="99253-145">**Header:** WMINet_Utils.idl</span></span>

<span data-ttu-id="99253-146">**Versiones de .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="99253-146">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="99253-147">Vea también</span><span class="sxs-lookup"><span data-stu-id="99253-147">See also</span></span>

- [<span data-ttu-id="99253-148">WMI y contadores de rendimiento (referencia de API no administrada)</span><span class="sxs-lookup"><span data-stu-id="99253-148">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)