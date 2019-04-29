---
title: 'Tutorial: Heredar de un control de formularios Windows Forms con Visual C#'
ms.date: 03/30/2017
helpviewer_keywords:
- inheritance [Windows Forms], custom controls
- inheritance [Windows Forms], control
- Windows Forms controls, inheritance
- inheritance [Windows Forms], walkthroughs
- custom controls [Windows Forms], inheritance
ms.assetid: 09476da0-8d4c-4a4c-b969-649519dfb438
ms.openlocfilehash: cafd8685f34537f8efb372967dc45682afbe8fa0
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61792241"
---
# <a name="walkthrough-inheriting-from-a-windows-forms-control-with-visual-c"></a><span data-ttu-id="6f0ed-102">Tutorial: Heredar de un Control de Windows Forms con Visual c#\#</span><span class="sxs-lookup"><span data-stu-id="6f0ed-102">Walkthrough: Inheriting from a Windows Forms Control with Visual C\#</span></span>
<span data-ttu-id="6f0ed-103">Con [!INCLUDE[csprcslong](../../../../includes/csprcslong-md.md)], puede crear controles personalizados eficaces mediante *herencia*.</span><span class="sxs-lookup"><span data-stu-id="6f0ed-103">With [!INCLUDE[csprcslong](../../../../includes/csprcslong-md.md)], you can create powerful custom controls through *inheritance*.</span></span> <span data-ttu-id="6f0ed-104">A través de la herencia puede crear controles que conserven toda la funcionalidad inherente de controles de Windows Forms estándar y además incorporen funcionalidad personalizada.</span><span class="sxs-lookup"><span data-stu-id="6f0ed-104">Through inheritance you are able to create controls that retain all of the inherent functionality of standard Windows Forms controls but also incorporate custom functionality.</span></span> <span data-ttu-id="6f0ed-105">En este tutorial, creará un control heredado simple denominado `ValueButton`.</span><span class="sxs-lookup"><span data-stu-id="6f0ed-105">In this walkthrough, you will create a simple inherited control called `ValueButton`.</span></span> <span data-ttu-id="6f0ed-106">Este botón heredará funcionalidad de los formularios de Windows estándar <xref:System.Windows.Forms.Button> controlar y expondrá una propiedad personalizada denominada `ButtonValue`.</span><span class="sxs-lookup"><span data-stu-id="6f0ed-106">This button will inherit functionality from the standard Windows Forms <xref:System.Windows.Forms.Button> control, and will expose a custom property called `ButtonValue`.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6f0ed-107">Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos.</span><span class="sxs-lookup"><span data-stu-id="6f0ed-107">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="6f0ed-108">Para cambiar la configuración, elija la opción **Importar y exportar configuraciones** del menú **Herramientas** .</span><span class="sxs-lookup"><span data-stu-id="6f0ed-108">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="6f0ed-109">Para más información, vea [Personalizar el IDE de Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).</span><span class="sxs-lookup"><span data-stu-id="6f0ed-109">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
## <a name="creating-the-project"></a><span data-ttu-id="6f0ed-110">Crear el proyecto</span><span class="sxs-lookup"><span data-stu-id="6f0ed-110">Creating the Project</span></span>  
 <span data-ttu-id="6f0ed-111">Cuando cree un proyecto, especifique su nombre para establecer el espacio de nombres raíz, el nombre de ensamblado y el nombre del proyecto, y para asegurarse de que el componente predeterminado estará en el espacio de nombres correcto.</span><span class="sxs-lookup"><span data-stu-id="6f0ed-111">When you create a new project, you specify its name in order to set the root namespace, assembly name, and project name, and to ensure that the default component will be in the correct namespace.</span></span>  
  
#### <a name="to-create-the-valuebuttonlib-control-library-and-the-valuebutton-control"></a><span data-ttu-id="6f0ed-112">Para crear la biblioteca de controles ValueButtonLib y el control ValueButton</span><span class="sxs-lookup"><span data-stu-id="6f0ed-112">To create the ValueButtonLib control library and the ValueButton control</span></span>  
  
1. <span data-ttu-id="6f0ed-113">En el menú **Archivo**, elija **Nuevo** y haga clic en **Proyecto** para abrir el cuadro de diálogo **Nuevo proyecto**.</span><span class="sxs-lookup"><span data-stu-id="6f0ed-113">On the **File** menu, point to **New** and then click **Project** to open the **New Project** dialog box.</span></span>  
  
