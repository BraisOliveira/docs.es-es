---
title: 'Tutorial: Asignar propiedades mediante el uso del control ElementHost'
ms.date: 08/18/2018
dev_langs:
- csharp
- vb
helpviewer_keywords:
- mapping properties [WPF]
- ElementHost control [WPF], mapping properties
ms.assetid: bccd6e0d-2272-4924-9107-ff8ed58b88aa
ms.openlocfilehash: 360f19e558f97e1807b329ad18e429fa893bbf86
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/09/2019
ms.locfileid: "59300923"
---
# <a name="walkthrough-mapping-properties-using-the-elementhost-control"></a><span data-ttu-id="54405-102">Tutorial: Asignar propiedades mediante el uso del control ElementHost</span><span class="sxs-lookup"><span data-stu-id="54405-102">Walkthrough: Mapping Properties Using the ElementHost Control</span></span>

<span data-ttu-id="54405-103">En este tutorial se muestra cómo usar el <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A> propiedad para la asignación [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] propiedades a las propiedades correspondientes en una hospedada [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] elemento.</span><span class="sxs-lookup"><span data-stu-id="54405-103">This walkthrough shows you how to use the <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A> property to map [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] properties to corresponding properties on a hosted [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] element.</span></span>

<span data-ttu-id="54405-104">Las tareas ilustradas en este tutorial incluyen:</span><span class="sxs-lookup"><span data-stu-id="54405-104">Tasks illustrated in this walkthrough include:</span></span>

-   <span data-ttu-id="54405-105">Crear el proyecto.</span><span class="sxs-lookup"><span data-stu-id="54405-105">Creating the project.</span></span>

-   <span data-ttu-id="54405-106">Definir una nueva asignación de propiedades.</span><span class="sxs-lookup"><span data-stu-id="54405-106">Defining a new property mapping.</span></span>

-   <span data-ttu-id="54405-107">Quitar una asignación de propiedades predeterminada.</span><span class="sxs-lookup"><span data-stu-id="54405-107">Removing a default property mapping.</span></span>

-   <span data-ttu-id="54405-108">Extender una asignación de propiedades predeterminada.</span><span class="sxs-lookup"><span data-stu-id="54405-108">Extending a default property mapping.</span></span>

