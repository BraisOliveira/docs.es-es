---
ms.openlocfilehash: 84f570cbbd97be79426e117d4c97ec182a397fd4
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59235838"
---
### <a name="ipad-should-not-be-used-in-custom-capabilities-file-because-it-is-now-a-browser-capability"></a><span data-ttu-id="e5282-101">No se debe usar IPad en el archivo de funciones personalizado porque ahora es una funcionalidad del explorador</span><span class="sxs-lookup"><span data-stu-id="e5282-101">IPad should not be used in custom capabilities file because it is now a browser capability</span></span>

|   |   |
|---|---|
|<span data-ttu-id="e5282-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="e5282-102">Details</span></span>|<span data-ttu-id="e5282-103">A partir de .NET Framework 4.5, iPad es un identificador en el archivo de funciones de explorador de ASP.NET predeterminado, por lo que no se debe usar en un archivo de funciones personalizado.</span><span class="sxs-lookup"><span data-stu-id="e5282-103">Beginning in .NET Framework 4.5, iPad is an identifier in the default ASP.NET browser capabilities file, so it should not be used in a custom capabilities file</span></span>|
|<span data-ttu-id="e5282-104">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="e5282-104">Suggestion</span></span>|<span data-ttu-id="e5282-105">Si se requieren funciones específicas de iPad, es necesario modificar el comportamiento de iPad estableciéndolas en el refID &quot;IPad&quot; de puerta de enlace predefinido en lugar de mediante la generación de un nuevo id. &quot;IPad&quot; mediante la búsqueda de coincidencias de agente de usuario.</span><span class="sxs-lookup"><span data-stu-id="e5282-105">If iPad-specific capabilities are required, it is necessary to modify iPad behavior by setting capabilities on the pre-defined gateway refID &quot;IPad&quot; instead of by generating a new &quot;IPad&quot; ID by user agent matching.</span></span>|
|<span data-ttu-id="e5282-106">Ámbito</span><span class="sxs-lookup"><span data-stu-id="e5282-106">Scope</span></span>|<span data-ttu-id="e5282-107">Borde</span><span class="sxs-lookup"><span data-stu-id="e5282-107">Edge</span></span>|
|<span data-ttu-id="e5282-108">Versión</span><span class="sxs-lookup"><span data-stu-id="e5282-108">Version</span></span>|<span data-ttu-id="e5282-109">4.5</span><span class="sxs-lookup"><span data-stu-id="e5282-109">4.5</span></span>|
|<span data-ttu-id="e5282-110">Tipo</span><span class="sxs-lookup"><span data-stu-id="e5282-110">Type</span></span>|<span data-ttu-id="e5282-111">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="e5282-111">Runtime</span></span>|
