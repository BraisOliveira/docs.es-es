---
ms.openlocfilehash: a2d4b7592727ca20ee79867094d6972eb9c4baed
ms.sourcegitcommit: d55e14eb63588830c0ba1ea95a24ce6c57ef8c8c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/11/2019
ms.locfileid: "67857272"
---
### <a name="wcf-msmqsecurehashalgorithm-default-value-is-now-sha256"></a><span data-ttu-id="03626-101">El valor predeterminado de MsmqSecureHashAlgorithm de WCF ahora es SHA256</span><span class="sxs-lookup"><span data-stu-id="03626-101">WCF MsmqSecureHashAlgorithm default value is now SHA256</span></span>

|   |   |
|---|---|
|<span data-ttu-id="03626-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="03626-102">Details</span></span>|<span data-ttu-id="03626-103">A partir de .NET Framework 4.7.1, el algoritmo de firma de mensajes predeterminado de WCF para los mensajes de Msmq es SHA256.</span><span class="sxs-lookup"><span data-stu-id="03626-103">Starting with the .NET Framework 4.7.1, the default message signing algorithm in WCF for Msmq messages is SHA256.</span></span> <span data-ttu-id="03626-104">En .NET Framework 4.7 y versiones anteriores, el algoritmo de firma de mensajes predeterminado es SHA1.</span><span class="sxs-lookup"><span data-stu-id="03626-104">In the .NET Framework 4.7 and earlier versions, the default message signing algorithm is SHA1.</span></span>|
|<span data-ttu-id="03626-105">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="03626-105">Suggestion</span></span>|<span data-ttu-id="03626-106">Si tiene problemas de compatibilidad con este cambio en .NET Framework 4.7.1 o una versión posterior, puede excluirlo mediante la adición de la línea siguiente a la sección <code>&lt;runtime&gt;</code> del archivo app.config:</span><span class="sxs-lookup"><span data-stu-id="03626-106">If you run into compatibility issues with this change on the .NET Framework 4.7.1 or later, you can opt-out the change by adding the following line to the <code>&lt;runtime&gt;</code>section of your app.config file:</span></span><pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.ServiceModel.UseSha1InMsmqEncryptionAlgorithm=true&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>|
|<span data-ttu-id="03626-107">Ámbito</span><span class="sxs-lookup"><span data-stu-id="03626-107">Scope</span></span>|<span data-ttu-id="03626-108">Secundaria</span><span class="sxs-lookup"><span data-stu-id="03626-108">Minor</span></span>|
|<span data-ttu-id="03626-109">Versión</span><span class="sxs-lookup"><span data-stu-id="03626-109">Version</span></span>|<span data-ttu-id="03626-110">4.7.1</span><span class="sxs-lookup"><span data-stu-id="03626-110">4.7.1</span></span>|
|<span data-ttu-id="03626-111">Tipo</span><span class="sxs-lookup"><span data-stu-id="03626-111">Type</span></span>|<span data-ttu-id="03626-112">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="03626-112">Runtime</span></span>|

