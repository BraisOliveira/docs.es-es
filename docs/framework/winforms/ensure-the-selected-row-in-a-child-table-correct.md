---
title: Procedimiento para garantizar que la fila seleccionada de una tabla secundaria conserve la posición correcta
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- master-details view
- row position [Windows Forms]
- parent/child view [Windows Forms]
- resetting child position
- data binding [.NET Framework], row selection
- caching [.NET Framework], child position
- child position
- master/details view [Windows Forms]
- child tables row selection
- current child position
ms.assetid: c5fa2562-43a4-46fa-a604-52d8526a87bd
ms.openlocfilehash: 891a9a4d092de35ceff2f5ceb6dbde77cf2ca2ce
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59303146"
---
# <a name="how-to-ensure-the-selected-row-in-a-child-table-remains-at-the-correct-position"></a><span data-ttu-id="17fc0-102">Procedimiento para garantizar que la fila seleccionada de una tabla secundaria conserve la posición correcta</span><span class="sxs-lookup"><span data-stu-id="17fc0-102">How to: Ensure the Selected Row in a Child Table Remains at the Correct Position</span></span>
<span data-ttu-id="17fc0-103">A menudo, cuando se trabaja con enlace de datos en Windows Forms, los datos se muestran en lo que se denomina una vista primaria/secundaria o una vista maestra/detalles.</span><span class="sxs-lookup"><span data-stu-id="17fc0-103">Oftentimes when you work with data binding in Windows Forms, you will display data in what is called a parent/child or master/details view.</span></span> <span data-ttu-id="17fc0-104">Esto hace referencia a un escenario de enlace de datos donde los datos del mismo origen se muestran en dos controles.</span><span class="sxs-lookup"><span data-stu-id="17fc0-104">This refers to a data-binding scenario where data from the same source is displayed in two controls.</span></span> <span data-ttu-id="17fc0-105">Al cambiar la selección en un control, los datos mostrados en el segundo control cambiarán.</span><span class="sxs-lookup"><span data-stu-id="17fc0-105">Changing the selection in one control causes the data displayed in the second control to change.</span></span> <span data-ttu-id="17fc0-106">Por ejemplo, el primer control puede contener una lista de clientes y el segundo de una lista de pedidos relacionados con el cliente seleccionado en el primer control.</span><span class="sxs-lookup"><span data-stu-id="17fc0-106">For example, the first control might contain a list of customers and the second a list of orders related to the selected customer in the first control.</span></span>  
  
 <span data-ttu-id="17fc0-107">A partir de .NET Framework versión 2.0, cuando se muestran datos en una vista primaria/secundaria, quizás tenga que realizar algunos pasos adicionales para asegurarse de que la fila seleccionada actualmente en la tabla secundaria no se restablece a la primera fila de la tabla.</span><span class="sxs-lookup"><span data-stu-id="17fc0-107">Starting with the .NET Framework version 2.0, when you display data in a parent/child view you might have to take extra steps to make sure that the currently selected row in the child table is not reset to the first row of the table.</span></span> <span data-ttu-id="17fc0-108">Para ello, tendrá que almacenar en caché la posición de la tabla secundaria y restablecerla después de que cambie la tabla primaria.</span><span class="sxs-lookup"><span data-stu-id="17fc0-108">In order to do this, you will have to cache the child table position and reset it after the parent table changes.</span></span> <span data-ttu-id="17fc0-109">Normalmente, el restablecimiento del elemento secundario se produce la primera vez que cambia un campo en una fila de la tabla primaria.</span><span class="sxs-lookup"><span data-stu-id="17fc0-109">Typically the child reset occurs the first time a field in a row of the parent table changes.</span></span>  
  
### <a name="to-cache-the-current-child-position"></a><span data-ttu-id="17fc0-110">Para almacenar en caché la posición secundaria actual</span><span class="sxs-lookup"><span data-stu-id="17fc0-110">To Cache the Current Child Position</span></span>  
  
