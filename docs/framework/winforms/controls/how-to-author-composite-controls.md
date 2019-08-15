---
title: Procedimiento para crear controles compuestos
ms.date: 03/30/2017
helpviewer_keywords:
- UserControl class [Windows Forms], creating composite controls
- user controls [Windows Forms], creating
- user controls [Windows Forms], inheriting from
- composite controls [Windows Forms], creating
ms.assetid: 79c9cf05-5ab6-4a18-886d-88a64748b098
ms.openlocfilehash: 7b0ee8efa62175e2ced2a810ca6dd76e8adc103b
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/15/2019
ms.locfileid: "69039894"
---
# <a name="how-to-author-composite-controls"></a><span data-ttu-id="93a08-102">Procedimiento para crear controles compuestos</span><span class="sxs-lookup"><span data-stu-id="93a08-102">How to: Author Composite Controls</span></span>

<span data-ttu-id="93a08-103">Los controles compuestos pueden emplearse de muchas formas.</span><span class="sxs-lookup"><span data-stu-id="93a08-103">Composite controls can be employed in many ways.</span></span> <span data-ttu-id="93a08-104">Puede crearlos como parte de un proyecto de aplicación de escritorio de Windows y utilizarlos solo en formularios del proyecto.</span><span class="sxs-lookup"><span data-stu-id="93a08-104">You can author them as part of a Windows desktop application project, and use them only on forms in the project.</span></span> <span data-ttu-id="93a08-105">También podría crearlos en un proyecto de Biblioteca de controles de Windows, compilar el proyecto en un ensamblado y utilizar los controles en otros proyectos.</span><span class="sxs-lookup"><span data-stu-id="93a08-105">Or you can author them in a Windows Control Library project, compile the project into an assembly, and use the controls in other projects.</span></span> <span data-ttu-id="93a08-106">Incluso puede heredar de ellos y utilizar la herencia visual para personalizarlos rápidamente para fines especiales.</span><span class="sxs-lookup"><span data-stu-id="93a08-106">You can even inherit from them and use visual inheritance to customize them quickly for special purposes.</span></span>

