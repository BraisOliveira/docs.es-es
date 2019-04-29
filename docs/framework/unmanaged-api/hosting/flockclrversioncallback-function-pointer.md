---
title: puntero a la función FLockClrVersionCallback
ms.date: 03/30/2017
api_name:
- FLockClrVersionCallback
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- FLockClrVersionCallback
helpviewer_keywords:
- FLockClrVersionCallback function pointer [.NET Framework hosting]
ms.assetid: 98a4762d-9ad2-45bd-9d03-39064a028b44
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8062ab151efc6175aa68cb0563cd2ad042ee9cd8
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61628021"
---
# <a name="flockclrversioncallback-function-pointer"></a><span data-ttu-id="2c831-102">puntero a la función FLockClrVersionCallback</span><span class="sxs-lookup"><span data-stu-id="2c831-102">FLockClrVersionCallback Function Pointer</span></span>
<span data-ttu-id="2c831-103">Señala una función que las llamadas de runtime (CLR) de lenguaje común para indicar que la inicialización se ha iniciado o completado.</span><span class="sxs-lookup"><span data-stu-id="2c831-103">Points to a function that the common language runtime (CLR) calls to indicate that initialization has either started or completed.</span></span>  
  
 <span data-ttu-id="2c831-104">Este puntero de función ha quedado obsoleto en la [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2c831-104">This function pointer has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2c831-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2c831-105">Syntax</span></span>  
  
```  
typedef HRESULT (__stdcall *FLockClrVersionCallback) ( );  
```  
  
## <a name="remarks"></a><span data-ttu-id="2c831-106">Comentarios</span><span class="sxs-lookup"><span data-stu-id="2c831-106">Remarks</span></span>  
 <span data-ttu-id="2c831-107">Esta función se implementa el host.</span><span class="sxs-lookup"><span data-stu-id="2c831-107">This function is implemented by the host.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2c831-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2c831-108">Requirements</span></span>  
 <span data-ttu-id="2c831-109">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2c831-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2c831-110">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="2c831-110">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="2c831-111">**Biblioteca:** MSCorWks.dll</span><span class="sxs-lookup"><span data-stu-id="2c831-111">**Library:** MSCorWks.dll</span></span>  
  
 <span data-ttu-id="2c831-112">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2c831-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2c831-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="2c831-113">See also</span></span>

- [<span data-ttu-id="2c831-114">LockClrVersion (Función)</span><span class="sxs-lookup"><span data-stu-id="2c831-114">LockClrVersion Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/lockclrversion-function.md)
- [<span data-ttu-id="2c831-115">Funciones de hospedaje de CLR en desuso</span><span class="sxs-lookup"><span data-stu-id="2c831-115">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
