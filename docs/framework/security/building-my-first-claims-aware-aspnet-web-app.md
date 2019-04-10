---
title: Crear mi primera aplicación web de ASP.NET para notificaciones
ms.date: 03/30/2017
ms.assetid: 3ee8ee7f-caba-4267-9343-e313fae2876d
author: BrucePerlerMS
ms.openlocfilehash: 5a24a2117a031bfe49d0c27dbcefae6db00e6045
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/09/2019
ms.locfileid: "59314560"
---
# <a name="building-my-first-claims-aware-aspnet-web-application"></a><span data-ttu-id="67836-102">Crear mi primera aplicación web de ASP.NET para notificaciones</span><span class="sxs-lookup"><span data-stu-id="67836-102">Building My First Claims-Aware ASP.NET Web Application</span></span>
## <a name="applies-to"></a><span data-ttu-id="67836-103">Se aplica a</span><span class="sxs-lookup"><span data-stu-id="67836-103">Applies To</span></span>  
  
-   <span data-ttu-id="67836-104">Windows Identity Foundation (WIF)</span><span class="sxs-lookup"><span data-stu-id="67836-104">Windows Identity Foundation (WIF)</span></span>  
  
-   <span data-ttu-id="67836-105">ASP.NET</span><span class="sxs-lookup"><span data-stu-id="67836-105">ASP.NET</span></span>  
  
 <span data-ttu-id="67836-106">En este tema se describe el escenario de compilación de aplicaciones web ASP.NET compatibles con notificaciones mediante WIF.</span><span class="sxs-lookup"><span data-stu-id="67836-106">This topic outlines the scenario of building claims-aware ASP.NET web applications using WIF.</span></span> <span data-ttu-id="67836-107">En un escenario de aplicación compatible con notificaciones suele haber tres participantes: la propia aplicación, el usuario final y el servicio de token de seguridad (STS).</span><span class="sxs-lookup"><span data-stu-id="67836-107">There are usually three participants in a claims-aware application scenario: the application itself, the end user, and the Security Token Service (STS).</span></span> <span data-ttu-id="67836-108">En la ilustración siguiente se describe este escenario:</span><span class="sxs-lookup"><span data-stu-id="67836-108">The following figure describes this scenario:</span></span>  
  
 ![Diagrama que muestra los componentes de una aplicación Web básica de WIF.](./media/building-my-first-claims-aware-aspnet-web-app/windows-identity-foundation-basic-web-application.gif)  
  
1. <span data-ttu-id="67836-110">La aplicación para notificaciones usa WIF para identificar las solicitudes no autenticadas y redirigirlas al STS.</span><span class="sxs-lookup"><span data-stu-id="67836-110">The claims-aware application uses WIF to identify unauthenticated requests and to redirect them to the STS.</span></span>  
  
2. <span data-ttu-id="67836-111">El usuario final proporciona las credenciales al STS y, tras su correcta autenticación, el STS emite un token para el usuario.</span><span class="sxs-lookup"><span data-stu-id="67836-111">The end user provides credentials to the STS and upon successful authentication the user is issued a token by the STS.</span></span>  
  
3. <span data-ttu-id="67836-112">Se redirige al usuario del STS a la aplicación para notificaciones con el token emitido por el STS en la solicitud.</span><span class="sxs-lookup"><span data-stu-id="67836-112">The user is redirected from the STS to the claims-aware application with the STS-issued token in the request.</span></span>  
  
4. <span data-ttu-id="67836-113">La aplicación para notificaciones se configura para confiar en el STS y en los token que emite.</span><span class="sxs-lookup"><span data-stu-id="67836-113">The claims-aware application is configured to trust the STS and the tokens it issues.</span></span> <span data-ttu-id="67836-114">Asimismo, dicha aplicación usa WIF para validar el token y analizarlo.</span><span class="sxs-lookup"><span data-stu-id="67836-114">The claims-aware application uses WIF to validate the token and to parse it.</span></span> <span data-ttu-id="67836-115">Los desarrolladores usan la API y los tipos de WIF adecuados, por ejemplo, **ClaimsPrincpal**, para las necesidades de la aplicación, como la implementación de autorización correspondiente.</span><span class="sxs-lookup"><span data-stu-id="67836-115">Developers use the appropriate WIF API and types, for example, **ClaimsPrincpal** for the application’s needs, such as implementing authorization for it.</span></span>  
  
 <span data-ttu-id="67836-116">A partir de .NET 4.5, WIF forma parte del paquete de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="67836-116">Starting from .NET 4.5, WIF is part of the .NET Framework package.</span></span> <span data-ttu-id="67836-117">Poder disponer de las clases de WIF directamente en el marco de trabajo permite una integración mucho más profunda de la identidad basada en notificaciones en .NET, lo que facilita el uso de notificaciones.</span><span class="sxs-lookup"><span data-stu-id="67836-117">Having the WIF classes directly available in the framework allows a much deeper integration of claims-based identity in .NET, making it easier to use claims.</span></span> <span data-ttu-id="67836-118">Con WIF 4.5, no es necesario instalar ningún componente fuera de banda para comenzar a desarrollar aplicaciones web compatibles con notificaciones.</span><span class="sxs-lookup"><span data-stu-id="67836-118">With WIF 4.5, you do not need to install any out-of-band components in order to start developing claims-aware web applications.</span></span> <span data-ttu-id="67836-119">Las clases de WIF se extienden ahora por diversos ensamblados; los principales son System.Security.Claims, System.IdentityModel y System.IdentityModel.Services.</span><span class="sxs-lookup"><span data-stu-id="67836-119">WIF classes are now spread across various assemblies, the main ones being System.Security.Claims, System.IdentityModel and System.IdentityModel.Services.</span></span>  
  
 <span data-ttu-id="67836-120">El STS es un servicio que emite tokens tras haberse realizado la autenticación correctamente.</span><span class="sxs-lookup"><span data-stu-id="67836-120">STS is a service that issues tokens upon successful authentication.</span></span> <span data-ttu-id="67836-121">Microsoft ofrece dos STS estándar del sector:</span><span class="sxs-lookup"><span data-stu-id="67836-121">Microsoft offers two industry standard STS’s:</span></span>  
  
