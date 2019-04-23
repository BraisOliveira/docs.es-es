---
title: CALL_ID (Estructura)
ms.date: 03/30/2017
api_name:
- CALL_ID
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- CALL_ID
helpviewer_keywords:
- CALL_ID structure [.NET Framework debugging]
ms.assetid: bfd46324-afec-4782-9c18-586d81fb4740
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b6fa729b131d12b2825a2def700fd918ce8acc40
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59220180"
---
# <a name="callid-structure"></a><span data-ttu-id="ad593-102">CALL_ID (Estructura)</span><span class="sxs-lookup"><span data-stu-id="ad593-102">CALL_ID Structure</span></span>
<span data-ttu-id="ad593-103">Proporciona información a un depurador sobre una función que se llama.</span><span class="sxs-lookup"><span data-stu-id="ad593-103">Provides information to a debugger about a function that is being called.</span></span> <span data-ttu-id="ad593-104">Consulte la [INotifySink2](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-interface.md) interfaz para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="ad593-104">See the [INotifySink2](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-interface.md) interface for more information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ad593-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ad593-105">Syntax</span></span>  
  
```  
typedef struct tagCALL_ID  
{  
    LPCOLESTR       szMachine;  
    DWORD           dwPid;  
    USER_THREAD     *pUserThread;  
    STACK_ADDRESS   addrStackPointer;  
    LPCOLESTR       szEntryPoint;  
    LPCOLESTR       szDestinationMachine;  
} CALL_ID;  
```  
  
## <a name="members"></a><span data-ttu-id="ad593-106">Miembros</span><span class="sxs-lookup"><span data-stu-id="ad593-106">Members</span></span>  
  
|<span data-ttu-id="ad593-107">Miembro</span><span class="sxs-lookup"><span data-stu-id="ad593-107">Member</span></span>|<span data-ttu-id="ad593-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="ad593-108">Description</span></span>|  
|------------|-----------------|  
|`szMachine`|<span data-ttu-id="ad593-109">Identifica el equipo que realiza la llamada.</span><span class="sxs-lookup"><span data-stu-id="ad593-109">Identifies the machine that is making the call.</span></span>|  
|`dwPid`|<span data-ttu-id="ad593-110">Identifica el procesador del equipo.</span><span class="sxs-lookup"><span data-stu-id="ad593-110">Identifies the machine processor.</span></span>|  
|`pUserThread`|<span data-ttu-id="ad593-111">Identifica el subproceso que se está ejecutando la llamada.</span><span class="sxs-lookup"><span data-stu-id="ad593-111">Identifies the thread that is executing the call.</span></span>|  
|`addrStackPointer`|<span data-ttu-id="ad593-112">Especifica la dirección de la pila de llamadas.</span><span class="sxs-lookup"><span data-stu-id="ad593-112">Specifies the address of the call stack.</span></span>|  
|`szEntryPoint`|<span data-ttu-id="ad593-113">Especifica la dirección de la llamada.</span><span class="sxs-lookup"><span data-stu-id="ad593-113">Specifies the address of the call.</span></span>|  
|`szDestinationMachine`|<span data-ttu-id="ad593-114">Identifica el equipo que ejecutará la llamada.</span><span class="sxs-lookup"><span data-stu-id="ad593-114">Identifies the machine that will execute the call.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ad593-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ad593-115">Requirements</span></span>  
 <span data-ttu-id="ad593-116">**Encabezado**: ProtocolNotify2.idl</span><span class="sxs-lookup"><span data-stu-id="ad593-116">**Header:** ProtocolNotify2.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ad593-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="ad593-117">See also</span></span>

- [<span data-ttu-id="ad593-118">INotifySink2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ad593-118">INotifySink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-interface.md)
- [<span data-ttu-id="ad593-119">Estructuras de almacén de símbolos de diagnósticos</span><span class="sxs-lookup"><span data-stu-id="ad593-119">Diagnostics Symbol Store Structures</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-structures.md)
