---
ms.openlocfilehash: 74ce1bbc9a887aee3a33eaf05084e8c2000967c2
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59805095"
---
### <a name="wpf-textbox-selected-text-appears-a-different-color-when-the-text-box-is-inactive"></a><span data-ttu-id="cb46f-101">El texto seleccionado de un cuadro de texto de WPF aparece en otro color cuando el cuadro de texto está inactivo</span><span class="sxs-lookup"><span data-stu-id="cb46f-101">WPF TextBox selected text appears a different color when the text box is inactive</span></span>

|   |   |
|---|---|
|<span data-ttu-id="cb46f-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="cb46f-102">Details</span></span>|<span data-ttu-id="cb46f-103">En .NET Framework 4.5, cuando un control de cuadro de texto de WPF está inactivo (sin el foco), el texto seleccionado dentro del cuadro aparecerá en un color diferente al que lo haría con el control activo.</span><span class="sxs-lookup"><span data-stu-id="cb46f-103">In .NET Framework 4.5, when a WPF text box control is inactive (it doesn't have focus), the selected text inside the box will appear a different color than when the control is active.</span></span>|
|<span data-ttu-id="cb46f-104">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="cb46f-104">Suggestion</span></span>|<span data-ttu-id="cb46f-105">El comportamiento anterior (.NET Framework 4.0) se puede restaurar si se establece la propiedad <xref:System.Windows.FrameworkCompatibilityPreferences.AreInactiveSelectionHighlightBrushKeysSupported> en <code>false</code>.</span><span class="sxs-lookup"><span data-stu-id="cb46f-105">The previous (.NET Framework 4.0) behavior may be restored by setting the <xref:System.Windows.FrameworkCompatibilityPreferences.AreInactiveSelectionHighlightBrushKeysSupported> property to <code>false</code>.</span></span>|
|<span data-ttu-id="cb46f-106">Ámbito</span><span class="sxs-lookup"><span data-stu-id="cb46f-106">Scope</span></span>|<span data-ttu-id="cb46f-107">Borde</span><span class="sxs-lookup"><span data-stu-id="cb46f-107">Edge</span></span>|
|<span data-ttu-id="cb46f-108">Versión</span><span class="sxs-lookup"><span data-stu-id="cb46f-108">Version</span></span>|<span data-ttu-id="cb46f-109">4.5</span><span class="sxs-lookup"><span data-stu-id="cb46f-109">4.5</span></span>|
|<span data-ttu-id="cb46f-110">Tipo</span><span class="sxs-lookup"><span data-stu-id="cb46f-110">Type</span></span>|<span data-ttu-id="cb46f-111">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="cb46f-111">Runtime</span></span>|
|<span data-ttu-id="cb46f-112">API afectadas</span><span class="sxs-lookup"><span data-stu-id="cb46f-112">Affected APIs</span></span>|<ul><li><xref:System.Windows.Controls.TextBox?displayProperty=nameWithType></li></ul>|
