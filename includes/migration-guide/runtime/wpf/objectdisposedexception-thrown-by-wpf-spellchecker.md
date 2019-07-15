---
ms.openlocfilehash: 9d09f598538b9d5ee3f995d6281b8eb4b2668050
ms.sourcegitcommit: d55e14eb63588830c0ba1ea95a24ce6c57ef8c8c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/11/2019
ms.locfileid: "67802530"
---
### <a name="objectdisposedexception-thrown-by-wpf-spellchecker"></a><span data-ttu-id="ba9d3-101">El corrector ortográfico de WPF inicia la excepción ObjectDisposedException</span><span class="sxs-lookup"><span data-stu-id="ba9d3-101">ObjectDisposedException thrown by WPF spellchecker</span></span>

|   |   |
|---|---|
|<span data-ttu-id="ba9d3-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="ba9d3-102">Details</span></span>|<span data-ttu-id="ba9d3-103">En ocasiones, las aplicaciones de WPF se bloquean durante el cierre de la aplicación y el corrector ortográfico inicia una excepción <xref:System.ObjectDisposedException?displayProperty=name>.</span><span class="sxs-lookup"><span data-stu-id="ba9d3-103">WPF applications occasionally crash during application shutdown with an <xref:System.ObjectDisposedException?displayProperty=name> thrown by the spellchecker.</span></span> <span data-ttu-id="ba9d3-104">Esto se ha corregido en WPF de .NET Framework 4.7 mediante el control correcto de la excepción, lo que garantiza que las aplicaciones ya no se ven afectadas de manera negativa.</span><span class="sxs-lookup"><span data-stu-id="ba9d3-104">This is fixed in .NET Framework 4.7 WPF by handling the exception gracefully, and thus ensuring that applications are no longer adversely affected.</span></span> <span data-ttu-id="ba9d3-105">Debe tenerse en cuenta que se pueden seguir observando primeras excepciones ocasionales en las aplicaciones que se ejecutan con un depurador.</span><span class="sxs-lookup"><span data-stu-id="ba9d3-105">It should be noted that occasional first-chance exceptions would continue to be observed in applications running under a debugger.</span></span>|
|<span data-ttu-id="ba9d3-106">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="ba9d3-106">Suggestion</span></span>|<span data-ttu-id="ba9d3-107">Actualizar a .NET Framework 4.7</span><span class="sxs-lookup"><span data-stu-id="ba9d3-107">Upgrade to .NET Framework 4.7</span></span>|
|<span data-ttu-id="ba9d3-108">Ámbito</span><span class="sxs-lookup"><span data-stu-id="ba9d3-108">Scope</span></span>|<span data-ttu-id="ba9d3-109">Borde</span><span class="sxs-lookup"><span data-stu-id="ba9d3-109">Edge</span></span>|
|<span data-ttu-id="ba9d3-110">Versión</span><span class="sxs-lookup"><span data-stu-id="ba9d3-110">Version</span></span>|<span data-ttu-id="ba9d3-111">4.6.1</span><span class="sxs-lookup"><span data-stu-id="ba9d3-111">4.6.1</span></span>|
|<span data-ttu-id="ba9d3-112">Tipo</span><span class="sxs-lookup"><span data-stu-id="ba9d3-112">Type</span></span>|<span data-ttu-id="ba9d3-113">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="ba9d3-113">Runtime</span></span>|