2. <span data-ttu-id="6f0ed-114">Seleccione el **biblioteca de controles de Windows Forms** plantilla de proyecto en la lista de proyectos de Visual C# y el tipo `ValueButtonLib` en el **nombre** cuadro.</span><span class="sxs-lookup"><span data-stu-id="6f0ed-114">Select the **Windows Forms Control Library** project template from the list of Visual C# Projects, and type `ValueButtonLib` in the **Name** box.</span></span>  
  
     <span data-ttu-id="6f0ed-115">El nombre del proyecto, `ValueButtonLib` también se asigna de forma predeterminada al espacio de nombres raíz.</span><span class="sxs-lookup"><span data-stu-id="6f0ed-115">The project name, `ValueButtonLib`, is also assigned to the root namespace by default.</span></span> <span data-ttu-id="6f0ed-116">El espacio de nombres raíz se utiliza para calificar los nombres de los componentes del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="6f0ed-116">The root namespace is used to qualify the names of components in the assembly.</span></span> <span data-ttu-id="6f0ed-117">Por ejemplo, si dos ensamblados proporcionan componentes denominados `ValueButton`, puede especificar su componente `ValueButton` mediante `ValueButtonLib.ValueButton`.</span><span class="sxs-lookup"><span data-stu-id="6f0ed-117">For example, if two assemblies provide components named `ValueButton`, you can specify your `ValueButton` component using `ValueButtonLib.ValueButton`.</span></span> <span data-ttu-id="6f0ed-118">Para más información, consulte [Espacios de nombres](../../../csharp/programming-guide/namespaces/index.md).</span><span class="sxs-lookup"><span data-stu-id="6f0ed-118">For more information, see [Namespaces](../../../csharp/programming-guide/namespaces/index.md).</span></span>  
  
3. <span data-ttu-id="6f0ed-119">En el **Explorador de soluciones**, haga clic con el botón derecho en **UserControl1.cs** y elija **Cambiar nombre** en el menú contextual.</span><span class="sxs-lookup"><span data-stu-id="6f0ed-119">In **Solution Explorer**, right-click **UserControl1.cs**, then choose **Rename** from the shortcut menu.</span></span> <span data-ttu-id="6f0ed-120">Cambie el nombre del archivo a `ValueButton.cs`.</span><span class="sxs-lookup"><span data-stu-id="6f0ed-120">Change the file name to `ValueButton.cs`.</span></span> <span data-ttu-id="6f0ed-121">Haga clic en el botón **Sí** cuando se le pregunte si desea cambiar el nombre de todas las referencias al elemento de código "`UserControl1`".</span><span class="sxs-lookup"><span data-stu-id="6f0ed-121">Click the **Yes** button when you are asked if you want to rename all references to the code element '`UserControl1`'.</span></span>  
  
4. <span data-ttu-id="6f0ed-122">En el **Explorador de soluciones**, haga clic con el botón derecho en **ValueButton.cs** y seleccione **Ver código**.</span><span class="sxs-lookup"><span data-stu-id="6f0ed-122">In **Solution Explorer**, right-click **ValueButton.cs** and select **View Code**.</span></span>  
  
5. <span data-ttu-id="6f0ed-123">Busque el `class` línea de la instrucción, `public partial class ValueButton`y cambie el tipo del que hereda este control de <xref:System.Windows.Forms.UserControl> a <xref:System.Windows.Forms.Button>.</span><span class="sxs-lookup"><span data-stu-id="6f0ed-123">Locate the `class` statement line, `public partial class ValueButton`, and change the type from which this control inherits from <xref:System.Windows.Forms.UserControl> to <xref:System.Windows.Forms.Button>.</span></span> <span data-ttu-id="6f0ed-124">Esto permite que el control heredado herede toda la funcionalidad de la <xref:System.Windows.Forms.Button> control.</span><span class="sxs-lookup"><span data-stu-id="6f0ed-124">This allows your inherited control to inherit all the functionality of the <xref:System.Windows.Forms.Button> control.</span></span>  
  
6. <span data-ttu-id="6f0ed-125">En el **Explorador de soluciones**, abra el nodo **ValueButton.cs** para mostrar el archivo de código generado por el diseñador, **ValueButton.Designer.cs**.</span><span class="sxs-lookup"><span data-stu-id="6f0ed-125">In **Solution Explorer**, open the **ValueButton.cs** node to display the designer-generated code file, **ValueButton.Designer.cs**.</span></span> <span data-ttu-id="6f0ed-126">Abra este archivo en el **Editor de código**.</span><span class="sxs-lookup"><span data-stu-id="6f0ed-126">Open this file in the **Code Editor**.</span></span>  
  
