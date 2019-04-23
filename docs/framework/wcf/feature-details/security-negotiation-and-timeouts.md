---
title: Negociación de seguridad y tiempos de espera
ms.date: 03/30/2017
ms.assetid: 02a428f1-84e5-4d28-a11f-53ce31d63196
ms.openlocfilehash: a02c9d7b42eadf9a5ce9af8022fe292d6c23249c
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59180653"
---
# <a name="security-negotiation-and-timeouts"></a><span data-ttu-id="46bc3-102">Negociación de seguridad y tiempos de espera</span><span class="sxs-lookup"><span data-stu-id="46bc3-102">Security Negotiation and Timeouts</span></span>
<span data-ttu-id="46bc3-103">Cuando los clientes y servicios autentican, Windows Communication Foundation (WCF) admite un modo donde se negocia la credencial de servicio como parte de la autenticación.</span><span class="sxs-lookup"><span data-stu-id="46bc3-103">When clients and services authenticate, Windows Communication Foundation (WCF) supports a mode where the service credential is negotiated as part of authentication.</span></span> <span data-ttu-id="46bc3-104">En tales escenarios, se produce un intercambio potencial de autenticación mutua entre el cliente y el servicio para propagar la credencial del servicio al cliente.</span><span class="sxs-lookup"><span data-stu-id="46bc3-104">In such scenarios, a potentially multi-leg exchange occurs between the client and the service to propagate the service credential to the client.</span></span> <span data-ttu-id="46bc3-105">La propiedad <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings.NegotiationTimeout%2A> controla cuánto tiempo puede tardar en completarse el intercambio de autenticación mutua.</span><span class="sxs-lookup"><span data-stu-id="46bc3-105">The <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings.NegotiationTimeout%2A> property controls how long the multi-leg exchange can take to complete.</span></span> <span data-ttu-id="46bc3-106">Sin embargo, este tiempo de espera sólo se aplica si el intercambio tarda más realmente que una solicitud-respuesta.</span><span class="sxs-lookup"><span data-stu-id="46bc3-106">However, this timeout only applies if the exchange actually takes more that a single request-response.</span></span> <span data-ttu-id="46bc3-107">En casos donde la negociación se completa en un viaje de ida y vuelta (round trip) único, el tiempo de espera no se aplica.</span><span class="sxs-lookup"><span data-stu-id="46bc3-107">In cases where the negotiation completes in a single round trip, the timeout does not apply.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="46bc3-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="46bc3-108">See also</span></span>

- <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings>
- [<span data-ttu-id="46bc3-109">Cómo: Conjunto un sesgo de reloj máximo</span><span class="sxs-lookup"><span data-stu-id="46bc3-109">How to: Set a Max Clock Skew</span></span>](../../../../docs/framework/wcf/feature-details/how-to-set-a-max-clock-skew.md)
