---
title: Crear una aplicación de WPF en Visual Studio
ms.date: 10/26/2018
dev_langs:
- csharp
- vb
helpviewer_keywords:
- getting started [WPF], WPF
- WPF [WPF], getting started
ms.assetid: b96bed40-8946-4285-8fe4-88045ab854ed
author: mairaw
ms.author: mairaw
ms.custom: vs-dotnet
ms.openlocfilehash: dbfc40bd1fcc97810ea1397731bd8c232297cbd1
ms.sourcegitcommit: 68eb5c4928e2b082f178a42c16f73fedf52c2ab8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/05/2019
ms.locfileid: "59055253"
---
# <a name="walkthrough-my-first-wpf-desktop-application"></a><span data-ttu-id="e4d13-102">Tutorial: Mi primera aplicación de escritorio WPF</span><span class="sxs-lookup"><span data-stu-id="e4d13-102">Walkthrough: My first WPF desktop application</span></span>

<span data-ttu-id="e4d13-103">Este artículo muestra cómo desarrollar una aplicación de Windows Presentation Foundation (WPF) simple que incluye los elementos que son comunes a la mayoría de las aplicaciones de WPF: Extensible Application Markup Language (XAML) marcado, código subyacente, definiciones de aplicación, controles, diseño, enlace de datos y estilos.</span><span class="sxs-lookup"><span data-stu-id="e4d13-103">This article shows you how to develop a simple Windows Presentation Foundation (WPF) application that includes the elements that are common to most WPF applications: Extensible Application Markup Language (XAML) markup, code-behind, application definitions, controls, layout, data binding, and styles.</span></span>

<span data-ttu-id="e4d13-104">En este tutorial incluye los siguientes pasos:</span><span class="sxs-lookup"><span data-stu-id="e4d13-104">This walkthrough includes the following steps:</span></span>

- <span data-ttu-id="e4d13-105">Usar XAML para diseñar la apariencia de la interfaz de usuario (UI) de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="e4d13-105">Use XAML to design the appearance of the application's user interface (UI).</span></span>

- <span data-ttu-id="e4d13-106">Escribir código para construir el comportamiento de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="e4d13-106">Write code to build the application's behavior.</span></span>

- <span data-ttu-id="e4d13-107">Crear una definición de aplicación para administrar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="e4d13-107">Create an application definition to manage the application.</span></span>

- <span data-ttu-id="e4d13-108">Agregar controles y crear el diseño para crear la interfaz de usuario de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="e4d13-108">Add controls and create the layout to compose the application UI.</span></span>

- <span data-ttu-id="e4d13-109">Crear estilos para una apariencia coherente en toda la interfaz de usuario de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="e4d13-109">Create styles for a consistent appearance throughout an application's UI.</span></span>

- <span data-ttu-id="e4d13-110">Enlazar la interfaz de usuario a los datos a rellenar la interfaz de usuario de datos y mantener los datos y la interfaz de usuario sincronizada.</span><span class="sxs-lookup"><span data-stu-id="e4d13-110">Bind the UI to data to both populate the UI from data and keep the data and UI synchronized.</span></span>

<span data-ttu-id="e4d13-111">Al final del tutorial, habrá creado una aplicación de Windows que permite a los usuarios ver los informes de gastos para personas seleccionadas independiente.</span><span class="sxs-lookup"><span data-stu-id="e4d13-111">By the end of the walkthrough, you'll have built a standalone Windows application that allows users to view expense reports for selected people.</span></span> <span data-ttu-id="e4d13-112">La aplicación se compone de varias páginas WPF que se hospedan en una ventana del explorador de estilo.</span><span class="sxs-lookup"><span data-stu-id="e4d13-112">The application is composed of several WPF pages that are hosted in a browser-style window.</span></span>

> [!TIP]
> <span data-ttu-id="e4d13-113">El código de ejemplo que se usa para crear este tutorial está disponible para Visual Basic y C# en [Introduction to Building WPF Applications](https://go.microsoft.com/fwlink/?LinkID=160008).</span><span class="sxs-lookup"><span data-stu-id="e4d13-113">The sample code that is used to build this walkthrough is available for both Visual Basic and C# at [Introduction to Building WPF Applications](https://go.microsoft.com/fwlink/?LinkID=160008).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="e4d13-114">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="e4d13-114">Prerequisites</span></span>

- <span data-ttu-id="e4d13-115">Visual Studio 2017 o posterior</span><span class="sxs-lookup"><span data-stu-id="e4d13-115">Visual Studio 2017 or later</span></span>

   <span data-ttu-id="e4d13-116">Para obtener más información acerca de cómo instalar la versión más reciente de Visual Studio, consulte [instalar Visual Studio](/visualstudio/install/install-visual-studio).</span><span class="sxs-lookup"><span data-stu-id="e4d13-116">For more information about installing the latest version of Visual Studio, see [Install Visual Studio](/visualstudio/install/install-visual-studio).</span></span>

## <a name="create-the-application-project"></a><span data-ttu-id="e4d13-117">Crear el proyecto de aplicación</span><span class="sxs-lookup"><span data-stu-id="e4d13-117">Create the application project</span></span>

<span data-ttu-id="e4d13-118">El primer paso es crear la infraestructura de aplicación, que incluye una definición de aplicación, dos páginas y una imagen.</span><span class="sxs-lookup"><span data-stu-id="e4d13-118">The first step is to create the application infrastructure, which includes an application definition, two pages, and an image.</span></span>

1. <span data-ttu-id="e4d13-119">Cree un nuevo proyecto de aplicación de WPF en Visual Basic o Visual C# llamado **`ExpenseIt`**:</span><span class="sxs-lookup"><span data-stu-id="e4d13-119">Create a new WPF Application project in Visual Basic or Visual C# named **`ExpenseIt`**:</span></span>

   1. <span data-ttu-id="e4d13-120">Abra Visual Studio y seleccione **archivo** > **New** > **proyecto**.</span><span class="sxs-lookup"><span data-stu-id="e4d13-120">Open Visual Studio and select **File** > **New** > **Project**.</span></span>

      <span data-ttu-id="e4d13-121">El **nuevo proyecto** abre el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="e4d13-121">The **New Project** dialog opens.</span></span>

   2. <span data-ttu-id="e4d13-122">En el **instalado** categoría, expanda el **Visual C#**  o **Visual Basic** nodo y, a continuación, seleccione **Windows Desktop**.</span><span class="sxs-lookup"><span data-stu-id="e4d13-122">Under the **Installed** category, expand either the **Visual C#** or **Visual Basic** node, and then select **Windows Desktop**.</span></span>

   3. <span data-ttu-id="e4d13-123">Seleccione el **aplicación de WPF (.NET Framework)** plantilla.</span><span class="sxs-lookup"><span data-stu-id="e4d13-123">Select the **WPF App (.NET Framework)** template.</span></span> <span data-ttu-id="e4d13-124">Escriba el nombre **`ExpenseIt`** y, a continuación, seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="e4d13-124">Enter the name **`ExpenseIt`** and then select **OK**.</span></span>

      ![Cuadro de diálogo nuevo proyecto con la aplicación WPF seleccionada](./media/new-project-dialog.png)

      <span data-ttu-id="e4d13-126">Visual Studio crea el proyecto y abre el Diseñador de la ventana de aplicación predeterminada denominado **MainWindow.xaml**.</span><span class="sxs-lookup"><span data-stu-id="e4d13-126">Visual Studio creates the project and opens the designer for the default application window named **MainWindow.xaml**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="e4d13-127">Este tutorial utiliza el <xref:System.Windows.Controls.DataGrid> control que está disponible en .NET Framework 4 y versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="e4d13-127">This walkthrough uses the <xref:System.Windows.Controls.DataGrid> control that is available in the .NET Framework 4 and later.</span></span> <span data-ttu-id="e4d13-128">Estar seguro de que el proyecto tiene como destino .NET Framework 4 o posterior.</span><span class="sxs-lookup"><span data-stu-id="e4d13-128">Be sure that your project targets the .NET Framework 4 or later.</span></span> <span data-ttu-id="e4d13-129">Para obtener más información, vea [Cómo: usar una versión de .NET Framework como destino](/visualstudio/ide/how-to-target-a-version-of-the-dotnet-framework).</span><span class="sxs-lookup"><span data-stu-id="e4d13-129">For more information, see [How to: Target a Version of the .NET Framework](/visualstudio/ide/how-to-target-a-version-of-the-dotnet-framework).</span></span>

