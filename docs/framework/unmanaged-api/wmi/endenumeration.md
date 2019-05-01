---
title: EndEnumeration (función) (referencia de API no administrada)
description: La función EndEnumeration finaliza una enumeración.
ms.date: 11/06/2017
api_name:
- EndEnumeration
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- EndEnumeration
helpviewer_keywords:
- EndEnumeration function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 65904da9efea90d31960d71ae0da8c81dffeccf1
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62000472"
---
# <a name="endenumeration-function"></a><span data-ttu-id="ac2b6-103">Función EndEnumeration</span><span class="sxs-lookup"><span data-stu-id="ac2b6-103">EndEnumeration function</span></span>

<span data-ttu-id="ac2b6-104">Finaliza una secuencia de enumeración que se inició con una llamada a la [BeginEnumeration (función)](beginenumeration.md).</span><span class="sxs-lookup"><span data-stu-id="ac2b6-104">Terminates an enumeration sequence started with a call to the [BeginEnumeration function](beginenumeration.md).</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="ac2b6-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ac2b6-105">Syntax</span></span>

```cpp
HRESULT EndEnumeration (
   [in] int               vFunc,
   [in] IWbemClassObject* ptr
);
```

## <a name="parameters"></a><span data-ttu-id="ac2b6-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ac2b6-106">Parameters</span></span>

`vFunc`\
<span data-ttu-id="ac2b6-107">[in] Este parámetro se usa.</span><span class="sxs-lookup"><span data-stu-id="ac2b6-107">[in] This parameter is unused.</span></span>

`ptr`\
<span data-ttu-id="ac2b6-108">[in] Un puntero a un [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instancia.</span><span class="sxs-lookup"><span data-stu-id="ac2b6-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

## <a name="return-value"></a><span data-ttu-id="ac2b6-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="ac2b6-109">Return value</span></span>

<span data-ttu-id="ac2b6-110">Los siguientes valores devueltos por esta función se definen en el *WbemCli.h* archivo de encabezado, también puede definir como constantes en el código:</span><span class="sxs-lookup"><span data-stu-id="ac2b6-110">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="ac2b6-111">Constante</span><span class="sxs-lookup"><span data-stu-id="ac2b6-111">Constant</span></span>  |<span data-ttu-id="ac2b6-112">Valor</span><span class="sxs-lookup"><span data-stu-id="ac2b6-112">Value</span></span>  |<span data-ttu-id="ac2b6-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="ac2b6-113">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_FAILED` | <span data-ttu-id="ac2b6-114">0x80041001</span><span class="sxs-lookup"><span data-stu-id="ac2b6-114">0x80041001</span></span> | <span data-ttu-id="ac2b6-115">Ha habido un error general.</span><span class="sxs-lookup"><span data-stu-id="ac2b6-115">There has been a general failure.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="ac2b6-116">0</span><span class="sxs-lookup"><span data-stu-id="ac2b6-116">0</span></span> | <span data-ttu-id="ac2b6-117">La llamada de función fue correcta.</span><span class="sxs-lookup"><span data-stu-id="ac2b6-117">The function call was successful.</span></span>  |

## <a name="remarks"></a><span data-ttu-id="ac2b6-118">Comentarios</span><span class="sxs-lookup"><span data-stu-id="ac2b6-118">Remarks</span></span>

<span data-ttu-id="ac2b6-119">Esta función contiene una llamada a la [IWbemClassObject::EndEnumeration](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) método.</span><span class="sxs-lookup"><span data-stu-id="ac2b6-119">This function wraps a call to the [IWbemClassObject::EndEnumeration](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) method.</span></span>

<span data-ttu-id="ac2b6-120">Una llamada a la `EndEnumeration` función no es necesaria, pero se recomienda porque lo libera los recursos asociados a la enumeración.</span><span class="sxs-lookup"><span data-stu-id="ac2b6-120">A call to the `EndEnumeration` function is not required, but it is recommended because it releases resources associated with the enumeration.</span></span> <span data-ttu-id="ac2b6-121">Sin embargo, los recursos se desasignan automáticamente cuando se inicia la enumeración siguiente o se libera el objeto.</span><span class="sxs-lookup"><span data-stu-id="ac2b6-121">However, the resources are deallocated automatically when the next enumeration is started or the object is released.</span></span>

## <a name="requirements"></a><span data-ttu-id="ac2b6-122">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ac2b6-122">Requirements</span></span>

<span data-ttu-id="ac2b6-123">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ac2b6-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="ac2b6-124">**Encabezado**: WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="ac2b6-124">**Header:** WMINet_Utils.idl</span></span>

<span data-ttu-id="ac2b6-125">**Versiones de .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="ac2b6-125">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="ac2b6-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="ac2b6-126">See also</span></span>

- [<span data-ttu-id="ac2b6-127">WMI y contadores de rendimiento (referencia de API no administrada)</span><span class="sxs-lookup"><span data-stu-id="ac2b6-127">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)