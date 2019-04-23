---
title: Procedimiento para enlazar controles de formularios Windows Forms con el componente BindingSource mediante el diseñador
ms.date: 03/30/2017
helpviewer_keywords:
- controls [Windows Forms], binding
- BindingSource component [Windows Forms], binding controls
- data binding [Windows Forms], BindingSource component
ms.assetid: 391ae170-de5c-40f8-8233-91cb2ee4683a
ms.openlocfilehash: a4f87303954494e8e32d32e68fb3f1244f25680a
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59304563"
---
# <a name="how-to-bind-windows-forms-controls-with-the-bindingsource-component-using-the-designer"></a><span data-ttu-id="8007a-102">Procedimiento para enlazar controles de formularios Windows Forms con el componente BindingSource mediante el diseñador</span><span class="sxs-lookup"><span data-stu-id="8007a-102">How to: Bind Windows Forms Controls with the BindingSource Component Using the Designer</span></span>
<span data-ttu-id="8007a-103">Una vez que haya agregado los controles al formulario y determina la interfaz de usuario para la aplicación, puede enlazar los controles a un origen de datos, por lo que, en tiempo de ejecución, los usuarios pueden modificar y guardar los datos relacionados con la aplicación.</span><span class="sxs-lookup"><span data-stu-id="8007a-103">After you have added controls to your form and determined the user interface for your application, you can bind the controls to a data source, so that, at run time, users can alter and save data related to the application.</span></span>  
  
 <span data-ttu-id="8007a-104">Enlazar un control o una serie de controles en Windows Forms se consigue más fácilmente mediante el <xref:System.Windows.Forms.BindingSource> control como un puente entre los controles del formulario y el origen de datos.</span><span class="sxs-lookup"><span data-stu-id="8007a-104">Binding a control or series of controls in Windows Forms is most easily accomplished using the <xref:System.Windows.Forms.BindingSource> control as a bridge between the controls on the form and the data source.</span></span>  
  
 <span data-ttu-id="8007a-105">Uno o varios controles en un formulario que se pueden enlazar a datos; en el procedimiento siguiente, un <xref:System.Windows.Forms.TextBox> control se enlaza a un origen de datos.</span><span class="sxs-lookup"><span data-stu-id="8007a-105">One or more controls on a form can be bound to data; in the following procedure, a <xref:System.Windows.Forms.TextBox> control is bound to a data source.</span></span>  
  
 <span data-ttu-id="8007a-106">Para completar el procedimiento, se supone que se enlazará a un origen de datos derivado de una base de datos.</span><span class="sxs-lookup"><span data-stu-id="8007a-106">To complete the procedure, it is assumed that you will bind to a data source derived from a database.</span></span> <span data-ttu-id="8007a-107">Para obtener más información sobre cómo crear orígenes de datos desde otros almacenes de datos, vea [agregar nuevos orígenes de datos](/visualstudio/data-tools/add-new-data-sources).</span><span class="sxs-lookup"><span data-stu-id="8007a-107">For more information on creating data sources from other stores of data, see [Add new data sources](/visualstudio/data-tools/add-new-data-sources).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8007a-108">Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos.</span><span class="sxs-lookup"><span data-stu-id="8007a-108">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="8007a-109">Para cambiar la configuración, elija la opción **Importar y exportar configuraciones** del menú **Herramientas** .</span><span class="sxs-lookup"><span data-stu-id="8007a-109">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="8007a-110">Para más información, vea [Personalizar el IDE de Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).</span><span class="sxs-lookup"><span data-stu-id="8007a-110">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-bind-a-control-at-design-time"></a><span data-ttu-id="8007a-111">Para enlazar un control en tiempo de diseño</span><span class="sxs-lookup"><span data-stu-id="8007a-111">To bind a control at design time</span></span>  
  
1. <span data-ttu-id="8007a-112">Arrastre un <xref:System.Windows.Forms.TextBox> control de sesión en el formulario.</span><span class="sxs-lookup"><span data-stu-id="8007a-112">Drag a <xref:System.Windows.Forms.TextBox> control on to the form.</span></span>  
  
2. <span data-ttu-id="8007a-113">En el **propiedades** ventana:</span><span class="sxs-lookup"><span data-stu-id="8007a-113">In the **Properties** window:</span></span>  
  
    1.  <span data-ttu-id="8007a-114">Expanda el **(DataBindings)** nodo.</span><span class="sxs-lookup"><span data-stu-id="8007a-114">Expand the **(DataBindings)** node.</span></span>  
  
    2.  <span data-ttu-id="8007a-115">Haga clic en la flecha situada junto a la <xref:System.Windows.Forms.TextBox.Text%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="8007a-115">Click the arrow next to the <xref:System.Windows.Forms.TextBox.Text%2A> property.</span></span>  
  
         <span data-ttu-id="8007a-116">El **DataSource** abre el editor de tipos de interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="8007a-116">The **DataSource** UI type editor opens.</span></span>  
  
         <span data-ttu-id="8007a-117">Si un origen de datos se ha configurado previamente para el proyecto o formulario, aparecerá.</span><span class="sxs-lookup"><span data-stu-id="8007a-117">If a data source has previously been configured for the project or form, it will appear.</span></span>  
  
