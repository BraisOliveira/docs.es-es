---
title: Procedimiento para mostrar ayuda emergente
ms.date: 03/30/2017
helpviewer_keywords:
- pop-up Help
- Help [Windows Forms], pop-up Help
- Windows Forms, displaying Help
- forms [Windows Forms], displaying Help
- modal dialog boxes [Windows Forms], pop-up Help
- F1 Help [Windows Forms], in dialog boxes
- HelpProvider component [Windows Forms]
- Help [Windows Forms], adding to dialog boxes
ms.assetid: 218aa81e-e87e-4d67-af05-11627bbdce3b
ms.openlocfilehash: f805840ea3b1a8aef6a289dba064c468a4da0cb0
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59331486"
---
# <a name="how-to-display-pop-up-help"></a><span data-ttu-id="dd515-102">Procedimiento para mostrar ayuda emergente</span><span class="sxs-lookup"><span data-stu-id="dd515-102">How to: Display Pop-up Help</span></span>
<span data-ttu-id="dd515-103">Es una manera de mostrar la Ayuda en Windows Forms a través de la **ayuda** situado en el lado derecho de la barra de título, accesible a través de la <xref:System.Windows.Forms.Form.HelpButton%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="dd515-103">One way to display Help on Windows Forms is through the **Help** button, located on the right side of the title bar, accessible through the <xref:System.Windows.Forms.Form.HelpButton%2A> property.</span></span> <span data-ttu-id="dd515-104">Este tipo de visualización de la Ayuda está indicado para cuadros de diálogo.</span><span class="sxs-lookup"><span data-stu-id="dd515-104">This type of Help display is well-suited for use with dialog boxes.</span></span> <span data-ttu-id="dd515-105">Los cuadros de diálogo que se muestran de forma modal (con el método <xref:System.Windows.Forms.Form.ShowDialog%2A>) tienen problemas para abrir los sistemas de Ayuda externos porque los cuadros de diálogo modales deben cerrarse antes de poder pasar el foco a otra ventana.</span><span class="sxs-lookup"><span data-stu-id="dd515-105">Dialog boxes shown modally (with the <xref:System.Windows.Forms.Form.ShowDialog%2A> method) have trouble bringing up external Help systems, because modal dialog boxes need to be closed before focus can shift to another window.</span></span> <span data-ttu-id="dd515-106">Además, el uso de la **ayuda** botón requiere que no hay ningún **minimizar** botón o **maximizar** botón se muestra en la barra de título.</span><span class="sxs-lookup"><span data-stu-id="dd515-106">Additionally, using the **Help** button requires that there is no **Minimize** button or **Maximize** button shown in the title bar.</span></span> <span data-ttu-id="dd515-107">Esta es una convención de cuadro de diálogo estándar, mientras que los formularios normalmente tienen **minimizar** y **maximizar** botones.</span><span class="sxs-lookup"><span data-stu-id="dd515-107">This is a standard dialog-box convention, whereas forms usually have **Minimize** and **Maximize** buttons.</span></span>  
  
 <span data-ttu-id="dd515-108">Tenga en cuenta que también puede usar el componente <xref:System.Windows.Forms.HelpProvider> para vincular controles a archivos en un sistema de Ayuda, aunque haya implementado ayuda emergente.</span><span class="sxs-lookup"><span data-stu-id="dd515-108">Be aware that you can also use the <xref:System.Windows.Forms.HelpProvider> component to link controls to files in a Help system, even if you have implemented pop-up Help.</span></span> <span data-ttu-id="dd515-109">Para obtener más información, consulte [proporcionar ayuda en una aplicación de Windows](how-to-provide-help-in-a-windows-application.md).</span><span class="sxs-lookup"><span data-stu-id="dd515-109">For more information, see [Providing Help in a Windows Application](how-to-provide-help-in-a-windows-application.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="dd515-110">Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos.</span><span class="sxs-lookup"><span data-stu-id="dd515-110">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="dd515-111">Para cambiar la configuración, elija la opción **Importar y exportar configuraciones** del menú **Herramientas** .</span><span class="sxs-lookup"><span data-stu-id="dd515-111">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="dd515-112">Para más información, vea [Personalizar el IDE de Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).</span><span class="sxs-lookup"><span data-stu-id="dd515-112">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-display-pop-up-help"></a><span data-ttu-id="dd515-113">Para mostrar Ayuda emergente</span><span class="sxs-lookup"><span data-stu-id="dd515-113">To display pop-up Help</span></span>  
  
1. <span data-ttu-id="dd515-114">Arrastre un [HelpProvider](../controls/helpprovider-component-windows-forms.md) componente desde el cuadro de herramientas al formulario.</span><span class="sxs-lookup"><span data-stu-id="dd515-114">Drag a [HelpProvider](../controls/helpprovider-component-windows-forms.md) component from the Toolbox to your form.</span></span>  
  
     <span data-ttu-id="dd515-115">Se colocará en la bandeja, en la parte inferior del Diseñador de Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="dd515-115">It will sit in the tray at the bottom of the Windows Forms Designer.</span></span>  
  
2. <span data-ttu-id="dd515-116">En la ventana de propiedades, establezca la propiedad <xref:System.Windows.Forms.Form.HelpButton%2A> en `true`.</span><span class="sxs-lookup"><span data-stu-id="dd515-116">In the Properties window, set the <xref:System.Windows.Forms.Form.HelpButton%2A> property to `true`.</span></span> <span data-ttu-id="dd515-117">Se mostrará un botón con un signo de interrogación en el lado derecho de la barra de título del formulario.</span><span class="sxs-lookup"><span data-stu-id="dd515-117">This will display a button with a question mark in it on the right side of the title bar of the form.</span></span>  
  
3. <span data-ttu-id="dd515-118">Para que el <xref:System.Windows.Forms.Form.HelpButton%2A> se muestre, las propiedades <xref:System.Windows.Forms.Form.MinimizeBox%2A> y <xref:System.Windows.Forms.Form.MaximizeBox%2A> del formulario deben establecerse en `false`, la propiedad <xref:System.Windows.Forms.Form.ControlBox%2A> debe establecerse en `true` y la propiedad <xref:System.Windows.Forms.Form.FormBorderStyle%2A> debe establecerse en uno de los siguientes valores: <xref:System.Windows.Forms.FormBorderStyle.FixedSingle>, <xref:System.Windows.Forms.FormBorderStyle.Fixed3D>, <xref:System.Windows.Forms.FormBorderStyle.FixedDialog> o <xref:System.Windows.Forms.FormBorderStyle.Sizable>.</span><span class="sxs-lookup"><span data-stu-id="dd515-118">In order for the <xref:System.Windows.Forms.Form.HelpButton%2A> to display, the form's <xref:System.Windows.Forms.Form.MinimizeBox%2A> and <xref:System.Windows.Forms.Form.MaximizeBox%2A> properties must be set to `false`, the <xref:System.Windows.Forms.Form.ControlBox%2A> property set to `true`, and the <xref:System.Windows.Forms.Form.FormBorderStyle%2A> property to one of the following values: <xref:System.Windows.Forms.FormBorderStyle.FixedSingle>, <xref:System.Windows.Forms.FormBorderStyle.Fixed3D>, <xref:System.Windows.Forms.FormBorderStyle.FixedDialog> or <xref:System.Windows.Forms.FormBorderStyle.Sizable>.</span></span>  
  
4. <span data-ttu-id="dd515-119">Seleccione el control para el que quiere mostrar la Ayuda en el formulario y establezca la cadena de Ayuda en la ventana Propiedades.</span><span class="sxs-lookup"><span data-stu-id="dd515-119">Select the control for which you want to show help on your form and set the Help string in the Properties window.</span></span> <span data-ttu-id="dd515-120">Esta es la cadena de texto que se mostrará en una ventana similar a un [información sobre herramientas](../controls/tooltip-component-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="dd515-120">This is the string of text that will be displayed in a window similar to a [ToolTip](../controls/tooltip-component-windows-forms.md).</span></span>  
  
5. <span data-ttu-id="dd515-121">Presione **F5**.</span><span class="sxs-lookup"><span data-stu-id="dd515-121">Press **F5**.</span></span>  
  
6. <span data-ttu-id="dd515-122">Presione el **ayuda** situado en la barra de título y haga clic en el control en el que se establece la cadena de ayuda.</span><span class="sxs-lookup"><span data-stu-id="dd515-122">Press the **Help** button on the title bar and click the control on which you set the Help string.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dd515-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="dd515-123">See also</span></span>

- [<span data-ttu-id="dd515-124">Controlar la ayuda mediante componentes Tooltip</span><span class="sxs-lookup"><span data-stu-id="dd515-124">Control Help Using ToolTips</span></span>](control-help-using-tooltips.md)
- [<span data-ttu-id="dd515-125">Integrar la Ayuda de usuario en Windows Forms</span><span class="sxs-lookup"><span data-stu-id="dd515-125">Integrating User Help in Windows Forms</span></span>](integrating-user-help-in-windows-forms.md)
- [<span data-ttu-id="dd515-126">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="dd515-126">Windows Forms</span></span>](../index.md)
