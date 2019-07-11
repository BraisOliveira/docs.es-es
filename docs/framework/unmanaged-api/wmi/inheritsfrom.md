---
title: Función InheritsFrom (referencia de API no administrada)
description: La función InheritsFrom determina si una instancia o clase se deriva de una clase primaria determinada.
ms.date: 11/06/2017
api_name:
- InheritsFrom
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- InheritsFrom
helpviewer_keywords:
- InheritsFrom function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5c04a08c9712359453b9c5a9d136e22e1de8648a
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67746512"
---
# <a name="inheritsfrom-function"></a><span data-ttu-id="29856-103">Función InheritsFrom</span><span class="sxs-lookup"><span data-stu-id="29856-103">InheritsFrom function</span></span>
<span data-ttu-id="29856-104">Determina si la clase o instancia actual deriva de una clase principal especificada.</span><span class="sxs-lookup"><span data-stu-id="29856-104">Determines whether the current class or instance derives from a specified parent class.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="29856-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="29856-105">Syntax</span></span>  
  
```cpp
HRESULT InheritsFrom (
   [in] int               vFunc, 
   [in] IWbemClassObject* ptr, 
   [in] LPCWSTR           wszAncestor 
); 
```  

## <a name="parameters"></a><span data-ttu-id="29856-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="29856-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="29856-107">[in] Este parámetro se usa.</span><span class="sxs-lookup"><span data-stu-id="29856-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="29856-108">[in] Un puntero a un [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instancia.</span><span class="sxs-lookup"><span data-stu-id="29856-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`wszAncestor`  
<span data-ttu-id="29856-109">[in] El nombre de la clase.</span><span class="sxs-lookup"><span data-stu-id="29856-109">[in] The name of the class.</span></span> <span data-ttu-id="29856-110">`wszAncestor` debe apuntar a una `LPCWSTR`.</span><span class="sxs-lookup"><span data-stu-id="29856-110">`wszAncestor` must point to a valid `LPCWSTR`.</span></span>

## <a name="return-value"></a><span data-ttu-id="29856-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="29856-111">Return value</span></span>

<span data-ttu-id="29856-112">Los siguientes valores devueltos por esta función se definen en el *WbemCli.h* archivo de encabezado, también puede definir como constantes en el código:</span><span class="sxs-lookup"><span data-stu-id="29856-112">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="29856-113">Constante</span><span class="sxs-lookup"><span data-stu-id="29856-113">Constant</span></span>  |<span data-ttu-id="29856-114">Valor</span><span class="sxs-lookup"><span data-stu-id="29856-114">Value</span></span>  |<span data-ttu-id="29856-115">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="29856-115">Description</span></span>  |
|---------|---------|---------|
| `WBEM_S_NO_ERROR` | <span data-ttu-id="29856-116">0</span><span class="sxs-lookup"><span data-stu-id="29856-116">0</span></span> | <span data-ttu-id="29856-117">El objeto actual se hereda de `wszAncestor`.</span><span class="sxs-lookup"><span data-stu-id="29856-117">The current object inherits from `wszAncestor`.</span></span>  |
| `WBEM_S_FALSE` | <span data-ttu-id="29856-118">1</span><span class="sxs-lookup"><span data-stu-id="29856-118">1</span></span> | <span data-ttu-id="29856-119">El objeto actual no hereda de `wszAncestor`.</span><span class="sxs-lookup"><span data-stu-id="29856-119">The current object does not inherit from `wszAncestor`.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="29856-120">0x80041008</span><span class="sxs-lookup"><span data-stu-id="29856-120">0x80041008</span></span> | <span data-ttu-id="29856-121">El valor de `wszAncestor` es `null`.</span><span class="sxs-lookup"><span data-stu-id="29856-121">`wszAncestor` is `null`.</span></span> |
  
## <a name="remarks"></a><span data-ttu-id="29856-122">Comentarios</span><span class="sxs-lookup"><span data-stu-id="29856-122">Remarks</span></span>

<span data-ttu-id="29856-123">Esta función contiene una llamada a la [IWbemClassObject::InheritsFrom](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-inheritsfrom) método.</span><span class="sxs-lookup"><span data-stu-id="29856-123">This function wraps a call to the [IWbemClassObject::InheritsFrom](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-inheritsfrom) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="29856-124">Requisitos</span><span class="sxs-lookup"><span data-stu-id="29856-124">Requirements</span></span>  
 <span data-ttu-id="29856-125">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="29856-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="29856-126">**Encabezado**: WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="29856-126">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="29856-127">**Versiones de .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="29856-127">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="29856-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="29856-128">See also</span></span>

- [<span data-ttu-id="29856-129">WMI y contadores de rendimiento (referencia de API no administrada)</span><span class="sxs-lookup"><span data-stu-id="29856-129">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
