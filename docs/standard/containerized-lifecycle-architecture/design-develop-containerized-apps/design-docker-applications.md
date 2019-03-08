---
title: Diseñar aplicaciones de Docker
description: Aquí encontrará una referencia a una guía exhaustiva para la arquitectura de microservicios, ya que es un tema que no se detallan en esta guía.
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 02/15/2019
ms.openlocfilehash: 858147883b3b4a5a5f487856028fdbfa84f6cca9
ms.sourcegitcommit: 58fc0e6564a37fa1b9b1b140a637e864c4cf696e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/08/2019
ms.locfileid: "57675191"
---
# <a name="design-docker-applications"></a><span data-ttu-id="12c2d-103">Diseñar aplicaciones de Docker</span><span class="sxs-lookup"><span data-stu-id="12c2d-103">Design Docker applications</span></span>

<span data-ttu-id="12c2d-104">Capítulo 1 introdujo los conceptos fundamentales sobre los contenedores y Docker.</span><span class="sxs-lookup"><span data-stu-id="12c2d-104">Chapter 1 introduced the fundamental concepts regarding containers and Docker.</span></span> <span data-ttu-id="12c2d-105">Esa información es el nivel básico de la información que necesita para empezar a trabajar.</span><span class="sxs-lookup"><span data-stu-id="12c2d-105">That information is the basic level of information you need to get started.</span></span> <span data-ttu-id="12c2d-106">Sin embargo, las aplicaciones empresariales pueden ser complejos y formada por varios servicios en lugar de un único servicio o contenedor.</span><span class="sxs-lookup"><span data-stu-id="12c2d-106">But, enterprise applications can be complex and composed of multiple services instead of a single service or container.</span></span> <span data-ttu-id="12c2d-107">Para esos casos de uso opcional, deberá saber otros enfoques de diseño, como la arquitectura orientada a servicios (SOA) y los conceptos de microservicios y contenedor más avanzados conceptos de orquestación.</span><span class="sxs-lookup"><span data-stu-id="12c2d-107">For those optional use cases, you need to know additional approaches to design, such as Service-Oriented Architecture (SOA) and the more advanced microservices concepts and container orchestration concepts.</span></span> <span data-ttu-id="12c2d-108">El ámbito de este documento no se limita a los microservicios, pero a cualquier ciclo de vida de aplicación de Docker, por lo tanto, no explora la arquitectura de microservicios en profundidad porque también puede usar los contenedores y Docker con los trabajos, tareas en segundo plano o SOA regular, o incluso con los métodos de implementación de la aplicación monolítica.</span><span class="sxs-lookup"><span data-stu-id="12c2d-108">The scope of this document is not limited to microservices but to any Docker application life cycle, therefore, it does not explore microservices architecture in depth because you also can use containers and Docker with regular SOA, background tasks or jobs, or even with monolithic application deployment approaches.</span></span>

<span data-ttu-id="12c2d-109">**Obtener más información** para obtener más información acerca de las aplicaciones empresariales y la arquitectura de microservicios en profundidad, lea la guía [NET Microservicios: Arquitectura de aplicaciones .NET en contenedor](https://docs.microsoft.com/dotnet/standard/microservices-architecture) que también puede descargar desde <https://aka.ms/MicroservicesEbook>.</span><span class="sxs-lookup"><span data-stu-id="12c2d-109">**More info** To learn more about enterprise applications and microservices architecture in depth, read the guide [NET Microservices: Architecture for Containerized .NET Applications](https://docs.microsoft.com/dotnet/standard/microservices-architecture) that you can also download from <https://aka.ms/MicroservicesEbook>.</span></span>

<span data-ttu-id="12c2d-110">Sin embargo, antes de entrar en el ciclo de vida de aplicación y DevOps, es importante saber cómo va a diseño y construir la aplicación y cuáles son las opciones de diseño.</span><span class="sxs-lookup"><span data-stu-id="12c2d-110">However, before we get into the application life cycle and DevOps, it's important to know how you're going to design and construct your application and what are your design choices.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="12c2d-111">[Anterior](index.md)
>[Siguiente](common-container-design-principles.md)</span><span class="sxs-lookup"><span data-stu-id="12c2d-111">[Previous](index.md)
[Next](common-container-design-principles.md)</span></span>
