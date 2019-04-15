---
ms.openlocfilehash: 8433899058c6f569e380999800557dbe8ed0a169
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59235809"
---
### <a name="corprfgcroothandles-are-not-being-enumerated-by-profilers"></a><span data-ttu-id="d6458-101">Los generadores de perfiles no enumeran COR_PRF_GC_ROOT_HANDLE</span><span class="sxs-lookup"><span data-stu-id="d6458-101">COR_PRF_GC_ROOT_HANDLEs are not being enumerated by profilers</span></span>

|   |   |
|---|---|
|<span data-ttu-id="d6458-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="d6458-102">Details</span></span>|<span data-ttu-id="d6458-103">En .NET Framework v4.5.1, el método <code>RootReferences2()</code> de la API de generación de perfiles de manera incorrecta nunca devuelve <code>COR_PRF_GC_ROOT_HANDLE</code> (en su lugar se devuelven como <code>COR_PRF_GC_ROOT_OTHER</code>).</span><span class="sxs-lookup"><span data-stu-id="d6458-103">In the .NET Framework v4.5.1, the profiling API <code>RootReferences2()</code> is incorrectly never returning <code>COR_PRF_GC_ROOT_HANDLE</code> (they are returned as <code>COR_PRF_GC_ROOT_OTHER</code> instead).</span></span> <span data-ttu-id="d6458-104">Este problema se corrigió a partir de .NET Framework 4.6.</span><span class="sxs-lookup"><span data-stu-id="d6458-104">This issue is fixed beginning in the .NET Framework 4.6.</span></span>|
|<span data-ttu-id="d6458-105">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="d6458-105">Suggestion</span></span>|<span data-ttu-id="d6458-106">Este problema se ha corregido en .NET Framework 4.6 y se puede solucionar mediante la actualización a esa versión de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="d6458-106">This issue has been fixed in the .NET Framework 4.6 and may be addressed by upgrading to that version of the .NET Framework.</span></span>|
|<span data-ttu-id="d6458-107">Ámbito</span><span class="sxs-lookup"><span data-stu-id="d6458-107">Scope</span></span>|<span data-ttu-id="d6458-108">Secundaria</span><span class="sxs-lookup"><span data-stu-id="d6458-108">Minor</span></span>|
|<span data-ttu-id="d6458-109">Versión</span><span class="sxs-lookup"><span data-stu-id="d6458-109">Version</span></span>|<span data-ttu-id="d6458-110">4.5.1</span><span class="sxs-lookup"><span data-stu-id="d6458-110">4.5.1</span></span>|
|<span data-ttu-id="d6458-111">Tipo</span><span class="sxs-lookup"><span data-stu-id="d6458-111">Type</span></span>|<span data-ttu-id="d6458-112">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="d6458-112">Runtime</span></span>|
