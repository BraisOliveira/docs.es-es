---
title: Función NextMethod (referencia de API no administrada)
description: La función NextMethod recupera el siguiente método en una enumeración.
ms.date: 11/06/2017
api_name:
- NextMethod
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- NextMethod
helpviewer_keywords:
- NextMethod function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2b3667f7371131a4c1394ba5ca619d1f605c89ce
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62000186"
---
# <a name="nextmethod-function"></a><span data-ttu-id="f7531-103">Función NextMethod</span><span class="sxs-lookup"><span data-stu-id="f7531-103">NextMethod function</span></span>
<span data-ttu-id="f7531-104">Recupera el siguiente método en una enumeración que comienza con una llamada a [BeginMethodEnumeration](beginmethodenumeration.md).</span><span class="sxs-lookup"><span data-stu-id="f7531-104">Retrieves the next method in an enumeration that begins with a call to [BeginMethodEnumeration](beginmethodenumeration.md).</span></span>  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="f7531-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f7531-105">Syntax</span></span>  
  
```  
HRESULT NextMethod (
   [in] int                 vFunc, 
   [in] IWbemClassObject*   ptr, 
   [in] LONG                lFlags,
   [out] BSTR*              pName,
   [out] IWbemClassObject** ppInSignature,
   [out] IWbemClassObject** ppOutSignature   
); 
```  

## <a name="parameters"></a><span data-ttu-id="f7531-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f7531-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="f7531-107">[in] Este parámetro se usa.</span><span class="sxs-lookup"><span data-stu-id="f7531-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="f7531-108">[in] Un puntero a un [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instancia.</span><span class="sxs-lookup"><span data-stu-id="f7531-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`lFlags`  
<span data-ttu-id="f7531-109">[in] Reservado.</span><span class="sxs-lookup"><span data-stu-id="f7531-109">[in] Reserved.</span></span> <span data-ttu-id="f7531-110">Este parámetro debe ser 0.</span><span class="sxs-lookup"><span data-stu-id="f7531-110">This parameter must be 0.</span></span>

`pName`  
<span data-ttu-id="f7531-111">[out] Un puntero que señala a `null` antes de la llamada.</span><span class="sxs-lookup"><span data-stu-id="f7531-111">[out] A pointer that points to `null` prior to the call.</span></span> <span data-ttu-id="f7531-112">Cuando se devuelve la función, la dirección de un nuevo `BSTR` que contiene el nombre del método.</span><span class="sxs-lookup"><span data-stu-id="f7531-112">When the function returns, the address of a new `BSTR` that contains the method name.</span></span> 

`ppSignatureIn`  
<span data-ttu-id="f7531-113">[out] Un puntero que recibe un puntero a un [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) que contiene el `in` parámetros del método.</span><span class="sxs-lookup"><span data-stu-id="f7531-113">[out] A pointer that receives a pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) that contains the `in` parameters for the method.</span></span> 

`ppSignatureOut`  
<span data-ttu-id="f7531-114">[out] Un puntero que recibe un puntero a un [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) que contiene el `out` parámetros del método.</span><span class="sxs-lookup"><span data-stu-id="f7531-114">[out] A pointer that receives a pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) that contains the `out` parameters for the method.</span></span> 

## <a name="return-value"></a><span data-ttu-id="f7531-115">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="f7531-115">Return value</span></span>

