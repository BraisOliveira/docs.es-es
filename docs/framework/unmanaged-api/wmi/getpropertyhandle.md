---
title: GetPropertyHandle (función) (referencia de API no administrada)
description: GetPropertyHandle (función) devuelve un identificador único que identifica una propiedad.
ms.date: 11/06/2017
api_name:
- GetPropertyHandle
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- GetPropertyHandle
helpviewer_keywords:
- GetPropertyHandle function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 92d48caf7de873850135c7410a5e4b5861131212
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2019
ms.locfileid: "57366379"
---
# <a name="getpropertyhandle-function"></a><span data-ttu-id="b4cc7-103">GetPropertyHandle (función)</span><span class="sxs-lookup"><span data-stu-id="b4cc7-103">GetPropertyHandle function</span></span>

<span data-ttu-id="b4cc7-104">Devuelve un controlador único que identifica una propiedad.</span><span class="sxs-lookup"><span data-stu-id="b4cc7-104">Returns a unique handle that identifies a property.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="b4cc7-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b4cc7-105">Syntax</span></span>

```cpp
HRESULT GetPropertyHandle (
   [in] int                  vFunc,
   [in] IWbemObjectAccess*   ptr,
   [in] LPCWSTR              wszPropertyName,
   [out] CIMTYPE*            pType,
   [out] long*               pHandle
);
```

## <a name="parameters"></a><span data-ttu-id="b4cc7-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="b4cc7-106">Parameters</span></span>

`vFunc`\
<span data-ttu-id="b4cc7-107">[in] Este parámetro se usa.</span><span class="sxs-lookup"><span data-stu-id="b4cc7-107">[in] This parameter is unused.</span></span>

`ptr`\
<span data-ttu-id="b4cc7-108">[in] Un puntero a un [IWbemObjectAccess](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemobjectaccess) instancia.</span><span class="sxs-lookup"><span data-stu-id="b4cc7-108">[in] A pointer to an [IWbemObjectAccess](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemobjectaccess) instance.</span></span>

`wszPropertyName`\
<span data-ttu-id="b4cc7-109">[in] Una-cadena terminada en null de caracteres codificados UTF16 que contiene el nombre de propiedad.</span><span class="sxs-lookup"><span data-stu-id="b4cc7-109">[in] A null-terminated string of UTF16-encoded characters that contains the property name.</span></span>

`pType`\
<span data-ttu-id="b4cc7-110">[out] Un puntero a un [ `CIMTYPE` ](/windows/desktop/api/wbemcli/ne-wbemcli-tag_cimtype_enumeration) miembro de enumeración que representa el tipo CIM de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="b4cc7-110">[out] A pointer to a [`CIMTYPE`](/windows/desktop/api/wbemcli/ne-wbemcli-tag_cimtype_enumeration) enumeration member that represents the CIM type of the property.</span></span>

`pHandle`\
<span data-ttu-id="b4cc7-111">[out] Un puntero a un entero que contiene el identificador de propiedad.</span><span class="sxs-lookup"><span data-stu-id="b4cc7-111">[out] A pointer to an integer that contains the property handle.</span></span>

## <a name="return-value"></a><span data-ttu-id="b4cc7-112">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="b4cc7-112">Return value</span></span>

<span data-ttu-id="b4cc7-113">Los siguientes valores devueltos por esta función se definen en el *WbemCli.h* archivo de encabezado, también puede definir como constantes en el código:</span><span class="sxs-lookup"><span data-stu-id="b4cc7-113">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="b4cc7-114">Constante</span><span class="sxs-lookup"><span data-stu-id="b4cc7-114">Constant</span></span>  |<span data-ttu-id="b4cc7-115">Valor</span><span class="sxs-lookup"><span data-stu-id="b4cc7-115">Value</span></span>  |<span data-ttu-id="b4cc7-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="b4cc7-116">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_NOT_FOUND` | <span data-ttu-id="b4cc7-117">0x80041002</span><span class="sxs-lookup"><span data-stu-id="b4cc7-117">0x80041002</span></span> | <span data-ttu-id="b4cc7-118">No se encontró el nombre de propiedad especificado.</span><span class="sxs-lookup"><span data-stu-id="b4cc7-118">The specified property name was not found.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="b4cc7-119">0x80041008</span><span class="sxs-lookup"><span data-stu-id="b4cc7-119">0x80041008</span></span> | <span data-ttu-id="b4cc7-120">Un parámetro no es válido.</span><span class="sxs-lookup"><span data-stu-id="b4cc7-120">A parameter is not valid.</span></span> |
|`WBEM_E_NOT_SUPPORTED` | <span data-ttu-id="b4cc7-121">0x8004100c</span><span class="sxs-lookup"><span data-stu-id="b4cc7-121">0x8004100c</span></span> | <span data-ttu-id="b4cc7-122">La propiedad solicitada es de tipo son `CIM_OBJECT` o `CIM_ARRAY`.</span><span class="sxs-lookup"><span data-stu-id="b4cc7-122">The requested property is of type are `CIM_OBJECT` or `CIM_ARRAY`.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="b4cc7-123">0</span><span class="sxs-lookup"><span data-stu-id="b4cc7-123">0</span></span> | <span data-ttu-id="b4cc7-124">La llamada de función fue correcta.</span><span class="sxs-lookup"><span data-stu-id="b4cc7-124">The function call was successful.</span></span>  |

## <a name="remarks"></a><span data-ttu-id="b4cc7-125">Comentarios</span><span class="sxs-lookup"><span data-stu-id="b4cc7-125">Remarks</span></span>

<span data-ttu-id="b4cc7-126">Esta función contiene una llamada a la [IWbemClassObject::GetPropertyHandle](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemobjectaccess-getpropertyhandle) método.</span><span class="sxs-lookup"><span data-stu-id="b4cc7-126">This function wraps a call to the [IWbemClassObject::GetPropertyHandle](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemobjectaccess-getpropertyhandle) method.</span></span>

<span data-ttu-id="b4cc7-127">Puede usar este identificador para identificar las propiedades cuando se usa [IWbemObjectAccess](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemobjectaccess) métodos para leer o escribir los valores de propiedad.</span><span class="sxs-lookup"><span data-stu-id="b4cc7-127">You can use this handle to identify properties when using  [IWbemObjectAccess](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemobjectaccess) methods to read or write property values.</span></span>

<span data-ttu-id="b4cc7-128">Identificadores se pueden recuperar de las propiedades de todos los tipos de datos distinto `CIM_OBJECT` y `CIM_ARRAY`.</span><span class="sxs-lookup"><span data-stu-id="b4cc7-128">Handles can be retrieved for properties of all data types other than `CIM_OBJECT` and `CIM_ARRAY`.</span></span> <span data-ttu-id="b4cc7-129">Devuelve el trabajo de identificadores en todas las instancias de una clase.</span><span class="sxs-lookup"><span data-stu-id="b4cc7-129">Returned handles work across all instances of a class.</span></span>

## <a name="requirements"></a><span data-ttu-id="b4cc7-130">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b4cc7-130">Requirements</span></span>

<span data-ttu-id="b4cc7-131">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b4cc7-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="b4cc7-132">**Encabezado**: WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="b4cc7-132">**Header:** WMINet_Utils.idl</span></span>

<span data-ttu-id="b4cc7-133">**Versiones de .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="b4cc7-133">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="b4cc7-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="b4cc7-134">See also</span></span>

- [<span data-ttu-id="b4cc7-135">WMI y contadores de rendimiento (referencia de API no administrada)</span><span class="sxs-lookup"><span data-stu-id="b4cc7-135">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)