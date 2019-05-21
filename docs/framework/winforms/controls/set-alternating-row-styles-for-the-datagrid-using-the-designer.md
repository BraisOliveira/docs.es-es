---
title: Procedimiento para establecer estilos de fila alternos en el control DataGridView de formularios Windows Forms mediante el diseñador
ms.date: 03/30/2017
helpviewer_keywords:
- ledger-like formats
- DataGridView control [Windows Forms], row style alternation
- Windows Forms, rows
- rows [Windows Forms], alternating
- data [Windows Forms], displaying
ms.assetid: 02373442-bf94-4470-9f8a-e44c4a9d5b88
ms.openlocfilehash: fea160e62939a27521592201cd47615975b7733f
ms.sourcegitcommit: ffd7dd79468a81bbb0d6449f6d65513e050c04c4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/21/2019
ms.locfileid: "65959397"
---
# <a name="how-to-set-alternating-row-styles-for-the-windows-forms-datagridview-control-using-the-designer"></a><span data-ttu-id="f8153-102">Procedimiento para establecer estilos de fila alternos en el control DataGridView de formularios Windows Forms mediante el diseñador</span><span class="sxs-lookup"><span data-stu-id="f8153-102">How to: Set Alternating Row Styles for the Windows Forms DataGridView Control Using the Designer</span></span>

<span data-ttu-id="f8153-103">Datos tabulares a menudo se presentan en un formato de carta donde las filas alternas tienen distintos colores de fondo.</span><span class="sxs-lookup"><span data-stu-id="f8153-103">Tabular data is often presented in a ledger-like format where alternating rows have different background colors.</span></span> <span data-ttu-id="f8153-104">Este formato permite a los usuarios saber fácilmente qué celdas están en cada fila, especialmente con tablas anchas que tienen muchas columnas.</span><span class="sxs-lookup"><span data-stu-id="f8153-104">This format makes it easier for users to tell which cells are in each row, especially with wide tables that have many columns.</span></span>

<span data-ttu-id="f8153-105">Con el control <xref:System.Windows.Forms.DataGridView>, puede especificar la información de estilo completa para las filas alternas.</span><span class="sxs-lookup"><span data-stu-id="f8153-105">With the <xref:System.Windows.Forms.DataGridView> control, you can specify complete style information for alternating rows.</span></span> <span data-ttu-id="f8153-106">Puede usar las características de estilo, como el color de primer plano y la fuente, además del color de fondo, para diferenciar las filas alternas.</span><span class="sxs-lookup"><span data-stu-id="f8153-106">You can use style characteristics like foreground color and font, in addition to background color, to differentiate alternating rows.</span></span> <span data-ttu-id="f8153-107">Para obtener más información, consulte [estilos de celda en el DataGridView Control de Windows Forms](cell-styles-in-the-windows-forms-datagridview-control.md).</span><span class="sxs-lookup"><span data-stu-id="f8153-107">For more information, see [Cell Styles in the Windows Forms DataGridView Control](cell-styles-in-the-windows-forms-datagridview-control.md).</span></span>

