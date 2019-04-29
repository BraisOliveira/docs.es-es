---
title: Procedimiento para ocultar columnas en el control DataGridView de formularios Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGridView control [Windows Forms], hiding columns
- data grids [Windows Forms], hiding columns
- columns [Windows Forms], hiding
ms.assetid: 3f94143a-2ef0-49a5-a22a-b2e6f9289642
ms.openlocfilehash: 40fccee551e7840ef474e7775873d4e7178748fe
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61941263"
---
# <a name="how-to-hide-columns-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="fef28-102">Procedimiento para ocultar columnas en el control DataGridView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="fef28-102">How to: Hide Columns in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="fef28-103">Algunas veces querrá mostrar solo algunas de las columnas que están disponibles en un control <xref:System.Windows.Forms.DataGridView> de Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="fef28-103">Sometimes you will want to display only some of the columns that are available in a Windows Forms <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="fef28-104">Por ejemplo, quiere mostrar una columna con el salario de los empleados a usuarios que tengan credenciales de administración, y ocultarla a otros usuarios.</span><span class="sxs-lookup"><span data-stu-id="fef28-104">For example, you might want to show an employee salary column to users with management credentials while hiding it from other users.</span></span> <span data-ttu-id="fef28-105">O quizás quiera enlazar el control a un origen de datos que contiene muchas columnas y mostrar solo algunas de ellas.</span><span class="sxs-lookup"><span data-stu-id="fef28-105">Alternately, you might want to bind the control to a data source that contains many columns, only some of which you want to display.</span></span> <span data-ttu-id="fef28-106">En este caso, normalmente quitaría las columnas que no quiere mostrar en lugar de ocultarlas.</span><span class="sxs-lookup"><span data-stu-id="fef28-106">In this case, you will typically remove the columns you are not interested in displaying rather than hide them.</span></span>  
  
 <span data-ttu-id="fef28-107">En el control <xref:System.Windows.Forms.DataGridView>, el valor de la propiedad <xref:System.Windows.Forms.DataGridViewColumn.Visible%2A> de una columna determina si esa columna se muestra.</span><span class="sxs-lookup"><span data-stu-id="fef28-107">In the <xref:System.Windows.Forms.DataGridView> control, the <xref:System.Windows.Forms.DataGridViewColumn.Visible%2A> property value of a column determines whether that column is displayed.</span></span>  
  
 <span data-ttu-id="fef28-108">Visual Studio es compatible con esta tarea.</span><span class="sxs-lookup"><span data-stu-id="fef28-108">There is support for this task in Visual Studio.</span></span>  <span data-ttu-id="fef28-109">Consulte también [Cómo: Ocultar columnas en la Windows Forms mediante el Diseñador de Control de DataGridView](hide-columns-in-the-datagrid-using-the-designer.md).</span><span class="sxs-lookup"><span data-stu-id="fef28-109">Also see [How to: Hide Columns in the Windows Forms DataGridView Control Using the Designer](hide-columns-in-the-datagrid-using-the-designer.md).</span></span>  
  
### <a name="to-hide-a-column-programmatically"></a><span data-ttu-id="fef28-110">Para ocultar una columna mediante programación</span><span class="sxs-lookup"><span data-stu-id="fef28-110">To hide a column programmatically</span></span>  
  
- <span data-ttu-id="fef28-111">Establezca la propiedad <xref:System.Windows.Forms.DataGridViewColumn.Visible%2A?displayProperty=nameWithType> en `false`.</span><span class="sxs-lookup"><span data-stu-id="fef28-111">Set the <xref:System.Windows.Forms.DataGridViewColumn.Visible%2A?displayProperty=nameWithType> property to `false`.</span></span> <span data-ttu-id="fef28-112">Para ocultar una columna `CustomerID` que se genera automáticamente durante el enlace de datos, coloque el siguiente código de ejemplo en un controlador de eventos <xref:System.Windows.Forms.DataGridView.DataBindingComplete>.</span><span class="sxs-lookup"><span data-stu-id="fef28-112">To hide a `CustomerID` column that is automatically generated during data binding, place the following code example in a <xref:System.Windows.Forms.DataGridView.DataBindingComplete> event handler.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#063](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#063)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#063](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#063)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="fef28-113">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="fef28-113">Compiling the Code</span></span>  
 <span data-ttu-id="fef28-114">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="fef28-114">This example requires:</span></span>  
  
- <span data-ttu-id="fef28-115">Un control <xref:System.Windows.Forms.DataGridView> llamado `dataGridView1` que contiene una columna llamada `CustomerID`.</span><span class="sxs-lookup"><span data-stu-id="fef28-115">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1` that contains a column named `CustomerID`.</span></span>  
  
- <span data-ttu-id="fef28-116">Referencias a los ensamblados <xref:System?displayProperty=nameWithType> y <xref:System.Windows.Forms?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="fef28-116">References to the <xref:System?displayProperty=nameWithType> and <xref:System.Windows.Forms?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fef28-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="fef28-117">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewColumn.Visible%2A?displayProperty=nameWithType>
- [<span data-ttu-id="fef28-118">Características básicas de columnas, filas y celdas en el control DataGridView de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="fef28-118">Basic Column, Row, and Cell Features in the Windows Forms DataGridView Control</span></span>](basic-column-row-and-cell-features-wf-datagridview-control.md)
- [<span data-ttu-id="fef28-119">Cómo: Quitar columnas generadas automáticamente desde un Control DataGridView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="fef28-119">How to: Remove Autogenerated Columns from a Windows Forms DataGridView Control</span></span>](remove-autogenerated-columns-from-a-wf-datagridview-control.md)
- [<span data-ttu-id="fef28-120">Cómo: Cambiar el orden de columnas en el Control DataGridView de formularios de Windows</span><span class="sxs-lookup"><span data-stu-id="fef28-120">How to: Change the Order of Columns in the Windows Forms DataGridView Control</span></span>](how-to-change-the-order-of-columns-in-the-windows-forms-datagridview-control.md)
