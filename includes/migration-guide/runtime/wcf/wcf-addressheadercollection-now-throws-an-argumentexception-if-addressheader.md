---
ms.openlocfilehash: a26b8c8a6315e57e70f4810ac4f5fb7ab4ba9b58
ms.sourcegitcommit: 0aca6c5d166d7961a1e354c248495645b97a1dc5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2019
ms.locfileid: "58760468"
---
### <a name="wcf-addressheadercollection-now-throws-an-argumentexception-if-an-addressheader-element-is-null"></a><span data-ttu-id="13e6b-101">WCF AddressHeaderCollection ahora inicia una excepción ArgumentException si un elemento addressHeader es NULL</span><span class="sxs-lookup"><span data-stu-id="13e6b-101">WCF AddressHeaderCollection now throws an ArgumentException if an addressHeader element is null</span></span>

|   |   |
|---|---|
|<span data-ttu-id="13e6b-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="13e6b-102">Details</span></span>|<span data-ttu-id="13e6b-103">A partir de .NET Framework 4.7.1, el constructor <xref:System.ServiceModel.Channels.AddressHeaderCollection.%23ctor(System.Collections.Generic.IEnumerable{System.ServiceModel.Channels.AddressHeader})> inicia una excepción <xref:System.ArgumentException> si uno de los elementos es <code>null</code>.</span><span class="sxs-lookup"><span data-stu-id="13e6b-103">Starting with the .NET Framework 4.7.1, the <xref:System.ServiceModel.Channels.AddressHeaderCollection.%23ctor(System.Collections.Generic.IEnumerable{System.ServiceModel.Channels.AddressHeader})> constructor throws an <xref:System.ArgumentException> if one of the elements is <code>null</code>.</span></span> <span data-ttu-id="13e6b-104">En .NET Framework 4.7 y versiones anteriores no se inicia ninguna excepción.</span><span class="sxs-lookup"><span data-stu-id="13e6b-104">In the .NET Framework 4.7 and earlier versions, no exception is thrown.</span></span>|
|<span data-ttu-id="13e6b-105">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="13e6b-105">Suggestion</span></span>|<span data-ttu-id="13e6b-106">Si encuentra problemas de compatibilidad con este cambio en .NET Framework 4.7.1 o una versión posterior, puede excluirlo mediante la adición de la línea siguiente a la sección <code>&lt;runtime&gt;</code> del archivo app.config:</span><span class="sxs-lookup"><span data-stu-id="13e6b-106">If you encounter compatibility issues with this change on the .NET Framework 4.7.1 or a later version, you can opt-out of it by adding the following line to the <code>&lt;runtime&gt;</code> section of the app.config file::</span></span><pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.ServiceModel.DisableAddressHeaderCollectionValidation=true&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>|
|<span data-ttu-id="13e6b-107">Ámbito</span><span class="sxs-lookup"><span data-stu-id="13e6b-107">Scope</span></span>|<span data-ttu-id="13e6b-108">Secundaria</span><span class="sxs-lookup"><span data-stu-id="13e6b-108">Minor</span></span>|
|<span data-ttu-id="13e6b-109">Versión</span><span class="sxs-lookup"><span data-stu-id="13e6b-109">Version</span></span>|<span data-ttu-id="13e6b-110">4.7.1</span><span class="sxs-lookup"><span data-stu-id="13e6b-110">4.7.1</span></span>|
|<span data-ttu-id="13e6b-111">Tipo</span><span class="sxs-lookup"><span data-stu-id="13e6b-111">Type</span></span>|<span data-ttu-id="13e6b-112">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="13e6b-112">Runtime</span></span>|
|<span data-ttu-id="13e6b-113">API afectadas</span><span class="sxs-lookup"><span data-stu-id="13e6b-113">Affected APIs</span></span>|<ul><li><xref:System.ServiceModel.Channels.AddressHeaderCollection.%23ctor(System.Collections.Generic.IEnumerable{System.ServiceModel.Channels.AddressHeader})?displayProperty=nameWithType></li></ul>|

