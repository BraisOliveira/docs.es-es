---
title: AXL_AUTHENTICODE_TIMESTAMPER_INFO (Estructura)
ms.date: 03/30/2017
ms.assetid: 89e41a81-0f41-45ad-8f20-a120e4ff24fb
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ae7879e1f6598108d839287792ed441391764ae2
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70776649"
---
# <a name="axl_authenticode_timestamper_info-structure"></a><span data-ttu-id="6153e-102">AXL_AUTHENTICODE_TIMESTAMPER_INFO (Estructura)</span><span class="sxs-lookup"><span data-stu-id="6153e-102">AXL_AUTHENTICODE_TIMESTAMPER_INFO Structure</span></span>
<span data-ttu-id="6153e-103">Define la información del autor de la marca de hora de Authenticode.</span><span class="sxs-lookup"><span data-stu-id="6153e-103">Defines the Authenticode time stamper information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6153e-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6153e-104">Syntax</span></span>  
  
```cpp  
typedef struct _AXL_AUTHENTICODE_SIGNER_INFO {  
    DWORD cbSize;  
    HRESULT dwError;  
    ALG_ID algHash;  
    FILETIME ftTimestamp  
    PCCERT_CHAIN_CONTEXT pChainContext;  
} AXL_AUTHENTICODE_TIMESTAMPER_INFO, * PAXL_AUTHENTICODE_TIMESTAMPER_INFO;  
```  
  
## <a name="members"></a><span data-ttu-id="6153e-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="6153e-105">Members</span></span>  
  
|<span data-ttu-id="6153e-106">Member</span><span class="sxs-lookup"><span data-stu-id="6153e-106">Member</span></span>|<span data-ttu-id="6153e-107">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="6153e-107">Description</span></span>|  
|------------|-----------------|  
|`cbSize`|<span data-ttu-id="6153e-108">Tamaño de esta estructura.</span><span class="sxs-lookup"><span data-stu-id="6153e-108">The size of this structure.</span></span>|  
|`dwError`|<span data-ttu-id="6153e-109">Código de error.</span><span class="sxs-lookup"><span data-stu-id="6153e-109">The error code.</span></span>|  
|`algHash`|<span data-ttu-id="6153e-110">Algoritmo hash.</span><span class="sxs-lookup"><span data-stu-id="6153e-110">The hash algorithm.</span></span>|  
|`ftTimestamp`|<span data-ttu-id="6153e-111">Hora de la marca de hora.</span><span class="sxs-lookup"><span data-stu-id="6153e-111">The time of the time stamp.</span></span>|  
|`pChainContext`|<span data-ttu-id="6153e-112">Contexto de cadena del autor de la marca de hora.</span><span class="sxs-lookup"><span data-stu-id="6153e-112">The time stamper’s chain context.</span></span>  <span data-ttu-id="6153e-113">Vea la estructura [CERT_CONTEXT](/windows/win32/api/wincrypt/ns-wincrypt-cert_context) .</span><span class="sxs-lookup"><span data-stu-id="6153e-113">See the [CERT_CONTEXT](/windows/win32/api/wincrypt/ns-wincrypt-cert_context) structure.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6153e-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="6153e-114">See also</span></span>

- [<span data-ttu-id="6153e-115">Authenticode</span><span class="sxs-lookup"><span data-stu-id="6153e-115">Authenticode</span></span>](index.md)
