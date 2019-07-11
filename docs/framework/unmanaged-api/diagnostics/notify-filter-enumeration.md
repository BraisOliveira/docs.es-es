---
title: NOTIFY_FILTER (Enumeración)
ms.date: 03/30/2017
api_name:
- NOTIFY_FILTER
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- NOTIFY_FILTER
helpviewer_keywords:
- NOTIFY_FILTER enumeration [.NET Framework debugging]
ms.assetid: 4789d08f-8683-45d3-ac30-73d48c61e470
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 09c36dd65c8a4202f13d362668f74cd9a362e35a
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67744359"
---
# <a name="notifyfilter-enumeration"></a><span data-ttu-id="ee4f2-102">NOTIFY_FILTER (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="ee4f2-102">NOTIFY_FILTER Enumeration</span></span>
<span data-ttu-id="ee4f2-103">Identifica las devoluciones de llamada para las funciones del depurador.</span><span class="sxs-lookup"><span data-stu-id="ee4f2-103">Identifies callbacks for debugger functions.</span></span> <span data-ttu-id="ee4f2-104">Para obtener más información, consulte el [INotifySource2:: SetNotifyFilter](../../../../docs/framework/unmanaged-api/diagnostics/inotifysource2-setnotifyfilter-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="ee4f2-104">For more information, see the [INotifySource2::SetNotifyFilter](../../../../docs/framework/unmanaged-api/diagnostics/inotifysource2-setnotifyfilter-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ee4f2-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ee4f2-105">Syntax</span></span>  
  
```cpp  
enum tagNOTIFY_FILTER  
{  
    NOTIFY_FILTER_ONSYNCCALLOUT    = 0x1,  
    NOTIFY_FILTER_ONSYNCCALLENTER  = 0x2,  
    NOTIFY_FILTER_ONSYNCCALLEXIT   = 0x4,  
    NOTIFY_FILTER_ONSYNCCALLRETURN = 0x8,  
    NOTIFY_FILTER_ALLSYNC = NOTIFY_FILTER_ONSYNCCALLOUT | NOTIFY_FILTER_ONSYNCCALLENTER | NOTIFY_FILTER_ONSYNCCALLEXIT | NOTIFY_FILTER_ONSYNCCALLRETURN,  
    NOTIFY_FILTER_ALL              = 0xffffffff,  
    NOTIFY_FILTER_NONE             = 0  
};  
```  
  
## <a name="members"></a><span data-ttu-id="ee4f2-106">Miembros</span><span class="sxs-lookup"><span data-stu-id="ee4f2-106">Members</span></span>  
  
|<span data-ttu-id="ee4f2-107">Member</span><span class="sxs-lookup"><span data-stu-id="ee4f2-107">Member</span></span>|<span data-ttu-id="ee4f2-108">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="ee4f2-108">Description</span></span>|  
|------------|-----------------|  
|`NOTIFY_FILTER_ONSYNCCALLOUT`|<span data-ttu-id="ee4f2-109">Indica que el [Inotifysink2](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-onsynccallout-method.md) se debe invocar el método.</span><span class="sxs-lookup"><span data-stu-id="ee4f2-109">Indicates that the [INotifySink2::OnSyncCallOut](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-onsynccallout-method.md) method should be invoked.</span></span>|  
|`NOTIFY_FILTER_ONSYNCCALLENTER`|<span data-ttu-id="ee4f2-110">Indica que el [Inotifysink2](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-onsynccallenter-method.md) se debe invocar el método.</span><span class="sxs-lookup"><span data-stu-id="ee4f2-110">Indicates that the [INotifySink2::OnSyncCallEnter](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-onsynccallenter-method.md) method should be invoked.</span></span>|  
|`NOTIFY_FILTER_ONSYNCCALLEXIT`|<span data-ttu-id="ee4f2-111">Indica que el [Inotifysink2](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-onsynccallexit-method.md) se debe invocar el método.</span><span class="sxs-lookup"><span data-stu-id="ee4f2-111">Indicates that the [INotifySink2::OnSyncCallExit](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-onsynccallexit-method.md) method should be invoked.</span></span>|  
|`NOTIFY_FILTER_ONSYNCCALLRETURN`|<span data-ttu-id="ee4f2-112">Indica que el [Inotifysink2](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-onsynccallreturn-method.md) se debe invocar el método.</span><span class="sxs-lookup"><span data-stu-id="ee4f2-112">Indicates that the [INotifySink2::OnSyncCallReturn](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-onsynccallreturn-method.md) method should be invoked.</span></span>|  
|`NOTIFY_FILTER_ALLSYNC`|<span data-ttu-id="ee4f2-113">Indica que todos los [INotifySink2](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-interface.md) se deben invocar métodos.</span><span class="sxs-lookup"><span data-stu-id="ee4f2-113">Indicates that all of the [INotifySink2](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-interface.md) methods should be invoked.</span></span>|  
|`NOTIFY_FILTER_ALL`|<span data-ttu-id="ee4f2-114">Activa todas las notificaciones existentes y futuras.</span><span class="sxs-lookup"><span data-stu-id="ee4f2-114">Activates all existing and future notifications.</span></span>|  
|`NOTIFY_FILTER_NONE`|<span data-ttu-id="ee4f2-115">Indica que no se debe invocar ningún método de notificación.</span><span class="sxs-lookup"><span data-stu-id="ee4f2-115">Indicates that no notification methods should be invoked.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ee4f2-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ee4f2-116">Requirements</span></span>  
 <span data-ttu-id="ee4f2-117">**Encabezado**: ProtocolNotify2.idl</span><span class="sxs-lookup"><span data-stu-id="ee4f2-117">**Header:** ProtocolNotify2.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ee4f2-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="ee4f2-118">See also</span></span>

- [<span data-ttu-id="ee4f2-119">Enumeraciones de almacén de símbolos de diagnósticos</span><span class="sxs-lookup"><span data-stu-id="ee4f2-119">Diagnostics Symbol Store Enumerations</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-enumerations.md)
