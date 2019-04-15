---
ms.openlocfilehash: 958a89015420ce5632d596688963d576c40b4cb6
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59235853"
---
### <a name="sharing-session-state-with-aspnet-stateserver-requires-all-servers-in-the-web-farm-to-use-the-same-net-framework-version"></a><span data-ttu-id="33faa-101">Compartir el estado de sesión con StateServer de ASP.NET requiere que todos los servidores de la granja de servidores web usen la misma versión de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="33faa-101">Sharing session state with Asp.Net StateServer requires all servers in the web farm to use the same .NET Framework version</span></span>

|   |   |
|---|---|
|<span data-ttu-id="33faa-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="33faa-102">Details</span></span>|<span data-ttu-id="33faa-103">Al habilitar el estado de sesión <xref:System.Web.SessionState.SessionStateMode.StateServer?displayProperty=name>, todos los servidores de la granja de servidores web indicada deben usar la misma versión de .NET Framework para que el estado se comparta correctamente.</span><span class="sxs-lookup"><span data-stu-id="33faa-103">When enabling <xref:System.Web.SessionState.SessionStateMode.StateServer?displayProperty=name> session state, all of the servers in the given web farm must use the same version of the .NET Framework in order for state to be properly shared.</span></span>|
|<span data-ttu-id="33faa-104">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="33faa-104">Suggestion</span></span>|<span data-ttu-id="33faa-105">Asegúrese de actualizar las versiones de .NET Framework en los servidores web que compartan el estado al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="33faa-105">Be sure to upgrade .NET Framework versions on web servers that share state at the same time.</span></span>|
|<span data-ttu-id="33faa-106">Ámbito</span><span class="sxs-lookup"><span data-stu-id="33faa-106">Scope</span></span>|<span data-ttu-id="33faa-107">Borde</span><span class="sxs-lookup"><span data-stu-id="33faa-107">Edge</span></span>|
|<span data-ttu-id="33faa-108">Versión</span><span class="sxs-lookup"><span data-stu-id="33faa-108">Version</span></span>|<span data-ttu-id="33faa-109">4.5</span><span class="sxs-lookup"><span data-stu-id="33faa-109">4.5</span></span>|
|<span data-ttu-id="33faa-110">Tipo</span><span class="sxs-lookup"><span data-stu-id="33faa-110">Type</span></span>|<span data-ttu-id="33faa-111">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="33faa-111">Runtime</span></span>|
|<span data-ttu-id="33faa-112">API afectadas</span><span class="sxs-lookup"><span data-stu-id="33faa-112">Affected APIs</span></span>|<ul><li><xref:System.Web.SessionState.SessionStateMode.StateServer?displayProperty=nameWithType></li></ul>|
