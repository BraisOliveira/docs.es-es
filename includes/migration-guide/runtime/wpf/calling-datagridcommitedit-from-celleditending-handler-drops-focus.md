---
ms.openlocfilehash: b5f12e648a82ebaba7d09b546e8aa2fc7cd82a37
ms.sourcegitcommit: d55e14eb63588830c0ba1ea95a24ce6c57ef8c8c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/11/2019
ms.locfileid: "67803162"
---
### <a name="calling-datagridcommitedit-from-a-celleditending-handler-drops-focus"></a><span data-ttu-id="dd4ea-101">Las llamadas a DataGrid.CommitEdit desde un controlador CellEditEnding eliminan el foco</span><span class="sxs-lookup"><span data-stu-id="dd4ea-101">Calling DataGrid.CommitEdit from a CellEditEnding handler drops focus</span></span>

|   |   |
|---|---|
|<span data-ttu-id="dd4ea-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="dd4ea-102">Details</span></span>|<span data-ttu-id="dd4ea-103">Las llamadas a <xref:System.Windows.Controls.DataGrid.CommitEdit> desde uno de los controladores de eventos <xref:System.Windows.Controls.DataGrid.CellEditEnding?displayProperty=name> de <xref:System.Windows.Controls.DataGrid?displayProperty=name> provoca que <xref:System.Windows.Controls.DataGrid?displayProperty=name> pierda el foco.</span><span class="sxs-lookup"><span data-stu-id="dd4ea-103">Calling <xref:System.Windows.Controls.DataGrid.CommitEdit> from one of the <xref:System.Windows.Controls.DataGrid?displayProperty=name>'s <xref:System.Windows.Controls.DataGrid.CellEditEnding?displayProperty=name> event handlers causes the <xref:System.Windows.Controls.DataGrid?displayProperty=name> to lose focus.</span></span>|
|<span data-ttu-id="dd4ea-104">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="dd4ea-104">Suggestion</span></span>|<span data-ttu-id="dd4ea-105">Este error se corrigió en .NET Framework 4.5.2, por lo que se puede evitar actualizando a una versión posterior de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="dd4ea-105">This bug has been fixed in the .NET Framework 4.5.2, so it can be avoided by upgrading the .NET Framework.</span></span> <span data-ttu-id="dd4ea-106">Como alternativa, se puede evitar si se selecciona <xref:System.Windows.Controls.DataGrid?displayProperty=name> de forma explícita después de llamar a <xref:System.Windows.Controls.DataGrid.CommitEdit?displayProperty=name>.</span><span class="sxs-lookup"><span data-stu-id="dd4ea-106">Alternatively, it can be avoided by explicitly re-selecting the <xref:System.Windows.Controls.DataGrid?displayProperty=name> after calling <xref:System.Windows.Controls.DataGrid.CommitEdit?displayProperty=name>.</span></span>|
|<span data-ttu-id="dd4ea-107">Ámbito</span><span class="sxs-lookup"><span data-stu-id="dd4ea-107">Scope</span></span>|<span data-ttu-id="dd4ea-108">Borde</span><span class="sxs-lookup"><span data-stu-id="dd4ea-108">Edge</span></span>|
|<span data-ttu-id="dd4ea-109">Versión</span><span class="sxs-lookup"><span data-stu-id="dd4ea-109">Version</span></span>|<span data-ttu-id="dd4ea-110">4.5</span><span class="sxs-lookup"><span data-stu-id="dd4ea-110">4.5</span></span>|
|<span data-ttu-id="dd4ea-111">Tipo</span><span class="sxs-lookup"><span data-stu-id="dd4ea-111">Type</span></span>|<span data-ttu-id="dd4ea-112">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="dd4ea-112">Runtime</span></span>|
|<span data-ttu-id="dd4ea-113">API afectadas</span><span class="sxs-lookup"><span data-stu-id="dd4ea-113">Affected APIs</span></span>|<ul><li><xref:System.Windows.Controls.DataGrid.CommitEdit?displayProperty=nameWithType></li><li><xref:System.Windows.Controls.DataGrid.CommitEdit(System.Windows.Controls.DataGridEditingUnit,System.Boolean)?displayProperty=nameWithType></li></ul>|

