---
title: Procedimiento para obtener acceso a objetos de una lista desplegable DataGridViewComboBoxCell en formularios Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGridView control [Windows Forms], accessing objects in combo box cells
- combo boxes [Windows Forms], in DataGridView control
- combo boxes [Windows Forms], accessing objects in DataGridViewComboBoxCell drop-down lists
ms.assetid: bcbe794a-d1fa-47f8-b5a3-5f085b32097d
ms.openlocfilehash: 17b7c93effe9338a9e2d6cb207a948a956d9b666
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59334281"
---
# <a name="how-to-access-objects-in-a-windows-forms-datagridviewcomboboxcell-drop-down-list"></a><span data-ttu-id="7df44-102">Procedimiento para obtener acceso a objetos de una lista desplegable DataGridViewComboBoxCell en formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="7df44-102">How to: Access Objects in a Windows Forms DataGridViewComboBoxCell Drop-Down List</span></span>
<span data-ttu-id="7df44-103">Al igual que el <xref:System.Windows.Forms.ComboBox> (control), el <xref:System.Windows.Forms.DataGridViewComboBoxColumn> y <xref:System.Windows.Forms.DataGridViewComboBoxCell> tipos le permiten agregar objetos arbitrarios a las listas de la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="7df44-103">Like the <xref:System.Windows.Forms.ComboBox> control, the <xref:System.Windows.Forms.DataGridViewComboBoxColumn> and <xref:System.Windows.Forms.DataGridViewComboBoxCell> types enable you to add arbitrary objects to their drop-down lists.</span></span> <span data-ttu-id="7df44-104">Con esta característica, puede representar estados complejos en una lista desplegable sin tener que almacenar los objetos correspondientes en una colección independiente.</span><span class="sxs-lookup"><span data-stu-id="7df44-104">With this feature, you can represent complex states in a drop-down list without having to store corresponding objects in a separate collection.</span></span>  
  
 <span data-ttu-id="7df44-105">A diferencia de la <xref:System.Windows.Forms.ComboBox> (control), el <xref:System.Windows.Forms.DataGridView> tipos no tienen un <xref:System.Windows.Forms.ComboBox.SelectedItem%2A> propiedad para recuperar el objeto seleccionado actualmente.</span><span class="sxs-lookup"><span data-stu-id="7df44-105">Unlike the <xref:System.Windows.Forms.ComboBox> control, the <xref:System.Windows.Forms.DataGridView> types do not have a <xref:System.Windows.Forms.ComboBox.SelectedItem%2A> property for retrieving the currently selected object.</span></span> <span data-ttu-id="7df44-106">En su lugar, debe establecer el <xref:System.Windows.Forms.DataGridViewComboBoxColumn.ValueMember%2A?displayProperty=nameWithType> o <xref:System.Windows.Forms.DataGridViewComboBoxCell.ValueMember%2A?displayProperty=nameWithType> propiedad en el nombre de una propiedad en el objeto comercial.</span><span class="sxs-lookup"><span data-stu-id="7df44-106">Instead, you must set the <xref:System.Windows.Forms.DataGridViewComboBoxColumn.ValueMember%2A?displayProperty=nameWithType> or <xref:System.Windows.Forms.DataGridViewComboBoxCell.ValueMember%2A?displayProperty=nameWithType> property to the name of a property on your business object.</span></span> <span data-ttu-id="7df44-107">Cuando el usuario realiza una selección, la propiedad indicada del objeto comercial establece la celda <xref:System.Windows.Forms.DataGridViewCell.Value%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="7df44-107">When the user makes a selection, the indicated property of the business object sets the cell <xref:System.Windows.Forms.DataGridViewCell.Value%2A> property.</span></span>  
  
 <span data-ttu-id="7df44-108">Para recuperar el objeto de negocios a través del valor de celda, el `ValueMember` propiedad debe indicar una propiedad que devuelve una referencia al propio objeto de negocios.</span><span class="sxs-lookup"><span data-stu-id="7df44-108">To retrieve the business object through the cell value, the `ValueMember` property must indicate a property that returns a reference to the business object itself.</span></span> <span data-ttu-id="7df44-109">Por lo tanto, si el tipo del objeto comercial no está bajo su control, debe agregar esa propiedad mediante la extensión de tipo a través de herencia.</span><span class="sxs-lookup"><span data-stu-id="7df44-109">Therefore, if the type of the business object is not under your control, you must add such a property by extending the type through inheritance.</span></span>  
  
 <span data-ttu-id="7df44-110">Los procedimientos siguientes muestran cómo rellenar una lista desplegable con objetos de negocios y recuperar los objetos a través de la celda <xref:System.Windows.Forms.DataGridViewCell.Value%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="7df44-110">The following procedures demonstrate how to populate a drop-down list with business objects and retrieve the objects through the cell <xref:System.Windows.Forms.DataGridViewCell.Value%2A> property.</span></span>  
  