<span data-ttu-id="f7531-116">Los siguientes valores devueltos por esta función se definen en el *WbemCli.h* archivo de encabezado, también puede definir como constantes en el código:</span><span class="sxs-lookup"><span data-stu-id="f7531-116">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="f7531-117">Constante</span><span class="sxs-lookup"><span data-stu-id="f7531-117">Constant</span></span>  |<span data-ttu-id="f7531-118">Valor</span><span class="sxs-lookup"><span data-stu-id="f7531-118">Value</span></span>  |<span data-ttu-id="f7531-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="f7531-119">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_UNEXPECTED` | <span data-ttu-id="f7531-120">0x8004101d</span><span class="sxs-lookup"><span data-stu-id="f7531-120">0x8004101d</span></span> | <span data-ttu-id="f7531-121">Se ha producido ninguna llamada a la [ `BeginEnumeration` ](beginenumeration.md) función.</span><span class="sxs-lookup"><span data-stu-id="f7531-121">There was no call to the [`BeginEnumeration`](beginenumeration.md) function.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="f7531-122">0</span><span class="sxs-lookup"><span data-stu-id="f7531-122">0</span></span> | <span data-ttu-id="f7531-123">La llamada de función fue correcta.</span><span class="sxs-lookup"><span data-stu-id="f7531-123">The function call was successful.</span></span>  |
| `WBEM_S_NO_MORE_DATA` | <span data-ttu-id="f7531-124">0x40005</span><span class="sxs-lookup"><span data-stu-id="f7531-124">0x40005</span></span> | <span data-ttu-id="f7531-125">No hay ninguna propiedad más en la enumeración.</span><span class="sxs-lookup"><span data-stu-id="f7531-125">There are no more properties in the enumeration.</span></span> |
  
## <a name="remarks"></a><span data-ttu-id="f7531-126">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f7531-126">Remarks</span></span>

<span data-ttu-id="f7531-127">Esta función contiene una llamada a la [IWbemClassObject::NextMethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-nextmethod) método.</span><span class="sxs-lookup"><span data-stu-id="f7531-127">This function wraps a call to the [IWbemClassObject::NextMethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-nextmethod) method.</span></span>

<span data-ttu-id="f7531-128">El llamador inicia la secuencia de enumeración al llamar a la [BeginMethodEnumeration](beginmethodenumeration.md) función y, a continuación, llama a la función [NextMethod] hasta que la función devuelve `WBEM_S_NO_MORE_DATA`.</span><span class="sxs-lookup"><span data-stu-id="f7531-128">The caller begins the enumeration sequence by calling the [BeginMethodEnumeration](beginmethodenumeration.md) function, and then calls the [NextMethod] function until the function returns `WBEM_S_NO_MORE_DATA`.</span></span> <span data-ttu-id="f7531-129">Si lo desea, el llamador finaliza la secuencia mediante una llamada a [EndMethodEnumeration](endmethodenumeration.md).</span><span class="sxs-lookup"><span data-stu-id="f7531-129">Optionally, the caller finishes the sequence by calling [EndMethodEnumeration](endmethodenumeration.md).</span></span> <span data-ttu-id="f7531-130">El llamador puede finalizar la enumeración al principio mediante una llamada a [EndMethodEnumeration](endmethodenumeration.md) en cualquier momento.</span><span class="sxs-lookup"><span data-stu-id="f7531-130">The caller may terminate the enumeration early by calling [EndMethodEnumeration](endmethodenumeration.md) at any time.</span></span>

## <a name="example"></a><span data-ttu-id="f7531-131">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f7531-131">Example</span></span>

<span data-ttu-id="f7531-132">Para obtener un ejemplo de C++, vea el [IWbemClassObject::NextMethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-nextmethod) método.</span><span class="sxs-lookup"><span data-stu-id="f7531-132">For a C++ example, see the [IWbemClassObject::NextMethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-nextmethod) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="f7531-133">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f7531-133">Requirements</span></span>  
 <span data-ttu-id="f7531-134">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f7531-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f7531-135">**Encabezado**: WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="f7531-135">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="f7531-136">**Versiones de .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="f7531-136">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f7531-137">Vea también</span><span class="sxs-lookup"><span data-stu-id="f7531-137">See also</span></span>

- [<span data-ttu-id="f7531-138">WMI y contadores de rendimiento (referencia de API no administrada)</span><span class="sxs-lookup"><span data-stu-id="f7531-138">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
