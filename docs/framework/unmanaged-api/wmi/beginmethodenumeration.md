---
title: BeginMethodEnumeration (función) (referencia de API no administrada)
description: La función BeginMethodEnumeration comienza una enumeración de los métodos del objeto
ms.date: 11/06/2017
api_name:
- BeginMethodEnumeration
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- BeginMethodEnumeration
helpviewer_keywords:
- BeginMethodEnumeration function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 46ef53acdfa06b0c2be9d2aa55e89ce8fa34dfb0
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67761740"
---
# <a name="beginenumeration-function"></a><span data-ttu-id="5fd42-103">Función BeginEnumeration</span><span class="sxs-lookup"><span data-stu-id="5fd42-103">BeginEnumeration function</span></span>
<span data-ttu-id="5fd42-104">Comienza una enumeración de los métodos disponibles para el objeto.</span><span class="sxs-lookup"><span data-stu-id="5fd42-104">Begins an enumeration of the methods available for the object.</span></span>  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="5fd42-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5fd42-105">Syntax</span></span>  
  
```cpp 
HRESULT BeginMethodEnumeration (
   [in] int               vFunc, 
   [in] IWbemClassObject* ptr, 
   [in] LONG              lEnumFlags
); 
```  

## <a name="parameters"></a><span data-ttu-id="5fd42-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="5fd42-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="5fd42-107">[in] Este parámetro se usa.</span><span class="sxs-lookup"><span data-stu-id="5fd42-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="5fd42-108">[in] Un puntero a un [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instancia.</span><span class="sxs-lookup"><span data-stu-id="5fd42-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`lEnumFlags`  
<span data-ttu-id="5fd42-109">[in] Cero (0) para todos los métodos, o una marca que especifica el ámbito de la enumeración.</span><span class="sxs-lookup"><span data-stu-id="5fd42-109">[in] Zero (0) for all methods, or a flag that specifies the scope of the enumeration.</span></span> <span data-ttu-id="5fd42-110">Las marcas siguientes se definen en el *WbemCli.h* archivo de encabezado, también puede definir como constantes en el código:</span><span class="sxs-lookup"><span data-stu-id="5fd42-110">The following flags are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

<span data-ttu-id="5fd42-111">Constante</span><span class="sxs-lookup"><span data-stu-id="5fd42-111">Constant</span></span>  |<span data-ttu-id="5fd42-112">Valor</span><span class="sxs-lookup"><span data-stu-id="5fd42-112">Value</span></span>  |<span data-ttu-id="5fd42-113">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="5fd42-113">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAG_LOCAL_ONLY` | <span data-ttu-id="5fd42-114">0x10</span><span class="sxs-lookup"><span data-stu-id="5fd42-114">0x10</span></span> | <span data-ttu-id="5fd42-115">Limitar la enumeración a los métodos que se definen en la propia clase.</span><span class="sxs-lookup"><span data-stu-id="5fd42-115">Limit the enumeration to methods that are defined in the class itself.</span></span> |
| `WBEM_FLAG_PROPAGATED_ONLY` |  <span data-ttu-id="5fd42-116">0x20</span><span class="sxs-lookup"><span data-stu-id="5fd42-116">0x20</span></span> | <span data-ttu-id="5fd42-117">Limitar la enumeración de propiedades que se heredan de clases base.</span><span class="sxs-lookup"><span data-stu-id="5fd42-117">Limit the enumeration to properties that are inherited from base classes.</span></span> |

## <a name="return-value"></a><span data-ttu-id="5fd42-118">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="5fd42-118">Return value</span></span>

<span data-ttu-id="5fd42-119">Los siguientes valores devueltos por esta función se definen en el *WbemCli.h* archivo de encabezado, también puede definir como constantes en el código:</span><span class="sxs-lookup"><span data-stu-id="5fd42-119">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="5fd42-120">Constante</span><span class="sxs-lookup"><span data-stu-id="5fd42-120">Constant</span></span>  |<span data-ttu-id="5fd42-121">Value</span><span class="sxs-lookup"><span data-stu-id="5fd42-121">Value</span></span>  |<span data-ttu-id="5fd42-122">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="5fd42-122">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="5fd42-123">0x80041008</span><span class="sxs-lookup"><span data-stu-id="5fd42-123">0x80041008</span></span> | <span data-ttu-id="5fd42-124">`lEnnumFlags` es distinto de cero y no es uno de los marcadores especificados.</span><span class="sxs-lookup"><span data-stu-id="5fd42-124">`lEnnumFlags` is non-zero and is not one of the specified flags.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="5fd42-125">0</span><span class="sxs-lookup"><span data-stu-id="5fd42-125">0</span></span> | <span data-ttu-id="5fd42-126">La llamada de función fue correcta.</span><span class="sxs-lookup"><span data-stu-id="5fd42-126">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="5fd42-127">Comentarios</span><span class="sxs-lookup"><span data-stu-id="5fd42-127">Remarks</span></span>

<span data-ttu-id="5fd42-128">Esta función contiene una llamada a la [IWbemClassObject::BeginMethodEnumeration](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-beginmethodenumeration) método.</span><span class="sxs-lookup"><span data-stu-id="5fd42-128">This function wraps a call to the [IWbemClassObject::BeginMethodEnumeration](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-beginmethodenumeration) method.</span></span>

<span data-ttu-id="5fd42-129">Esta llamada al método solo se admite si el objeto actual es una definición de clase.</span><span class="sxs-lookup"><span data-stu-id="5fd42-129">This method call is only supported if the current object is a class definition.</span></span> <span data-ttu-id="5fd42-130">Manipulación de método no está disponible en [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) punteros que señalan a las instancias.</span><span class="sxs-lookup"><span data-stu-id="5fd42-130">Method manipulation is not available from [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) pointers that point to instances.</span></span> <span data-ttu-id="5fd42-131">Se garantiza el orden en el que se enumeran los métodos invariantes para una instancia determinada de [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject).</span><span class="sxs-lookup"><span data-stu-id="5fd42-131">The order in which methods are enumerated is guaranteed to be invariant for a given instance of [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject).</span></span>

## <a name="requirements"></a><span data-ttu-id="5fd42-132">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5fd42-132">Requirements</span></span>  
 <span data-ttu-id="5fd42-133">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5fd42-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5fd42-134">**Encabezado**: WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="5fd42-134">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="5fd42-135">**Versiones de .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="5fd42-135">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5fd42-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="5fd42-136">See also</span></span>

- [<span data-ttu-id="5fd42-137">WMI y contadores de rendimiento (referencia de API no administrada)</span><span class="sxs-lookup"><span data-stu-id="5fd42-137">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
