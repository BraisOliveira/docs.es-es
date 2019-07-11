---
title: Función GetErrorInfo (referencia de API no administrada)
description: La función GetErrorInfo recupera información de error de la llamada de función anterior.
ms.date: 11/06/2017
api_name:
- GetErrorInfo
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- GetErrorInfo
helpviewer_keywords:
- GetErrorInfo function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e33a18487da420eb3b317bb70e0ac9e68b4b8ad6
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67746541"
---
# <a name="geterrorinfo-function"></a><span data-ttu-id="2f702-103">GetErrorInfo (función)</span><span class="sxs-lookup"><span data-stu-id="2f702-103">GetErrorInfo function</span></span>
<span data-ttu-id="2f702-104">Recupera información sobre el error de la llamada de función anterior.</span><span class="sxs-lookup"><span data-stu-id="2f702-104">Retrieves error information from the previous function call.</span></span>  
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="2f702-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2f702-105">Syntax</span></span>  
  
```cpp  
IErrorInfo* GetErrorInfo(); 
```  

## <a name="return-value"></a><span data-ttu-id="2f702-106">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="2f702-106">Return value</span></span>

<span data-ttu-id="2f702-107">Un puntero a un [IErrorInfo](https://docs.microsoft.com/previous-versions/windows/desktop/api/oaidl/nn-oaidl-ierrorinfo) objeto si la llamada de función se realiza correctamente, o `null` si se produce un error.</span><span class="sxs-lookup"><span data-stu-id="2f702-107">An pointer to an [IErrorInfo](https://docs.microsoft.com/previous-versions/windows/desktop/api/oaidl/nn-oaidl-ierrorinfo) object if the function call succeeds, or `null` if it fails.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="2f702-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="2f702-108">Remarks</span></span>

<span data-ttu-id="2f702-109">Esta función contiene una llamada a la [IComThreadingInfo::GetErrorInfo](/windows/desktop/api/objidlbase/nf-objidlbase-icomthreadinginfo-getcurrentapartmenttype) método.</span><span class="sxs-lookup"><span data-stu-id="2f702-109">This function wraps a call to the [IComThreadingInfo::GetErrorInfo](/windows/desktop/api/objidlbase/nf-objidlbase-icomthreadinginfo-getcurrentapartmenttype) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="2f702-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2f702-110">Requirements</span></span>  
 <span data-ttu-id="2f702-111">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2f702-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2f702-112">**Encabezado**: WMINet_Utils.def</span><span class="sxs-lookup"><span data-stu-id="2f702-112">**Header:** WMINet_Utils.def</span></span>  
  
 <span data-ttu-id="2f702-113">**Versiones de .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="2f702-113">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2f702-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="2f702-114">See also</span></span>

- [<span data-ttu-id="2f702-115">WMI y contadores de rendimiento (referencia de API no administrada)</span><span class="sxs-lookup"><span data-stu-id="2f702-115">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
