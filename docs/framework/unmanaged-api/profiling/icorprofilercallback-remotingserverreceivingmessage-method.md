---
title: ICorProfilerCallback::RemotingServerReceivingMessage (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.RemotingServerReceivingMessage
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::RemotingServerReceivingMessage
helpviewer_keywords:
- ICorProfilerCallback::RemotingServerReceivingMessage method [.NET Framework profiling]
- RemotingServerReceivingMessage method [.NET Framework profiling]
ms.assetid: 5604d21f-e6b7-490e-b469-42122a7568e1
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 30015cc6cae935c43cdbfec1a6eeae5c703ef9f2
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59103212"
---
# <a name="icorprofilercallbackremotingserverreceivingmessage-method"></a><span data-ttu-id="5afcc-102">ICorProfilerCallback::RemotingServerReceivingMessage (Método)</span><span class="sxs-lookup"><span data-stu-id="5afcc-102">ICorProfilerCallback::RemotingServerReceivingMessage Method</span></span>
<span data-ttu-id="5afcc-103">Notifica al generador de perfiles que el proceso ha recibido una solicitud de activación o la invocación de método remoto.</span><span class="sxs-lookup"><span data-stu-id="5afcc-103">Notifies the profiler that the process has received a remote method invocation or activation request.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5afcc-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5afcc-104">Syntax</span></span>  
  
```  
HRESULT RemotingClientSendingMessage(  
    [in] GUID *pCookie,  
    [in] BOOL fIsAsync);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5afcc-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="5afcc-105">Parameters</span></span>  
 `pCookie`  
 <span data-ttu-id="5afcc-106">[in] Un valor que se corresponde con el valor proporcionado en [RemotingClientSendingMessage](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientsendingmessage-method.md) en estas condiciones:</span><span class="sxs-lookup"><span data-stu-id="5afcc-106">[in] A value that will correspond with the value provided in [ICorProfilerCallback::RemotingClientSendingMessage](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientsendingmessage-method.md) under these conditions:</span></span>  
  
-   <span data-ttu-id="5afcc-107">Las cookies GUID de comunicación remota están activas.</span><span class="sxs-lookup"><span data-stu-id="5afcc-107">Remoting GUID cookies are active.</span></span>  
  
-   <span data-ttu-id="5afcc-108">El canal se realiza correctamente en la transmisión del mensaje.</span><span class="sxs-lookup"><span data-stu-id="5afcc-108">The channel succeeds in transmitting the message.</span></span>  
  
-   <span data-ttu-id="5afcc-109">Las cookies de GUID están activas en el proceso de cliente.</span><span class="sxs-lookup"><span data-stu-id="5afcc-109">GUID cookies are active on the client-side process.</span></span>  
  
 <span data-ttu-id="5afcc-110">Esto permite que simplifica el emparejamiento de las llamadas remotas y la creación de una pila de llamadas lógicas.</span><span class="sxs-lookup"><span data-stu-id="5afcc-110">This allows easy pairing of remoting calls and the creation of a logical call stack.</span></span>  
  
 `fIsAsync`  
 <span data-ttu-id="5afcc-111">[in] Un valor que es `true` si la llamada es asincrónica; en caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="5afcc-111">[in] A value that is `true` if the call is asynchronous; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5afcc-112">Comentarios</span><span class="sxs-lookup"><span data-stu-id="5afcc-112">Remarks</span></span>  
 <span data-ttu-id="5afcc-113">Si la solicitud de mensaje es asincrónica, se puede atender la solicitud de cualquier subproceso arbitrario.</span><span class="sxs-lookup"><span data-stu-id="5afcc-113">If the message request is asynchronous, the request can be serviced by any arbitrary thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5afcc-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5afcc-114">Requirements</span></span>  
 <span data-ttu-id="5afcc-115">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5afcc-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5afcc-116">**Encabezado**: CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="5afcc-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="5afcc-117">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5afcc-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5afcc-118">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5afcc-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5afcc-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="5afcc-119">See also</span></span>

- [<span data-ttu-id="5afcc-120">ICorProfilerCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="5afcc-120">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
