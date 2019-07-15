---
ms.openlocfilehash: 79005f19ac31ba32e7e468ef61eb867a052eff40
ms.sourcegitcommit: d55e14eb63588830c0ba1ea95a24ce6c57ef8c8c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/11/2019
ms.locfileid: "67858979"
---
### <a name="improved-accessibility-for-some-net-sdk-tools"></a><span data-ttu-id="d0839-101">Mejor accesibilidad para algunas herramientas del SDK de .NET</span><span class="sxs-lookup"><span data-stu-id="d0839-101">Improved accessibility for some .NET SDK tools</span></span>

|   |   |
|---|---|
|<span data-ttu-id="d0839-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="d0839-102">Details</span></span>|<span data-ttu-id="d0839-103">En el SDK de .NET Framework 4.7.1, se han mejorado las herramientas SvcConfigEditor.exe y SvcTraceViewer.exe mediante la corrección de varios problemas de accesibilidad.</span><span class="sxs-lookup"><span data-stu-id="d0839-103">In the .NET Framework SDK 4.7.1, the SvcConfigEditor.exe and SvcTraceViewer.exe tools have been improved by fixing varied accessibility issues.</span></span> <span data-ttu-id="d0839-104">La mayoría eran problemas menores como un nombre sin definir o determinados patrones de automatización de la interfaz de usuario que no se implementaban correctamente.</span><span class="sxs-lookup"><span data-stu-id="d0839-104">Most of these were small issues like a name not being defined or certain UI automation patterns not being implemented correctly.</span></span> <span data-ttu-id="d0839-105">Aunque muchos usuarios no eran conscientes de estos valores incorrectos, los clientes que usan tecnologías de asistencia como lectores de pantalla encontrarán estas herramientas del SDK más accesibles.</span><span class="sxs-lookup"><span data-stu-id="d0839-105">While many users wouldn’t be aware of these incorrect values, customers who use assistive technologies like screen readers will find these SDK tools more accessible.</span></span> <span data-ttu-id="d0839-106">De hecho, estas correcciones cambian algunos comportamientos anteriores, como el orden del foco del teclado. Para obtener todas las correcciones de accesibilidad en estas herramientas, puede agregar lo siguiente al archivo app.config:</span><span class="sxs-lookup"><span data-stu-id="d0839-106">Certainly, these fixes change some previous behaviors, like keyboard focus order.In order to get all the accessibility fixes in these tools, you can the following to your app.config file:</span></span><pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.UseLegacyAccessibilityFeatures=false&quot;/&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>|
|<span data-ttu-id="d0839-107">Ámbito</span><span class="sxs-lookup"><span data-stu-id="d0839-107">Scope</span></span>|<span data-ttu-id="d0839-108">Borde</span><span class="sxs-lookup"><span data-stu-id="d0839-108">Edge</span></span>|
|<span data-ttu-id="d0839-109">Versión</span><span class="sxs-lookup"><span data-stu-id="d0839-109">Version</span></span>|<span data-ttu-id="d0839-110">4.7.1</span><span class="sxs-lookup"><span data-stu-id="d0839-110">4.7.1</span></span>|
|<span data-ttu-id="d0839-111">Tipo</span><span class="sxs-lookup"><span data-stu-id="d0839-111">Type</span></span>|<span data-ttu-id="d0839-112">Redestinación</span><span class="sxs-lookup"><span data-stu-id="d0839-112">Retargeting</span></span>|

