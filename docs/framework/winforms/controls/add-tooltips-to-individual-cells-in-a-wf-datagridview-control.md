---
title: Procedimiento para agregar información sobre herramientas a celdas individuales en un control DataGridView de formularios Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- tooltips [Windows Forms], adding to data grids
- DataGridView control [Windows Forms], adding tooltips
- data grids [Windows Forms], adding tooltips
ms.assetid: 2a81f9de-d58b-4ea8-bc0b-8d93c2f4cf78
ms.openlocfilehash: d0e9b3ad742633b135a2fe1c00af3fa72af7b44a
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64663452"
---
# <a name="how-to-add-tooltips-to-individual-cells-in-a-windows-forms-datagridview-control"></a><span data-ttu-id="f65b8-102">Procedimiento para agregar información sobre herramientas a celdas individuales en un control DataGridView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f65b8-102">How to: Add ToolTips to Individual Cells in a Windows Forms DataGridView Control</span></span>
<span data-ttu-id="f65b8-103">De forma predeterminada, la información sobre herramientas se usa para mostrar los valores de <xref:System.Windows.Forms.DataGridView> celdas que son demasiado pequeñas para mostrar todo su contenido.</span><span class="sxs-lookup"><span data-stu-id="f65b8-103">By default, ToolTips are used to display the values of <xref:System.Windows.Forms.DataGridView> cells that are too small to show their entire contents.</span></span> <span data-ttu-id="f65b8-104">Puede invalidar este comportamiento, sin embargo, para establecer los valores de texto de información sobre herramientas de celdas individuales.</span><span class="sxs-lookup"><span data-stu-id="f65b8-104">You can override this behavior, however, to set ToolTip-text values for individual cells.</span></span> <span data-ttu-id="f65b8-105">Esto es útil para mostrar a los usuarios información adicional sobre una celda o para proporcionar a los usuarios una descripción alternativa del contenido de la celda.</span><span class="sxs-lookup"><span data-stu-id="f65b8-105">This is useful to display to users additional information about a cell or to provide to users an alternate description of the cell contents.</span></span> <span data-ttu-id="f65b8-106">Por ejemplo, si tiene una fila que muestra los iconos de estado, es posible que desee proporcionar explicaciones de texto mediante información sobre herramientas.</span><span class="sxs-lookup"><span data-stu-id="f65b8-106">For example, if you have a row that displays status icons, you may want to provide text explanations using ToolTips.</span></span>  
  
 <span data-ttu-id="f65b8-107">También puede deshabilitar la presentación de información sobre herramientas de nivel de celda estableciendo el <xref:System.Windows.Forms.DataGridView.ShowCellToolTips%2A?displayProperty=nameWithType> propiedad `false`.</span><span class="sxs-lookup"><span data-stu-id="f65b8-107">You can also disable the display of cell-level ToolTips by setting the <xref:System.Windows.Forms.DataGridView.ShowCellToolTips%2A?displayProperty=nameWithType> property to `false`.</span></span>  
  
### <a name="to-add-a-tooltip-to-a-cell"></a><span data-ttu-id="f65b8-108">Para agregar una información sobre herramientas a una celda</span><span class="sxs-lookup"><span data-stu-id="f65b8-108">To add a ToolTip to a cell</span></span>  
  