7. <span data-ttu-id="6f0ed-127">Busque el `InitializeComponent` método y quite la línea que asigna el <xref:System.Windows.Forms.ContainerControl.AutoScaleMode%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="6f0ed-127">Locate the `InitializeComponent` method and remove the line that assigns the <xref:System.Windows.Forms.ContainerControl.AutoScaleMode%2A> property.</span></span> <span data-ttu-id="6f0ed-128">Esta propiedad no existe en el <xref:System.Windows.Forms.Button> control.</span><span class="sxs-lookup"><span data-stu-id="6f0ed-128">This property does not exist in the <xref:System.Windows.Forms.Button> control.</span></span>  
  
8. <span data-ttu-id="6f0ed-129">En el menú **Archivo**, elija **Guardar todo** para guardar el proyecto.</span><span class="sxs-lookup"><span data-stu-id="6f0ed-129">From the **File** menu, choose **Save All** to save the project.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="6f0ed-130">Ya no hay disponible ningún diseñador visual.</span><span class="sxs-lookup"><span data-stu-id="6f0ed-130">A visual designer is no longer available.</span></span> <span data-ttu-id="6f0ed-131">Dado que el <xref:System.Windows.Forms.Button> control realiza su propia representación, no puede modificar su apariencia en el diseñador.</span><span class="sxs-lookup"><span data-stu-id="6f0ed-131">Because the <xref:System.Windows.Forms.Button> control does its own painting, you are unable to modify its appearance in the designer.</span></span> <span data-ttu-id="6f0ed-132">Su representación visual será exactamente el mismo que el de la clase que hereda (es decir, <xref:System.Windows.Forms.Button>) a menos que modifique en el código.</span><span class="sxs-lookup"><span data-stu-id="6f0ed-132">Its visual representation will be exactly the same as that of the class it inherits from (that is, <xref:System.Windows.Forms.Button>) unless modified in the code.</span></span> <span data-ttu-id="6f0ed-133">Todavía puede agregar componentes, que no tienen ningún elemento de interfaz de usuario, a la superficie de diseño.</span><span class="sxs-lookup"><span data-stu-id="6f0ed-133">You can still add components, which have no UI elements, to the design surface.</span></span>  
  
## <a name="adding-a-property-to-your-inherited-control"></a><span data-ttu-id="6f0ed-134">Agregar una propiedad al control heredado</span><span class="sxs-lookup"><span data-stu-id="6f0ed-134">Adding a Property to Your Inherited Control</span></span>  
 <span data-ttu-id="6f0ed-135">Un uso posible de los controles de Windows Forms heredados es la creación de controles que sean idénticos en apariencia y comportamiento a los controles de Windows Forms estándar, pero que expongan propiedades personalizadas.</span><span class="sxs-lookup"><span data-stu-id="6f0ed-135">One possible use of inherited Windows Forms controls is the creation of controls that are identical in look and feel of standard Windows Forms controls, but expose custom properties.</span></span> <span data-ttu-id="6f0ed-136">En esta sección, agregará una propiedad denominada `ButtonValue` al control.</span><span class="sxs-lookup"><span data-stu-id="6f0ed-136">In this section, you will add a property called `ButtonValue` to your control.</span></span>  
  
#### <a name="to-add-the-value-property"></a><span data-ttu-id="6f0ed-137">Para agregar la propiedad Value</span><span class="sxs-lookup"><span data-stu-id="6f0ed-137">To add the Value property</span></span>  
  
1. <span data-ttu-id="6f0ed-138">En el **Explorador de soluciones**, haga clic con el botón derecho en **ValueButton.cs** y haga clic en **Ver código** en el menú contextual.</span><span class="sxs-lookup"><span data-stu-id="6f0ed-138">In **Solution Explorer**, right-click **ValueButton.cs**, and then click **View Code** from the shortcut menu.</span></span>  
  
