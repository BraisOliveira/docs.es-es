---
title: Procedimiento para cambiar el orden de las columnas en el control DataGridView de formularios Windows Forms mediante el diseñador
ms.date: 03/30/2017
helpviewer_keywords:
- columns [Windows Forms], order of
- DataGridView control [Windows Forms], column order
- Windows Forms, columns
- data [Windows Forms], displaying
ms.assetid: 7fe52a98-75d6-448c-97a5-65ca2c568c1a
ms.openlocfilehash: cb8aeb30e12f7af18b475fd7707fa9d2ede6a299
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61939092"
---
# <a name="how-to-change-the-order-of-columns-in-the-windows-forms-datagridview-control-using-the-designer"></a><span data-ttu-id="83c09-102">Procedimiento para cambiar el orden de las columnas en el control DataGridView de formularios Windows Forms mediante el diseñador</span><span class="sxs-lookup"><span data-stu-id="83c09-102">How to: Change the Order of Columns in the Windows Forms DataGridView Control Using the Designer</span></span>
<span data-ttu-id="83c09-103">Al enlazar un formulario Windows Forms <xref:System.Windows.Forms.DataGridView> control a un origen de datos, el orden de visualización de las columnas generadas automáticamente viene determinado por el origen de datos.</span><span class="sxs-lookup"><span data-stu-id="83c09-103">When you bind a Windows Forms <xref:System.Windows.Forms.DataGridView> control to a data source, the display order of the automatically generated columns is dictated by the data source.</span></span> <span data-ttu-id="83c09-104">Si este orden es no lo que prefiere, puede cambiar el orden de las columnas mediante el diseñador.</span><span class="sxs-lookup"><span data-stu-id="83c09-104">If this order is not what you prefer, you can change the order of the columns using the designer.</span></span> <span data-ttu-id="83c09-105">También puede agregar columnas sin enlazar al control y cambiar su orden de presentación.</span><span class="sxs-lookup"><span data-stu-id="83c09-105">You may also want to add unbound columns to the control and change their display order.</span></span> <span data-ttu-id="83c09-106">Para obtener información acerca de cómo cambiar el orden de columna mediante programación, vea [Cómo: Cambiar el orden de columnas en el Control DataGridView de formularios de Windows](how-to-change-the-order-of-columns-in-the-windows-forms-datagridview-control.md).</span><span class="sxs-lookup"><span data-stu-id="83c09-106">For information about how to change the column order programmatically, see [How to: Change the Order of Columns in the Windows Forms DataGridView Control](how-to-change-the-order-of-columns-in-the-windows-forms-datagridview-control.md).</span></span>  
  
 <span data-ttu-id="83c09-107">El procedimiento siguiente requiere una **aplicación Windows** proyecto con un formulario que contenga un <xref:System.Windows.Forms.DataGridView> control.</span><span class="sxs-lookup"><span data-stu-id="83c09-107">The following procedure requires a **Windows Application** project with a form containing a <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="83c09-108">Para obtener información acerca de cómo configurar un proyecto de este tipo, vea [Cómo: Cree un proyecto de aplicación de Windows Forms](/visualstudio/ide/step-1-create-a-windows-forms-application-project) y [Cómo: Agregar controles a Windows Forms](how-to-add-controls-to-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="83c09-108">For information about setting up such a project, see [How to: Create a Windows Forms application project](/visualstudio/ide/step-1-create-a-windows-forms-application-project) and [How to: Add Controls to Windows Forms](how-to-add-controls-to-windows-forms.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="83c09-109">Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos.</span><span class="sxs-lookup"><span data-stu-id="83c09-109">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="83c09-110">Para cambiar la configuración, elija la opción **Importar y exportar configuraciones** del menú **Herramientas** .</span><span class="sxs-lookup"><span data-stu-id="83c09-110">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="83c09-111">Para obtener más información, consulte [personalizar el IDE de Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide)</span><span class="sxs-lookup"><span data-stu-id="83c09-111">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide)</span></span>  
  
### <a name="to-change-the-column-order-using-the-designer"></a><span data-ttu-id="83c09-112">Para cambiar el orden de columna mediante el diseñador</span><span class="sxs-lookup"><span data-stu-id="83c09-112">To change the column order using the designer</span></span>  
  
1. <span data-ttu-id="83c09-113">Haga clic en el glifo de etiqueta inteligente (![glifo de etiqueta inteligente](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) en la esquina superior derecha de la <xref:System.Windows.Forms.DataGridView> control y, a continuación, seleccione **Editar columnas**.</span><span class="sxs-lookup"><span data-stu-id="83c09-113">Click the smart tag glyph (![Smart Tag Glyph](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) on the upper-right corner of the <xref:System.Windows.Forms.DataGridView> control, and then select **Edit Columns**.</span></span>  
  
2. <span data-ttu-id="83c09-114">Seleccione una columna en la **columnas seleccionadas** lista.</span><span class="sxs-lookup"><span data-stu-id="83c09-114">Select a column from the **Selected Columns** list.</span></span>  
  
3. <span data-ttu-id="83c09-115">Haga clic en arriba o abajo a la derecha de la **columnas seleccionadas** lista hasta que la columna seleccionada en la posición que desee.</span><span class="sxs-lookup"><span data-stu-id="83c09-115">Click the up or down arrow to the right of the **Selected Columns** list until the selected column is in the position you want.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83c09-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="83c09-116">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- [<span data-ttu-id="83c09-117">Cómo: Agregar y quitar columnas en el Control de DataGridView de Windows Forms mediante el diseñador</span><span class="sxs-lookup"><span data-stu-id="83c09-117">How to: Add and Remove Columns in the Windows Forms DataGridView Control Using the Designer</span></span>](add-and-remove-columns-in-the-datagrid-using-the-designer.md)
- [<span data-ttu-id="83c09-118">Cómo: Crear un proyecto de aplicación de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="83c09-118">How to: Create a Windows Forms application project</span></span>](/visualstudio/ide/step-1-create-a-windows-forms-application-project)
- [<span data-ttu-id="83c09-119">Cómo: Agregar controles a Windows Forms</span><span class="sxs-lookup"><span data-stu-id="83c09-119">How to: Add Controls to Windows Forms</span></span>](how-to-add-controls-to-windows-forms.md)
