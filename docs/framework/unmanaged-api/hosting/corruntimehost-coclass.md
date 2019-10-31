---
title: CorRuntimeHost (Coclase)
ms.date: 03/30/2017
api_name:
- CorRuntimeHost Coclass
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorRuntimeHost
helpviewer_keywords:
- CoRuntimeHost coclass [.NET Framework hosting]
ms.assetid: 5833740b-7d67-44b4-865c-b5bf45e291e3
topic_type:
- apiref
ms.openlocfilehash: 512009e053605e2018f1fcbafa422c1a36ddecc1
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73136906"
---
# <a name="corruntimehost-coclass"></a><span data-ttu-id="ccbcf-102">CorRuntimeHost (Coclase)</span><span class="sxs-lookup"><span data-stu-id="ccbcf-102">CorRuntimeHost Coclass</span></span>
<span data-ttu-id="ccbcf-103">Proporciona interfaces para administrar las aplicaciones que se ejecutan en el Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="ccbcf-103">Provides interfaces for managing applications that are being executed by the common language runtime.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ccbcf-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ccbcf-104">Syntax</span></span>  
  
```cpp  
coclass CorRuntimeHost {  
    [default] interface ICorRuntimeHost;  
    interface IGCHost;  
    interface ICorConfiguration;  
    interface IValidator;  
    interface IDebuggerInfo;  
};  
```  
  
## <a name="interfaces"></a><span data-ttu-id="ccbcf-105">Interfaces</span><span class="sxs-lookup"><span data-stu-id="ccbcf-105">Interfaces</span></span>  
  
|<span data-ttu-id="ccbcf-106">Interfaz</span><span class="sxs-lookup"><span data-stu-id="ccbcf-106">Interface</span></span>|<span data-ttu-id="ccbcf-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="ccbcf-107">Description</span></span>|  
|---------------|-----------------|  
|[<span data-ttu-id="ccbcf-108">ICorConfiguration (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ccbcf-108">ICorConfiguration Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-interface.md)|<span data-ttu-id="ccbcf-109">Proporciona métodos para configurar el Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="ccbcf-109">Provides methods for configuring the common language runtime (CLR).</span></span>|  
|[<span data-ttu-id="ccbcf-110">ICorRuntimeHost (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ccbcf-110">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)|<span data-ttu-id="ccbcf-111">Proporciona métodos que permiten al host iniciar y detener el Common Language Runtime explícitamente, para crear y configurar dominios de aplicación, para tener acceso al dominio predeterminado y para enumerar todos los dominios que se ejecutan en el proceso.</span><span class="sxs-lookup"><span data-stu-id="ccbcf-111">Provides methods that enable the host to start and stop the common language runtime explicitly, to create and configure application domains, to access the default domain, and to enumerate all domains running in the process.</span></span>|  
|[<span data-ttu-id="ccbcf-112">IDebuggerInfo (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ccbcf-112">IDebuggerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/idebuggerinfo-interface.md)|<span data-ttu-id="ccbcf-113">Proporciona métodos para obtener información sobre el estado de los servicios de depuración.</span><span class="sxs-lookup"><span data-stu-id="ccbcf-113">Provides methods for obtaining information about the state of the debugging services.</span></span>|  
|[<span data-ttu-id="ccbcf-114">IGCHost (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ccbcf-114">IGCHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost-interface.md)|<span data-ttu-id="ccbcf-115">Proporciona métodos para obtener información sobre el sistema de recolección de elementos no utilizados y para controlar algunos aspectos de la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="ccbcf-115">Provides methods for obtaining information about the garbage collection system and for controlling some aspects of garbage collection.</span></span>|  
|<span data-ttu-id="ccbcf-116">IValidator</span><span class="sxs-lookup"><span data-stu-id="ccbcf-116">"IValidator"</span></span>|<span data-ttu-id="ccbcf-117">Proporciona métodos para la validación de imágenes ejecutables portables e informes detallados de errores de validación.</span><span class="sxs-lookup"><span data-stu-id="ccbcf-117">Provides methods for validation of portable executable images and detailed reporting of validation errors.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ccbcf-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ccbcf-118">Requirements</span></span>  
 <span data-ttu-id="ccbcf-119">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ccbcf-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ccbcf-120">**Encabezado:** MSCorEE. idl</span><span class="sxs-lookup"><span data-stu-id="ccbcf-120">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="ccbcf-121">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="ccbcf-121">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ccbcf-122">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ccbcf-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ccbcf-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="ccbcf-123">See also</span></span>

- [<span data-ttu-id="ccbcf-124">Coclases para el hospedaje</span><span class="sxs-lookup"><span data-stu-id="ccbcf-124">Hosting Coclasses</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-coclasses.md)