2. <span data-ttu-id="6f0ed-139">Busque la instrucción `class`.</span><span class="sxs-lookup"><span data-stu-id="6f0ed-139">Locate the `class` statement.</span></span> <span data-ttu-id="6f0ed-140">Inmediatamente detrás de `{`, escriba el siguiente código:</span><span class="sxs-lookup"><span data-stu-id="6f0ed-140">Immediately after the `{`, type the following code:</span></span>  
  
    ```csharp  
    // Creates the private variable that will store the value of your   
    // property.  
    private int varValue;  
    // Declares the property.  
    public int ButtonValue  
    {  
       // Sets the method for retrieving the value of your property.  
       get  
       {  
          return varValue;  
       }  
       // Sets the method for setting the value of your property.  
       set  
       {  
          varValue = value;  
       }  
    }  
    ```  
  
     <span data-ttu-id="6f0ed-141">Este código establece los métodos por los que se almacena y se recupera la propiedad `ButtonValue`.</span><span class="sxs-lookup"><span data-stu-id="6f0ed-141">This code sets the methods by which the `ButtonValue` property is stored and retrieved.</span></span> <span data-ttu-id="6f0ed-142">La instrucción `get` establece el valor devuelto en el valor que se almacena en la variable privada `varValue`, y la instrucción `set` establece el valor de la variable privada mediante la palabra clave `value`.</span><span class="sxs-lookup"><span data-stu-id="6f0ed-142">The `get` statement sets the value returned to the value that is stored in the private variable `varValue`, and the `set` statement sets the value of the private variable by use of the `value` keyword.</span></span>  
  
3. <span data-ttu-id="6f0ed-143">En el menú **Archivo**, elija **Guardar todo** para guardar el proyecto.</span><span class="sxs-lookup"><span data-stu-id="6f0ed-143">From the **File** menu, choose **Save All** to save the project.</span></span>  
  
## <a name="testing-your-control"></a><span data-ttu-id="6f0ed-144">Probar el control</span><span class="sxs-lookup"><span data-stu-id="6f0ed-144">Testing Your Control</span></span>  
 <span data-ttu-id="6f0ed-145">Los controles no son proyectos independientes; deben hospedarse en un contenedor.</span><span class="sxs-lookup"><span data-stu-id="6f0ed-145">Controls are not stand-alone projects; they must be hosted in a container.</span></span> <span data-ttu-id="6f0ed-146">Para probar el control, debe proporcionar un proyecto de prueba donde pueda ejecutarse.</span><span class="sxs-lookup"><span data-stu-id="6f0ed-146">In order to test your control, you must provide a test project for it to run in.</span></span> <span data-ttu-id="6f0ed-147">También debe hacer que el control resulte accesible al proyecto de prueba al compilarlo.</span><span class="sxs-lookup"><span data-stu-id="6f0ed-147">You must also make your control accessible to the test project by building (compiling) it.</span></span> <span data-ttu-id="6f0ed-148">En esta sección, compilará el control y lo probará en Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="6f0ed-148">In this section, you will build your control and test it in a Windows Form.</span></span>  
  
#### <a name="to-build-your-control"></a><span data-ttu-id="6f0ed-149">Para compilar el control</span><span class="sxs-lookup"><span data-stu-id="6f0ed-149">To build your control</span></span>  
  
1. <span data-ttu-id="6f0ed-150">En el menú **Compilar** , haga clic en **Compilar solución**.</span><span class="sxs-lookup"><span data-stu-id="6f0ed-150">On the **Build** menu, click **Build Solution**.</span></span>  
  
     <span data-ttu-id="6f0ed-151">La compilación debería completarse correctamente sin advertencias ni errores del compilador.</span><span class="sxs-lookup"><span data-stu-id="6f0ed-151">The build should be successful with no compiler errors or warnings.</span></span>  
  
#### <a name="to-create-a-test-project"></a><span data-ttu-id="6f0ed-152">Para crear un proyecto de prueba</span><span class="sxs-lookup"><span data-stu-id="6f0ed-152">To create a test project</span></span>  
  
1. <span data-ttu-id="6f0ed-153">En el menú **Archivo**, elija **Agregar** y haga clic en **Nuevo proyecto** para abrir el cuadro de diálogo **Agregar nuevo proyecto**.</span><span class="sxs-lookup"><span data-stu-id="6f0ed-153">On the **File** menu, point to **Add** and then click **New Project** to open the **Add New Project** dialog box.</span></span>  
  
2. <span data-ttu-id="6f0ed-154">Seleccione el nodo **Windows**, debajo del nodo **Visual C#**, y haga clic en **Aplicación de Windows Forms**.</span><span class="sxs-lookup"><span data-stu-id="6f0ed-154">Select the **Windows** node, beneath the **Visual C#** node, and click **Windows Forms Application**.</span></span>  
  
