---
ms.openlocfilehash: d4f22aa41eb7aeffd655d980cb8418649462273e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61757791"
---
## <a name="introduction"></a><span data-ttu-id="4691f-101">Introducción</span><span class="sxs-lookup"><span data-stu-id="4691f-101">Introduction</span></span>
<span data-ttu-id="4691f-102">Los cambios de redestinación afectan a las aplicaciones que se vuelven a compilar para tener como destino otra versión de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="4691f-102">Retargeting changes affect apps that are recompiled to target a different .NET Framework.</span></span> <span data-ttu-id="4691f-103">Son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="4691f-103">They include:</span></span>

* <span data-ttu-id="4691f-104">Cambios en el entorno en tiempo de diseño.</span><span class="sxs-lookup"><span data-stu-id="4691f-104">Changes in the design-time environment.</span></span> <span data-ttu-id="4691f-105">Por ejemplo, las herramientas de compilación pueden emitir advertencias cuando antes no lo hacían.</span><span class="sxs-lookup"><span data-stu-id="4691f-105">For example, build tools may emit warnings when previously they did not.</span></span>

* <span data-ttu-id="4691f-106">Cambios en el entorno en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="4691f-106">Changes in the runtime environment.</span></span> <span data-ttu-id="4691f-107">Estos solo afectan a las aplicaciones que tienen como destino específico la versión de .NET Framework redestinada.</span><span class="sxs-lookup"><span data-stu-id="4691f-107">These affect only apps that specifically target the retargeted .NET Framework.</span></span> <span data-ttu-id="4691f-108">Las aplicaciones compiladas para versiones anteriores de .NET Framework se comportan de la misma manera que cuando se ejecutan en esas versiones.</span><span class="sxs-lookup"><span data-stu-id="4691f-108">Apps that target previous versions of the .NET Framework behave as they did when running under those versions.</span></span>

<span data-ttu-id="4691f-109">En los temas en los que describen cambios de redestinación, hemos ordenado los elementos individuales por su impacto esperado, como sigue:</span><span class="sxs-lookup"><span data-stu-id="4691f-109">In the topics that describe retargeting changes, we have classified individual items by their expected impact, as follows:</span></span>

<span data-ttu-id="4691f-110">**Importante** Se trata de un cambio significativo que afecta a un gran número de aplicaciones o que requiere una modificación sustancial del código.</span><span class="sxs-lookup"><span data-stu-id="4691f-110">**Major** This is a significant change that affects a large number of apps or that requires substantial modification of code.</span></span>

<span data-ttu-id="4691f-111">**Leve** Se trata de un cambio que afecta a un pequeño número de aplicaciones o que requiere ligeras modificaciones en el código.</span><span class="sxs-lookup"><span data-stu-id="4691f-111">**Minor** This is a change that affects a small number of apps or that requires minor modification of code.</span></span>

<span data-ttu-id="4691f-112">**Caso específico** Se trata de un cambio que afecta a aplicaciones de escenarios muy concretos que no son frecuentes.</span><span class="sxs-lookup"><span data-stu-id="4691f-112">**Edge case** This is a change that affects apps under very specific scenarios that are not common.</span></span>

<span data-ttu-id="4691f-113">**Transparente** Se trata de un cambio que no tiene ningún efecto apreciable en el programador o el usuario de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="4691f-113">**Transparent** This is a change that has no noticeable effect on the app's developer or user.</span></span> <span data-ttu-id="4691f-114">No es necesario modificar la aplicación debido a este cambio.</span><span class="sxs-lookup"><span data-stu-id="4691f-114">The app should not require modification because of this change.</span></span>
