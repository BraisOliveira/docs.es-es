---
title: Procedimiento Crear un cuadro de diálogo estándar de interfaz de usuario mediante Grid
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- dialog boxes [WPF], creating
- Grid control [WPF], creating [WPF], dialog box
ms.assetid: d6ac3d51-844b-4d29-96d8-81a696a7b960
ms.openlocfilehash: 0ade908e92e552017acb9ba242ccba2c28c3c995
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59149531"
---
# <a name="how-to-build-a-standard-ui-dialog-box-by-using-grid"></a><span data-ttu-id="5b495-102">Procedimiento Crear un cuadro de diálogo estándar de interfaz de usuario mediante Grid</span><span class="sxs-lookup"><span data-stu-id="5b495-102">How to: Build a Standard UI Dialog Box by Using Grid</span></span>
<span data-ttu-id="5b495-103">En este ejemplo se muestra cómo crear un estándar [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] cuadro de diálogo mediante el uso de la <xref:System.Windows.Controls.Grid> elemento.</span><span class="sxs-lookup"><span data-stu-id="5b495-103">This example shows how to create a standard [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] dialog box by using the <xref:System.Windows.Controls.Grid> element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5b495-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="5b495-104">Example</span></span>  
 <span data-ttu-id="5b495-105">En el ejemplo siguiente se crea un cuadro de diálogo como el **ejecutar** cuadro de diálogo en el [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="5b495-105">The following example creates a dialog box like the **Run** dialog box in the [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] operating system.</span></span>  
  
 <span data-ttu-id="5b495-106">El ejemplo se crea un <xref:System.Windows.Controls.Grid> y usa el <xref:System.Windows.Controls.ColumnDefinition> y <xref:System.Windows.Controls.RowDefinition> las clases para definir las cinco columnas y cuatro filas.</span><span class="sxs-lookup"><span data-stu-id="5b495-106">The example creates a <xref:System.Windows.Controls.Grid> and uses the <xref:System.Windows.Controls.ColumnDefinition> and <xref:System.Windows.Controls.RowDefinition> classes to define five columns and four rows.</span></span>  
  
 <span data-ttu-id="5b495-107">En el ejemplo, a continuación, agrega y coloca un <xref:System.Windows.Controls.Image>, `RunIcon.png`, para representar la imagen que se encuentra en el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="5b495-107">The example then adds and positions an <xref:System.Windows.Controls.Image>, `RunIcon.png`, to represent the image that is found in the dialog box.</span></span> <span data-ttu-id="5b495-108">La imagen se coloca en la primera columna y fila de la <xref:System.Windows.Controls.Grid> (la esquina superior izquierda).</span><span class="sxs-lookup"><span data-stu-id="5b495-108">The image is placed in the first column and row of the <xref:System.Windows.Controls.Grid> (the upper-left corner).</span></span>  
  
 <span data-ttu-id="5b495-109">A continuación, en el ejemplo se agrega un <xref:System.Windows.Controls.TextBlock> elemento a la primera columna, que abarca las columnas restantes de la primera fila.</span><span class="sxs-lookup"><span data-stu-id="5b495-109">Next, the example adds a <xref:System.Windows.Controls.TextBlock> element to the first column, which spans the remaining columns of the first row.</span></span> <span data-ttu-id="5b495-110">También agrega otro <xref:System.Windows.Controls.TextBlock> elemento a la segunda fila de la primera columna, para representar el **abierto** cuadro de texto.</span><span class="sxs-lookup"><span data-stu-id="5b495-110">It adds another <xref:System.Windows.Controls.TextBlock> element to the second row in the first column, to represent the **Open** text box.</span></span> <span data-ttu-id="5b495-111">Un <xref:System.Windows.Controls.TextBlock> siguiente, que representa el área de entrada de datos.</span><span class="sxs-lookup"><span data-stu-id="5b495-111">A <xref:System.Windows.Controls.TextBlock> follows, which represents the data entry area.</span></span>  
  
 <span data-ttu-id="5b495-112">Por último, el ejemplo agrega tres <xref:System.Windows.Controls.Button> elementos a la fila final, que representan el **Aceptar**, **cancelar**, y **examinar** eventos.</span><span class="sxs-lookup"><span data-stu-id="5b495-112">Finally, the example adds three <xref:System.Windows.Controls.Button> elements to the final row, which represent the **OK**, **Cancel**, and **Browse** events.</span></span>  
  
 [!code-csharp[GridRunDialog#1](~/samples/snippets/csharp/VS_Snippets_Wpf/GridRunDialog/CSharp/window1.xaml.cs#1)]
 [!code-vb[GridRunDialog#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/GridRunDialog/VisualBasic/grid_vb.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="5b495-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="5b495-113">See also</span></span>

- <xref:System.Windows.Controls.Grid>
- <xref:System.Windows.GridUnitType>
- [<span data-ttu-id="5b495-114">Información general sobre elementos Panel</span><span class="sxs-lookup"><span data-stu-id="5b495-114">Panels Overview</span></span>](panels-overview.md)
- [<span data-ttu-id="5b495-115">Temas "Cómo..."</span><span class="sxs-lookup"><span data-stu-id="5b495-115">How-to Topics</span></span>](grid-how-to-topics.md)
