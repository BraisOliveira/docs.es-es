---
ms.openlocfilehash: 891c29b731214fb0028e960256b79cfc267d86b9
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59235813"
---
### <a name="deserialization-of-objects-across-appdomains-can-fail"></a><span data-ttu-id="a2678-101">Se puede producir un error en la deserialización de objetos entre dominios de aplicación</span><span class="sxs-lookup"><span data-stu-id="a2678-101">Deserialization of objects across appdomains can fail</span></span>

|   |   |
|---|---|
|<span data-ttu-id="a2678-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="a2678-102">Details</span></span>|<span data-ttu-id="a2678-103">En algunos casos, cuando una aplicación usa dos o más dominios de aplicación con distintas bases de aplicación, un intento de deserializar objetos en el contexto de llamada lógico entre dominios de aplicación produce una excepción.</span><span class="sxs-lookup"><span data-stu-id="a2678-103">In some cases, when an app uses two or more app domains with different application bases, trying to deserialize objects in the logical call context across app domains throws an exception.</span></span>|
|<span data-ttu-id="a2678-104">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="a2678-104">Suggestion</span></span>|<span data-ttu-id="a2678-105">Consulte [Mitigación: deserialización de objetos en distintos dominios de aplicación](~/docs/framework/migration-guide/mitigation-deserialization-of-objects-across-app-domains.md)</span><span class="sxs-lookup"><span data-stu-id="a2678-105">See [Mitigation: Deserialization of Objects Across App Domains](~/docs/framework/migration-guide/mitigation-deserialization-of-objects-across-app-domains.md)</span></span>|
|<span data-ttu-id="a2678-106">Ámbito</span><span class="sxs-lookup"><span data-stu-id="a2678-106">Scope</span></span>|<span data-ttu-id="a2678-107">Borde</span><span class="sxs-lookup"><span data-stu-id="a2678-107">Edge</span></span>|
|<span data-ttu-id="a2678-108">Versión</span><span class="sxs-lookup"><span data-stu-id="a2678-108">Version</span></span>|<span data-ttu-id="a2678-109">4.5.1</span><span class="sxs-lookup"><span data-stu-id="a2678-109">4.5.1</span></span>|
|<span data-ttu-id="a2678-110">Tipo</span><span class="sxs-lookup"><span data-stu-id="a2678-110">Type</span></span>|<span data-ttu-id="a2678-111">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="a2678-111">Runtime</span></span>|