<span data-ttu-id="f8153-108">El procedimiento siguiente requiere una **aplicación Windows** proyecto con un formulario que contenga un <xref:System.Windows.Forms.DataGridView> control.</span><span class="sxs-lookup"><span data-stu-id="f8153-108">The following procedure requires a **Windows Application** project with a form containing a <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="f8153-109">Para obtener información acerca de cómo configurar un proyecto de este tipo, vea [Cómo: Cree un proyecto de aplicación de Windows Forms](/visualstudio/ide/step-1-create-a-windows-forms-application-project) y [Cómo: Agregar controles a Windows Forms](how-to-add-controls-to-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="f8153-109">For information about setting up such a project, see [How to: Create a Windows Forms application project](/visualstudio/ide/step-1-create-a-windows-forms-application-project) and [How to: Add Controls to Windows Forms](how-to-add-controls-to-windows-forms.md).</span></span>

> [!NOTE]
> <span data-ttu-id="f8153-110">Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos.</span><span class="sxs-lookup"><span data-stu-id="f8153-110">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="f8153-111">Para cambiar la configuración, elija la opción **Importar y exportar configuraciones** del menú **Herramientas** .</span><span class="sxs-lookup"><span data-stu-id="f8153-111">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="f8153-112">Para más información, vea [Personalizar el IDE de Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).</span><span class="sxs-lookup"><span data-stu-id="f8153-112">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>

### <a name="define-styles-for-alternating-rows"></a><span data-ttu-id="f8153-113">Definir estilos para las filas alternas</span><span class="sxs-lookup"><span data-stu-id="f8153-113">Define styles for alternating rows</span></span>

1. <span data-ttu-id="f8153-114">Seleccione el <xref:System.Windows.Forms.DataGridView> control en el diseñador.</span><span class="sxs-lookup"><span data-stu-id="f8153-114">Select the <xref:System.Windows.Forms.DataGridView> control in the designer.</span></span>

2. <span data-ttu-id="f8153-115">En el **propiedades** ventana, haga clic en el botón de puntos suspensivos (![los puntos suspensivos (...) en la ventana Propiedades de Visual Studio.](./media/visual-studio-ellipsis-button.png)) junto a la <xref:System.Windows.Forms.DataGridView.AlternatingRowsDefaultCellStyle%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="f8153-115">In the **Properties** window, click the ellipsis button (![The Ellipsis button (...) in the Properties window of Visual Studio.](./media/visual-studio-ellipsis-button.png)) next to the <xref:System.Windows.Forms.DataGridView.AlternatingRowsDefaultCellStyle%2A> property.</span></span>

3. <span data-ttu-id="f8153-116">En el **generador de CellStyle** definir el estilo estableciendo las propiedades de cuadro de diálogo y usar el **Preview** panel para confirmar las opciones seleccionadas.</span><span class="sxs-lookup"><span data-stu-id="f8153-116">In the **CellStyle Builder** dialog box, define the style by setting the properties, and use the **Preview** pane to confirm your choices.</span></span> <span data-ttu-id="f8153-117">Los estilos que especifique se usan para todas las demás filas mostrado en el control, empezando por la segunda.</span><span class="sxs-lookup"><span data-stu-id="f8153-117">The styles you specify are used for every other row displayed in the control, starting with the second one.</span></span>

4. <span data-ttu-id="f8153-118">Para definir estilos para las filas restantes, repita los pasos 2 y 3 con el <xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="f8153-118">To define styles for the remaining rows, repeat steps 2 and 3 using the <xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A> property.</span></span>

    > [!NOTE]
    > <span data-ttu-id="f8153-119">Se muestran las celdas con los estilos que se hereda de varias propiedades.</span><span class="sxs-lookup"><span data-stu-id="f8153-119">Cells are displayed using styles inherited from multiple properties.</span></span> <span data-ttu-id="f8153-120">Para obtener más información sobre la herencia de estilo, consulte [estilos de celda en el DataGridView Control de Windows Forms](cell-styles-in-the-windows-forms-datagridview-control.md).</span><span class="sxs-lookup"><span data-stu-id="f8153-120">For more information about style inheritance, see [Cell Styles in the Windows Forms DataGridView Control](cell-styles-in-the-windows-forms-datagridview-control.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="f8153-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="f8153-121">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- [<span data-ttu-id="f8153-122">Estilos de celda en el control DataGridView de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f8153-122">Cell Styles in the Windows Forms DataGridView Control</span></span>](cell-styles-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="f8153-123">Estilo y formato básicos del control DataGridView en formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f8153-123">Basic Formatting and Styling in the Windows Forms DataGridView Control</span></span>](basic-formatting-and-styling-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="f8153-124">Utilizar el Diseñador con el control DataGridView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f8153-124">Using the Designer with the Windows Forms DataGridView Control</span></span>](using-the-designer-with-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="f8153-125">Cómo: Crear un proyecto de aplicación de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f8153-125">How to: Create a Windows Forms application project</span></span>](/visualstudio/ide/step-1-create-a-windows-forms-application-project)
- [<span data-ttu-id="f8153-126">Cómo: Agregar controles a Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f8153-126">How to: Add Controls to Windows Forms</span></span>](how-to-add-controls-to-windows-forms.md)
