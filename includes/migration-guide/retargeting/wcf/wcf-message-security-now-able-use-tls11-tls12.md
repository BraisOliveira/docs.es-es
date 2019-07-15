---
ms.openlocfilehash: 3b7b50700541649a785fa9bbe3ecc56c2697fbfc
ms.sourcegitcommit: d55e14eb63588830c0ba1ea95a24ce6c57ef8c8c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/11/2019
ms.locfileid: "67859101"
---
### <a name="wcf-message-security-now-is-able-to-use-tls11-and-tls12"></a><span data-ttu-id="dda48-101">La seguridad de los mensajes de WCF ahora puede usar TLS1.1 y TLS1.2</span><span class="sxs-lookup"><span data-stu-id="dda48-101">WCF message security now is able to use TLS1.1 and TLS1.2</span></span>

|   |   |
|---|---|
|<span data-ttu-id="dda48-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="dda48-102">Details</span></span>|<span data-ttu-id="dda48-103">A partir de .NET Framework 4.7, los clientes pueden configurar TLS1.1 o TLS1.2 en la seguridad de los mensajes de WCF además de SSL3.0 y TLS1.0 a través de ajustes de configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="dda48-103">Starting in the .NET Framework 4.7, customers can configure either TLS1.1 or TLS1.2 in WCF message security in addition to SSL3.0 and TLS1.0 through application configuration settings.</span></span>|
|<span data-ttu-id="dda48-104">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="dda48-104">Suggestion</span></span>|<span data-ttu-id="dda48-105">En .NET Framework 4.7, la compatibilidad con TLS1.1 y TLS1.2 en la seguridad de los mensajes de WCF está deshabilitada de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="dda48-105">In the .NET Framework 4.7, support for TLS1.1 and TLS1.2 in WCF message security is disabled by default.</span></span> <span data-ttu-id="dda48-106">Se puede habilitar si se agrega la línea siguiente a la sección <code>&lt;runtime&gt;</code> del archivo app.config o web.config:</span><span class="sxs-lookup"><span data-stu-id="dda48-106">You can enable it by adding the following line to the <code>&lt;runtime&gt;</code> section of the app.config or web.config file:</span></span><pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.ServiceModel.DisableUsingServicePointManagerSecurityProtocols=false;Switch.System.Net.DontEnableSchUseStrongCrypto=false&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>|
|<span data-ttu-id="dda48-107">Ámbito</span><span class="sxs-lookup"><span data-stu-id="dda48-107">Scope</span></span>|<span data-ttu-id="dda48-108">Borde</span><span class="sxs-lookup"><span data-stu-id="dda48-108">Edge</span></span>|
|<span data-ttu-id="dda48-109">Versión</span><span class="sxs-lookup"><span data-stu-id="dda48-109">Version</span></span>|<span data-ttu-id="dda48-110">4.7</span><span class="sxs-lookup"><span data-stu-id="dda48-110">4.7</span></span>|
|<span data-ttu-id="dda48-111">Tipo</span><span class="sxs-lookup"><span data-stu-id="dda48-111">Type</span></span>|<span data-ttu-id="dda48-112">Redestinación</span><span class="sxs-lookup"><span data-stu-id="dda48-112">Retargeting</span></span>|