3. <span data-ttu-id="6f0ed-155">En el cuadro **Nombre**, escriba `Test`.</span><span class="sxs-lookup"><span data-stu-id="6f0ed-155">In the **Name** box, type `Test`.</span></span>  
  
4. <span data-ttu-id="6f0ed-156">En el **Explorador de soluciones**, haga clic con el botón derecho en el nodo **Referencias** para su proyecto de prueba y seleccione **Agregar referencia** en el menú contextual para mostrar el cuadro de diálogo **Agregar referencia**.</span><span class="sxs-lookup"><span data-stu-id="6f0ed-156">In **Solution Explorer**, right-click the **References** node for your test project, then select **Add Reference** from the shortcut menu to display the **Add Reference** dialog box.</span></span>  
  
5. <span data-ttu-id="6f0ed-157">Haga clic en la pestaña etiquetada como **Proyectos**.</span><span class="sxs-lookup"><span data-stu-id="6f0ed-157">Click the tab labeled **Projects**.</span></span> <span data-ttu-id="6f0ed-158">El proyecto `ValueButtonLib` aparecerá bajo **Nombre de proyecto**.</span><span class="sxs-lookup"><span data-stu-id="6f0ed-158">Your `ValueButtonLib` project will be listed under **Project Name**.</span></span> <span data-ttu-id="6f0ed-159">Haga doble clic en el proyecto para agregar la referencia al proyecto de prueba.</span><span class="sxs-lookup"><span data-stu-id="6f0ed-159">Double-click the project to add the reference to the test project.</span></span>  
  
6. <span data-ttu-id="6f0ed-160">En el **Explorador de soluciones**, haga clic con el botón derecho en **Probar** y seleccione **Compilar**.</span><span class="sxs-lookup"><span data-stu-id="6f0ed-160">In **Solution Explorer,** right-click **Test** and select **Build**.</span></span>  
  
#### <a name="to-add-your-control-to-the-form"></a><span data-ttu-id="6f0ed-161">Para agregar el control al formulario</span><span class="sxs-lookup"><span data-stu-id="6f0ed-161">To add your control to the form</span></span>  
  
1. <span data-ttu-id="6f0ed-162">En el **Explorador de soluciones**, haga clic con el botón derecho en **Form1.cs** y elija **Ver diseñador** en el menú contextual.</span><span class="sxs-lookup"><span data-stu-id="6f0ed-162">In **Solution Explorer**, right-click **Form1.cs** and choose **View Designer** from the shortcut menu.</span></span>  
  
2. <span data-ttu-id="6f0ed-163">En el **cuadro de herramientas**, haga clic en **Componentes de ValueButtonLib**.</span><span class="sxs-lookup"><span data-stu-id="6f0ed-163">In the **Toolbox**, click **ValueButtonLib Components**.</span></span> <span data-ttu-id="6f0ed-164">Haga doble clic en **ValueButton**.</span><span class="sxs-lookup"><span data-stu-id="6f0ed-164">Double-click **ValueButton**.</span></span>  
  
     <span data-ttu-id="6f0ed-165">Aparece un componente **ValueButton** en el formulario.</span><span class="sxs-lookup"><span data-stu-id="6f0ed-165">A **ValueButton** appears on the form.</span></span>  
  
3. <span data-ttu-id="6f0ed-166">Haga clic con el botón derecho en **ValueButton** y seleccione **Propiedades** en el menú contextual.</span><span class="sxs-lookup"><span data-stu-id="6f0ed-166">Right-click the **ValueButton** and select **Properties** from the shortcut menu.</span></span>  
  
4. <span data-ttu-id="6f0ed-167">En la ventana **Propiedades**, examine las propiedades de este control.</span><span class="sxs-lookup"><span data-stu-id="6f0ed-167">In the **Properties** window, examine the properties of this control.</span></span> <span data-ttu-id="6f0ed-168">Observe que son idénticas a las propiedades expuestas por un botón estándar, excepto en que hay una propiedad adicional, `ButtonValue`.</span><span class="sxs-lookup"><span data-stu-id="6f0ed-168">Note that they are identical to the properties exposed by a standard button, except that there is an additional property, `ButtonValue`.</span></span>  
  
