---
ms.openlocfilehash: 4cc91e7c6054fdb8e96cecf7120df5b9f25de56c
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59805130"
---
### <a name="mef-catalogs-implement-ienumerable-and-therefore-can-no-longer-be-used-to-create-a-serializer"></a><span data-ttu-id="75889-101">Los catálogos de MEF implementan IEnumerable y, por tanto, ya no se pueden usar para crear un serializador</span><span class="sxs-lookup"><span data-stu-id="75889-101">MEF catalogs implement IEnumerable and therefore can no longer be used to create a serializer</span></span>

|   |   |
|---|---|
|<span data-ttu-id="75889-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="75889-102">Details</span></span>|<span data-ttu-id="75889-103">A partir de .NET Framework 4.5, los catálogos de MEF implementan IEnumerable y, por tanto, ya no se pueden usar para crear un serializador (un objeto <xref:System.Xml.Serialization.XmlSerializer?displayProperty=name>).</span><span class="sxs-lookup"><span data-stu-id="75889-103">Starting with the .NET Framework 4.5, MEF catalogs implement IEnumerable and therefore can no longer be used to create a serializer (<xref:System.Xml.Serialization.XmlSerializer?displayProperty=name> object).</span></span> <span data-ttu-id="75889-104">Al intentar serializar un catálogo de MEF se inicia una excepción.</span><span class="sxs-lookup"><span data-stu-id="75889-104">Trying to serialize a MEF catalog throws an exception.</span></span>|
|<span data-ttu-id="75889-105">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="75889-105">Suggestion</span></span>|<span data-ttu-id="75889-106">Ya no se puede usar MEF para crear un serializador.</span><span class="sxs-lookup"><span data-stu-id="75889-106">Can no longer use MEF to create a serializer</span></span>|
|<span data-ttu-id="75889-107">Ámbito</span><span class="sxs-lookup"><span data-stu-id="75889-107">Scope</span></span>|<span data-ttu-id="75889-108">Major</span><span class="sxs-lookup"><span data-stu-id="75889-108">Major</span></span>|
|<span data-ttu-id="75889-109">Versión</span><span class="sxs-lookup"><span data-stu-id="75889-109">Version</span></span>|<span data-ttu-id="75889-110">4.5</span><span class="sxs-lookup"><span data-stu-id="75889-110">4.5</span></span>|
|<span data-ttu-id="75889-111">Tipo</span><span class="sxs-lookup"><span data-stu-id="75889-111">Type</span></span>|<span data-ttu-id="75889-112">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="75889-112">Runtime</span></span>|
