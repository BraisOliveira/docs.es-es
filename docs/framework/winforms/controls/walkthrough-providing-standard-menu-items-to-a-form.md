---
title: 'Tutorial: Proporcionar elementos de menú estándar a un formulario'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- menu items [Windows Forms], standard
- toolbars [Windows Forms], walkthroughs
- StatusStrip control [Windows Forms]
- ToolStrip control [Windows Forms]
ms.assetid: dac37d98-589e-4d6d-9673-6437e8943122
ms.openlocfilehash: b4957a3f2efcb31594806a188e3d3bb10c2dac09
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61792215"
---
# <a name="walkthrough-providing-standard-menu-items-to-a-form"></a><span data-ttu-id="69b22-102">Tutorial: Proporcionar elementos de menú estándar a un formulario</span><span class="sxs-lookup"><span data-stu-id="69b22-102">Walkthrough: Providing Standard Menu Items to a Form</span></span>
<span data-ttu-id="69b22-103">Puede proporcionar un menú estándar para los formularios con el control <xref:System.Windows.Forms.MenuStrip>.</span><span class="sxs-lookup"><span data-stu-id="69b22-103">You can provide a standard menu for your forms with the <xref:System.Windows.Forms.MenuStrip> control.</span></span>  
  
 <span data-ttu-id="69b22-104">Este tutorial muestra cómo usar un <xref:System.Windows.Forms.MenuStrip> control para crear un menú estándar.</span><span class="sxs-lookup"><span data-stu-id="69b22-104">This walkthrough demonstrates how to use a <xref:System.Windows.Forms.MenuStrip> control to create a standard menu.</span></span> <span data-ttu-id="69b22-105">El formulario también responde cuando un usuario selecciona un elemento de menú.</span><span class="sxs-lookup"><span data-stu-id="69b22-105">The form also responds when a user selects a menu item.</span></span> <span data-ttu-id="69b22-106">En este tutorial se muestran las tareas siguientes:</span><span class="sxs-lookup"><span data-stu-id="69b22-106">The following tasks are illustrated in this walkthrough:</span></span>  
  
- <span data-ttu-id="69b22-107">Crear un proyecto de Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="69b22-107">Creating a Windows Forms project.</span></span>  
  
- <span data-ttu-id="69b22-108">Crear un menú estándar.</span><span class="sxs-lookup"><span data-stu-id="69b22-108">Creating a standard menu.</span></span>  
  
- <span data-ttu-id="69b22-109">Creación de un <xref:System.Windows.Forms.StatusStrip> control.</span><span class="sxs-lookup"><span data-stu-id="69b22-109">Creating a <xref:System.Windows.Forms.StatusStrip> control.</span></span>  
  
