---
ms.openlocfilehash: 318609c15d2e0b9a7ee59b38463735b33ef87974
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59805066"
---
### <a name="wcf-pipeconnectiongethashalgorithm-now-uses-sha256"></a><span data-ttu-id="471c3-101">En PipeConnection.GetHashAlgorithm de WCF ahora se usa SHA256</span><span class="sxs-lookup"><span data-stu-id="471c3-101">WCF PipeConnection.GetHashAlgorithm now uses SHA256</span></span>

|   |   |
|---|---|
|<span data-ttu-id="471c3-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="471c3-102">Details</span></span>|<span data-ttu-id="471c3-103">A partir de .NET Framework 4.7.1, Windows Communication Foundation usa un código hash SHA256 para generar nombres aleatorios para las canalizaciones con nombre.</span><span class="sxs-lookup"><span data-stu-id="471c3-103">Starting with the .NET Framework 4.7.1, Windows Communication Foundation uses a SHA256 hash to generate random names for named pipes.</span></span> <span data-ttu-id="471c3-104">En .NET Framework 4.7 y versiones anteriores, usaba un hash SHA1.</span><span class="sxs-lookup"><span data-stu-id="471c3-104">In the .NET Framework 4.7 and earlier versions, it used a SHA1 hash.</span></span>|
|<span data-ttu-id="471c3-105">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="471c3-105">Suggestion</span></span>|<span data-ttu-id="471c3-106">Si tiene problemas de compatibilidad con este cambio en .NET Framework 4.7.1 o una versión posterior, puede excluirlo mediante la adición de la línea siguiente a la sección <code>&lt;runtime&gt;</code> del archivo app.config:</span><span class="sxs-lookup"><span data-stu-id="471c3-106">If you run into compatibility issue with this change on the .NET Framework 4.7.1 or later, you can opt-out it by adding the following line to the <code>&lt;runtime&gt;</code> section of your app.config file:</span></span><pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.ServiceModel.UseSha1InPipeConnectionGetHashAlgorithm=true&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>|
|<span data-ttu-id="471c3-107">Ámbito</span><span class="sxs-lookup"><span data-stu-id="471c3-107">Scope</span></span>|<span data-ttu-id="471c3-108">Secundaria</span><span class="sxs-lookup"><span data-stu-id="471c3-108">Minor</span></span>|
|<span data-ttu-id="471c3-109">Versión</span><span class="sxs-lookup"><span data-stu-id="471c3-109">Version</span></span>|<span data-ttu-id="471c3-110">4.7.1</span><span class="sxs-lookup"><span data-stu-id="471c3-110">4.7.1</span></span>|
|<span data-ttu-id="471c3-111">Tipo</span><span class="sxs-lookup"><span data-stu-id="471c3-111">Type</span></span>|<span data-ttu-id="471c3-112">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="471c3-112">Runtime</span></span>|