> [!NOTE]
> <span data-ttu-id="93a08-107">Si desea crear un control compuesto para utilizarlo en los formularios Web Forms, vea [Desarrollar controles de servidor ASP.NET personalizados](https://docs.microsoft.com/previous-versions/aspnet/zt27tfhy(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="93a08-107">If you want to author a composite control to use on Web Forms, see [Developing Custom ASP.NET Server Controls](https://docs.microsoft.com/previous-versions/aspnet/zt27tfhy(v=vs.100)).</span></span>

## <a name="to-author-a-composite-control"></a><span data-ttu-id="93a08-108">Para crear un control compuesto</span><span class="sxs-lookup"><span data-stu-id="93a08-108">To author a composite control</span></span>

1. <span data-ttu-id="93a08-109">En Visual Studio, cree un nuevo proyecto de **aplicación** para `DemoControlHost`Windows denominado.</span><span class="sxs-lookup"><span data-stu-id="93a08-109">In Visual Studio, create a new **Windows Application** project called `DemoControlHost`.</span></span>

2. <span data-ttu-id="93a08-110">En el menú **Proyecto** , haga clic en **Agregar control de usuario**.</span><span class="sxs-lookup"><span data-stu-id="93a08-110">On the **Project** menu, click **Add User Control**.</span></span>

3. <span data-ttu-id="93a08-111">En el cuadro de diálogo **Agregar nuevo elemento**, dé al archivo de clase (archivo .vb o .cs) el nombre que desea para el control compuesto.</span><span class="sxs-lookup"><span data-stu-id="93a08-111">In the **Add New Item** dialog box, give the class file (.vb or .cs file) the name you want the composite control to have.</span></span>

4. <span data-ttu-id="93a08-112">Seleccione el botón **Agregar** para crear el archivo de clase para el control compuesto.</span><span class="sxs-lookup"><span data-stu-id="93a08-112">Select the **Add** button to create the class file for the composite control.</span></span>

5. <span data-ttu-id="93a08-113">Agregue controles del **Cuadro de herramientas** a la superficie del control compuesto.</span><span class="sxs-lookup"><span data-stu-id="93a08-113">Add controls from the **Toolbox** to the composite control surface.</span></span>

6. <span data-ttu-id="93a08-114">Escriba código en los procedimientos de evento para controlar los eventos que produzca el control compuesto o sus controles constituyentes.</span><span class="sxs-lookup"><span data-stu-id="93a08-114">Place code in event procedures, to handle events raised by the composite control or by its constituent controls.</span></span>

7. <span data-ttu-id="93a08-115">Cierre el diseñador para el control compuesto y guarde el archivo cuando se le indique.</span><span class="sxs-lookup"><span data-stu-id="93a08-115">Close the designer for the composite control, and save the file when you are prompted.</span></span>

8. <span data-ttu-id="93a08-116">En el menú **Compilar** , haga clic en **Compilar solución**.</span><span class="sxs-lookup"><span data-stu-id="93a08-116">On the **Build** menu, click **Build Solution**.</span></span>

     <span data-ttu-id="93a08-117">Para que los controles personalizados aparezcan en el **Cuadro de herramientas**, deberá compilar el proyecto.</span><span class="sxs-lookup"><span data-stu-id="93a08-117">The project must be built in order for custom controls to appear in the **Toolbox**.</span></span>

9. <span data-ttu-id="93a08-118">Use la pestaña **DemoControlHost** del **Cuadro de herramientas** para agregar instancias del control a `Form1`.</span><span class="sxs-lookup"><span data-stu-id="93a08-118">Use the **DemoControlHost** tab of the **Toolbox** to add instances of your control to `Form1`.</span></span>

## <a name="to-author-a-control-class-library"></a><span data-ttu-id="93a08-119">Para crear una biblioteca de clases de controles</span><span class="sxs-lookup"><span data-stu-id="93a08-119">To author a control class library</span></span>

1. <span data-ttu-id="93a08-120">Abra un nuevo proyecto de tipo **Biblioteca de controles de Windows**.</span><span class="sxs-lookup"><span data-stu-id="93a08-120">Open a new **Windows Control Library** project.</span></span>

     <span data-ttu-id="93a08-121">De forma predeterminada, el proyecto contiene un control compuesto.</span><span class="sxs-lookup"><span data-stu-id="93a08-121">By default, the project contains a composite control.</span></span>

2. <span data-ttu-id="93a08-122">Agregue controles y código como se describió en el procedimiento anterior.</span><span class="sxs-lookup"><span data-stu-id="93a08-122">Add controls and code as described in the procedure above.</span></span>

3. <span data-ttu-id="93a08-123">Elija un control cuyas clases de herencia no desee que cambien y establezca la propiedad **Modifiers** de este control en **Private**.</span><span class="sxs-lookup"><span data-stu-id="93a08-123">Choose a control you do not want inheriting classes to change, and set the **Modifiers** property of this control to **Private**.</span></span>

4. <span data-ttu-id="93a08-124">Compile el archivo DLL.</span><span class="sxs-lookup"><span data-stu-id="93a08-124">Build the DLL.</span></span>

## <a name="to-inherit-from-a-composite-control-in-a-control-class-library"></a><span data-ttu-id="93a08-125">Para heredar de un control compuesto de una biblioteca de clases de controles</span><span class="sxs-lookup"><span data-stu-id="93a08-125">To inherit from a composite control in a control class library</span></span>

1. <span data-ttu-id="93a08-126">En el menú **Archivo**, seleccione **Agregar** y **Nuevo proyecto** para agregar un nuevo proyecto **Aplicación Windows** a la solución.</span><span class="sxs-lookup"><span data-stu-id="93a08-126">On the **File** menu, point to **Add** and select **New Project** to add a new **Windows Application** project to the solution.</span></span>

2. <span data-ttu-id="93a08-127">En el **Explorador de soluciones**, haga clic con el botón derecho en la carpeta **Referencias** del nuevo proyecto y elija **Agregar referencia** para abrir el cuadro de diálogo **Agregar referencia**.</span><span class="sxs-lookup"><span data-stu-id="93a08-127">In **Solution Explorer**, right-click the **References** folder for the new project and choose **Add Reference** to open the **Add Reference** dialog box.</span></span>

3. <span data-ttu-id="93a08-128">Seleccione la pestaña **Proyectos** y haga doble clic en el proyecto de Biblioteca de controles.</span><span class="sxs-lookup"><span data-stu-id="93a08-128">Select the **Projects** tab and double-click your control library project.</span></span>

4. <span data-ttu-id="93a08-129">En el menú **Compilar** , haga clic en **Compilar solución**.</span><span class="sxs-lookup"><span data-stu-id="93a08-129">On the **Build** menu, click **Build Solution**.</span></span>

5. <span data-ttu-id="93a08-130">En el **Explorador de soluciones**, haga clic con el botón derecho en el proyecto de Biblioteca de controles y elija **Agregar nuevo elemento** en el menú contextual.</span><span class="sxs-lookup"><span data-stu-id="93a08-130">In **Solution Explorer**, right-click your control library project and select **Add New Item** from the shortcut menu.</span></span>

6. <span data-ttu-id="93a08-131">Seleccione la plantilla **Control de usuario heredado** en el cuadro de diálogo **Agregar nuevo elemento**.</span><span class="sxs-lookup"><span data-stu-id="93a08-131">Select the **Inherited User Control** template from the **Add New Item** dialog box.</span></span>

7. <span data-ttu-id="93a08-132">En el cuadro de diálogo **Selector de herencia**, haga doble clic en el control del que desea heredar.</span><span class="sxs-lookup"><span data-stu-id="93a08-132">In the **Inheritance Picker** dialog box, double-click the control you want to inherit from.</span></span>

     <span data-ttu-id="93a08-133">Se agrega un nuevo control al proyecto.</span><span class="sxs-lookup"><span data-stu-id="93a08-133">A new control is added to your project.</span></span>

8. <span data-ttu-id="93a08-134">Abra el diseñador visual para el nuevo control y agregue controles constituyentes adicionales.</span><span class="sxs-lookup"><span data-stu-id="93a08-134">Open the visual designer for the new control and add additional constituent controls.</span></span>

     <span data-ttu-id="93a08-135">Puede ver los controles constituyentes heredados del control de usuario en la DLL, así como alterar las propiedades de aquellos controles cuya propiedad **Modifiers** sea **Public**.</span><span class="sxs-lookup"><span data-stu-id="93a08-135">You can see the constituent controls that were inherited from the composite control in your DLL, and you can alter the properties of controls whose **Modifiers** property is **Public**.</span></span> <span data-ttu-id="93a08-136">En cambio, no puede cambiar las propiedades del control cuya propiedad **Modifiers** sea **Private**.</span><span class="sxs-lookup"><span data-stu-id="93a08-136">You cannot change the properties of the control whose **Modifiers** property is **Private**.</span></span>

## <a name="see-also"></a><span data-ttu-id="93a08-137">Vea también</span><span class="sxs-lookup"><span data-stu-id="93a08-137">See also</span></span>

- [<span data-ttu-id="93a08-138">Tutorial: Crear un control compuesto con Visual Basic</span><span class="sxs-lookup"><span data-stu-id="93a08-138">Walkthrough: Authoring a Composite Control with Visual Basic</span></span>](walkthrough-authoring-a-composite-control-with-visual-basic.md)
- [<span data-ttu-id="93a08-139">Tutorial: Crear un control compuesto con VisualC#</span><span class="sxs-lookup"><span data-stu-id="93a08-139">Walkthrough: Authoring a Composite Control with Visual C#</span></span>](walkthrough-authoring-a-composite-control-with-visual-csharp.md)
- [<span data-ttu-id="93a08-140">Tutorial: Heredar de un control Windows Forms con Visual Basic</span><span class="sxs-lookup"><span data-stu-id="93a08-140">Walkthrough: Inheriting from a Windows Forms Control with Visual Basic</span></span>](walkthrough-inheriting-from-a-windows-forms-control-with-visual-basic.md)
- [<span data-ttu-id="93a08-141">Tutorial: Heredar de un control Windows Forms con VisualC#</span><span class="sxs-lookup"><span data-stu-id="93a08-141">Walkthrough: Inheriting from a Windows Forms Control with Visual C#</span></span>](walkthrough-inheriting-from-a-windows-forms-control-with-visual-csharp.md)
- [<span data-ttu-id="93a08-142">Recomendaciones sobre tipos de controles</span><span class="sxs-lookup"><span data-stu-id="93a08-142">Control Type Recommendations</span></span>](control-type-recommendations.md)
- [<span data-ttu-id="93a08-143">Cómo: Controles de autor para Windows Forms</span><span class="sxs-lookup"><span data-stu-id="93a08-143">How to: Author Controls for Windows Forms</span></span>](how-to-author-controls-for-windows-forms.md)
- [<span data-ttu-id="93a08-144">Variedades de controles personalizados</span><span class="sxs-lookup"><span data-stu-id="93a08-144">Varieties of Custom Controls</span></span>](varieties-of-custom-controls.md)