- <span data-ttu-id="69b22-110">Control de selección de elementos de menú.</span><span class="sxs-lookup"><span data-stu-id="69b22-110">Handling menu item selection.</span></span>  
  
 <span data-ttu-id="69b22-111">Cuando haya terminado, tendrá un formulario con un menú estándar que muestra las selecciones de elementos de menú en un <xref:System.Windows.Forms.StatusStrip> control.</span><span class="sxs-lookup"><span data-stu-id="69b22-111">When you are finished, you will have a form with a standard menu that displays menu item selections in a <xref:System.Windows.Forms.StatusStrip> control.</span></span>  
  
 <span data-ttu-id="69b22-112">Para copiar el código de este tema como una sola lista, vea [Cómo: Proporcionar elementos de menú estándar a un formulario](how-to-provide-standard-menu-items-to-a-form.md).</span><span class="sxs-lookup"><span data-stu-id="69b22-112">To copy the code in this topic as a single listing, see [How to: Provide Standard Menu Items to a Form](how-to-provide-standard-menu-items-to-a-form.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="69b22-113">Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos.</span><span class="sxs-lookup"><span data-stu-id="69b22-113">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="69b22-114">Para cambiar la configuración, elija la opción **Importar y exportar configuraciones** del menú **Herramientas** .</span><span class="sxs-lookup"><span data-stu-id="69b22-114">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="69b22-115">Para más información, vea [Personalizar el IDE de Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).</span><span class="sxs-lookup"><span data-stu-id="69b22-115">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="69b22-116">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="69b22-116">Prerequisites</span></span>  
 <span data-ttu-id="69b22-117">Para poder completar este tutorial, necesitará:</span><span class="sxs-lookup"><span data-stu-id="69b22-117">In order to complete this walkthrough, you will need:</span></span>  
  
- <span data-ttu-id="69b22-118">Permisos suficientes para poder crear y ejecutar proyectos de aplicación de Windows Forms en el equipo donde está instalado Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="69b22-118">Sufficient permissions to be able to create and run Windows Forms application projects on the computer where Visual Studio is installed.</span></span>  
  
## <a name="creating-the-project"></a><span data-ttu-id="69b22-119">Crear el proyecto</span><span class="sxs-lookup"><span data-stu-id="69b22-119">Creating the Project</span></span>  
 <span data-ttu-id="69b22-120">El primer paso es crear el proyecto y configurar el formulario.</span><span class="sxs-lookup"><span data-stu-id="69b22-120">The first step is to create the project and set up the form.</span></span>  
  
#### <a name="to-create-the-project"></a><span data-ttu-id="69b22-121">Para crear el proyecto</span><span class="sxs-lookup"><span data-stu-id="69b22-121">To create the project</span></span>  
  
1. <span data-ttu-id="69b22-122">Cree un proyecto de aplicación de Windows denominado **StandardMenuForm** (**archivo** > **New** > **proyecto**  >  **Visual C#** o **Visual Basic** > **escritorio clásico de** > **Windows Forms Aplicación**).</span><span class="sxs-lookup"><span data-stu-id="69b22-122">Create a Windows application project called **StandardMenuForm** (**File** > **New** > **Project** > **Visual C#** or **Visual Basic** > **Classic Desktop** > **Windows Forms Application**).</span></span>  
  
2. <span data-ttu-id="69b22-123">En el Diseñador de formularios de Windows, seleccione el formulario.</span><span class="sxs-lookup"><span data-stu-id="69b22-123">In the Windows Forms Designer, select the form.</span></span>  
  
## <a name="creating-a-standard-menu"></a><span data-ttu-id="69b22-124">Crear un menú estándar</span><span class="sxs-lookup"><span data-stu-id="69b22-124">Creating a Standard Menu</span></span>  
 <span data-ttu-id="69b22-125">El Diseñador de Windows Forms puede rellenar automáticamente un <xref:System.Windows.Forms.MenuStrip> control con elementos de menú estándar.</span><span class="sxs-lookup"><span data-stu-id="69b22-125">The Windows Forms Designer can automatically populate a <xref:System.Windows.Forms.MenuStrip> control with standard menu items.</span></span>  
  
#### <a name="to-create-a-standard-menu"></a><span data-ttu-id="69b22-126">Para crear un menú estándar</span><span class="sxs-lookup"><span data-stu-id="69b22-126">To create a standard menu</span></span>  
  
1. <span data-ttu-id="69b22-127">Desde el **cuadro de herramientas**, arrastre un <xref:System.Windows.Forms.MenuStrip> control al formulario.</span><span class="sxs-lookup"><span data-stu-id="69b22-127">From the **Toolbox**, drag a <xref:System.Windows.Forms.MenuStrip> control onto your form.</span></span>  
  
2. <span data-ttu-id="69b22-128">Haga clic en el <xref:System.Windows.Forms.MenuStrip> glifo de etiqueta inteligente del control (![glifo de etiqueta inteligente](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) y seleccione **insertar elementos estándar**.</span><span class="sxs-lookup"><span data-stu-id="69b22-128">Click the <xref:System.Windows.Forms.MenuStrip> control's smart tag glyph (![Smart Tag Glyph](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) and select **Insert Standard Items**.</span></span>  
  
     <span data-ttu-id="69b22-129">El <xref:System.Windows.Forms.MenuStrip> control se rellena con los elementos de menú estándar.</span><span class="sxs-lookup"><span data-stu-id="69b22-129">The <xref:System.Windows.Forms.MenuStrip> control is populated with the standard menu items.</span></span>  
  
3. <span data-ttu-id="69b22-130">Haga clic en el **archivo** elemento de menú para ver sus elementos de menú predeterminados y los iconos correspondientes.</span><span class="sxs-lookup"><span data-stu-id="69b22-130">Click the **File** menu item to see its default menu items and corresponding icons.</span></span>  
  
## <a name="creating-a-statusstrip-control"></a><span data-ttu-id="69b22-131">Crear un Control StatusStrip</span><span class="sxs-lookup"><span data-stu-id="69b22-131">Creating a StatusStrip Control</span></span>  
 <span data-ttu-id="69b22-132">Use el <xref:System.Windows.Forms.StatusStrip> control para mostrar el estado de las aplicaciones de Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="69b22-132">Use the <xref:System.Windows.Forms.StatusStrip> control to display status for your Windows Forms applications.</span></span> <span data-ttu-id="69b22-133">En el ejemplo actual, se muestran los elementos de menú seleccionados por el usuario en un <xref:System.Windows.Forms.StatusStrip> control.</span><span class="sxs-lookup"><span data-stu-id="69b22-133">In the current example, menu items selected by the user are displayed in a <xref:System.Windows.Forms.StatusStrip> control.</span></span>  
  
#### <a name="to-create-a-statusstrip-control"></a><span data-ttu-id="69b22-134">Para crear un control StatusStrip</span><span class="sxs-lookup"><span data-stu-id="69b22-134">To create a StatusStrip control</span></span>  
  
1. <span data-ttu-id="69b22-135">Desde el **cuadro de herramientas**, arrastre un <xref:System.Windows.Forms.StatusStrip> control al formulario.</span><span class="sxs-lookup"><span data-stu-id="69b22-135">From the **Toolbox**, drag a <xref:System.Windows.Forms.StatusStrip> control onto your form.</span></span>  
  
     <span data-ttu-id="69b22-136">El <xref:System.Windows.Forms.StatusStrip> control se acopla automáticamente a la parte inferior del formulario.</span><span class="sxs-lookup"><span data-stu-id="69b22-136">The <xref:System.Windows.Forms.StatusStrip> control automatically docks to the bottom of the form.</span></span>  
  
2. <span data-ttu-id="69b22-137">Haga clic en el <xref:System.Windows.Forms.StatusStrip> del control de botón de lista desplegable y seleccione **StatusLabel como** para agregar un <xref:System.Windows.Forms.ToolStripStatusLabel> el control a la <xref:System.Windows.Forms.StatusStrip> control.</span><span class="sxs-lookup"><span data-stu-id="69b22-137">Click the <xref:System.Windows.Forms.StatusStrip> control's drop-down button and select **StatusLabel** to add a <xref:System.Windows.Forms.ToolStripStatusLabel> control to the <xref:System.Windows.Forms.StatusStrip> control.</span></span>  
  
## <a name="handling-item-selection"></a><span data-ttu-id="69b22-138">Selección de elementos de control</span><span class="sxs-lookup"><span data-stu-id="69b22-138">Handling Item Selection</span></span>  
 <span data-ttu-id="69b22-139">Controlar la <xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItemClicked> eventos para responder cuando el usuario selecciona un elemento de menú.</span><span class="sxs-lookup"><span data-stu-id="69b22-139">Handle the <xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItemClicked> event to respond when the user selects a menu item.</span></span>  
  
#### <a name="to-handle-item-selection"></a><span data-ttu-id="69b22-140">Para controlar la selección de elementos</span><span class="sxs-lookup"><span data-stu-id="69b22-140">To handle item selection</span></span>  
  
1. <span data-ttu-id="69b22-141">Haga clic en el **archivo** elemento de menú que creó en la creación una sección de menú estándar.</span><span class="sxs-lookup"><span data-stu-id="69b22-141">Click the **File** menu item that you created in the Creating a Standard Menu section.</span></span>  
  
2. <span data-ttu-id="69b22-142">En la ventana **Propiedades**, haga clic en **Eventos**.</span><span class="sxs-lookup"><span data-stu-id="69b22-142">In the **Properties** window, click **Events**.</span></span>  
  
3. <span data-ttu-id="69b22-143">Haga doble clic en el <xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItemClicked> eventos.</span><span class="sxs-lookup"><span data-stu-id="69b22-143">Double-click the <xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItemClicked> event.</span></span>  
  
     <span data-ttu-id="69b22-144">El Diseñador de Windows Forms genera un controlador de eventos para el <xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItemClicked> eventos.</span><span class="sxs-lookup"><span data-stu-id="69b22-144">The Windows Forms Designer generates an event handler for the <xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItemClicked> event.</span></span>  
  
4. <span data-ttu-id="69b22-145">Inserte el código siguiente en el controlador de eventos.</span><span class="sxs-lookup"><span data-stu-id="69b22-145">Insert the following code into the event handler.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ToolStrip.StandardMenu#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StandardMenu/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.ToolStrip.StandardMenu#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StandardMenu/VB/Form1.vb#3)]  
  
5. <span data-ttu-id="69b22-146">Insertar el `UpdateStatus` definición de método de utilidad en el formulario.</span><span class="sxs-lookup"><span data-stu-id="69b22-146">Insert the `UpdateStatus` utility method definition into the form.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ToolStrip.StandardMenu#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StandardMenu/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.ToolStrip.StandardMenu#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StandardMenu/VB/Form1.vb#2)]  
  
## <a name="checkpoint"></a><span data-ttu-id="69b22-147">Punto de control</span><span class="sxs-lookup"><span data-stu-id="69b22-147">Checkpoint</span></span>  
  
#### <a name="to-test-your-form"></a><span data-ttu-id="69b22-148">Para probar el formulario</span><span class="sxs-lookup"><span data-stu-id="69b22-148">To test your form</span></span>  
  
1. <span data-ttu-id="69b22-149">Presione F5 para compilar y ejecutar el formulario.</span><span class="sxs-lookup"><span data-stu-id="69b22-149">Press F5 to compile and run your form.</span></span>  
  
2. <span data-ttu-id="69b22-150">Haga clic en el **archivo** elemento de menú para abrir el menú.</span><span class="sxs-lookup"><span data-stu-id="69b22-150">Click the **File** menu item to open the menu.</span></span>  
  
3. <span data-ttu-id="69b22-151">En el **archivo** menú, haga clic en uno de los elementos para seleccionarlo.</span><span class="sxs-lookup"><span data-stu-id="69b22-151">On the **File** menu, click one of the items to select it.</span></span>  
  
     <span data-ttu-id="69b22-152">El <xref:System.Windows.Forms.StatusStrip> control muestra el elemento seleccionado.</span><span class="sxs-lookup"><span data-stu-id="69b22-152">The <xref:System.Windows.Forms.StatusStrip> control displays the selected item.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="69b22-153">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="69b22-153">Next Steps</span></span>  
 <span data-ttu-id="69b22-154">En este tutorial, ha creado un formulario con un menú estándar.</span><span class="sxs-lookup"><span data-stu-id="69b22-154">In this walkthrough, you have created a form with a standard menu.</span></span> <span data-ttu-id="69b22-155">Puede usar el <xref:System.Windows.Forms.ToolStrip> familia de controles para muchos otros objetivos:</span><span class="sxs-lookup"><span data-stu-id="69b22-155">You can use the <xref:System.Windows.Forms.ToolStrip> family of controls for many other purposes:</span></span>  
  
- <span data-ttu-id="69b22-156">Crear menús contextuales para los controles con <xref:System.Windows.Forms.ContextMenuStrip>.</span><span class="sxs-lookup"><span data-stu-id="69b22-156">Create shortcut menus for your controls with <xref:System.Windows.Forms.ContextMenuStrip>.</span></span> <span data-ttu-id="69b22-157">Para obtener más información, consulte [información general del componente ContextMenu](contextmenu-component-overview-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="69b22-157">For more information, see [ContextMenu Component Overview](contextmenu-component-overview-windows-forms.md).</span></span>  
  
- <span data-ttu-id="69b22-158">Crear un formulario de múltiples documentos (MDI) de la interfaz con acoplamiento <xref:System.Windows.Forms.ToolStrip> controles.</span><span class="sxs-lookup"><span data-stu-id="69b22-158">Create a multiple document interface (MDI) form with docking <xref:System.Windows.Forms.ToolStrip> controls.</span></span> <span data-ttu-id="69b22-159">Para obtener más información, vea [Tutorial: Crear un formulario MDI con combinación de menús y controles ToolStrip](walkthrough-creating-an-mdi-form-with-menu-merging-and-toolstrip-controls.md).</span><span class="sxs-lookup"><span data-stu-id="69b22-159">For more information, see [Walkthrough: Creating an MDI Form with Menu Merging and ToolStrip Controls](walkthrough-creating-an-mdi-form-with-menu-merging-and-toolstrip-controls.md).</span></span>  
  
- <span data-ttu-id="69b22-160">Asigne a su <xref:System.Windows.Forms.ToolStrip> controla un aspecto profesional.</span><span class="sxs-lookup"><span data-stu-id="69b22-160">Give your <xref:System.Windows.Forms.ToolStrip> controls a professional appearance.</span></span> <span data-ttu-id="69b22-161">Para obtener más información, vea [Cómo: Establecer la representación de ToolStrip para una aplicación](how-to-set-the-toolstrip-renderer-for-an-application.md).</span><span class="sxs-lookup"><span data-stu-id="69b22-161">For more information, see [How to: Set the ToolStrip Renderer for an Application](how-to-set-the-toolstrip-renderer-for-an-application.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="69b22-162">Vea también</span><span class="sxs-lookup"><span data-stu-id="69b22-162">See also</span></span>

- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.StatusStrip>
- [<span data-ttu-id="69b22-163">Control MenuStrip</span><span class="sxs-lookup"><span data-stu-id="69b22-163">MenuStrip Control</span></span>](menustrip-control-windows-forms.md)