1. <span data-ttu-id="17fc0-111">Declare una variable entera para almacenar la posición de lista secundaria y una variable booleana para almacenar en caché la posición secundaria.</span><span class="sxs-lookup"><span data-stu-id="17fc0-111">Declare an integer variable to store the child list position and a Boolean variable to store whether to cache the child position.</span></span>  
  
     [!code-csharp[System.Windows.Forms.CurrencyManagerReset#4](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.CurrencyManagerReset/CS/Form1.cs#4)]
     [!code-vb[System.Windows.Forms.CurrencyManagerReset#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.CurrencyManagerReset/VB/Form1.vb#4)]  
  
2. <span data-ttu-id="17fc0-112">Controle el evento <xref:System.Windows.Forms.CurrencyManager.ListChanged> del <xref:System.Windows.Forms.CurrencyManager> del enlace y busque un <xref:System.ComponentModel.ListChangedType> de <xref:System.ComponentModel.ListChangedType.Reset>.</span><span class="sxs-lookup"><span data-stu-id="17fc0-112">Handle the <xref:System.Windows.Forms.CurrencyManager.ListChanged> event for the binding's <xref:System.Windows.Forms.CurrencyManager> and check for a <xref:System.ComponentModel.ListChangedType> of <xref:System.ComponentModel.ListChangedType.Reset>.</span></span>  
  
3. <span data-ttu-id="17fc0-113">Compruebe la posición actual del <xref:System.Windows.Forms.CurrencyManager>.</span><span class="sxs-lookup"><span data-stu-id="17fc0-113">Check the current position of the <xref:System.Windows.Forms.CurrencyManager>.</span></span> <span data-ttu-id="17fc0-114">Si es mayor que la primera entrada de la lista (normalmente 0), guárdela en una variable.</span><span class="sxs-lookup"><span data-stu-id="17fc0-114">If it is greater than first entry in the list (typically 0), save it to a variable.</span></span>  
  
     [!code-csharp[System.Windows.Forms.CurrencyManagerReset#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.CurrencyManagerReset/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.CurrencyManagerReset#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.CurrencyManagerReset/VB/Form1.vb#2)]  
  
4. <span data-ttu-id="17fc0-115">Controle el evento <xref:System.Windows.Forms.BindingManagerBase.CurrentChanged> de la lista primaria para el administrador de moneda principal.</span><span class="sxs-lookup"><span data-stu-id="17fc0-115">Handle the parent list's <xref:System.Windows.Forms.BindingManagerBase.CurrentChanged> event for the parent currency manager.</span></span> <span data-ttu-id="17fc0-116">En el controlador, establezca el valor booleano para indicar que no es un escenario de almacenamiento en caché.</span><span class="sxs-lookup"><span data-stu-id="17fc0-116">In the handler, set the Boolean value to indicate it is not a caching scenario.</span></span> <span data-ttu-id="17fc0-117">Si se produce <xref:System.Windows.Forms.BindingManagerBase.CurrentChanged>, el cambio en el elemento primario es un cambio de posición de lista y no un cambio de valor del elemento.</span><span class="sxs-lookup"><span data-stu-id="17fc0-117">If the <xref:System.Windows.Forms.BindingManagerBase.CurrentChanged> occurs, the change to the parent is a list position change and not an item value change.</span></span>  
  
     [!code-csharp[System.Windows.Forms.CurrencyManagerReset#5](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.CurrencyManagerReset/CS/Form1.cs#5)]
     [!code-vb[System.Windows.Forms.CurrencyManagerReset#5](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.CurrencyManagerReset/VB/Form1.vb#5)]  
  
### <a name="to-reset-the-child-position"></a><span data-ttu-id="17fc0-118">Para restablecer la posición secundaria</span><span class="sxs-lookup"><span data-stu-id="17fc0-118">To Reset the Child Position</span></span>  
  
1. <span data-ttu-id="17fc0-119">Controle el evento <xref:System.Windows.Forms.BindingManagerBase.PositionChanged> del <xref:System.Windows.Forms.CurrencyManager> del enlace secundario.</span><span class="sxs-lookup"><span data-stu-id="17fc0-119">Handle the <xref:System.Windows.Forms.BindingManagerBase.PositionChanged> event for the child binding's <xref:System.Windows.Forms.CurrencyManager>.</span></span>  
  
2. <span data-ttu-id="17fc0-120">Restablezca la posición de la tabla secundaria a la posición almacenada en caché que se guardó en el procedimiento anterior.</span><span class="sxs-lookup"><span data-stu-id="17fc0-120">Reset the child table position to the cached position saved in the previous procedure.</span></span>  
  
     [!code-csharp[System.Windows.Forms.CurrencyManagerReset#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.CurrencyManagerReset/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.CurrencyManagerReset#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.CurrencyManagerReset/VB/Form1.vb#3)]  
  
## <a name="example"></a><span data-ttu-id="17fc0-121">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="17fc0-121">Example</span></span>  
 <span data-ttu-id="17fc0-122">En el ejemplo siguiente se muestra cómo guardar la posición actual en el <xref:System.Windows.Forms.CurrencyManager> para una tabla secundaria y cómo restablecer la posición de una vez completada una modificación en la tabla primaria.</span><span class="sxs-lookup"><span data-stu-id="17fc0-122">The following example demonstrates how to save the current position on the <xref:System.Windows.Forms.CurrencyManager>.for a child table and reset the position after an edit is completed on the parent table.</span></span> <span data-ttu-id="17fc0-123">Este ejemplo contiene dos controles <xref:System.Windows.Forms.DataGridView> enlazados a dos tablas en un <xref:System.Data.DataSet> mediante el componente <xref:System.Windows.Forms.BindingSource>.</span><span class="sxs-lookup"><span data-stu-id="17fc0-123">This example contains two <xref:System.Windows.Forms.DataGridView> controls bound to two tables in a <xref:System.Data.DataSet> using a <xref:System.Windows.Forms.BindingSource> component.</span></span> <span data-ttu-id="17fc0-124">Se establece una relación entre las dos tablas y la relación se agrega al <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="17fc0-124">A relation is established between the two tables and the relation is added to the <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="17fc0-125">La posición en la tabla secundaria se establece inicialmente en la tercera fila para fines de demostración.</span><span class="sxs-lookup"><span data-stu-id="17fc0-125">The position in the child table is initially set to the third row for demonstration purposes.</span></span>  
  
 [!code-csharp[System.Windows.Forms.CurrencyManagerReset#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.CurrencyManagerReset/CS/Form1.cs#1)]
 [!code-vb[System.Windows.Forms.CurrencyManagerReset#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.CurrencyManagerReset/VB/Form1.vb#1)]  
  
 <span data-ttu-id="17fc0-126">Para probar el ejemplo de código, realice los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="17fc0-126">To test the code example, perform the following steps:</span></span>  
  
1. <span data-ttu-id="17fc0-127">Ejecute el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="17fc0-127">Run the example.</span></span>  
  
2. <span data-ttu-id="17fc0-128">Asegúrese de que la casilla **Cache and reset position** está activada.</span><span class="sxs-lookup"><span data-stu-id="17fc0-128">Make sure the **Cache and reset position** check box is selected.</span></span>  
  
3. <span data-ttu-id="17fc0-129">Haga clic en el botón **Clear parent field** para producir un cambio en un campo de la tabla primaria.</span><span class="sxs-lookup"><span data-stu-id="17fc0-129">Click the **Clear parent field** button to cause a change in a field of the parent table.</span></span> <span data-ttu-id="17fc0-130">Observe que la fila seleccionada en la tabla secundaria no cambia.</span><span class="sxs-lookup"><span data-stu-id="17fc0-130">Notice that the selected row in the child table does not change.</span></span>  
  
4. <span data-ttu-id="17fc0-131">Cierre y vuelva a ejecutar el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="17fc0-131">Close and run the example again.</span></span> <span data-ttu-id="17fc0-132">Deberá hacerlo porque el restablecimiento solo se produce en el primer cambio de la fila primaria.</span><span class="sxs-lookup"><span data-stu-id="17fc0-132">You need to do this because the reset behavior occurs only on the first change in the parent row.</span></span>  
  
5. <span data-ttu-id="17fc0-133">Desactive la casilla **Cache and reset position**.</span><span class="sxs-lookup"><span data-stu-id="17fc0-133">Clear the **Cache and reset position** check box.</span></span>  
  
6. <span data-ttu-id="17fc0-134">Haga clic en el botón **Clear parent field**.</span><span class="sxs-lookup"><span data-stu-id="17fc0-134">Click the **Clear parent field** button.</span></span> <span data-ttu-id="17fc0-135">Observe que la fila seleccionada en la tabla secundaria cambia a la primera fila.</span><span class="sxs-lookup"><span data-stu-id="17fc0-135">Notice that the selected row in the child table changes to the first row.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="17fc0-136">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="17fc0-136">Compiling the Code</span></span>  
 <span data-ttu-id="17fc0-137">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="17fc0-137">This example requires:</span></span>  
  
-   <span data-ttu-id="17fc0-138">Referencias a los ensamblados System, System.Data, System.Drawing, System.Windows.Forms y System.XML.</span><span class="sxs-lookup"><span data-stu-id="17fc0-138">References to the System, System.Data, System.Drawing, System.Windows.Forms, and System.XML assemblies.</span></span>  
  
 <span data-ttu-id="17fc0-139">Para obtener información sobre cómo compilar este ejemplo desde la línea de comandos para Visual Basic o Visual C#, vea [compilar desde la línea de comandos](../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) o [compilación de línea de comandos con csc.exe](../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="17fc0-139">For information about how to build this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="17fc0-140">También puede compilar este ejemplo en Visual Studio pegando el código en un nuevo proyecto.</span><span class="sxs-lookup"><span data-stu-id="17fc0-140">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="17fc0-141">Vea también</span><span class="sxs-lookup"><span data-stu-id="17fc0-141">See also</span></span>

- [<span data-ttu-id="17fc0-142">Cómo: Garantizar que varios controles enlazados al mismo origen de datos permanezcan sincronizados</span><span class="sxs-lookup"><span data-stu-id="17fc0-142">How to: Ensure Multiple Controls Bound to the Same Data Source Remain Synchronized</span></span>](multiple-controls-bound-to-data-source-synchronized.md)
- [<span data-ttu-id="17fc0-143">Componente BindingSource</span><span class="sxs-lookup"><span data-stu-id="17fc0-143">BindingSource Component</span></span>](./controls/bindingsource-component.md)
- [<span data-ttu-id="17fc0-144">Enlace de datos y Windows Forms</span><span class="sxs-lookup"><span data-stu-id="17fc0-144">Data Binding and Windows Forms</span></span>](data-binding-and-windows-forms.md)
