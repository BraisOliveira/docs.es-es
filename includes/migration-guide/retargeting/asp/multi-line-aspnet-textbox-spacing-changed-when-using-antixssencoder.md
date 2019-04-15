---
ms.openlocfilehash: e2bca42daebd25667ab2f312d5e59089b986503c
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59234785"
---
### <a name="multi-line-aspnet-textbox-spacing-changed-when-using-antixssencoder"></a><span data-ttu-id="4bddc-101">Cambio de interlineado de los cuadros de texto multilínea de ASP.NET al usar AntiXSSEncoder</span><span class="sxs-lookup"><span data-stu-id="4bddc-101">Multi-line ASP.Net TextBox spacing changed when using AntiXSSEncoder</span></span>

|   |   |
|---|---|
|<span data-ttu-id="4bddc-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="4bddc-102">Details</span></span>|<span data-ttu-id="4bddc-103">En .NET Framework 4.0, se introdujeron líneas adicionales entre las líneas de un cuadro de texto multilínea en postback si se usaba el elemento <xref:System.Web.Security.AntiXss.AntiXssEncoder?displayProperty=name>.</span><span class="sxs-lookup"><span data-stu-id="4bddc-103">In .NET Framework 4.0, extra lines were inserted between lines of a multi-line text box on postback, if using the <xref:System.Web.Security.AntiXss.AntiXssEncoder?displayProperty=name>.</span></span> <span data-ttu-id="4bddc-104">En .NET Framework 4.5 no se incluyen estos saltos de línea adicionales, pero únicamente si la aplicación web tiene como destino .NET Framework 4.5.</span><span class="sxs-lookup"><span data-stu-id="4bddc-104">In .NET Framework 4.5, those extra line breaks are not included, but only if the web app is targeting .NET Framework 4.5</span></span>|
|<span data-ttu-id="4bddc-105">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="4bddc-105">Suggestion</span></span>|<span data-ttu-id="4bddc-106">Tenga en cuenta que las aplicaciones web de la versión 4.0 redestinadas a .NET Framework 4.5 pueden tener cuadros de texto multilínea mejorados para dejar de introducir saltos de línea adicionales.</span><span class="sxs-lookup"><span data-stu-id="4bddc-106">Be aware that 4.0 web apps retargeted to .NET Framework 4.5 may have multi-line text boxes improved to no longer insert extra line breaks.</span></span> <span data-ttu-id="4bddc-107">Si este no es el comportamiento deseado, la aplicación puede tener el anterior cuando se ejecuta en .NET Framework 4.5 si se establece .NET Framework 4.0 como destino.</span><span class="sxs-lookup"><span data-stu-id="4bddc-107">If this is not desirable, the app  can have the old behavior when running on .NET Framework 4.5 by targeting the .NET Framework 4.0.</span></span>|
|<span data-ttu-id="4bddc-108">Ámbito</span><span class="sxs-lookup"><span data-stu-id="4bddc-108">Scope</span></span>|<span data-ttu-id="4bddc-109">Secundaria</span><span class="sxs-lookup"><span data-stu-id="4bddc-109">Minor</span></span>|
|<span data-ttu-id="4bddc-110">Versión</span><span class="sxs-lookup"><span data-stu-id="4bddc-110">Version</span></span>|<span data-ttu-id="4bddc-111">4.5</span><span class="sxs-lookup"><span data-stu-id="4bddc-111">4.5</span></span>|
|<span data-ttu-id="4bddc-112">Tipo</span><span class="sxs-lookup"><span data-stu-id="4bddc-112">Type</span></span>|<span data-ttu-id="4bddc-113">Redestinación</span><span class="sxs-lookup"><span data-stu-id="4bddc-113">Retargeting</span></span>|