- <span data-ttu-id="f65b8-109">Establecer la propiedad <xref:System.Windows.Forms.DataGridViewCell.ToolTipText%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="f65b8-109">Set the <xref:System.Windows.Forms.DataGridViewCell.ToolTipText%2A?displayProperty=nameWithType> property.</span></span>  
  
     [!code-cpp[System.Windows.Forms.DataGridViewCell.ToolTipText#1](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCell.ToolTipText/cpp/datagridviewcell.tooltiptext.cpp#1)]
     [!code-csharp[System.Windows.Forms.DataGridViewCell.ToolTipText#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCell.ToolTipText/CS/datagridviewcell.tooltiptext.cs#1)]
     [!code-vb[System.Windows.Forms.DataGridViewCell.ToolTipText#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCell.ToolTipText/VB/datagridviewcell.tooltiptext.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="f65b8-110">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="f65b8-110">Compiling the Code</span></span>  
  
- <span data-ttu-id="f65b8-111">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="f65b8-111">This example requires:</span></span>  
  
- <span data-ttu-id="f65b8-112">Un <xref:System.Windows.Forms.DataGridView> control denominado `dataGridView1` que contiene una columna denominada `Rating` para mostrar los valores de cadena de uno a cuatro asterisco ("\*") los símbolos.</span><span class="sxs-lookup"><span data-stu-id="f65b8-112">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1` that contains a column named `Rating` for displaying string values of one through four asterisk ("\*") symbols.</span></span> <span data-ttu-id="f65b8-113">El <xref:System.Windows.Forms.DataGridView.CellFormatting> evento del control debe estar asociada con el método de controlador de eventos que se muestra en el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="f65b8-113">The <xref:System.Windows.Forms.DataGridView.CellFormatting> event of the control must be associated with the event handler method shown in the example.</span></span>  
  
- <span data-ttu-id="f65b8-114">Referencias a los ensamblados <xref:System?displayProperty=nameWithType> y <xref:System.Windows.Forms?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="f65b8-114">References to the <xref:System?displayProperty=nameWithType> and <xref:System.Windows.Forms?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="f65b8-115">Programación sólida</span><span class="sxs-lookup"><span data-stu-id="f65b8-115">Robust Programming</span></span>  
 <span data-ttu-id="f65b8-116">Al enlazar la <xref:System.Windows.Forms.DataGridView> el control a un origen de datos externo o proporcionar su propio origen de datos al implementar el modo virtual, podría encontrar problemas de rendimiento.</span><span class="sxs-lookup"><span data-stu-id="f65b8-116">When you bind the <xref:System.Windows.Forms.DataGridView> control to an external data source or provide your own data source by implementing virtual mode, you might encounter performance issues.</span></span> <span data-ttu-id="f65b8-117">Para evitar una reducción del rendimiento cuando se trabaja con grandes cantidades de datos, controlar el <xref:System.Windows.Forms.DataGridView.CellToolTipTextNeeded> evento en lugar de la configuración de la <xref:System.Windows.Forms.DataGridViewCell.ToolTipText%2A> propiedad de varias celdas.</span><span class="sxs-lookup"><span data-stu-id="f65b8-117">To avoid a performance penalty when working with large amounts of data, handle the <xref:System.Windows.Forms.DataGridView.CellToolTipTextNeeded> event rather than setting the <xref:System.Windows.Forms.DataGridViewCell.ToolTipText%2A> property of multiple cells.</span></span> <span data-ttu-id="f65b8-118">Cuando controle este evento, obtener el valor de una celda <xref:System.Windows.Forms.DataGridViewCell.ToolTipText%2A> propiedad provoca el evento y devuelve el valor de la <xref:System.Windows.Forms.DataGridViewCellToolTipTextNeededEventArgs.ToolTipText%2A?displayProperty=nameWithType> la propiedad especificados en el evento de controlador.</span><span class="sxs-lookup"><span data-stu-id="f65b8-118">When you handle this event, getting the value of a cell <xref:System.Windows.Forms.DataGridViewCell.ToolTipText%2A> property raises the event and returns the value of the <xref:System.Windows.Forms.DataGridViewCellToolTipTextNeededEventArgs.ToolTipText%2A?displayProperty=nameWithType> property as specified in the event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f65b8-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="f65b8-119">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.ShowCellToolTips%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.CellToolTipTextNeeded?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewCell>
- <xref:System.Windows.Forms.DataGridViewCell.ToolTipText%2A?displayProperty=nameWithType>
- [<span data-ttu-id="f65b8-120">Programar con celdas, filas y columnas en el control DataGridView de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f65b8-120">Programming with Cells, Rows, and Columns in the Windows Forms DataGridView Control</span></span>](programming-with-cells-rows-and-columns-in-the-datagrid.md)