-   [<span data-ttu-id="67836-122">Servicios de federación de Active Directory (AD FS) 2.0</span><span class="sxs-lookup"><span data-stu-id="67836-122">Active Directory Federation Services (AD FS) 2.0</span></span>](https://go.microsoft.com/fwlink/?LinkID=247516)
  
-   [<span data-ttu-id="67836-123">Windows Azure Access Control Service (ACS)</span><span class="sxs-lookup"><span data-stu-id="67836-123">Windows Azure Access Control Service (ACS)</span></span>](https://go.microsoft.com/fwlink/?LinkID=247517)
  
 <span data-ttu-id="67836-124">AD FS 2.0 forma parte de Windows Server R2 y se puede usar como STS para escenarios locales.</span><span class="sxs-lookup"><span data-stu-id="67836-124">AD FS 2.0 is part of the Windows Server R2 and can be used as an STS for on-premise scenarios.</span></span> <span data-ttu-id="67836-125">ACS es un servicio de nube que se ofrece como parte de la plataforma Microsoft Azure.</span><span class="sxs-lookup"><span data-stu-id="67836-125">ACS is a cloud service, offered as part of the Windows Azure Platform.</span></span> <span data-ttu-id="67836-126">Con fines de pruebas o educativos, también pueden usarse otros STS para compilar las aplicaciones compatibles con notificaciones.</span><span class="sxs-lookup"><span data-stu-id="67836-126">For testing or educational purposes, you can also use other STS’s in order to build your claims-aware applications.</span></span> <span data-ttu-id="67836-127">Por ejemplo, puede usar el STS de desarrollo Local que forma parte de la [Identity and Access Tool para Visual Studio](https://go.microsoft.com/fwlink/?LinkID=245849) que está disponible de forma gratuita en línea.</span><span class="sxs-lookup"><span data-stu-id="67836-127">For example, you can use the Local Development STS that is part of the [Identity and Access Tool for Visual Studio](https://go.microsoft.com/fwlink/?LinkID=245849) which is freely available online.</span></span>  
  
 <span data-ttu-id="67836-128">Para compilar la primera aplicación ASP.NET compatible con notificaciones mediante WIF, siga las instrucciones de uno de los sitios siguientes:</span><span class="sxs-lookup"><span data-stu-id="67836-128">To build your first claims-aware ASP.NET application using WIF, follow the instructions in one of the following:</span></span>  
  
-   [<span data-ttu-id="67836-129">Cómo compilar aplicaciones web MVC de ASP.NET con reconocimiento de notificaciones mediante WIF</span><span class="sxs-lookup"><span data-stu-id="67836-129">How To: Build Claims-Aware ASP.NET MVC Web Application Using WIF</span></span>](../../../docs/framework/security/how-to-build-claims-aware-aspnet-mvc-web-app-using-wif.md)  
  
-   [<span data-ttu-id="67836-130">Cómo compilar aplicaciones de formularios Web Forms de ASP.NET con reconocimiento de notificaciones mediante WIF</span><span class="sxs-lookup"><span data-stu-id="67836-130">How To: Build Claims-Aware ASP.NET Web Forms Application Using WIF</span></span>](../../../docs/framework/security/how-to-build-claims-aware-aspnet-web-forms-app-using-wif.md)  
  
-   [<span data-ttu-id="67836-131">Cómo compilar aplicaciones ASP.NET con reconocimiento de mediante la autenticación basada en formularios</span><span class="sxs-lookup"><span data-stu-id="67836-131">How To: Build Claims-Aware ASP.NET Application Using Forms-Based Authentication</span></span>](../../../docs/framework/security/claims-aware-aspnet-app-forms-authentication.md)  
  
## <a name="see-also"></a><span data-ttu-id="67836-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="67836-132">See also</span></span>

- [<span data-ttu-id="67836-133">Introducción a WIF</span><span class="sxs-lookup"><span data-stu-id="67836-133">Getting Started With WIF</span></span>](../../../docs/framework/security/getting-started-with-wif.md)