5. <span data-ttu-id="6f0ed-169">Establezca la propiedad `ButtonValue` en `5`.</span><span class="sxs-lookup"><span data-stu-id="6f0ed-169">Set the `ButtonValue` property to `5`.</span></span>  
  
6. <span data-ttu-id="6f0ed-170">En el **todos los formularios de Windows** pestaña de la **cuadro de herramientas**, haga doble clic en **etiqueta** para agregar un <xref:System.Windows.Forms.Label> al formulario.</span><span class="sxs-lookup"><span data-stu-id="6f0ed-170">In the **All Windows Forms** tab of the **Toolbox**, double-click **Label** to add a <xref:System.Windows.Forms.Label> control to your form.</span></span>  
  
7. <span data-ttu-id="6f0ed-171">Mueva la etiqueta al centro del formulario.</span><span class="sxs-lookup"><span data-stu-id="6f0ed-171">Relocate the label to the center of the form.</span></span>  
  
8. <span data-ttu-id="6f0ed-172">Haga doble clic en `valueButton1`.</span><span class="sxs-lookup"><span data-stu-id="6f0ed-172">Double-click `valueButton1`.</span></span>  
  
     <span data-ttu-id="6f0ed-173">Se abre el **Editor de código** en el evento `valueButton1_Click`.</span><span class="sxs-lookup"><span data-stu-id="6f0ed-173">The **Code Editor** opens to the `valueButton1_Click` event.</span></span>  
  
9. <span data-ttu-id="6f0ed-174">Inserte la siguiente línea de código.</span><span class="sxs-lookup"><span data-stu-id="6f0ed-174">Insert the following line of code.</span></span>  
  
    ```csharp  
    label1.Text = valueButton1.ButtonValue.ToString();  
    ```  
  
10. <span data-ttu-id="6f0ed-175">En el **Explorador de soluciones**, haga clic con el botón derecho en **Probar** y elija **Establecer como proyecto de inicio** en el menú contextual.</span><span class="sxs-lookup"><span data-stu-id="6f0ed-175">In **Solution Explorer**, right-click **Test**, and choose **Set as Startup Project** from the shortcut menu.</span></span>  
  
11. <span data-ttu-id="6f0ed-176">En el menú **Depurar**, seleccione **Iniciar depuración**.</span><span class="sxs-lookup"><span data-stu-id="6f0ed-176">From the **Debug** menu, select **Start Debugging**.</span></span>  
  
     <span data-ttu-id="6f0ed-177">Aparece `Form1`.</span><span class="sxs-lookup"><span data-stu-id="6f0ed-177">`Form1` appears.</span></span>  
  
12. <span data-ttu-id="6f0ed-178">Haga clic en `valueButton1`.</span><span class="sxs-lookup"><span data-stu-id="6f0ed-178">Click `valueButton1`.</span></span>  
  
     <span data-ttu-id="6f0ed-179">Se muestra el número "5" en `label1`, lo que demuestra que la propiedad `ButtonValue` del control heredado se ha pasado a `label1` a través del método `valueButton1_Click`.</span><span class="sxs-lookup"><span data-stu-id="6f0ed-179">The numeral '5' is displayed in `label1`, demonstrating that the `ButtonValue` property of your inherited control has been passed to `label1` through the `valueButton1_Click` method.</span></span> <span data-ttu-id="6f0ed-180">Por lo tanto, su control `ValueButton` hereda toda la funcionalidad del botón estándar de Windows Forms, pero expone una propiedad personalizada adicional.</span><span class="sxs-lookup"><span data-stu-id="6f0ed-180">Thus your `ValueButton` control inherits all the functionality of the standard Windows Forms button, but exposes an additional, custom property.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6f0ed-181">Vea también</span><span class="sxs-lookup"><span data-stu-id="6f0ed-181">See also</span></span>

- [<span data-ttu-id="6f0ed-182">Cómo: Mostrar un Control en la elija el cuadro de diálogo de elementos de cuadro de herramientas</span><span class="sxs-lookup"><span data-stu-id="6f0ed-182">How to: Display a Control in the Choose Toolbox Items Dialog Box</span></span>](how-to-display-a-control-in-the-choose-toolbox-items-dialog-box.md)
- [<span data-ttu-id="6f0ed-183">Tutorial: Crear un Control compuesto con VisualC#</span><span class="sxs-lookup"><span data-stu-id="6f0ed-183">Walkthrough: Authoring a Composite Control with Visual C#</span></span>](walkthrough-authoring-a-composite-control-with-visual-csharp.md)