2. <span data-ttu-id="e4d13-130">Abra *Application.xaml* (Visual Basic) o *App.xaml* (C#).</span><span class="sxs-lookup"><span data-stu-id="e4d13-130">Open *Application.xaml* (Visual Basic) or *App.xaml* (C#).</span></span>

    <span data-ttu-id="e4d13-131">Este archivo XAML define una aplicación de WPF y los recursos de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="e4d13-131">This XAML file defines a WPF application and any application resources.</span></span> <span data-ttu-id="e4d13-132">También usa este archivo para especificar la interfaz de usuario que se muestra automáticamente cuando se inicia la aplicación; en este caso, *MainWindow.xaml*.</span><span class="sxs-lookup"><span data-stu-id="e4d13-132">You also use this file to specify the UI that automatically shows when the application starts; in this case, *MainWindow.xaml*.</span></span>

    <span data-ttu-id="e4d13-133">En Visual Basic, el XAML debe tener el siguiente aspecto:</span><span class="sxs-lookup"><span data-stu-id="e4d13-133">Your XAML should look like this in Visual Basic:</span></span>

    [!code-xaml[ExpenseIt#1_A](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/Application.xaml#1_a)]

    <span data-ttu-id="e4d13-134">O a este en C#:</span><span class="sxs-lookup"><span data-stu-id="e4d13-134">Or like this in C#:</span></span>

    [!code-xaml[ExpenseIt#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/App.xaml#1)]

3. <span data-ttu-id="e4d13-135">Abra *MainWindow.xaml*.</span><span class="sxs-lookup"><span data-stu-id="e4d13-135">Open *MainWindow.xaml*.</span></span>

    <span data-ttu-id="e4d13-136">Este archivo XAML es la ventana principal de la aplicación y muestra contenido creado en páginas.</span><span class="sxs-lookup"><span data-stu-id="e4d13-136">This XAML file is the main window of your application and displays content created in pages.</span></span> <span data-ttu-id="e4d13-137">La <xref:System.Windows.Window> clase define las propiedades de una ventana, como su título, tamaño o icono y controla los eventos, como cerrar u ocultar.</span><span class="sxs-lookup"><span data-stu-id="e4d13-137">The <xref:System.Windows.Window> class defines the properties of a window, such as its title, size, or icon, and handles events, such as closing or hiding.</span></span>

4. <span data-ttu-id="e4d13-138">Cambiar el <xref:System.Windows.Window> elemento a un <xref:System.Windows.Navigation.NavigationWindow>, tal y como se muestra en el XAML siguiente:</span><span class="sxs-lookup"><span data-stu-id="e4d13-138">Change the <xref:System.Windows.Window> element to a <xref:System.Windows.Navigation.NavigationWindow>, as shown in the following XAML:</span></span>

   ```xaml
   <NavigationWindow x:Class="ExpenseIt.MainWindow"
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        ...
   </NavigationWindow>
   ```

   <span data-ttu-id="e4d13-139">Esta aplicación accede a contenido diferente según la entrada del usuario.</span><span class="sxs-lookup"><span data-stu-id="e4d13-139">This app navigates to different content depending on the user input.</span></span> <span data-ttu-id="e4d13-140">Por ello principal <xref:System.Windows.Window> debe cambiarse a un <xref:System.Windows.Navigation.NavigationWindow>.</span><span class="sxs-lookup"><span data-stu-id="e4d13-140">This is why the main <xref:System.Windows.Window> needs to be changed to a <xref:System.Windows.Navigation.NavigationWindow>.</span></span> <xref:System.Windows.Navigation.NavigationWindow> <span data-ttu-id="e4d13-141">hereda todas las propiedades de <xref:System.Windows.Window>.</span><span class="sxs-lookup"><span data-stu-id="e4d13-141">inherits all the properties of <xref:System.Windows.Window>.</span></span> <span data-ttu-id="e4d13-142">El <xref:System.Windows.Navigation.NavigationWindow> elemento en el archivo XAML crea una instancia de la <xref:System.Windows.Navigation.NavigationWindow> clase.</span><span class="sxs-lookup"><span data-stu-id="e4d13-142">The <xref:System.Windows.Navigation.NavigationWindow> element in the XAML file creates an instance of the <xref:System.Windows.Navigation.NavigationWindow> class.</span></span> <span data-ttu-id="e4d13-143">Para obtener más información, consulte [información general sobre navegación](../app-development/navigation-overview.md).</span><span class="sxs-lookup"><span data-stu-id="e4d13-143">For more information, see [Navigation overview](../app-development/navigation-overview.md).</span></span>

5. <span data-ttu-id="e4d13-144">Cambie las propiedades siguientes en el <xref:System.Windows.Navigation.NavigationWindow> elemento:</span><span class="sxs-lookup"><span data-stu-id="e4d13-144">Change the following properties on the <xref:System.Windows.Navigation.NavigationWindow> element:</span></span>

    - <span data-ttu-id="e4d13-145">Establecer el <xref:System.Windows.Window.Title%2A> propiedad en "`ExpenseIt`".</span><span class="sxs-lookup"><span data-stu-id="e4d13-145">Set the <xref:System.Windows.Window.Title%2A> property to "`ExpenseIt`".</span></span>

    - <span data-ttu-id="e4d13-146">Establecer el <xref:System.Windows.FrameworkElement.Width%2A> propiedad en 500 píxeles.</span><span class="sxs-lookup"><span data-stu-id="e4d13-146">Set the <xref:System.Windows.FrameworkElement.Width%2A> property to 500 pixels.</span></span>

    - <span data-ttu-id="e4d13-147">Establecer el <xref:System.Windows.FrameworkElement.Height%2A> propiedad en 350 píxeles.</span><span class="sxs-lookup"><span data-stu-id="e4d13-147">Set the <xref:System.Windows.FrameworkElement.Height%2A> property to 350 pixels.</span></span>

    - <span data-ttu-id="e4d13-148">Quitar el <xref:System.Windows.Controls.Grid> elementos situados entre la <xref:System.Windows.Navigation.NavigationWindow> etiquetas.</span><span class="sxs-lookup"><span data-stu-id="e4d13-148">Remove the <xref:System.Windows.Controls.Grid> elements between the <xref:System.Windows.Navigation.NavigationWindow> tags.</span></span>

    <span data-ttu-id="e4d13-149">En Visual Basic, el XAML debe tener el siguiente aspecto:</span><span class="sxs-lookup"><span data-stu-id="e4d13-149">Your XAML should look like this in Visual Basic:</span></span>

    [!code-xaml[ExpenseIt#2_A](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt/MainWindow.xaml#2_a)]

    <span data-ttu-id="e4d13-150">O a este en C#:</span><span class="sxs-lookup"><span data-stu-id="e4d13-150">Or like this in C#:</span></span>

    [!code-xaml[ExpenseIt#2](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/MainWindow.xaml#2)]

6. <span data-ttu-id="e4d13-151">Abra *MainWindow.xaml.vb* o *MainWindow.xaml.cs*.</span><span class="sxs-lookup"><span data-stu-id="e4d13-151">Open *MainWindow.xaml.vb* or *MainWindow.xaml.cs*.</span></span>

    <span data-ttu-id="e4d13-152">Este archivo es un archivo de código subyacente que contiene código para controlar los eventos declarados en *MainWindow.xaml*.</span><span class="sxs-lookup"><span data-stu-id="e4d13-152">This file is a code-behind file that contains code to handle the events declared in *MainWindow.xaml*.</span></span> <span data-ttu-id="e4d13-153">Este archivo contiene una clase parcial para la ventana definida en código XAML.</span><span class="sxs-lookup"><span data-stu-id="e4d13-153">This file contains a partial class for the window defined in XAML.</span></span>

7. <span data-ttu-id="e4d13-154">Si está utilizando C#, cambie la `MainWindow` clase derive de <xref:System.Windows.Navigation.NavigationWindow>.</span><span class="sxs-lookup"><span data-stu-id="e4d13-154">If you are using C#, change the `MainWindow` class to derive from <xref:System.Windows.Navigation.NavigationWindow>.</span></span> <span data-ttu-id="e4d13-155">(En Visual Basic, esto sucede automáticamente cuando se cambia la ventana en XAML.)</span><span class="sxs-lookup"><span data-stu-id="e4d13-155">(In Visual Basic, this happens automatically when you change the window in XAML.)</span></span>

   <span data-ttu-id="e4d13-156">El código debe tener este aspecto:</span><span class="sxs-lookup"><span data-stu-id="e4d13-156">Your code should look like this:</span></span>

   [!code-csharp[ExpenseIt#3](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/MainWindow.xaml.cs#3)]
   [!code-vb[ExpenseIt#3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/MainWindow.xaml.vb#3)]

   > [!TIP]
   > <span data-ttu-id="e4d13-157">Puede alternar el lenguaje de código del código de ejemplo entre C# y Visual Basic en el **lenguaje** desplegable en la parte superior derecha de este artículo.</span><span class="sxs-lookup"><span data-stu-id="e4d13-157">You can toggle the code language of the sample code between C# and Visual Basic in the **Language** drop-down on the upper right side of this article.</span></span>

## <a name="add-files-to-the-application"></a><span data-ttu-id="e4d13-158">Agregar archivos a la aplicación</span><span class="sxs-lookup"><span data-stu-id="e4d13-158">Add files to the application</span></span>

<span data-ttu-id="e4d13-159">En esta sección, agregará dos páginas y una imagen a la aplicación.</span><span class="sxs-lookup"><span data-stu-id="e4d13-159">In this section, you'll add two pages and an image to the application.</span></span>

1. <span data-ttu-id="e4d13-160">Agregue una nueva página WPF al proyecto y asígnele el nombre *`ExpenseItHome.xaml`*:</span><span class="sxs-lookup"><span data-stu-id="e4d13-160">Add a new WPF page to the project, and name it *`ExpenseItHome.xaml`*:</span></span>

   1. <span data-ttu-id="e4d13-161">En **el Explorador de soluciones**, haga doble clic en el **`ExpenseIt`** nodo de proyecto y elija **agregar** > **página**.</span><span class="sxs-lookup"><span data-stu-id="e4d13-161">In **Solution Explorer**, right-click on the **`ExpenseIt`** project node and choose **Add** > **Page**.</span></span>

   1. <span data-ttu-id="e4d13-162">En el **Agregar nuevo elemento** cuadro de diálogo, el **página (WPF)** plantilla ya está seleccionada.</span><span class="sxs-lookup"><span data-stu-id="e4d13-162">In the **Add New Item** dialog, the **Page (WPF)** template is already selected.</span></span> <span data-ttu-id="e4d13-163">Escriba el nombre **`ExpenseItHome`** y, a continuación, seleccione **agregar**.</span><span class="sxs-lookup"><span data-stu-id="e4d13-163">Enter the name **`ExpenseItHome`**, and then select **Add**.</span></span>

    <span data-ttu-id="e4d13-164">Esta página es la primera página que se muestra cuando se inicia la aplicación.</span><span class="sxs-lookup"><span data-stu-id="e4d13-164">This page is the first page that's displayed when the application is launched.</span></span> <span data-ttu-id="e4d13-165">Mostrará una lista de personas para seleccionar una, para mostrar un informe de gastos.</span><span class="sxs-lookup"><span data-stu-id="e4d13-165">It will show a list of people to select from, to show an expense report for.</span></span>

2. <span data-ttu-id="e4d13-166">Abra *`ExpenseItHome.xaml`*.</span><span class="sxs-lookup"><span data-stu-id="e4d13-166">Open *`ExpenseItHome.xaml`*.</span></span>

3. <span data-ttu-id="e4d13-167">Establecer el <xref:System.Windows.Controls.Page.Title%2A> a "`ExpenseIt - Home`".</span><span class="sxs-lookup"><span data-stu-id="e4d13-167">Set the <xref:System.Windows.Controls.Page.Title%2A> to "`ExpenseIt - Home`".</span></span>

    <span data-ttu-id="e4d13-168">En Visual Basic, el XAML debe tener el siguiente aspecto:</span><span class="sxs-lookup"><span data-stu-id="e4d13-168">Your XAML should look like this in Visual Basic:</span></span>

    [!code-xaml[ExpenseIt#6_A](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/ExpenseItHome.xaml#6_a)]

    <span data-ttu-id="e4d13-169">O a este en C#:</span><span class="sxs-lookup"><span data-stu-id="e4d13-169">Or this in C#:</span></span>

    [!code-xaml[ExpenseIt#6](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt2/ExpenseItHome.xaml#6)]

4. <span data-ttu-id="e4d13-170">Abra *MainWindow.xaml*.</span><span class="sxs-lookup"><span data-stu-id="e4d13-170">Open *MainWindow.xaml*.</span></span>

5. <span data-ttu-id="e4d13-171">Establecer el <xref:System.Windows.Navigation.NavigationWindow.Source%2A> propiedad en el <xref:System.Windows.Navigation.NavigationWindow> a "`ExpenseItHome.xaml`".</span><span class="sxs-lookup"><span data-stu-id="e4d13-171">Set the <xref:System.Windows.Navigation.NavigationWindow.Source%2A> property on the <xref:System.Windows.Navigation.NavigationWindow> to "`ExpenseItHome.xaml`".</span></span>

    <span data-ttu-id="e4d13-172">Esto establece *`ExpenseItHome.xaml`* como la primera página se abre cuando se inicia la aplicación.</span><span class="sxs-lookup"><span data-stu-id="e4d13-172">This sets *`ExpenseItHome.xaml`* to be the first page opened when the application starts.</span></span> <span data-ttu-id="e4d13-173">En Visual Basic, el XAML debe tener el siguiente aspecto:</span><span class="sxs-lookup"><span data-stu-id="e4d13-173">Your XAML should look like this in Visual Basic:</span></span>

    [!code-xaml[ExpenseIt#7_A](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/MainWindow.xaml#7_a)]

    <span data-ttu-id="e4d13-174">O a este en C#:</span><span class="sxs-lookup"><span data-stu-id="e4d13-174">Or this in C#:</span></span>

    [!code-xaml[ExpenseIt#7](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt2/MainWindow.xaml#7)]

   > [!TIP]
   > <span data-ttu-id="e4d13-175">También puede establecer el **origen** propiedad en el **varios** categoría de la **propiedades** ventana.</span><span class="sxs-lookup"><span data-stu-id="e4d13-175">You can also set the **Source** property in the **Miscellaneous** category of the **Properties** window.</span></span>
   >
   > ![Propiedad de origen en la ventana Propiedades](./media/properties-source.png)

6. <span data-ttu-id="e4d13-177">Agregue otra nueva página WPF al proyecto y asígnele el nombre *ExpenseReportPage.xaml*::</span><span class="sxs-lookup"><span data-stu-id="e4d13-177">Add another new WPF page to the project, and name it *ExpenseReportPage.xaml*::</span></span>

   1. <span data-ttu-id="e4d13-178">En **el Explorador de soluciones**, haga doble clic en el **`ExpenseIt`** nodo de proyecto y elija **agregar** > **página**.</span><span class="sxs-lookup"><span data-stu-id="e4d13-178">In **Solution Explorer**, right-click on the **`ExpenseIt`** project node and choose **Add** > **Page**.</span></span>

   1. <span data-ttu-id="e4d13-179">En el **Agregar nuevo elemento** cuadro de diálogo, el **página (WPF)** plantilla ya está seleccionada.</span><span class="sxs-lookup"><span data-stu-id="e4d13-179">In the **Add New Item** dialog, the **Page (WPF)** template is already selected.</span></span> <span data-ttu-id="e4d13-180">Escriba el nombre **ExpenseReportPage**y, a continuación, seleccione **agregar**.</span><span class="sxs-lookup"><span data-stu-id="e4d13-180">Enter the name **ExpenseReportPage**, and then select **Add**.</span></span>

    <span data-ttu-id="e4d13-181">Esta página mostrará el informe de gastos de la persona que está seleccionada en el **`ExpenseItHome`** página.</span><span class="sxs-lookup"><span data-stu-id="e4d13-181">This page will show the expense report for the person that is selected on the **`ExpenseItHome`** page.</span></span>

7. <span data-ttu-id="e4d13-182">Abra el archivo *ExpenseReportPage.xaml*.</span><span class="sxs-lookup"><span data-stu-id="e4d13-182">Open *ExpenseReportPage.xaml*.</span></span>

8. <span data-ttu-id="e4d13-183">Establecer el <xref:System.Windows.Controls.Page.Title%2A> a "`ExpenseIt - View Expense`".</span><span class="sxs-lookup"><span data-stu-id="e4d13-183">Set the <xref:System.Windows.Controls.Page.Title%2A> to "`ExpenseIt - View Expense`".</span></span>

    <span data-ttu-id="e4d13-184">En Visual Basic, el XAML debe tener el siguiente aspecto:</span><span class="sxs-lookup"><span data-stu-id="e4d13-184">Your XAML should look like this in Visual Basic:</span></span>

    [!code-xaml[ExpenseIt#4_A](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/ExpenseReportPage.xaml#4_a)]

    <span data-ttu-id="e4d13-185">O a este en C#:</span><span class="sxs-lookup"><span data-stu-id="e4d13-185">Or this in C#:</span></span>

    [!code-xaml[ExpenseIt#4](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/ExpenseReportPage.xaml#4)]

9. <span data-ttu-id="e4d13-186">Abra *ExpenseItHome.xaml.vb* y *ExpenseReportPage.xaml.vb*, o *ExpenseItHome.xaml.cs* y *ExpenseReportPage.xaml.cs*.</span><span class="sxs-lookup"><span data-stu-id="e4d13-186">Open *ExpenseItHome.xaml.vb* and *ExpenseReportPage.xaml.vb*, or *ExpenseItHome.xaml.cs* and *ExpenseReportPage.xaml.cs*.</span></span>

    <span data-ttu-id="e4d13-187">Cuando se crea un nuevo archivo de paginación, Visual Studio crea automáticamente un *código* archivo.</span><span class="sxs-lookup"><span data-stu-id="e4d13-187">When you create a new Page file, Visual Studio automatically creates a *code-behind* file.</span></span> <span data-ttu-id="e4d13-188">Estos archivos de código subyacente controlan la lógica para responder a la entrada del usuario.</span><span class="sxs-lookup"><span data-stu-id="e4d13-188">These code-behind files handle the logic for responding to user input.</span></span>

    <span data-ttu-id="e4d13-189">El código debe ser similar al siguiente para **`ExpenseItHome`**:</span><span class="sxs-lookup"><span data-stu-id="e4d13-189">Your code should look like this for **`ExpenseItHome`**:</span></span>

    [!code-csharp[ExpenseIt#2_5](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt2/ExpenseItHome.xaml.cs#2_5)]
    [!code-vb[ExpenseIt#2_5](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/ExpenseItHome.xaml.vb#2_5)]

    <span data-ttu-id="e4d13-190">Al igual que con esto para **ExpenseReportPage**:</span><span class="sxs-lookup"><span data-stu-id="e4d13-190">And like this for **ExpenseReportPage**:</span></span>

    [!code-csharp[ExpenseIt#5](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/ExpenseReportPage.xaml.cs#5)]
    [!code-vb[ExpenseIt#5](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/ExpenseReportPage.xaml.vb#5)]

10. <span data-ttu-id="e4d13-191">Agregue una imagen denominada *watermark.png* al proyecto.</span><span class="sxs-lookup"><span data-stu-id="e4d13-191">Add an image named *watermark.png* to the project.</span></span> <span data-ttu-id="e4d13-192">Puede crear su propia imagen, copie el archivo desde el código de ejemplo u obtenerlo [aquí](https://github.com/dotnet/docs/blob/master/docs/framework/wpf/getting-started/./media/watermark.png).</span><span class="sxs-lookup"><span data-stu-id="e4d13-192">You can create your own image, copy the file from the sample code, or get it [here](https://github.com/dotnet/docs/blob/master/docs/framework/wpf/getting-started/./media/watermark.png).</span></span>

    1. <span data-ttu-id="e4d13-193">Haga doble clic en el nodo del proyecto y seleccione **agregar** > **elemento existente**, o bien presione **MAYÚS**+**Alt** + **A**.</span><span class="sxs-lookup"><span data-stu-id="e4d13-193">Right-click on the project node and select **Add** > **Existing Item**, or press **Shift**+**Alt**+**A**.</span></span>

    2. <span data-ttu-id="e4d13-194">En el **Agregar elemento existente** cuadro de diálogo, busque el archivo de imagen que desea usar y, a continuación, seleccione **agregar**.</span><span class="sxs-lookup"><span data-stu-id="e4d13-194">In the **Add Existing Item** dialog, browse to the image file you want to use, and then select **Add**.</span></span>

## <a name="build-and-run-the-application"></a><span data-ttu-id="e4d13-195">Compilar y ejecutar la aplicación</span><span class="sxs-lookup"><span data-stu-id="e4d13-195">Build and run the application</span></span>

1. <span data-ttu-id="e4d13-196">Para compilar y ejecutar la aplicación, presione **F5** o seleccione **Iniciar depuración** desde el **depurar** menú.</span><span class="sxs-lookup"><span data-stu-id="e4d13-196">To build and run the application, press **F5** or select **Start Debugging** from the **Debug** menu.</span></span>

    <span data-ttu-id="e4d13-197">La siguiente ilustración muestra la aplicación con el <xref:System.Windows.Navigation.NavigationWindow> botones:</span><span class="sxs-lookup"><span data-stu-id="e4d13-197">The following illustration shows the application with the <xref:System.Windows.Navigation.NavigationWindow> buttons:</span></span>

    ![Captura de pantalla de ejemplo ExpenseIt](./media/gettingstartedfigure1.png)

2. <span data-ttu-id="e4d13-199">Cierre la aplicación para volver a Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="e4d13-199">Close the application to return to Visual Studio.</span></span>

## <a name="create-the-layout"></a><span data-ttu-id="e4d13-200">Crear el diseño</span><span class="sxs-lookup"><span data-stu-id="e4d13-200">Create the layout</span></span>

<span data-ttu-id="e4d13-201">Diseño proporciona una manera ordenada colocar los elementos de interfaz de usuario y también administra el tamaño y posición de dichos elementos cuando se cambia el tamaño de una interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="e4d13-201">Layout provides an ordered way to place UI elements, and also manages the size and position of those elements when a UI is resized.</span></span> <span data-ttu-id="e4d13-202">Normalmente, se crea un diseño con uno de los controles de diseño siguientes:</span><span class="sxs-lookup"><span data-stu-id="e4d13-202">You typically create a layout with one of the following layout controls:</span></span>

- <xref:System.Windows.Controls.Canvas>
- <xref:System.Windows.Controls.DockPanel>
- <xref:System.Windows.Controls.Grid>
- <xref:System.Windows.Controls.StackPanel>
- <xref:System.Windows.Controls.VirtualizingStackPanel>
- <xref:System.Windows.Controls.WrapPanel>

<span data-ttu-id="e4d13-203">Cada uno de estos controles de diseño admite un tipo especial de diseño para sus elementos secundarios.</span><span class="sxs-lookup"><span data-stu-id="e4d13-203">Each of these layout controls supports a special type of layout for its child elements.</span></span> `ExpenseIt` <span data-ttu-id="e4d13-204">se pueden cambiar el tamaño de las páginas y cada página tiene elementos organizados horizontalmente y verticalmente junto con otros elementos.</span><span class="sxs-lookup"><span data-stu-id="e4d13-204">pages can be resized, and each page has elements that are arranged horizontally and vertically alongside other elements.</span></span> <span data-ttu-id="e4d13-205">Por lo tanto, el <xref:System.Windows.Controls.Grid> es el elemento de diseño ideal para la aplicación.</span><span class="sxs-lookup"><span data-stu-id="e4d13-205">Consequently, the <xref:System.Windows.Controls.Grid> is the ideal layout element for the application.</span></span>

> [!TIP]
> <span data-ttu-id="e4d13-206">Para obtener más información acerca de <xref:System.Windows.Controls.Panel> elementos, vea [información general sobre](../controls/panels-overview.md).</span><span class="sxs-lookup"><span data-stu-id="e4d13-206">For more information about <xref:System.Windows.Controls.Panel> elements, see [Panels overview](../controls/panels-overview.md).</span></span> <span data-ttu-id="e4d13-207">Para obtener más información acerca del diseño, vea [diseño](../advanced/layout.md).</span><span class="sxs-lookup"><span data-stu-id="e4d13-207">For more information about layout, see [Layout](../advanced/layout.md).</span></span>

<span data-ttu-id="e4d13-208">En la sección, creará una tabla de una sola columna con tres filas y un margen de 10 píxeles agregando definiciones de columna y fila a la <xref:System.Windows.Controls.Grid> en *`ExpenseItHome.xaml`*.</span><span class="sxs-lookup"><span data-stu-id="e4d13-208">In the section, you create a single-column table with three rows and a 10-pixel margin by adding column and row definitions to the <xref:System.Windows.Controls.Grid> in *`ExpenseItHome.xaml`*.</span></span>

1. <span data-ttu-id="e4d13-209">Abra *`ExpenseItHome.xaml`*.</span><span class="sxs-lookup"><span data-stu-id="e4d13-209">Open *`ExpenseItHome.xaml`*.</span></span>

2. <span data-ttu-id="e4d13-210">Establecer el <xref:System.Windows.FrameworkElement.Margin%2A> propiedad en el <xref:System.Windows.Controls.Grid> elemento en "10,0,10,10", que corresponde a los márgenes izquierdo, superior, derecho e inferior:</span><span class="sxs-lookup"><span data-stu-id="e4d13-210">Set the <xref:System.Windows.FrameworkElement.Margin%2A> property on the <xref:System.Windows.Controls.Grid> element to "10,0,10,10", which corresponds to left, top, right and bottom margins:</span></span>

   ```xaml
   <Grid Margin="10,0,10,10">
   ```

   > [!TIP]
   > <span data-ttu-id="e4d13-211">También puede establecer el **margen** valores en el **propiedades** ventana, en el **diseño** categoría:</span><span class="sxs-lookup"><span data-stu-id="e4d13-211">You can also set the **Margin** values in the **Properties** window, under the **Layout** category:</span></span>
   >
   > ![Valores de margen en la ventana Propiedades](./media/properties-margin.png)

3. <span data-ttu-id="e4d13-213">Agregue el siguiente XAML entre el <xref:System.Windows.Controls.Grid> etiquetas para crear las definiciones de fila y columna:</span><span class="sxs-lookup"><span data-stu-id="e4d13-213">Add the following XAML between the <xref:System.Windows.Controls.Grid> tags to create the row and column definitions:</span></span>

    [!code-xaml[ExpenseIt#8](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt3/ExpenseItHome.xaml#8)]

    <span data-ttu-id="e4d13-214">El <xref:System.Windows.Controls.RowDefinition.Height%2A> de dos filas se establece en <xref:System.Windows.GridLength.Auto%2A>, lo que significa que las filas se ajusta el tamaño en función del contenido de las filas.</span><span class="sxs-lookup"><span data-stu-id="e4d13-214">The <xref:System.Windows.Controls.RowDefinition.Height%2A> of two rows is set to <xref:System.Windows.GridLength.Auto%2A>, which means that the rows are sized based on the content in the rows.</span></span> <span data-ttu-id="e4d13-215">El valor predeterminado <xref:System.Windows.Controls.RowDefinition.Height%2A> es <xref:System.Windows.GridUnitType.Star> ajuste de tamaño, lo que significa que el alto de fila es una proporción ponderada del espacio disponible.</span><span class="sxs-lookup"><span data-stu-id="e4d13-215">The default <xref:System.Windows.Controls.RowDefinition.Height%2A> is <xref:System.Windows.GridUnitType.Star> sizing, which means that the row height is a weighted proportion of the available space.</span></span> <span data-ttu-id="e4d13-216">Por ejemplo, si dos filas tienen un <xref:System.Windows.Controls.RowDefinition.Height%2A> de "\*", cada uno de ellos tiene un alto que sea la mitad del espacio disponible.</span><span class="sxs-lookup"><span data-stu-id="e4d13-216">For example if two rows each have a <xref:System.Windows.Controls.RowDefinition.Height%2A> of "\*", they each have a height that is half of the available space.</span></span>

    <span data-ttu-id="e4d13-217">Su <xref:System.Windows.Controls.Grid> debería parecerse ahora el XAML siguiente:</span><span class="sxs-lookup"><span data-stu-id="e4d13-217">Your <xref:System.Windows.Controls.Grid> should now look like the following XAML:</span></span>

    [!code-xaml[ExpenseIt#9](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt3/ExpenseItHome.xaml#9)]

## <a name="add-controls"></a><span data-ttu-id="e4d13-218">Agregar controles</span><span class="sxs-lookup"><span data-stu-id="e4d13-218">Add controls</span></span>

<span data-ttu-id="e4d13-219">En esta sección, actualizará la página principal de la interfaz de usuario para mostrar una lista de personas que un usuario puede seleccionar para mostrar el informe de gastos para.</span><span class="sxs-lookup"><span data-stu-id="e4d13-219">In this section, you'll update the home page UI to show a list of people that a user can select from to show the expense report for.</span></span> <span data-ttu-id="e4d13-220">Los controles son objetos de interfaz de usuario que permiten a los usuarios interactuar con su aplicación.</span><span class="sxs-lookup"><span data-stu-id="e4d13-220">Controls are UI objects that allow users to interact with your application.</span></span> <span data-ttu-id="e4d13-221">Para obtener más información, consulte [Controles](../controls/index.md).</span><span class="sxs-lookup"><span data-stu-id="e4d13-221">For more information, see [Controls](../controls/index.md).</span></span>

<span data-ttu-id="e4d13-222">Para crear esta interfaz de usuario, agregará los siguientes elementos para *`ExpenseItHome.xaml`*:</span><span class="sxs-lookup"><span data-stu-id="e4d13-222">To create this UI, you'll add the following elements to *`ExpenseItHome.xaml`*:</span></span>

- <xref:System.Windows.Controls.ListBox> <span data-ttu-id="e4d13-223">(para la lista de personas).</span><span class="sxs-lookup"><span data-stu-id="e4d13-223">(for the list of people).</span></span>
- <xref:System.Windows.Controls.Label> <span data-ttu-id="e4d13-224">(para el encabezado de lista).</span><span class="sxs-lookup"><span data-stu-id="e4d13-224">(for the list header).</span></span>
- <xref:System.Windows.Controls.Button> <span data-ttu-id="e4d13-225">(para hacer clic para ver el informe de gastos de la persona que está seleccionada en la lista).</span><span class="sxs-lookup"><span data-stu-id="e4d13-225">(to click to view the expense report for the person that is selected in the list).</span></span>

<span data-ttu-id="e4d13-226">Cada control se coloca en una fila de la <xref:System.Windows.Controls.Grid> estableciendo el <xref:System.Windows.Controls.Grid.Row%2A?displayProperty=nameWithType> propiedad adjunta.</span><span class="sxs-lookup"><span data-stu-id="e4d13-226">Each control is placed in a row of the <xref:System.Windows.Controls.Grid> by setting the <xref:System.Windows.Controls.Grid.Row%2A?displayProperty=nameWithType> attached property.</span></span> <span data-ttu-id="e4d13-227">Para obtener más información sobre las propiedades adjuntas, consulte [Attached Properties Overview](../advanced/attached-properties-overview.md).</span><span class="sxs-lookup"><span data-stu-id="e4d13-227">For more information about attached properties, see [Attached Properties Overview](../advanced/attached-properties-overview.md).</span></span>

1. <span data-ttu-id="e4d13-228">Abra *`ExpenseItHome.xaml`*.</span><span class="sxs-lookup"><span data-stu-id="e4d13-228">Open *`ExpenseItHome.xaml`*.</span></span>

2. <span data-ttu-id="e4d13-229">Agregue el siguiente XAML en algún lugar entre el <xref:System.Windows.Controls.Grid> etiquetas:</span><span class="sxs-lookup"><span data-stu-id="e4d13-229">Add the following XAML somewhere between the <xref:System.Windows.Controls.Grid> tags:</span></span>

   [!code-xaml[ExpenseIt#10](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt4/ExpenseItHome.xaml#10)]

   > [!TIP]
   > <span data-ttu-id="e4d13-230">También puede crear los controles arrastrándolos desde el **cuadro de herramientas** ventana en la ventana de diseño y, a continuación, establecer sus propiedades en el **propiedades** ventana.</span><span class="sxs-lookup"><span data-stu-id="e4d13-230">You can also create the controls by dragging them from the **Toolbox** window onto the design window, and then setting their properties in the **Properties** window.</span></span>

3. <span data-ttu-id="e4d13-231">Compile y ejecute la aplicación.</span><span class="sxs-lookup"><span data-stu-id="e4d13-231">Build and run the application.</span></span>

<span data-ttu-id="e4d13-232">La ilustración siguiente muestra los controles que acaba de crear:</span><span class="sxs-lookup"><span data-stu-id="e4d13-232">The following illustration shows the controls you just created:</span></span>

![Captura de pantalla de ejemplo ExpenseIt](./media/gettingstartedfigure2.png)

## <a name="add-an-image-and-a-title"></a><span data-ttu-id="e4d13-234">Agregar un título y una imagen</span><span class="sxs-lookup"><span data-stu-id="e4d13-234">Add an image and a title</span></span>

<span data-ttu-id="e4d13-235">En esta sección, actualizará la página principal de la interfaz de usuario con una imagen y un título de página.</span><span class="sxs-lookup"><span data-stu-id="e4d13-235">In this section, you'll update the home page UI with an image and a page title.</span></span>

1. <span data-ttu-id="e4d13-236">Abra *`ExpenseItHome.xaml`*.</span><span class="sxs-lookup"><span data-stu-id="e4d13-236">Open *`ExpenseItHome.xaml`*.</span></span>

2. <span data-ttu-id="e4d13-237">Agregue otra columna a la <xref:System.Windows.Controls.Grid.ColumnDefinitions%2A> con fijo <xref:System.Windows.Controls.ColumnDefinition.Width%2A> de 230 píxeles:</span><span class="sxs-lookup"><span data-stu-id="e4d13-237">Add another column to the <xref:System.Windows.Controls.Grid.ColumnDefinitions%2A> with a fixed <xref:System.Windows.Controls.ColumnDefinition.Width%2A> of 230 pixels:</span></span>

    [!code-xaml[ExpenseIt#11](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt5/ExpenseItHome.xaml#11)]

3. <span data-ttu-id="e4d13-238">Agregar otra fila a la <xref:System.Windows.Controls.Grid.RowDefinitions%2A>, para un total de cuatro filas:</span><span class="sxs-lookup"><span data-stu-id="e4d13-238">Add another row to the <xref:System.Windows.Controls.Grid.RowDefinitions%2A>, for a total of four rows:</span></span>

    [!code-xaml[ExpenseIt#11b](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt5/ExpenseItHome.xaml#11b)]

4. <span data-ttu-id="e4d13-239">Mueva los controles a la segunda columna estableciendo el <xref:System.Windows.Controls.Grid.Column%2A?displayProperty=nameWithType> propiedad en 1 en cada uno de los tres controles (borde, ListBox y botón).</span><span class="sxs-lookup"><span data-stu-id="e4d13-239">Move the controls to the second column by setting the <xref:System.Windows.Controls.Grid.Column%2A?displayProperty=nameWithType> property to 1 in each of the three controls (Border, ListBox, and Button).</span></span>

5. <span data-ttu-id="e4d13-240">Baje cada control una fila, al incrementar su <xref:System.Windows.Controls.Grid.Row%2A?displayProperty=nameWithType> valor en 1.</span><span class="sxs-lookup"><span data-stu-id="e4d13-240">Move each control down a row, by incrementing its <xref:System.Windows.Controls.Grid.Row%2A?displayProperty=nameWithType> value by 1.</span></span>

   <span data-ttu-id="e4d13-241">El XAML para los tres controles ahora este aspecto:</span><span class="sxs-lookup"><span data-stu-id="e4d13-241">The XAML for the three controls now looks like this:</span></span>

    [!code-xaml[ExpenseIt#12](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt5/ExpenseItHome.xaml#12)]

6. <span data-ttu-id="e4d13-242">Establecer el <xref:System.Windows.Controls.Panel.Background%2A> de la <xref:System.Windows.Controls.Grid> sea la *watermark.png* archivo de imagen, agregando el siguiente XAML en algún lugar entre el `<Grid>` y `</Grid>` etiquetas:</span><span class="sxs-lookup"><span data-stu-id="e4d13-242">Set the <xref:System.Windows.Controls.Panel.Background%2A> of the <xref:System.Windows.Controls.Grid> to be the *watermark.png* image file, by adding the following XAML somewhere between the `<Grid>` and `</Grid>` tags:</span></span>

    [!code-xaml[ExpenseIt#14](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt5/ExpenseItHome.xaml#14)]

7. <span data-ttu-id="e4d13-243">Antes de la <xref:System.Windows.Controls.Border> elemento, agregue un <xref:System.Windows.Controls.Label> con el contenido "View Expense Report".</span><span class="sxs-lookup"><span data-stu-id="e4d13-243">Before the <xref:System.Windows.Controls.Border> element, add a <xref:System.Windows.Controls.Label> with the content "View Expense Report".</span></span> <span data-ttu-id="e4d13-244">Este es el título de la página.</span><span class="sxs-lookup"><span data-stu-id="e4d13-244">This is the title of the page.</span></span>

    [!code-xaml[ExpenseIt#13](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt5/ExpenseItHome.xaml#13)]

8. <span data-ttu-id="e4d13-245">Compile y ejecute la aplicación.</span><span class="sxs-lookup"><span data-stu-id="e4d13-245">Build and run the application.</span></span>

<span data-ttu-id="e4d13-246">La ilustración siguiente muestra los resultados de lo que acaba de agregar:</span><span class="sxs-lookup"><span data-stu-id="e4d13-246">The following illustration shows the results of what you just added:</span></span>

![Captura de pantalla de ejemplo ExpenseIt](./media/gettingstartedfigure3.png)

## <a name="add-code-to-handle-events"></a><span data-ttu-id="e4d13-248">Agregue código para controlar eventos</span><span class="sxs-lookup"><span data-stu-id="e4d13-248">Add code to handle events</span></span>

1. <span data-ttu-id="e4d13-249">Abra *`ExpenseItHome.xaml`*.</span><span class="sxs-lookup"><span data-stu-id="e4d13-249">Open *`ExpenseItHome.xaml`*.</span></span>

2. <span data-ttu-id="e4d13-250">Agregar un <xref:System.Windows.Controls.Primitives.ButtonBase.Click> controlador de eventos para el <xref:System.Windows.Controls.Button> elemento.</span><span class="sxs-lookup"><span data-stu-id="e4d13-250">Add a <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event handler to the <xref:System.Windows.Controls.Button> element.</span></span> <span data-ttu-id="e4d13-251">Para obtener más información, vea [Cómo: Crear un controlador de eventos simple](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/bb675300(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="e4d13-251">For more information, see [How to: Create a simple event handler](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/bb675300(v=vs.100)).</span></span>

    [!code-xaml[ExpenseIt#15](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt6/ExpenseItHome.xaml#15)]

3. <span data-ttu-id="e4d13-252">Abra *`ExpenseItHome.xaml.vb`* o *`ExpenseItHome.xaml.cs`*.</span><span class="sxs-lookup"><span data-stu-id="e4d13-252">Open *`ExpenseItHome.xaml.vb`* or *`ExpenseItHome.xaml.cs`*.</span></span>

4. <span data-ttu-id="e4d13-253">Agregue el código siguiente a la `ExpenseItHome` clase para agregar un botón de controlador de eventos click.</span><span class="sxs-lookup"><span data-stu-id="e4d13-253">Add the following code to the `ExpenseItHome` class to add a button click event handler.</span></span> <span data-ttu-id="e4d13-254">El controlador de eventos abre la **ExpenseReportPage** página.</span><span class="sxs-lookup"><span data-stu-id="e4d13-254">The event handler opens the **ExpenseReportPage** page.</span></span>

    [!code-csharp[ExpenseIt#16](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt6/ExpenseItHome.xaml.cs#16)]
    [!code-vb[ExpenseIt#16](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt6/ExpenseItHome.xaml.vb#16)]

## <a name="create-the-ui-for-expensereportpage"></a><span data-ttu-id="e4d13-255">Crear la interfaz de usuario para ExpenseReportPage</span><span class="sxs-lookup"><span data-stu-id="e4d13-255">Create the UI for ExpenseReportPage</span></span>

<span data-ttu-id="e4d13-256">*ExpenseReportPage.xaml* muestra el informe de gastos de la persona que está seleccionada en el **`ExpenseItHome`** página.</span><span class="sxs-lookup"><span data-stu-id="e4d13-256">*ExpenseReportPage.xaml* displays the expense report for the person that's selected on the **`ExpenseItHome`** page.</span></span> <span data-ttu-id="e4d13-257">En esta sección, creará la interfaz de usuario para **ExpenseReportPage**.</span><span class="sxs-lookup"><span data-stu-id="e4d13-257">In this section, you'll create the UI for **ExpenseReportPage**.</span></span> <span data-ttu-id="e4d13-258">También agregará en segundo plano y los colores a los distintos elementos de interfaz de usuario de relleno.</span><span class="sxs-lookup"><span data-stu-id="e4d13-258">You'll also add background and fill colors to the various UI elements.</span></span>

1. <span data-ttu-id="e4d13-259">Abra el archivo *ExpenseReportPage.xaml*.</span><span class="sxs-lookup"><span data-stu-id="e4d13-259">Open *ExpenseReportPage.xaml*.</span></span>

2. <span data-ttu-id="e4d13-260">Agregue el siguiente XAML entre el <xref:System.Windows.Controls.Grid> etiquetas:</span><span class="sxs-lookup"><span data-stu-id="e4d13-260">Add the following XAML between the <xref:System.Windows.Controls.Grid> tags:</span></span>

    [!code-xaml[ExpenseIt#17](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt6/ExpenseReportPage.xaml#17)]

    <span data-ttu-id="e4d13-261">Esta interfaz de usuario es similar a *`ExpenseItHome.xaml`*, excepto en que los datos del informe se muestran en un <xref:System.Windows.Controls.DataGrid>.</span><span class="sxs-lookup"><span data-stu-id="e4d13-261">This UI is similar to *`ExpenseItHome.xaml`*, except the report data is displayed in a <xref:System.Windows.Controls.DataGrid>.</span></span>

3. <span data-ttu-id="e4d13-262">Compile y ejecute la aplicación.</span><span class="sxs-lookup"><span data-stu-id="e4d13-262">Build and run the application.</span></span>

    > [!NOTE]
    > <span data-ttu-id="e4d13-263">Si se produce un error que el <xref:System.Windows.Controls.DataGrid> no se encontró o no existe, asegúrese de que el proyecto tiene como destino .NET Framework 4 o posterior.</span><span class="sxs-lookup"><span data-stu-id="e4d13-263">If you get an error that the <xref:System.Windows.Controls.DataGrid> was not found or does not exist, make sure that your project targets the .NET Framework 4 or later.</span></span> <span data-ttu-id="e4d13-264">Para obtener más información, vea [Cómo: usar una versión de .NET Framework como destino](/visualstudio/ide/how-to-target-a-version-of-the-dotnet-framework).</span><span class="sxs-lookup"><span data-stu-id="e4d13-264">For more information, see [How to: Target a Version of the .NET Framework](/visualstudio/ide/how-to-target-a-version-of-the-dotnet-framework).</span></span>

4. <span data-ttu-id="e4d13-265">Seleccione el **vista** botón.</span><span class="sxs-lookup"><span data-stu-id="e4d13-265">Select the **View** button.</span></span>

    <span data-ttu-id="e4d13-266">Se mostrará la página de informe de gastos</span><span class="sxs-lookup"><span data-stu-id="e4d13-266">The expense report page appears.</span></span> <span data-ttu-id="e4d13-267">Tenga en cuenta que el botón de navegación hacia atrás está habilitado.</span><span class="sxs-lookup"><span data-stu-id="e4d13-267">Also notice that the back navigation button is enabled.</span></span>

<span data-ttu-id="e4d13-268">La ilustración siguiente muestra los elementos de interfaz de usuario agregados al *ExpenseReportPage.xaml*.</span><span class="sxs-lookup"><span data-stu-id="e4d13-268">The following illustration shows the UI elements added to *ExpenseReportPage.xaml*.</span></span>

![Captura de pantalla de ejemplo ExpenseIt](./media/gettingstartedfigure4.png)

## <a name="style-controls"></a><span data-ttu-id="e4d13-270">Aplicar estilo a controles</span><span class="sxs-lookup"><span data-stu-id="e4d13-270">Style controls</span></span>

<span data-ttu-id="e4d13-271">La apariencia de los diversos elementos a menudo es el mismo para todos los elementos del mismo tipo en una interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="e4d13-271">The appearance of various elements is often the same for all elements of the same type in a UI.</span></span> <span data-ttu-id="e4d13-272">Interfaz de usuario usa [estilos](../controls/styling-and-templating.md) para que las apariencias sean reutilizables en varios elementos.</span><span class="sxs-lookup"><span data-stu-id="e4d13-272">UI uses [styles](../controls/styling-and-templating.md) to make appearances reusable across multiple elements.</span></span> <span data-ttu-id="e4d13-273">La reutilización de los estilos ayuda a simplificar la administración y creación de XAML.</span><span class="sxs-lookup"><span data-stu-id="e4d13-273">The reusability of styles helps to simplify XAML creation and management.</span></span> <span data-ttu-id="e4d13-274">En esta sección se reemplazan los atributos de cada elemento que se definieron en pasos anteriores por estilos.</span><span class="sxs-lookup"><span data-stu-id="e4d13-274">This section replaces the per-element attributes that were defined in previous steps with styles.</span></span>

1. <span data-ttu-id="e4d13-275">Abra *Application.xaml* o *App.xaml*.</span><span class="sxs-lookup"><span data-stu-id="e4d13-275">Open *Application.xaml* or *App.xaml*.</span></span>

2. <span data-ttu-id="e4d13-276">Agregue el siguiente XAML entre el <xref:System.Windows.Application.Resources%2A?displayProperty=nameWithType> etiquetas:</span><span class="sxs-lookup"><span data-stu-id="e4d13-276">Add the following XAML between the <xref:System.Windows.Application.Resources%2A?displayProperty=nameWithType> tags:</span></span>

    [!code-xaml[ExpenseIt#18](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt7/App.xaml#18)]

    <span data-ttu-id="e4d13-277">Este código XAML agrega los estilos siguientes:</span><span class="sxs-lookup"><span data-stu-id="e4d13-277">This XAML adds the following styles:</span></span>

    - `headerTextStyle`<span data-ttu-id="e4d13-278">: Para dar formato al título de página <xref:System.Windows.Controls.Label>.</span><span class="sxs-lookup"><span data-stu-id="e4d13-278">: To format the page title <xref:System.Windows.Controls.Label>.</span></span>

    - `labelStyle`<span data-ttu-id="e4d13-279">: Para dar formato a la <xref:System.Windows.Controls.Label> controles.</span><span class="sxs-lookup"><span data-stu-id="e4d13-279">: To format the <xref:System.Windows.Controls.Label> controls.</span></span>

    - `columnHeaderStyle`<span data-ttu-id="e4d13-280">: Para dar formato a la <xref:System.Windows.Controls.Primitives.DataGridColumnHeader>.</span><span class="sxs-lookup"><span data-stu-id="e4d13-280">: To format the <xref:System.Windows.Controls.Primitives.DataGridColumnHeader>.</span></span>

    - `listHeaderStyle`<span data-ttu-id="e4d13-281">: Aplica formato al encabezado de lista <xref:System.Windows.Controls.Border> controles.</span><span class="sxs-lookup"><span data-stu-id="e4d13-281">: To format the list header <xref:System.Windows.Controls.Border> controls.</span></span>

    - `listHeaderTextStyle`<span data-ttu-id="e4d13-282">: Aplica formato al encabezado de lista <xref:System.Windows.Controls.Label>.</span><span class="sxs-lookup"><span data-stu-id="e4d13-282">: To format the list header <xref:System.Windows.Controls.Label>.</span></span>

    - `buttonStyle`<span data-ttu-id="e4d13-283">: Para dar formato a la <xref:System.Windows.Controls.Button> en `ExpenseItHome.xaml`.</span><span class="sxs-lookup"><span data-stu-id="e4d13-283">: To format the <xref:System.Windows.Controls.Button> on `ExpenseItHome.xaml`.</span></span>

    <span data-ttu-id="e4d13-284">Tenga en cuenta que los estilos son recursos y elementos secundarios de la <xref:System.Windows.Application.Resources%2A?displayProperty=nameWithType> property (elemento).</span><span class="sxs-lookup"><span data-stu-id="e4d13-284">Notice that the styles are resources and children of the <xref:System.Windows.Application.Resources%2A?displayProperty=nameWithType> property element.</span></span> <span data-ttu-id="e4d13-285">En esta ubicación, los estilos se aplican a todos los elementos de una aplicación.</span><span class="sxs-lookup"><span data-stu-id="e4d13-285">In this location, the styles are applied to all the elements in an application.</span></span> <span data-ttu-id="e4d13-286">Para obtener un ejemplo del uso de recursos en una aplicación de .NET Framework, vea [usar recursos de aplicaciones](../advanced/how-to-use-application-resources.md).</span><span class="sxs-lookup"><span data-stu-id="e4d13-286">For an example of using resources in a .NET Framework application, see [Use Application Resources](../advanced/how-to-use-application-resources.md).</span></span>

3. <span data-ttu-id="e4d13-287">Abra *`ExpenseItHome.xaml`*.</span><span class="sxs-lookup"><span data-stu-id="e4d13-287">Open *`ExpenseItHome.xaml`*.</span></span>

4. <span data-ttu-id="e4d13-288">Reemplace todo entre los <xref:System.Windows.Controls.Grid> elementos con el XAML siguiente:</span><span class="sxs-lookup"><span data-stu-id="e4d13-288">Replace everything between the <xref:System.Windows.Controls.Grid> elements with the following XAML:</span></span>

    [!code-xaml[ExpenseIt#19](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt7/ExpenseItHome.xaml#19)]

    <span data-ttu-id="e4d13-289">Las propiedades como <xref:System.Windows.VerticalAlignment> y <xref:System.Windows.Media.FontFamily> que definen la apariencia de cada control se quitan y reemplazan aplicando los estilos.</span><span class="sxs-lookup"><span data-stu-id="e4d13-289">The properties such as <xref:System.Windows.VerticalAlignment> and <xref:System.Windows.Media.FontFamily> that define the look of each control are removed and replaced by applying the styles.</span></span> <span data-ttu-id="e4d13-290">Por ejemplo, el `headerTextStyle` se aplica a "View Expense Report" <xref:System.Windows.Controls.Label>.</span><span class="sxs-lookup"><span data-stu-id="e4d13-290">For example, the `headerTextStyle` is applied to the "View Expense Report" <xref:System.Windows.Controls.Label>.</span></span>

5. <span data-ttu-id="e4d13-291">Abra el archivo *ExpenseReportPage.xaml*.</span><span class="sxs-lookup"><span data-stu-id="e4d13-291">Open *ExpenseReportPage.xaml*.</span></span>

6. <span data-ttu-id="e4d13-292">Reemplace todo entre los <xref:System.Windows.Controls.Grid> elementos con el XAML siguiente:</span><span class="sxs-lookup"><span data-stu-id="e4d13-292">Replace everything between the <xref:System.Windows.Controls.Grid> elements with the following XAML:</span></span>

    [!code-xaml[ExpenseIt#20](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt7/ExpenseReportPage.xaml#20)]

    <span data-ttu-id="e4d13-293">Esto agrega estilos a los elementos <xref:System.Windows.Controls.Label> y <xref:System.Windows.Controls.Border> .</span><span class="sxs-lookup"><span data-stu-id="e4d13-293">This adds styles to the <xref:System.Windows.Controls.Label> and <xref:System.Windows.Controls.Border> elements.</span></span>

## <a name="bind-data-to-a-control"></a><span data-ttu-id="e4d13-294">Enlazar datos a un control</span><span class="sxs-lookup"><span data-stu-id="e4d13-294">Bind data to a control</span></span>

<span data-ttu-id="e4d13-295">En esta sección, creará los datos XML que se enlazan a diversos controles.</span><span class="sxs-lookup"><span data-stu-id="e4d13-295">In this section, you'll create the XML data that is bound to various controls.</span></span>

1. <span data-ttu-id="e4d13-296">Abra *`ExpenseItHome.xaml`*.</span><span class="sxs-lookup"><span data-stu-id="e4d13-296">Open *`ExpenseItHome.xaml`*.</span></span>

2. <span data-ttu-id="e4d13-297">Después de la apertura <xref:System.Windows.Controls.Grid> elemento, agregue el siguiente XAML para crear un <xref:System.Windows.Data.XmlDataProvider> que contiene los datos para cada persona:</span><span class="sxs-lookup"><span data-stu-id="e4d13-297">After the opening <xref:System.Windows.Controls.Grid> element, add the following XAML to create an <xref:System.Windows.Data.XmlDataProvider> that contains the data for each person:</span></span>

    [!code-xaml[ExpenseIt#21](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml#21)]
    [!code-xaml[ExpenseIt#23](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml#23)]
    [!code-xaml[ExpenseIt#22](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml#22)]

    <span data-ttu-id="e4d13-298">Los datos se crean como un <xref:System.Windows.Controls.Grid> recursos.</span><span class="sxs-lookup"><span data-stu-id="e4d13-298">The data is created as a <xref:System.Windows.Controls.Grid> resource.</span></span> <span data-ttu-id="e4d13-299">Normalmente esto se cargaría como archivo, pero los datos se agregan en línea para simplificar.</span><span class="sxs-lookup"><span data-stu-id="e4d13-299">Normally this would be loaded as a file, but for simplicity the data is added inline.</span></span>

3. <span data-ttu-id="e4d13-300">Dentro de la `<Grid.Resources>` elemento, agregue el siguiente <xref:System.Windows.DataTemplate>, que define cómo mostrar los datos en el <xref:System.Windows.Controls.ListBox>:</span><span class="sxs-lookup"><span data-stu-id="e4d13-300">Within the `<Grid.Resources>` element, add the following <xref:System.Windows.DataTemplate>, which defines how to display the data in the <xref:System.Windows.Controls.ListBox>:</span></span>

    [!code-xaml[ExpenseIt#21](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml#21)]
    [!code-xaml[ExpenseIt#24](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml#24)]
    [!code-xaml[ExpenseIt#22](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml#22)]

    <span data-ttu-id="e4d13-301">Para obtener más información acerca de las plantillas de datos, vea [información general sobre plantillas de datos](../data/data-templating-overview.md).</span><span class="sxs-lookup"><span data-stu-id="e4d13-301">For more information about data templates, see [Data templating overview](../data/data-templating-overview.md).</span></span>

4. <span data-ttu-id="e4d13-302">Reemplazar existente <xref:System.Windows.Controls.ListBox> con el XAML siguiente:</span><span class="sxs-lookup"><span data-stu-id="e4d13-302">Replace the existing <xref:System.Windows.Controls.ListBox> with the following XAML:</span></span>

    [!code-xaml[ExpenseIt#25](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml#25)]

    <span data-ttu-id="e4d13-303">Este XAML enlaza la <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> propiedad de la <xref:System.Windows.Controls.ListBox> al origen de datos y aplica la plantilla de datos como el <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A>.</span><span class="sxs-lookup"><span data-stu-id="e4d13-303">This XAML binds the <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> property of the <xref:System.Windows.Controls.ListBox> to the data source and applies the data template as the <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A>.</span></span>

## <a name="connect-data-to-controls"></a><span data-ttu-id="e4d13-304">Conectar datos a controles</span><span class="sxs-lookup"><span data-stu-id="e4d13-304">Connect data to controls</span></span>

<span data-ttu-id="e4d13-305">A continuación, agregará código para recuperar el nombre que se han seleccionado en el **`ExpenseItHome`** página y pasarlo al constructor de **ExpenseReportPage**.</span><span class="sxs-lookup"><span data-stu-id="e4d13-305">Next, you'll add code to retrieve the name that's selected on the **`ExpenseItHome`** page and pass it to the constructor of **ExpenseReportPage**.</span></span> <span data-ttu-id="e4d13-306">**ExpenseReportPage** establece el contexto de datos con el elemento pasado, que es lo que los controles definidos en *ExpenseReportPage.xaml* enlazar.</span><span class="sxs-lookup"><span data-stu-id="e4d13-306">**ExpenseReportPage** sets its data context with the passed item, which is what the controls defined in *ExpenseReportPage.xaml* bind to.</span></span>

1. <span data-ttu-id="e4d13-307">Abra *ExpenseReportPage.xaml.vb* o *ExpenseReportPage.xaml.cs*.</span><span class="sxs-lookup"><span data-stu-id="e4d13-307">Open *ExpenseReportPage.xaml.vb* or *ExpenseReportPage.xaml.cs*.</span></span>

2. <span data-ttu-id="e4d13-308">Agregue un constructor que acepte un objeto, para que pueda pasar los datos del informe de gastos de la persona seleccionada.</span><span class="sxs-lookup"><span data-stu-id="e4d13-308">Add a constructor that takes an object so you can pass the expense report data of the selected person.</span></span>

    [!code-csharp[ExpenseIt#26](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseReportPage.xaml.cs#26)]
    [!code-vb[ExpenseIt#26](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt8/ExpenseReportPage.xaml.vb#26)]

3. <span data-ttu-id="e4d13-309">Abra *`ExpenseItHome.xaml.vb`* o *`ExpenseItHome.xaml.cs`*.</span><span class="sxs-lookup"><span data-stu-id="e4d13-309">Open *`ExpenseItHome.xaml.vb`* or *`ExpenseItHome.xaml.cs`*.</span></span>

4. <span data-ttu-id="e4d13-310">Cambiar el <xref:System.Windows.Controls.Primitives.ButtonBase.Click> controlador de eventos para llamar al nuevo constructor y pase los datos de informe de gastos de la persona seleccionada.</span><span class="sxs-lookup"><span data-stu-id="e4d13-310">Change the <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event handler to call the new constructor passing the expense report data of the selected person.</span></span>

    [!code-csharp[ExpenseIt#27](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml.cs#27)]
    [!code-vb[ExpenseIt#27](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt8/ExpenseItHome.xaml.vb#27)]

## <a name="style-data-with-data-templates"></a><span data-ttu-id="e4d13-311">Datos de estilo con plantillas de datos</span><span class="sxs-lookup"><span data-stu-id="e4d13-311">Style data with data templates</span></span>

<span data-ttu-id="e4d13-312">En esta sección, actualizará la interfaz de usuario para cada elemento en las listas de enlazado a datos mediante el uso de plantillas de datos.</span><span class="sxs-lookup"><span data-stu-id="e4d13-312">In this section, you'll update the UI for each item in the data-bound lists by using data templates.</span></span>

1. <span data-ttu-id="e4d13-313">Abra el archivo *ExpenseReportPage.xaml*.</span><span class="sxs-lookup"><span data-stu-id="e4d13-313">Open *ExpenseReportPage.xaml*.</span></span>

2. <span data-ttu-id="e4d13-314">Enlazar el contenido de la "Name" y "Department" <xref:System.Windows.Controls.Label> elementos a los datos apropiados del origen de propiedad.</span><span class="sxs-lookup"><span data-stu-id="e4d13-314">Bind the content of the "Name" and "Department" <xref:System.Windows.Controls.Label> elements to the appropriate data source property.</span></span> <span data-ttu-id="e4d13-315">Para obtener más información sobre el enlace de datos, vea [información general sobre el enlace de datos](../data/data-binding-overview.md).</span><span class="sxs-lookup"><span data-stu-id="e4d13-315">For more information about data binding, see [Data binding overview](../data/data-binding-overview.md).</span></span>

    [!code-xaml[ExpenseIt#31](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseReportPage.xaml#31)]

3. <span data-ttu-id="e4d13-316">Después de la apertura <xref:System.Windows.Controls.Grid> elemento, agregue las siguientes plantillas de datos, que definen cómo se muestran los datos de informe de gastos:</span><span class="sxs-lookup"><span data-stu-id="e4d13-316">After the opening <xref:System.Windows.Controls.Grid> element, add the following data templates, which define how to display the expense report data:</span></span>

    [!code-xaml[ExpenseIt#30](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseReportPage.xaml#30)]

4. <span data-ttu-id="e4d13-317">Reemplace el <xref:System.Windows.Controls.DataGridTextColumn> elementos con <xref:System.Windows.Controls.DataGridTemplateColumn> bajo el <xref:System.Windows.Controls.DataGrid> elemento y aplicar las plantillas.</span><span class="sxs-lookup"><span data-stu-id="e4d13-317">Replace the <xref:System.Windows.Controls.DataGridTextColumn> elements with <xref:System.Windows.Controls.DataGridTemplateColumn> under the <xref:System.Windows.Controls.DataGrid> element and apply the templates to them.</span></span>

    [!code-xaml[ExpenseIt#32](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseReportPage.xaml#32)]

5. <span data-ttu-id="e4d13-318">Compile y ejecute la aplicación.</span><span class="sxs-lookup"><span data-stu-id="e4d13-318">Build and run the application.</span></span>

6. <span data-ttu-id="e4d13-319">Seleccione una persona y, a continuación, seleccione el **vista** botón.</span><span class="sxs-lookup"><span data-stu-id="e4d13-319">Select a person and then select the **View** button.</span></span>

<span data-ttu-id="e4d13-320">La ilustración siguiente muestra ambas páginas de la `ExpenseIt` aplicación con controles, diseño, estilos, el enlace de datos y aplicar las plantillas de datos:</span><span class="sxs-lookup"><span data-stu-id="e4d13-320">The following illustration shows both pages of the `ExpenseIt` application with controls, layout, styles, data binding, and data templates applied:</span></span>

![Capturas de pantalla de ejemplo ExpenseIt](./media/gettingstartedfigure5.png)

> [!NOTE]
> <span data-ttu-id="e4d13-322">En este ejemplo se muestra una característica específica de WPF y no sigue todos los procedimientos recomendados para cosas como la seguridad, localización y accesibilidad.</span><span class="sxs-lookup"><span data-stu-id="e4d13-322">This sample demonstrates a specific feature of WPF and doesn't follow all best practices for things like security, localization, and accessibility.</span></span> <span data-ttu-id="e4d13-323">Para una completa cobertura de WPF y el desarrollo de aplicaciones .NET Framework procedimientos recomendados, consulte los temas siguientes:</span><span class="sxs-lookup"><span data-stu-id="e4d13-323">For comprehensive coverage of WPF and the .NET Framework application development best practices, see the following topics:</span></span>
>
> - [<span data-ttu-id="e4d13-324">Accesibilidad</span><span class="sxs-lookup"><span data-stu-id="e4d13-324">Accessibility</span></span>](../../ui-automation/accessibility-best-practices.md)
>
> - [<span data-ttu-id="e4d13-325">Seguridad</span><span class="sxs-lookup"><span data-stu-id="e4d13-325">Security</span></span>](../security-wpf.md)
>
> - [<span data-ttu-id="e4d13-326">Localización y globalización de WPF</span><span class="sxs-lookup"><span data-stu-id="e4d13-326">WPF globalization and localization</span></span>](../advanced/wpf-globalization-and-localization-overview.md)
>
> - [<span data-ttu-id="e4d13-327">WPF: rendimiento</span><span class="sxs-lookup"><span data-stu-id="e4d13-327">WPF performance</span></span>](../advanced/optimizing-wpf-application-performance.md)

## <a name="next-steps"></a><span data-ttu-id="e4d13-328">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="e4d13-328">Next steps</span></span>

<span data-ttu-id="e4d13-329">En este tutorial ha aprendido varias técnicas para crear una interfaz de usuario mediante Windows Presentation Foundation (WPF).</span><span class="sxs-lookup"><span data-stu-id="e4d13-329">In this walkthrough you learned a number of techniques for creating a UI using Windows Presentation Foundation (WPF).</span></span> <span data-ttu-id="e4d13-330">Ahora debería tener un conocimiento básico de los bloques de creación de una aplicación de .NET Framework, enlazado a datos.</span><span class="sxs-lookup"><span data-stu-id="e4d13-330">You should now have a basic understanding of the building blocks of a data-bound, .NET Framework application.</span></span> <span data-ttu-id="e4d13-331">Para más información sobre los modelos de programación y arquitectura de WPF, vea los temas siguientes:</span><span class="sxs-lookup"><span data-stu-id="e4d13-331">For more information about the WPF architecture and programming models, see the following topics:</span></span>

- [<span data-ttu-id="e4d13-332">Arquitectura de WPF</span><span class="sxs-lookup"><span data-stu-id="e4d13-332">WPF architecture</span></span>](../advanced/wpf-architecture.md)
- [<span data-ttu-id="e4d13-333">Información general XAML (WPF)</span><span class="sxs-lookup"><span data-stu-id="e4d13-333">XAML overview (WPF)</span></span>](../advanced/xaml-overview-wpf.md)
- [<span data-ttu-id="e4d13-334">Información general sobre las propiedades de dependencia</span><span class="sxs-lookup"><span data-stu-id="e4d13-334">Dependency properties overview</span></span>](../advanced/dependency-properties-overview.md)
- [<span data-ttu-id="e4d13-335">Diseño</span><span class="sxs-lookup"><span data-stu-id="e4d13-335">Layout</span></span>](../advanced/layout.md)

<span data-ttu-id="e4d13-336">Para más información sobre la creación de aplicaciones, vea los temas siguientes:</span><span class="sxs-lookup"><span data-stu-id="e4d13-336">For more information about creating applications, see the following topics:</span></span>

- [<span data-ttu-id="e4d13-337">Desarrollo de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="e4d13-337">Application development</span></span>](../app-development/index.md)
- [<span data-ttu-id="e4d13-338">Controles</span><span class="sxs-lookup"><span data-stu-id="e4d13-338">Controls</span></span>](../controls/index.md)
- [<span data-ttu-id="e4d13-339">Información general sobre el enlace de datos</span><span class="sxs-lookup"><span data-stu-id="e4d13-339">Data binding overview</span></span>](../data/data-binding-overview.md)
- [<span data-ttu-id="e4d13-340">Gráficos y multimedia</span><span class="sxs-lookup"><span data-stu-id="e4d13-340">Graphics and multimedia</span></span>](../graphics-multimedia/index.md)
- [<span data-ttu-id="e4d13-341">Documentos en WPF</span><span class="sxs-lookup"><span data-stu-id="e4d13-341">Documents in WPF</span></span>](../advanced/documents-in-wpf.md)

## <a name="see-also"></a><span data-ttu-id="e4d13-342">Vea también</span><span class="sxs-lookup"><span data-stu-id="e4d13-342">See also</span></span>

- [<span data-ttu-id="e4d13-343">Información general sobre</span><span class="sxs-lookup"><span data-stu-id="e4d13-343">Panels overview</span></span>](../controls/panels-overview.md)
- [<span data-ttu-id="e4d13-344">Información general sobre plantillas de datos</span><span class="sxs-lookup"><span data-stu-id="e4d13-344">Data templating overview</span></span>](../data/data-templating-overview.md)
- [<span data-ttu-id="e4d13-345">Crear una aplicación de WPF</span><span class="sxs-lookup"><span data-stu-id="e4d13-345">Build a WPF application</span></span>](../app-development/building-a-wpf-application-wpf.md)
- [<span data-ttu-id="e4d13-346">Estilos y plantillas</span><span class="sxs-lookup"><span data-stu-id="e4d13-346">Styles and templates</span></span>](../controls/styles-and-templates.md)
