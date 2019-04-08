---
ms.openlocfilehash: e613f0c52c77efebf250f5935d5cbfc29bc09a6b
ms.sourcegitcommit: 0aca6c5d166d7961a1e354c248495645b97a1dc5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2019
ms.locfileid: "58760447"
---
### <a name="wpf-printing-stack-update"></a><span data-ttu-id="47c1e-101">Actualización de la pila de impresión de WPF</span><span class="sxs-lookup"><span data-stu-id="47c1e-101">WPF Printing Stack Update</span></span>

|   |   |
|---|---|
|<span data-ttu-id="47c1e-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="47c1e-102">Details</span></span>|<span data-ttu-id="47c1e-103">Las API de impresión de WPF en las que se usa <xref:System.Printing.PrintQueue?displayProperty=name> ahora llaman a la API Print Document Package de Windows en lugar de la API XPS Print, que está en desuso.</span><span class="sxs-lookup"><span data-stu-id="47c1e-103">WPF's Printing APIs using <xref:System.Printing.PrintQueue?displayProperty=name> now call Window's Print Document Package API in favor of the now deprecated XPS Print API.</span></span> <span data-ttu-id="47c1e-104">El cambio se realizó con la facilidad en mente; ni los usuarios ni los desarrolladores deberían percibir cambios en el comportamiento o el uso de la API.</span><span class="sxs-lookup"><span data-stu-id="47c1e-104">The change was made with serviceability in mind; neither users nor developers should see any changes in behavior or API usage.</span></span> <span data-ttu-id="47c1e-105">La nueva pila de impresión está habilitada de forma predeterminada cuando se ejecuta en Windows 10 Creators Update.</span><span class="sxs-lookup"><span data-stu-id="47c1e-105">The new printing stack is enabled by default when running in Windows 10 Creators Update.</span></span> <span data-ttu-id="47c1e-106">La pila de impresión antigua seguirá funcionando como antes en las versiones anteriores de Windows.</span><span class="sxs-lookup"><span data-stu-id="47c1e-106">The old printing stack will still continue to work just as before in older Windows versions.</span></span>|
|<span data-ttu-id="47c1e-107">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="47c1e-107">Suggestion</span></span>|<span data-ttu-id="47c1e-108">Para usar la pila antigua en Windows 10 Creators Update, establezca el valor <code>UseXpsOMPrinting</code> REG_DWORD de la clave del Registro <code>HKEY_CURRENT_USER\Software\Microsoft\.NETFramework\Windows Presentation Foundation\Printing</code> en <code>1</code>.</span><span class="sxs-lookup"><span data-stu-id="47c1e-108">To use the old stack in Windows 10 Creators Update, set the <code>UseXpsOMPrinting</code> REG_DWORD value of the <code>HKEY_CURRENT_USER\Software\Microsoft\.NETFramework\Windows Presentation Foundation\Printing</code> registry key to <code>1</code>.</span></span>|
|<span data-ttu-id="47c1e-109">Ámbito</span><span class="sxs-lookup"><span data-stu-id="47c1e-109">Scope</span></span>|<span data-ttu-id="47c1e-110">Borde</span><span class="sxs-lookup"><span data-stu-id="47c1e-110">Edge</span></span>|
|<span data-ttu-id="47c1e-111">Versión</span><span class="sxs-lookup"><span data-stu-id="47c1e-111">Version</span></span>|<span data-ttu-id="47c1e-112">4.7</span><span class="sxs-lookup"><span data-stu-id="47c1e-112">4.7</span></span>|
|<span data-ttu-id="47c1e-113">Tipo</span><span class="sxs-lookup"><span data-stu-id="47c1e-113">Type</span></span>|<span data-ttu-id="47c1e-114">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="47c1e-114">Runtime</span></span>|

