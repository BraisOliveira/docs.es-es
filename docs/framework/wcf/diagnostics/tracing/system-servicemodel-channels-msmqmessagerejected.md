---
title: System.ServiceModel.Channels.MsmqMessageRejected
ms.date: 03/30/2017
ms.assetid: 9b7c10a7-2af6-44a2-8b1a-90bba0c7cf26
ms.openlocfilehash: 4feeb1b57d79c7445d51f5d688b0a9f55e761542
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59143395"
---
# <a name="systemservicemodelchannelsmsmqmessagerejected"></a><span data-ttu-id="2da22-102">System.ServiceModel.Channels.MsmqMessageRejected</span><span class="sxs-lookup"><span data-stu-id="2da22-102">System.ServiceModel.Channels.MsmqMessageRejected</span></span>
<span data-ttu-id="2da22-103">MSMQ rechazó el mensaje.</span><span class="sxs-lookup"><span data-stu-id="2da22-103">MSMQ rejected the message.</span></span>  
  
## <a name="description"></a><span data-ttu-id="2da22-104">Descripción</span><span class="sxs-lookup"><span data-stu-id="2da22-104">Description</span></span>  
 <span data-ttu-id="2da22-105">Este seguimiento indica que se rechazó un mensaje de MSMQ.</span><span class="sxs-lookup"><span data-stu-id="2da22-105">This trace indicates that an MSMQ message was rejected.</span></span>  
  
 <span data-ttu-id="2da22-106">Cuando Windows Communication Foundation (WCF) (usado con NetMsmqBinding o MsmqIntegrationBinding) no puede procesarlos, se pueden rechazar mensajes de MSMQ.</span><span class="sxs-lookup"><span data-stu-id="2da22-106">MSMQ messages can be rejected when Windows Communication Foundation (WCF) (used with either the NetMsmqBinding or MsmqIntegrationBinding) is unable to process them.</span></span> <span data-ttu-id="2da22-107">Tales mensajes se conocen como mensajes dudosos.</span><span class="sxs-lookup"><span data-stu-id="2da22-107">Such messages are referred to as poison messages.</span></span> <span data-ttu-id="2da22-108">Se rechaza un mensaje dudoso cuando la propiedad `ReceiveErrorHandling` de NetMsmqBinding o MsmqIntegrationBinding está establecida en `Reject`.</span><span class="sxs-lookup"><span data-stu-id="2da22-108">A poison message is rejected when the `ReceiveErrorHandling` property on the NetMsmqBinding or MsmqIntegrationBinding is set to `Reject`.</span></span> <span data-ttu-id="2da22-109">Un mensaje rechazado se entrega al remitente [cola](https://go.microsoft.com/fwlink/?LinkID=99544).</span><span class="sxs-lookup"><span data-stu-id="2da22-109">A rejected message is delivered back to the sender’s [Dead-Letter Queue](https://go.microsoft.com/fwlink/?LinkID=99544).</span></span>  
  
 <span data-ttu-id="2da22-110">Consulte [de mensajes dudosos](https://go.microsoft.com/fwlink/?LinkID=99546) para obtener más detalles sobre cuándo los mensajes en dudosos y cómo configurar el servicio para controlarlos adecuadamente.</span><span class="sxs-lookup"><span data-stu-id="2da22-110">See [Poison-Message Handling](https://go.microsoft.com/fwlink/?LinkID=99546) for more details on when messages become poison and how to configure your service to handle them appropriately.</span></span>  
  
 <span data-ttu-id="2da22-111">Consulte [MQMarkMessageRejected](https://go.microsoft.com/fwlink/?LinkID=99548) para obtener más detalles sobre lo que significa un mensaje rechazado en MSMQ.</span><span class="sxs-lookup"><span data-stu-id="2da22-111">See [MQMarkMessageRejected](https://go.microsoft.com/fwlink/?LinkID=99548) for more details on what a rejected message means in MSMQ.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2da22-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="2da22-112">See also</span></span>

- [<span data-ttu-id="2da22-113">Traza</span><span class="sxs-lookup"><span data-stu-id="2da22-113">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [<span data-ttu-id="2da22-114">Uso del seguimiento para solucionar problemas de su aplicación</span><span class="sxs-lookup"><span data-stu-id="2da22-114">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="2da22-115">Administración y diagnóstico</span><span class="sxs-lookup"><span data-stu-id="2da22-115">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
- [<span data-ttu-id="2da22-116">Administración de mensajes dudosos</span><span class="sxs-lookup"><span data-stu-id="2da22-116">Poison-Message Handling</span></span>](https://go.microsoft.com/fwlink/?LinkID=99546)
- [<span data-ttu-id="2da22-117">MQMarkMessageRejected</span><span class="sxs-lookup"><span data-stu-id="2da22-117">MQMarkMessageRejected</span></span>](https://go.microsoft.com/fwlink/?LinkID=99548)