3. <span data-ttu-id="8007a-118">Haga clic en **Agregar origen de datos del proyecto** para conectar con los datos y crear un origen de datos.</span><span class="sxs-lookup"><span data-stu-id="8007a-118">Click **Add Project Data Source** to connect to data and create a data source.</span></span>  
  
4. <span data-ttu-id="8007a-119">En la página principal del **Asistente para la configuración de orígenes de datos**, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="8007a-119">On the **Data Source Configuration Wizard** welcome page, click **Next**.</span></span>  
  
5. <span data-ttu-id="8007a-120">En el **elegir un tipo de origen de datos** página, seleccione **base de datos**.</span><span class="sxs-lookup"><span data-stu-id="8007a-120">On the **Choose a Data Source Type** page, select **Database**.</span></span>  
  
6. <span data-ttu-id="8007a-121">En el **elegir la conexión de datos** , seleccione una conexión de datos de la lista de conexiones disponibles.</span><span class="sxs-lookup"><span data-stu-id="8007a-121">On the **Choose Your Data Connection** page, select a data connection from the list of available connections.</span></span> <span data-ttu-id="8007a-122">Si la conexión de datos deseada no está disponible seleccione **nueva conexión** para crear una nueva conexión de datos.</span><span class="sxs-lookup"><span data-stu-id="8007a-122">If your desired data connection is not available select **New Connection** to create a new data connection.</span></span>  
  
7. <span data-ttu-id="8007a-123">Seleccione **Sí, guardar la conexión** para guardar la cadena de conexión en el archivo de configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="8007a-123">Select **Yes, save the connection** to save the connection string in the application configuration file.</span></span>  
  
8. <span data-ttu-id="8007a-124">Seleccione los objetos de base de datos que va a traer a su aplicación.</span><span class="sxs-lookup"><span data-stu-id="8007a-124">Select the database objects to bring into your application.</span></span> <span data-ttu-id="8007a-125">En este caso, seleccione un campo de una tabla que le gustaría el <xref:System.Windows.Forms.TextBox> para mostrar.</span><span class="sxs-lookup"><span data-stu-id="8007a-125">In this case, select a field in a table that you would like the <xref:System.Windows.Forms.TextBox> to display.</span></span>  
  
9. <span data-ttu-id="8007a-126">Reemplace el nombre del conjunto de datos predeterminado, si lo desea.</span><span class="sxs-lookup"><span data-stu-id="8007a-126">Replace the default dataset name if you want.</span></span>  
  
10. <span data-ttu-id="8007a-127">Haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="8007a-127">Click **Finish**.</span></span>  
  
11. <span data-ttu-id="8007a-128">En el **propiedades** ventana, haga clic en la flecha situada junto a la <xref:System.Windows.Forms.TextBox.Text%2A> propiedad nuevo.</span><span class="sxs-lookup"><span data-stu-id="8007a-128">In the **Properties** window, click the arrow next to the <xref:System.Windows.Forms.TextBox.Text%2A> property again.</span></span> <span data-ttu-id="8007a-129">En el **DataSource** editor de tipos de interfaz de usuario, seleccione el nombre del campo que se va a enlazar el <xref:System.Windows.Forms.TextBox> a.</span><span class="sxs-lookup"><span data-stu-id="8007a-129">In the **DataSource** UI type editor, select the name of the field to bind the <xref:System.Windows.Forms.TextBox> to.</span></span>  
  
     <span data-ttu-id="8007a-130">El **DataSource** la interfaz de usuario escriba editor cierra y el conjunto de datos, <xref:System.Windows.Forms.BindingSource> y adaptador de tabla específico para que la conexión de datos se agregan al formulario.</span><span class="sxs-lookup"><span data-stu-id="8007a-130">The **DataSource** UI type editor closes and the data set, <xref:System.Windows.Forms.BindingSource> and table adapter specific to that data connection are added to your form.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8007a-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="8007a-131">See also</span></span>

- <xref:System.Windows.Forms.BindingSource>
- <xref:System.Windows.Forms.BindingNavigator>
- [<span data-ttu-id="8007a-132">Agregar nuevos orígenes de datos</span><span class="sxs-lookup"><span data-stu-id="8007a-132">Add new data sources</span></span>](/visualstudio/data-tools/add-new-data-sources)
- <span data-ttu-id="8007a-133">[Ventana Orígenes de datos](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/6ckyxa83(v=vs.120))</span><span class="sxs-lookup"><span data-stu-id="8007a-133">[Data Sources Window](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/6ckyxa83(v=vs.120))</span></span>