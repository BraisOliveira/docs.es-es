---
ms.openlocfilehash: 71f61f23a8b17459610d253766a99e594f09428e
ms.sourcegitcommit: d55e14eb63588830c0ba1ea95a24ce6c57ef8c8c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/11/2019
ms.locfileid: "67857257"
---
### <a name="wcf-pipeconnectiongethashalgorithm-now-uses-sha256"></a><span data-ttu-id="b940c-101">En PipeConnection.GetHashAlgorithm de WCF ahora se usa SHA256</span><span class="sxs-lookup"><span data-stu-id="b940c-101">WCF PipeConnection.GetHashAlgorithm now uses SHA256</span></span>

|   |   |
|---|---|
|<span data-ttu-id="b940c-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="b940c-102">Details</span></span>|<span data-ttu-id="b940c-103">A partir de .NET Framework 4.7.1, Windows Communication Foundation usa un código hash SHA256 para generar nombres aleatorios para las canalizaciones con nombre.</span><span class="sxs-lookup"><span data-stu-id="b940c-103">Starting with the .NET Framework 4.7.1, Windows Communication Foundation uses a SHA256 hash to generate random names for named pipes.</span></span> <span data-ttu-id="b940c-104">En .NET Framework 4.7 y versiones anteriores, usaba un hash SHA1.</span><span class="sxs-lookup"><span data-stu-id="b940c-104">In the .NET Framework 4.7 and earlier versions, it used a SHA1 hash.</span></span>|
|<span data-ttu-id="b940c-105">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="b940c-105">Suggestion</span></span>|<span data-ttu-id="b940c-106">Si tiene problemas de compatibilidad con este cambio en .NET Framework 4.7.1 o una versión posterior, puede excluirlo mediante la adición de la línea siguiente a la sección <code>&lt;runtime&gt;</code> del archivo app.config:</span><span class="sxs-lookup"><span data-stu-id="b940c-106">If you run into compatibility issue with this change on the .NET Framework 4.7.1 or later, you can opt-out it by adding the following line to the <code>&lt;runtime&gt;</code> section of your app.config file:</span></span><pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.ServiceModel.UseSha1InPipeConnectionGetHashAlgorithm=true&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>|
|<span data-ttu-id="b940c-107">Ámbito</span><span class="sxs-lookup"><span data-stu-id="b940c-107">Scope</span></span>|<span data-ttu-id="b940c-108">Secundaria</span><span class="sxs-lookup"><span data-stu-id="b940c-108">Minor</span></span>|
|<span data-ttu-id="b940c-109">Versión</span><span class="sxs-lookup"><span data-stu-id="b940c-109">Version</span></span>|<span data-ttu-id="b940c-110">4.7.1</span><span class="sxs-lookup"><span data-stu-id="b940c-110">4.7.1</span></span>|
|<span data-ttu-id="b940c-111">Tipo</span><span class="sxs-lookup"><span data-stu-id="b940c-111">Type</span></span>|<span data-ttu-id="b940c-112">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="b940c-112">Runtime</span></span>|

