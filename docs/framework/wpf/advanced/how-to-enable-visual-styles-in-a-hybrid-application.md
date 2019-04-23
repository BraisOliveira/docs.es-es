---
title: Procedimiento para habilitar estilos visuales en una aplicación híbrida
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hybrid applications [WPF interoperability]
- visual styles [Windows Forms]
ms.assetid: 95de9b9c-d804-405c-b2d1-49a88c1e0fe1
ms.openlocfilehash: 7aa5208a4f378408a01a08a2f4c9dbf2edfa5243
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59323608"
---
# <a name="how-to-enable-visual-styles-in-a-hybrid-application"></a><span data-ttu-id="6ba25-102">Procedimiento para habilitar estilos visuales en una aplicación híbrida</span><span class="sxs-lookup"><span data-stu-id="6ba25-102">How to: Enable Visual Styles in a Hybrid Application</span></span>
<span data-ttu-id="6ba25-103">En este tema se muestra cómo habilitar [!INCLUDE[TLA#tla_winxp](../../../../includes/tlasharptla-winxp-md.md)] los estilos visuales en un [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control hospedado en un [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-aplicación basada en.</span><span class="sxs-lookup"><span data-stu-id="6ba25-103">This topic shows how to enable [!INCLUDE[TLA#tla_winxp](../../../../includes/tlasharptla-winxp-md.md)] visual styles on a [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control hosted in a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-based application.</span></span>  
  
 <span data-ttu-id="6ba25-104">Si la aplicación llama a la <xref:System.Windows.Forms.Application.EnableVisualStyles%2A> método, la mayoría de los [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controles usarán automáticamente los estilos visuales cuando la aplicación se ejecuta en [!INCLUDE[TLA#tla_winxp](../../../../includes/tlasharptla-winxp-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6ba25-104">If your application calls the <xref:System.Windows.Forms.Application.EnableVisualStyles%2A> method, most of your [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controls will automatically use visual styles when your application is run on [!INCLUDE[TLA#tla_winxp](../../../../includes/tlasharptla-winxp-md.md)].</span></span> <span data-ttu-id="6ba25-105">Para obtener más información, consulte [representar controles con estilos visuales](../../winforms/controls/rendering-controls-with-visual-styles.md).</span><span class="sxs-lookup"><span data-stu-id="6ba25-105">For more information, see [Rendering Controls with Visual Styles](../../winforms/controls/rendering-controls-with-visual-styles.md).</span></span>  
  
 <span data-ttu-id="6ba25-106">Para obtener una lista de código completo de las tareas ilustradas en este tema, consulte [Enabling Visual Styles in a Hybrid Application Sample](https://go.microsoft.com/fwlink/?LinkID=159986).</span><span class="sxs-lookup"><span data-stu-id="6ba25-106">For a complete code listing of the tasks illustrated in this topic, see [Enabling Visual Styles in a Hybrid Application Sample](https://go.microsoft.com/fwlink/?LinkID=159986).</span></span>  
  
## <a name="enabling-windows-forms-visual-styles"></a><span data-ttu-id="6ba25-107">Habilitar estilos visuales de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="6ba25-107">Enabling Windows Forms Visual Styles</span></span>  
  
#### <a name="to-enable-windows-forms-visual-styles"></a><span data-ttu-id="6ba25-108">Para habilitar estilos visuales de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="6ba25-108">To enable Windows Forms visual styles</span></span>  
  
1. <span data-ttu-id="6ba25-109">Crear un [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] proyecto de aplicación denominado `HostingWfWithVisualStyles`.</span><span class="sxs-lookup"><span data-stu-id="6ba25-109">Create a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Application project named `HostingWfWithVisualStyles`.</span></span>  
  
2. <span data-ttu-id="6ba25-110">En el Explorador de soluciones, agregue referencias a los ensamblados siguientes.</span><span class="sxs-lookup"><span data-stu-id="6ba25-110">In Solution Explorer, add references to the following assemblies.</span></span>  
  
    -   <span data-ttu-id="6ba25-111">WindowsFormsIntegration</span><span class="sxs-lookup"><span data-stu-id="6ba25-111">WindowsFormsIntegration</span></span>  
  
    -   <span data-ttu-id="6ba25-112">System.Windows.Forms</span><span class="sxs-lookup"><span data-stu-id="6ba25-112">System.Windows.Forms</span></span>  
  
3. <span data-ttu-id="6ba25-113">En el cuadro de herramientas, haga doble clic en el <xref:System.Windows.Controls.Grid> icono para colocar un <xref:System.Windows.Controls.Grid> elemento en la superficie de diseño.</span><span class="sxs-lookup"><span data-stu-id="6ba25-113">In the Toolbox, double-click the <xref:System.Windows.Controls.Grid> icon to place a <xref:System.Windows.Controls.Grid> element on the design surface.</span></span>  
  
4. <span data-ttu-id="6ba25-114">En la ventana Propiedades, establezca los valores de la <xref:System.Windows.FrameworkElement.Height%2A> y <xref:System.Windows.FrameworkElement.Width%2A> propiedades a **automática**.</span><span class="sxs-lookup"><span data-stu-id="6ba25-114">In the Properties window, set the values of the <xref:System.Windows.FrameworkElement.Height%2A> and <xref:System.Windows.FrameworkElement.Width%2A> properties to **Auto**.</span></span>  
  
5. <span data-ttu-id="6ba25-115">En la vista Diseño o la vista XAML, seleccione el <xref:System.Windows.Window>.</span><span class="sxs-lookup"><span data-stu-id="6ba25-115">In Design view or XAML view, select the <xref:System.Windows.Window>.</span></span>  
  
6. <span data-ttu-id="6ba25-116">En la ventana Propiedades, haga clic en el **eventos** ficha.</span><span class="sxs-lookup"><span data-stu-id="6ba25-116">In the Properties window, click the **Events** tab.</span></span>  
  
7. <span data-ttu-id="6ba25-117">Haga doble clic en el <xref:System.Windows.FrameworkElement.Loaded> eventos.</span><span class="sxs-lookup"><span data-stu-id="6ba25-117">Double-click the <xref:System.Windows.FrameworkElement.Loaded> event.</span></span>
  
8. <span data-ttu-id="6ba25-118">En MainWindow.xaml.vb o MainWindow.xaml.cs, inserte el código siguiente para controlar el <xref:System.Windows.FrameworkElement.Loaded> eventos.</span><span class="sxs-lookup"><span data-stu-id="6ba25-118">In MainWindow.xaml.vb or MainWindow.xaml.cs, insert the following code to handle the <xref:System.Windows.FrameworkElement.Loaded> event.</span></span>  
  
     [!code-csharp[HostingWfWithVisualStyles#11](~/samples/snippets/csharp/VS_Snippets_Wpf/HostingWfWithVisualStyles/CSharp/HostingWfWithVisualStyles/Window1.xaml.cs#11)]
     [!code-vb[HostingWfWithVisualStyles#11](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HostingWfWithVisualStyles/VisualBasic/HostingWfWithVisualStyles/Window1.xaml.vb#11)]  
  
9. <span data-ttu-id="6ba25-119">Presione F5 para compilar y ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="6ba25-119">Press F5 to build and run the application.</span></span>  
  
     <span data-ttu-id="6ba25-120">El [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control se dibuja con estilos visuales.</span><span class="sxs-lookup"><span data-stu-id="6ba25-120">The [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control is painted with visual styles.</span></span>  
  
## <a name="disabling-windows-forms-visual-styles"></a><span data-ttu-id="6ba25-121">Deshabilitar estilos visuales de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="6ba25-121">Disabling Windows Forms Visual Styles</span></span>  
 <span data-ttu-id="6ba25-122">Para deshabilitar estilos visuales, basta con quitar la llamada a la <xref:System.Windows.Forms.Application.EnableVisualStyles%2A> método.</span><span class="sxs-lookup"><span data-stu-id="6ba25-122">To disable visual styles, simply remove the call to the <xref:System.Windows.Forms.Application.EnableVisualStyles%2A> method.</span></span>  
  
#### <a name="to-disable-windows-forms-visual-styles"></a><span data-ttu-id="6ba25-123">Para deshabilitar estilos visuales de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="6ba25-123">To disable Windows Forms visual styles</span></span>  
  
1. <span data-ttu-id="6ba25-124">Abra MainWindow.xaml.vb o MainWindow.xaml.cs en el Editor de código.</span><span class="sxs-lookup"><span data-stu-id="6ba25-124">Open MainWindow.xaml.vb or MainWindow.xaml.cs in the Code Editor.</span></span>  
  
2. <span data-ttu-id="6ba25-125">Comente la llamada a la <xref:System.Windows.Forms.Application.EnableVisualStyles%2A> método.</span><span class="sxs-lookup"><span data-stu-id="6ba25-125">Comment out the call to the <xref:System.Windows.Forms.Application.EnableVisualStyles%2A> method.</span></span>  
  
3. <span data-ttu-id="6ba25-126">Presione F5 para compilar y ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="6ba25-126">Press F5 to build and run the application.</span></span>  
  
     <span data-ttu-id="6ba25-127">El [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control se dibuja con el estilo predeterminado del sistema.</span><span class="sxs-lookup"><span data-stu-id="6ba25-127">The [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control is painted with the default system style.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6ba25-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="6ba25-128">See also</span></span>

- <xref:System.Windows.Forms.Application.EnableVisualStyles%2A>
- <xref:System.Windows.Forms.VisualStyles>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [<span data-ttu-id="6ba25-129">Representar controles con estilos visuales</span><span class="sxs-lookup"><span data-stu-id="6ba25-129">Rendering Controls with Visual Styles</span></span>](../../winforms/controls/rendering-controls-with-visual-styles.md)
- [<span data-ttu-id="6ba25-130">Tutorial: Hospedar un Control de Windows Forms en WPF</span><span class="sxs-lookup"><span data-stu-id="6ba25-130">Walkthrough: Hosting a Windows Forms Control in WPF</span></span>](walkthrough-hosting-a-windows-forms-control-in-wpf.md)