<span data-ttu-id="54405-109">Para obtener una lista de código completo de las tareas ilustradas en este tutorial, vea [asignar propiedades mediante el ejemplo del Control ElementHost](https://go.microsoft.com/fwlink/?LinkID=160018).</span><span class="sxs-lookup"><span data-stu-id="54405-109">For a complete code listing of the tasks illustrated in this walkthrough, see [Mapping Properties Using the ElementHost Control Sample](https://go.microsoft.com/fwlink/?LinkID=160018).</span></span>

<span data-ttu-id="54405-110">Cuando haya terminado, podrá asignar [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] propiedades correspondiente [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] propiedades en un elemento hospedado.</span><span class="sxs-lookup"><span data-stu-id="54405-110">When you are finished, you will be able to map [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] properties to corresponding [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] properties on a hosted element.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="54405-111">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="54405-111">Prerequisites</span></span>

<span data-ttu-id="54405-112">Necesita los componentes siguientes para completar este tutorial:</span><span class="sxs-lookup"><span data-stu-id="54405-112">You need the following components to complete this walkthrough:</span></span>

-   <span data-ttu-id="54405-113">Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="54405-113">Visual Studio 2017</span></span>

## <a name="creating-the-project"></a><span data-ttu-id="54405-114">Crear el proyecto</span><span class="sxs-lookup"><span data-stu-id="54405-114">Creating the Project</span></span>

### <a name="to-create-the-project"></a><span data-ttu-id="54405-115">Para crear el proyecto</span><span class="sxs-lookup"><span data-stu-id="54405-115">To create the project</span></span>

1. <span data-ttu-id="54405-116">Crear un **aplicación de Windows Forms** proyecto denominado `PropertyMappingWithElementHost`.</span><span class="sxs-lookup"><span data-stu-id="54405-116">Create a **Windows Forms App** project named `PropertyMappingWithElementHost`.</span></span>

2. <span data-ttu-id="54405-117">En **el Explorador de soluciones**, agregue referencias a los siguientes [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] ensamblados.</span><span class="sxs-lookup"><span data-stu-id="54405-117">In **Solution Explorer**, add references to the following [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] assemblies.</span></span>

    -   <span data-ttu-id="54405-118">PresentationCore</span><span class="sxs-lookup"><span data-stu-id="54405-118">PresentationCore</span></span>

    -   <span data-ttu-id="54405-119">PresentationFramework</span><span class="sxs-lookup"><span data-stu-id="54405-119">PresentationFramework</span></span>

    -   <span data-ttu-id="54405-120">WindowsBase</span><span class="sxs-lookup"><span data-stu-id="54405-120">WindowsBase</span></span>

    -   <span data-ttu-id="54405-121">WindowsFormsIntegration</span><span class="sxs-lookup"><span data-stu-id="54405-121">WindowsFormsIntegration</span></span>

3. <span data-ttu-id="54405-122">Copie el código siguiente en la parte superior de la `Form1` archivo de código.</span><span class="sxs-lookup"><span data-stu-id="54405-122">Copy the following code into the top of the `Form1` code file.</span></span>

     [!code-csharp[PropertyMappingWithElementHost#10](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#10)]
     [!code-vb[PropertyMappingWithElementHost#10](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#10)]

4. <span data-ttu-id="54405-123">Abra `Form1` en el Diseñador de Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="54405-123">Open `Form1` in the Windows Forms Designer.</span></span> <span data-ttu-id="54405-124">Haga doble clic en el formulario para agregar un controlador de eventos para el <xref:System.Windows.Forms.Form.Load> eventos.</span><span class="sxs-lookup"><span data-stu-id="54405-124">Double-click the form to add an event handler for the <xref:System.Windows.Forms.Form.Load> event.</span></span>

5. <span data-ttu-id="54405-125">Vuelva al diseñador de Windows Forms y agregue un controlador de eventos para el formulario <xref:System.Windows.Forms.Control.Resize> eventos.</span><span class="sxs-lookup"><span data-stu-id="54405-125">Return to the Windows Forms Designer and add an event handler for the form's <xref:System.Windows.Forms.Control.Resize> event.</span></span> <span data-ttu-id="54405-126">Para obtener más información, vea [Cómo: Crear controladores de eventos mediante el diseñador](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/zwwsdtbk(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="54405-126">For more information, see [How to: Create Event Handlers Using the Designer](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/zwwsdtbk(v=vs.100)).</span></span>

6. <span data-ttu-id="54405-127">Declarar un <xref:System.Windows.Forms.Integration.ElementHost> campo el `Form1` clase.</span><span class="sxs-lookup"><span data-stu-id="54405-127">Declare an <xref:System.Windows.Forms.Integration.ElementHost> field in the `Form1` class.</span></span>

     [!code-csharp[PropertyMappingWithElementHost#16](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#16)]
     [!code-vb[PropertyMappingWithElementHost#16](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#16)]

## <a name="defining-new-property-mappings"></a><span data-ttu-id="54405-128">Definir nuevas asignaciones de propiedad</span><span class="sxs-lookup"><span data-stu-id="54405-128">Defining New Property Mappings</span></span>

<span data-ttu-id="54405-129">El <xref:System.Windows.Forms.Integration.ElementHost> control proporciona predeterminada varias asignaciones de propiedades.</span><span class="sxs-lookup"><span data-stu-id="54405-129">The <xref:System.Windows.Forms.Integration.ElementHost> control provides several default property mappings.</span></span> <span data-ttu-id="54405-130">Agregar una nueva asignación de propiedad mediante una llamada a la <xref:System.Windows.Forms.Integration.PropertyMap.Add%2A> método en el <xref:System.Windows.Forms.Integration.ElementHost> del control <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A>.</span><span class="sxs-lookup"><span data-stu-id="54405-130">You add a new property mapping by calling the <xref:System.Windows.Forms.Integration.PropertyMap.Add%2A> method on the <xref:System.Windows.Forms.Integration.ElementHost> control's <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A>.</span></span>

### <a name="to-define-new-property-mappings"></a><span data-ttu-id="54405-131">Para definir nuevas asignaciones de propiedad</span><span class="sxs-lookup"><span data-stu-id="54405-131">To define new property mappings</span></span>

1. <span data-ttu-id="54405-132">Copie el código siguiente en la definición para el `Form1` clase.</span><span class="sxs-lookup"><span data-stu-id="54405-132">Copy the following code into the definition for the `Form1` class.</span></span>

     [!code-csharp[PropertyMappingWithElementHost#12](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#12)]
     [!code-vb[PropertyMappingWithElementHost#12](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#12)]

     <span data-ttu-id="54405-133">El `AddMarginMapping` método agrega una nueva asignación para el <xref:System.Windows.Forms.Control.Margin%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="54405-133">The `AddMarginMapping` method adds a new mapping for the <xref:System.Windows.Forms.Control.Margin%2A> property.</span></span>

     <span data-ttu-id="54405-134">El `OnMarginChange` método traduce el <xref:System.Windows.Forms.Control.Margin%2A> propiedad a la [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.FrameworkElement.Margin%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="54405-134">The `OnMarginChange` method translates the <xref:System.Windows.Forms.Control.Margin%2A> property to the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.FrameworkElement.Margin%2A> property.</span></span>

2. <span data-ttu-id="54405-135">Copie el código siguiente en la definición para el `Form1` clase.</span><span class="sxs-lookup"><span data-stu-id="54405-135">Copy the following code into the definition for the `Form1` class.</span></span>

     [!code-csharp[PropertyMappingWithElementHost#14](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#14)]
     [!code-vb[PropertyMappingWithElementHost#14](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#14)]

     <span data-ttu-id="54405-136">El `AddRegionMapping` método agrega una nueva asignación para el <xref:System.Windows.Forms.Control.Region%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="54405-136">The `AddRegionMapping` method adds a new mapping for the <xref:System.Windows.Forms.Control.Region%2A> property.</span></span>

     <span data-ttu-id="54405-137">El `OnRegionChange` método traduce el <xref:System.Windows.Forms.Control.Region%2A> propiedad a la [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.UIElement.Clip%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="54405-137">The `OnRegionChange` method translates the <xref:System.Windows.Forms.Control.Region%2A> property to the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.UIElement.Clip%2A> property.</span></span>

     <span data-ttu-id="54405-138">El `Form1_Resize` método controla el formulario <xref:System.Windows.Forms.Control.Resize> eventos y ajusta el tamaño de la región de recorte para adaptarse al elemento hospedado.</span><span class="sxs-lookup"><span data-stu-id="54405-138">The `Form1_Resize` method handles the form's <xref:System.Windows.Forms.Control.Resize> event and sizes the clipping region to fit the hosted element.</span></span>

## <a name="removing-a-default-property-mapping"></a><span data-ttu-id="54405-139">Quitar una asignación de propiedades predeterminada</span><span class="sxs-lookup"><span data-stu-id="54405-139">Removing a Default Property Mapping</span></span>

<span data-ttu-id="54405-140">Quitar una asignación de propiedades predeterminada llamando el <xref:System.Windows.Forms.Integration.PropertyMap.Remove%2A> método en el <xref:System.Windows.Forms.Integration.ElementHost> del control <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A>.</span><span class="sxs-lookup"><span data-stu-id="54405-140">Remove a default property mapping by calling the <xref:System.Windows.Forms.Integration.PropertyMap.Remove%2A> method on the <xref:System.Windows.Forms.Integration.ElementHost> control's <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A>.</span></span>

### <a name="to-remove-a-default-property-mapping"></a><span data-ttu-id="54405-141">Para quitar una asignación de propiedades predeterminada</span><span class="sxs-lookup"><span data-stu-id="54405-141">To remove a default property mapping</span></span>

-   <span data-ttu-id="54405-142">Copie el código siguiente en la definición para el `Form1` clase.</span><span class="sxs-lookup"><span data-stu-id="54405-142">Copy the following code into the definition for the `Form1` class.</span></span>

     [!code-csharp[PropertyMappingWithElementHost#13](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#13)]
     [!code-vb[PropertyMappingWithElementHost#13](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#13)]

     <span data-ttu-id="54405-143">El `RemoveCursorMapping` método elimina la asignación predeterminada para el <xref:System.Windows.Forms.Control.Cursor%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="54405-143">The `RemoveCursorMapping` method deletes the default mapping for the <xref:System.Windows.Forms.Control.Cursor%2A> property.</span></span>

## <a name="extending-a-default-property-mapping"></a><span data-ttu-id="54405-144">Extender una asignación de propiedades predeterminada</span><span class="sxs-lookup"><span data-stu-id="54405-144">Extending a Default Property Mapping</span></span>

<span data-ttu-id="54405-145">Puede usar una asignación de propiedades predeterminada y extenderla con su propia asignación.</span><span class="sxs-lookup"><span data-stu-id="54405-145">You can use a default property mapping and also extend it with your own mapping.</span></span>

### <a name="to-extend-a-default-property-mapping"></a><span data-ttu-id="54405-146">Para extender una asignación de propiedades predeterminada</span><span class="sxs-lookup"><span data-stu-id="54405-146">To extend a default property mapping</span></span>

-   <span data-ttu-id="54405-147">Copie el código siguiente en la definición para el `Form1` clase.</span><span class="sxs-lookup"><span data-stu-id="54405-147">Copy the following code into the definition for the `Form1` class.</span></span>

     [!code-csharp[PropertyMappingWithElementHost#15](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#15)]
     [!code-vb[PropertyMappingWithElementHost#15](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#15)]

     <span data-ttu-id="54405-148">El `ExtendBackColorMapping` método agrega un traductor de propiedad personalizada existente <xref:System.Windows.Forms.Control.BackColor%2A> asignación de propiedades.</span><span class="sxs-lookup"><span data-stu-id="54405-148">The `ExtendBackColorMapping` method adds a custom property translator to the existing <xref:System.Windows.Forms.Control.BackColor%2A> property mapping.</span></span>

     <span data-ttu-id="54405-149">El `OnBackColorChange` método asigna una imagen específica para el control hospedado <xref:System.Windows.Controls.Control.Background%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="54405-149">The `OnBackColorChange` method assigns a specific image to the hosted control's <xref:System.Windows.Controls.Control.Background%2A> property.</span></span> <span data-ttu-id="54405-150">El `OnBackColorChange` se llama al método después de aplica la asignación de propiedades predeterminada.</span><span class="sxs-lookup"><span data-stu-id="54405-150">The `OnBackColorChange` method is called after the default property mapping is applied.</span></span>

## <a name="initialize-your-property-mappings"></a><span data-ttu-id="54405-151">Inicializar las asignaciones de propiedades</span><span class="sxs-lookup"><span data-stu-id="54405-151">Initialize your property mappings</span></span>

1. <span data-ttu-id="54405-152">Copie el código siguiente en la definición para el `Form1` clase.</span><span class="sxs-lookup"><span data-stu-id="54405-152">Copy the following code into the definition for the `Form1` class.</span></span>

     [!code-csharp[PropertyMappingWithElementHost#11](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#11)]
     [!code-vb[PropertyMappingWithElementHost#11](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#11)]

     <span data-ttu-id="54405-153">El `Form1_Load` método controla el <xref:System.Windows.Forms.Form.Load> eventos y realiza la inicialización siguiente.</span><span class="sxs-lookup"><span data-stu-id="54405-153">The `Form1_Load` method handles the <xref:System.Windows.Forms.Form.Load> event and performs the following initialization.</span></span>

    -   <span data-ttu-id="54405-154">Crea un [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.Button> elemento.</span><span class="sxs-lookup"><span data-stu-id="54405-154">Creates a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.Button> element.</span></span>

    -   <span data-ttu-id="54405-155">Llama a los métodos definidos anteriormente en el tutorial para configurar las asignaciones de propiedades.</span><span class="sxs-lookup"><span data-stu-id="54405-155">Calls the methods you defined earlier in the walkthrough to set up the property mappings.</span></span>

    -   <span data-ttu-id="54405-156">Asigna los valores iniciales a las propiedades asignadas.</span><span class="sxs-lookup"><span data-stu-id="54405-156">Assigns initial values to the mapped properties.</span></span>

2. <span data-ttu-id="54405-157">Presione F5 para compilar y ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="54405-157">Press F5 to build and run the application.</span></span>

## <a name="see-also"></a><span data-ttu-id="54405-158">Vea también</span><span class="sxs-lookup"><span data-stu-id="54405-158">See also</span></span>

- <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [<span data-ttu-id="54405-159">Asignación de propiedades en formularios Windows Forms y WPF</span><span class="sxs-lookup"><span data-stu-id="54405-159">Windows Forms and WPF Property Mapping</span></span>](windows-forms-and-wpf-property-mapping.md)
- [<span data-ttu-id="54405-160">Diseño de XAML en Visual Studio</span><span class="sxs-lookup"><span data-stu-id="54405-160">Design XAML in Visual Studio</span></span>](/visualstudio/designers/designing-xaml-in-visual-studio)
- [<span data-ttu-id="54405-161">Tutorial: Hospedar un control compuesto de WPF en formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="54405-161">Walkthrough: Hosting a WPF Composite Control in Windows Forms</span></span>](walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)