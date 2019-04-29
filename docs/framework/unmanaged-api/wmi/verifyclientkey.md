---
title: Función VerifyClientKey (referencia de API no administrada)
description: La función VerifyClientKey garantiza que la clave de cliente tiene la seguridad correcta.
ms.date: 11/06/2017
api_name:
- VerifyClientKey
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- VerifyClientKey
helpviewer_keywords:
- VerifyClientKey function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 47fee26a0c4c25e4bff5bca94e5e26daaf98cccd
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61782491"
---
# <a name="verifyclientkey-function"></a><span data-ttu-id="98ecd-103">Función VerifyClientKey</span><span class="sxs-lookup"><span data-stu-id="98ecd-103">VerifyClientKey function</span></span>
<span data-ttu-id="98ecd-104">Garantiza que la clave de cliente cuenta con la seguridad adecuada.</span><span class="sxs-lookup"><span data-stu-id="98ecd-104">Ensures that the client key has the correct security.</span></span>  
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="98ecd-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="98ecd-105">Syntax</span></span>  
  
```  
LONG VerifyClientKey(); 
```  

## <a name="return-value"></a><span data-ttu-id="98ecd-106">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="98ecd-106">Return value</span></span>

<span data-ttu-id="98ecd-107">Si la función se realiza correctamente, el valor devuelto es `ERROR_SUCCESS` (0).</span><span class="sxs-lookup"><span data-stu-id="98ecd-107">If the function succeeds, the return value is `ERROR_SUCCESS` (0).</span></span>

<span data-ttu-id="98ecd-108">Si se produce un error en la función, el valor devuelto es un código de error distinto de cero definido en *WinError.h*.</span><span class="sxs-lookup"><span data-stu-id="98ecd-108">If the function fails, the return value is a non-zero error code defined in *WinError.h*.</span></span>

## <a name="requirements"></a><span data-ttu-id="98ecd-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="98ecd-109">Requirements</span></span>  
 <span data-ttu-id="98ecd-110">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="98ecd-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="98ecd-111">**Encabezado**: WMINet_Utils.def</span><span class="sxs-lookup"><span data-stu-id="98ecd-111">**Header:** WMINet_Utils.def</span></span>  
  
 <span data-ttu-id="98ecd-112">**Versiones de .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="98ecd-112">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="98ecd-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="98ecd-113">See also</span></span>

- [<span data-ttu-id="98ecd-114">WMI y contadores de rendimiento (referencia de API no administrada)</span><span class="sxs-lookup"><span data-stu-id="98ecd-114">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