### <a name="to-add-business-objects-to-the-drop-down-list"></a><span data-ttu-id="7df44-111">Para agregar objetos de negocios a la lista desplegable</span><span class="sxs-lookup"><span data-stu-id="7df44-111">To add business objects to the drop-down list</span></span>  
  
1. <span data-ttu-id="7df44-112">Cree un nuevo <xref:System.Windows.Forms.DataGridViewComboBoxColumn> y rellenar sus <xref:System.Windows.Forms.DataGridViewComboBoxColumn.Items%2A> colección.</span><span class="sxs-lookup"><span data-stu-id="7df44-112">Create a new <xref:System.Windows.Forms.DataGridViewComboBoxColumn> and populate its <xref:System.Windows.Forms.DataGridViewComboBoxColumn.Items%2A> collection.</span></span> <span data-ttu-id="7df44-113">Como alternativa, puede establecer la columna <xref:System.Windows.Forms.DataGridViewComboBoxColumn.DataSource%2A> propiedad a la colección de objetos de negocios.</span><span class="sxs-lookup"><span data-stu-id="7df44-113">Alternatively, you can set the column <xref:System.Windows.Forms.DataGridViewComboBoxColumn.DataSource%2A> property to the collection of business objects.</span></span> <span data-ttu-id="7df44-114">En ese caso, sin embargo, no puede agregar "sin asignar" a la lista desplegable sin crear un objeto comercial correspondiente en la colección.</span><span class="sxs-lookup"><span data-stu-id="7df44-114">In that case, however, you cannot add "unassigned" to the drop-down list without creating a corresponding business object in your collection.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewComboBoxObjectBinding#110](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/CS/form1.cs#110)]
     [!code-vb[System.Windows.Forms.DataGridViewComboBoxObjectBinding#110](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/vb/form1.vb#110)]  
  
2. <span data-ttu-id="7df44-115">Establezca las propiedades <xref:System.Windows.Forms.DataGridViewComboBoxColumn.DisplayMember%2A> y <xref:System.Windows.Forms.DataGridViewComboBoxColumn.ValueMember%2A>.</span><span class="sxs-lookup"><span data-stu-id="7df44-115">Set the <xref:System.Windows.Forms.DataGridViewComboBoxColumn.DisplayMember%2A> and <xref:System.Windows.Forms.DataGridViewComboBoxColumn.ValueMember%2A> properties.</span></span> <span data-ttu-id="7df44-116"><xref:System.Windows.Forms.DataGridViewComboBoxColumn.DisplayMember%2A> indica la propiedad del objeto comercial que se muestra en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="7df44-116"><xref:System.Windows.Forms.DataGridViewComboBoxColumn.DisplayMember%2A> indicates the property of the business object to display in the drop-down list.</span></span> <span data-ttu-id="7df44-117"><xref:System.Windows.Forms.DataGridViewComboBoxColumn.ValueMember%2A> indica la propiedad que devuelve una referencia al objeto de negocios.</span><span class="sxs-lookup"><span data-stu-id="7df44-117"><xref:System.Windows.Forms.DataGridViewComboBoxColumn.ValueMember%2A> indicates the property that returns a reference to the business object.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewComboBoxObjectBinding#115](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/CS/form1.cs#115)]
     [!code-vb[System.Windows.Forms.DataGridViewComboBoxObjectBinding#115](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/vb/form1.vb#115)]  
  
3. <span data-ttu-id="7df44-118">Asegúrese de que el tipo de objeto de negocios contiene una propiedad que devuelve una referencia a la instancia actual.</span><span class="sxs-lookup"><span data-stu-id="7df44-118">Make sure that your business object type contains a property that returns a reference to the current instance.</span></span> <span data-ttu-id="7df44-119">Esta propiedad se debe denominar con el valor asignado a <xref:System.Windows.Forms.DataGridViewComboBoxColumn.ValueMember%2A> en el paso anterior.</span><span class="sxs-lookup"><span data-stu-id="7df44-119">This property must be named with the value assigned to <xref:System.Windows.Forms.DataGridViewComboBoxColumn.ValueMember%2A> in the previous step.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewComboBoxObjectBinding#310](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/CS/form1.cs#310)]
     [!code-vb[System.Windows.Forms.DataGridViewComboBoxObjectBinding#310](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/vb/form1.vb#310)]  
  
### <a name="to-retrieve-the-currently-selected-business-object"></a><span data-ttu-id="7df44-120">Para recuperar el objeto de negocios seleccionada actualmente</span><span class="sxs-lookup"><span data-stu-id="7df44-120">To retrieve the currently selected business object</span></span>  
  
-   <span data-ttu-id="7df44-121">Obtenga la celda <xref:System.Windows.Forms.DataGridViewCell.Value%2A> propiedad y convertirlo en el tipo de objeto de negocios.</span><span class="sxs-lookup"><span data-stu-id="7df44-121">Get the cell <xref:System.Windows.Forms.DataGridViewCell.Value%2A> property and cast it to the business object type.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewComboBoxObjectBinding#120](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/CS/form1.cs#120)]
     [!code-vb[System.Windows.Forms.DataGridViewComboBoxObjectBinding#120](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/vb/form1.vb#120)]  
  
## <a name="example"></a><span data-ttu-id="7df44-122">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="7df44-122">Example</span></span>  
 <span data-ttu-id="7df44-123">El ejemplo completo muestra el uso de objetos comerciales en una lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="7df44-123">The complete example demonstrates the use of business objects in a drop-down list.</span></span> <span data-ttu-id="7df44-124">En el ejemplo, un <xref:System.Windows.Forms.DataGridView> está enlazado a una colección de `Task` objetos.</span><span class="sxs-lookup"><span data-stu-id="7df44-124">In the example, a <xref:System.Windows.Forms.DataGridView> control is bound to a collection of `Task` objects.</span></span> <span data-ttu-id="7df44-125">Cada `Task` objeto tiene un `AssignedTo` propiedad que indica la `Employee` objeto asignado actualmente a esa tarea.</span><span class="sxs-lookup"><span data-stu-id="7df44-125">Each `Task` object has an `AssignedTo` property that indicates the `Employee` object currently assigned to that task.</span></span> <span data-ttu-id="7df44-126">El `Assigned To` columna muestra el `Name` asigna el valor de propiedad para cada empleado, o "no asignado" si el `Task.AssignedTo` es el valor de propiedad `null`.</span><span class="sxs-lookup"><span data-stu-id="7df44-126">The `Assigned To` column displays the `Name` property value for each assigned employee, or "unassigned" if the `Task.AssignedTo` property value is `null`.</span></span>  
  
 <span data-ttu-id="7df44-127">Para ver el comportamiento de este ejemplo, realice los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="7df44-127">To view the behavior of this example, perform the following steps:</span></span>  
  
1. <span data-ttu-id="7df44-128">Cambiar las asignaciones en el `Assigned To` columna seleccionando valores diferentes en las listas desplegables o presionar CTRL + 0 en una celda de cuadro combinado.</span><span class="sxs-lookup"><span data-stu-id="7df44-128">Change assignments in the `Assigned To` column by selecting different values from the drop-down lists or pressing CTRL+0 in a combo-box cell.</span></span>  
  
2. <span data-ttu-id="7df44-129">Haga clic en `Generate Report` para mostrar las asignaciones actuales.</span><span class="sxs-lookup"><span data-stu-id="7df44-129">Click `Generate Report` to display the current assignments.</span></span> <span data-ttu-id="7df44-130">Esto demuestra que un cambio en el `Assigned To` columna se actualiza automáticamente el `tasks` colección.</span><span class="sxs-lookup"><span data-stu-id="7df44-130">This demonstrates that a change in the `Assigned To` column automatically updates the `tasks` collection.</span></span>  
  
3. <span data-ttu-id="7df44-131">Haga clic en un `Request Status` botón para llamar a la `RequestStatus` método del actual `Employee` objeto para esa fila.</span><span class="sxs-lookup"><span data-stu-id="7df44-131">Click a `Request Status` button to call the `RequestStatus` method of the current `Employee` object for that row.</span></span> <span data-ttu-id="7df44-132">Esto demuestra que el objeto seleccionado se ha recuperado correctamente.</span><span class="sxs-lookup"><span data-stu-id="7df44-132">This demonstrates that the selected object has been successfully retrieved.</span></span>  
  
 [!code-csharp[System.Windows.Forms.DataGridViewComboBoxObjectBinding#000](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/CS/form1.cs#000)]
 [!code-vb[System.Windows.Forms.DataGridViewComboBoxObjectBinding#000](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/vb/form1.vb#000)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="7df44-133">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="7df44-133">Compiling the Code</span></span>  
 <span data-ttu-id="7df44-134">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="7df44-134">This example requires:</span></span>  
  
-   <span data-ttu-id="7df44-135">Referencias a los ensamblados System y System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="7df44-135">References to the System and System.Windows.Forms assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7df44-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="7df44-136">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewComboBoxColumn>
- <xref:System.Windows.Forms.DataGridViewComboBoxColumn.Items%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewComboBoxColumn.DataSource%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewComboBoxColumn.ValueMember%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewComboBoxCell>
- <xref:System.Windows.Forms.DataGridViewComboBoxCell.Items%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewComboBoxCell.DataSource%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewComboBoxCell.ValueMember%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewCell.Value%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.ComboBox>
- [<span data-ttu-id="7df44-137">Mostrar datos en el control DataGridView de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="7df44-137">Displaying Data in the Windows Forms DataGridView Control</span></span>](displaying-data-in-the-windows-forms-datagridview-control.md)
