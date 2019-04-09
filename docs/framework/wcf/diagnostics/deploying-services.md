---
title: Desarrollo de servicios
ms.date: 03/30/2017
ms.assetid: ac361bfb-017d-4da9-a2d7-fc0fb72d65bb
ms.openlocfilehash: 2c3cd17b597fafcd02b9155089bc583fafbc9dea
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59085770"
---
# <a name="deploying-services"></a><span data-ttu-id="69f0f-102">Desarrollo de servicios</span><span class="sxs-lookup"><span data-stu-id="69f0f-102">Deploying Services</span></span>
<span data-ttu-id="69f0f-103">Este tema describe cómo puede implementar una aplicación de Windows Communication Foundation (WCF) en un entorno de tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="69f0f-103">This topic describes how you can deploy a Windows Communication Foundation (WCF) application to a run-time environment.</span></span>  
  
## <a name="choosing-the-hosting-environment-for-your-application"></a><span data-ttu-id="69f0f-104">Elegir el entorno de alojamiento para su aplicación</span><span class="sxs-lookup"><span data-stu-id="69f0f-104">Choosing the Hosting Environment for Your Application</span></span>  
 <span data-ttu-id="69f0f-105">Servicios WCF están diseñados para ejecutarse en cualquier proceso de Windows que admita código administrado.</span><span class="sxs-lookup"><span data-stu-id="69f0f-105">WCF services are designed to run in any Windows process that supports managed code.</span></span> <span data-ttu-id="69f0f-106">Para activarse, se debe hospedar un servicio dentro de un entorno de tiempo en ejecución que lo crea y controla su contexto y duración.</span><span class="sxs-lookup"><span data-stu-id="69f0f-106">To become active, a service must be hosted within a run-time environment that creates it and controls its context and lifetime.</span></span> <span data-ttu-id="69f0f-107">Las opciones de alojamiento son ejecutarse dentro de la aplicación de consola más simple a entornos de servidor como un servicio de Windows, Internet Information Server (IIS), o dentro de un proceso de trabajo administrado por el Servicio de Activación de Windows (WAS).</span><span class="sxs-lookup"><span data-stu-id="69f0f-107">Hosting options range from running inside the simplest console application to server environments like a Windows service, Internet Information Services (IIS), or within a worker process managed by the Windows Activation Service (WAS).</span></span> <span data-ttu-id="69f0f-108">Para revisar las distintas opciones de hospedaje para la aplicación de WCF, vea [servicios de hospedaje](../../../../docs/framework/wcf/hosting-services.md).</span><span class="sxs-lookup"><span data-stu-id="69f0f-108">To review the different hosting options for your WCF application, see [Hosting Services](../../../../docs/framework/wcf/hosting-services.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="69f0f-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="69f0f-109">See also</span></span>

- [<span data-ttu-id="69f0f-110">Hospedaje</span><span class="sxs-lookup"><span data-stu-id="69f0f-110">Hosting</span></span>](../../../../docs/framework/wcf/feature-details/hosting.md)
- [<span data-ttu-id="69f0f-111">Servicios de hospedaje</span><span class="sxs-lookup"><span data-stu-id="69f0f-111">Hosting Services</span></span>](../../../../docs/framework/wcf/hosting-services.md)
