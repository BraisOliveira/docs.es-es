---
title: ECustomDumpFlavor (Enumeración)
ms.date: 03/30/2017
api_name:
- ECustomDumpFlavor
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ECustomDumpFlavor
helpviewer_keywords:
- ECustomDumpFlavor enumeration [.NET Framework hosting]
ms.assetid: b39b3320-fac7-41f1-9a03-ab6fb0cd89c7
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d1e69d9cbf39049e82803d2f7bc795cc9fd0b368
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59154445"
---
# <a name="ecustomdumpflavor-enumeration"></a><span data-ttu-id="40dba-102">ECustomDumpFlavor (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="40dba-102">ECustomDumpFlavor Enumeration</span></span>
<span data-ttu-id="40dba-103">Contiene valores que indican qué elementos desea incluir en un subconjunto de un montón personalizado de volcado de memoria al informar de errores.</span><span class="sxs-lookup"><span data-stu-id="40dba-103">Contains values that indicate which items to include in a custom subset of a heap dump when reporting errors.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="40dba-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="40dba-104">Syntax</span></span>  
  
```  
typedef enum {  
    DUMP_FLAVOR_Mini            = 1,  
    DUMP_FLAVOR_NonHeapCLRState = 2  
} ECustomDumpFlavor;  
```  
  
## <a name="members"></a><span data-ttu-id="40dba-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="40dba-105">Members</span></span>  
  
|<span data-ttu-id="40dba-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="40dba-106">Member</span></span>|<span data-ttu-id="40dba-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="40dba-107">Description</span></span>|  
|------------|-----------------|  
|`DUMP_FLAVOR_Mini`|<span data-ttu-id="40dba-108">Especifica que el volcado del montón personalizado debe iniciarse como minivolcado e incluir datos adicionales que se especificó ninguno [CustomDumpItem](../../../../docs/framework/unmanaged-api/hosting/customdumpitem-structure.md) las instancias que se pasan al mismo método.</span><span class="sxs-lookup"><span data-stu-id="40dba-108">Specifies that the custom heap dump should start as a minidump and include extra data specified by any [CustomDumpItem](../../../../docs/framework/unmanaged-api/hosting/customdumpitem-structure.md) instances passed to the same method.</span></span>|  
|`DUMP_FLAVOR_NonHeapCLRState`|<span data-ttu-id="40dba-109">Especifica que el volcado del montón personalizado debe recopilar todos los datos de estado de tiempo de ejecución que no se ha asignado dinámicamente.</span><span class="sxs-lookup"><span data-stu-id="40dba-109">Specifies that the custom heap dump should gather all run-time state data that was not dynamically allocated.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="40dba-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="40dba-110">Remarks</span></span>  
 <span data-ttu-id="40dba-111">Un parámetro de tipo `ECustomDumpFlavor` se pasa a la [ICLRErrorReportingManager:: BeginCustomDump](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-begincustomdump-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="40dba-111">A parameter of type `ECustomDumpFlavor` is passed to the [ICLRErrorReportingManager::BeginCustomDump](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-begincustomdump-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="40dba-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="40dba-112">Requirements</span></span>  
 <span data-ttu-id="40dba-113">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="40dba-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="40dba-114">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="40dba-114">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="40dba-115">**Biblioteca:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="40dba-115">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="40dba-116">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="40dba-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="40dba-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="40dba-117">See also</span></span>

- [<span data-ttu-id="40dba-118">ECustomDumpItemKind (enumeración)</span><span class="sxs-lookup"><span data-stu-id="40dba-118">ECustomDumpItemKind Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/ecustomdumpitemkind-enumeration.md)
- [<span data-ttu-id="40dba-119">ICLRErrorReportingManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="40dba-119">ICLRErrorReportingManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-interface.md)
- [<span data-ttu-id="40dba-120">Enumeraciones para hosts</span><span class="sxs-lookup"><span data-stu-id="40dba-120">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
