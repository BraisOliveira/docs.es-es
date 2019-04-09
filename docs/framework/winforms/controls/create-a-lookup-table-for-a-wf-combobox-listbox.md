---
title: Filtrar para crear una tabla de búsqueda para un control ComboBox, ListBox o CheckedListBox de formularios Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- CheckedListBox control [Windows Forms], creating lookup tables
- lookup tables
- list boxes [Windows Forms], lookup tables
- ListBox control [Windows Forms], lookup tables
- ComboBox control [Windows Forms], lookup table
- lookup tables [Windows Forms], creating for controls
- combo boxes [Windows Forms], lookup tables
- ListBox control [Windows Forms], creating lookup tables
ms.assetid: 4ce35f12-1f4e-4317-92d1-af8686a8cfaa
ms.openlocfilehash: 95b1962b83a44a99ebc466e27c732917d63dc3c2
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59125988"
---
# <a name="how-to-create-a-lookup-table-for-a-windows-forms-combobox-listbox-or-checkedlistbox-control"></a><span data-ttu-id="659cf-102">Filtrar para crear una tabla de búsqueda para un control ComboBox, ListBox o CheckedListBox de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="659cf-102">How to: Create a Lookup Table for a Windows Forms ComboBox, ListBox, or CheckedListBox Control</span></span>
<span data-ttu-id="659cf-103">A veces resulta útil mostrar datos en un formato fácil de usar en un formulario de Windows Forms y, no obstante, almacenar los datos en un formato más coherente para su programa.</span><span class="sxs-lookup"><span data-stu-id="659cf-103">Sometimes it is useful to display data in a user-friendly format on a Windows Form, but store the data in a format that is more meaningful to your program.</span></span> <span data-ttu-id="659cf-104">Por ejemplo, un formulario de pedido de comida puede mostrar los elementos del menú por nombre en un cuadro de lista.</span><span class="sxs-lookup"><span data-stu-id="659cf-104">For example, an order form for food might display the menu items by name in a list box.</span></span> <span data-ttu-id="659cf-105">Sin embargo, la tabla de datos que registra el pedido contendría los números de identificador únicos que representan la comida.</span><span class="sxs-lookup"><span data-stu-id="659cf-105">However, the data table recording the order would contain the unique ID numbers representing the food.</span></span> <span data-ttu-id="659cf-106">En las siguientes tablas se proporciona un ejemplo en el que se indica cómo almacenar y mostrar datos de formulario de pedido de comida.</span><span class="sxs-lookup"><span data-stu-id="659cf-106">The following tables show an example of how to store and display order-form data for food.</span></span>  
  
### <a name="orderdetailstable"></a><span data-ttu-id="659cf-107">OrderDetailsTable</span><span class="sxs-lookup"><span data-stu-id="659cf-107">OrderDetailsTable</span></span>  
  
|<span data-ttu-id="659cf-108">OrderID</span><span class="sxs-lookup"><span data-stu-id="659cf-108">OrderID</span></span>|<span data-ttu-id="659cf-109">ItemID</span><span class="sxs-lookup"><span data-stu-id="659cf-109">ItemID</span></span>|<span data-ttu-id="659cf-110">Cantidad</span><span class="sxs-lookup"><span data-stu-id="659cf-110">Quantity</span></span>|  
|-------------|------------|--------------|  
|<span data-ttu-id="659cf-111">4085</span><span class="sxs-lookup"><span data-stu-id="659cf-111">4085</span></span>|<span data-ttu-id="659cf-112">12</span><span class="sxs-lookup"><span data-stu-id="659cf-112">12</span></span>|<span data-ttu-id="659cf-113">1</span><span class="sxs-lookup"><span data-stu-id="659cf-113">1</span></span>|  
|<span data-ttu-id="659cf-114">4086</span><span class="sxs-lookup"><span data-stu-id="659cf-114">4086</span></span>|<span data-ttu-id="659cf-115">13</span><span class="sxs-lookup"><span data-stu-id="659cf-115">13</span></span>|<span data-ttu-id="659cf-116">3</span><span class="sxs-lookup"><span data-stu-id="659cf-116">3</span></span>|  
  
### <a name="itemtable"></a><span data-ttu-id="659cf-117">ItemTable</span><span class="sxs-lookup"><span data-stu-id="659cf-117">ItemTable</span></span>  
  
|<span data-ttu-id="659cf-118">ID</span><span class="sxs-lookup"><span data-stu-id="659cf-118">ID</span></span>|<span data-ttu-id="659cf-119">Name</span><span class="sxs-lookup"><span data-stu-id="659cf-119">Name</span></span>|  
|--------|----------|  
|<span data-ttu-id="659cf-120">12</span><span class="sxs-lookup"><span data-stu-id="659cf-120">12</span></span>|<span data-ttu-id="659cf-121">Patata</span><span class="sxs-lookup"><span data-stu-id="659cf-121">Potato</span></span>|  
|<span data-ttu-id="659cf-122">13</span><span class="sxs-lookup"><span data-stu-id="659cf-122">13</span></span>|<span data-ttu-id="659cf-123">Pollo</span><span class="sxs-lookup"><span data-stu-id="659cf-123">Chicken</span></span>|  
  
 <span data-ttu-id="659cf-124">En este escenario, una tabla, **OrderDetailsTable**, almacena la información real que interesa mostrar y guardar.</span><span class="sxs-lookup"><span data-stu-id="659cf-124">In this scenario, one table, **OrderDetailsTable**, stores the actual information you are concerned with displaying and saving.</span></span> <span data-ttu-id="659cf-125">Pero para ahorrar espacio, lo hace en un modo bastante críptico.</span><span class="sxs-lookup"><span data-stu-id="659cf-125">But to save space, it does so in a fairly cryptic fashion.</span></span> <span data-ttu-id="659cf-126">La otra tabla, **ItemTable**, contiene sólo información relativa al aspecto sobre qué Id. de número equivale a qué nombre de comida y nada sobre los pedidos de comida en Sí.</span><span class="sxs-lookup"><span data-stu-id="659cf-126">The other table, **ItemTable**, contains only appearance-related information about which ID number is equivalent to which food name, and nothing about the actual food orders.</span></span>  
  
 <span data-ttu-id="659cf-127">El **ItemTable** está conectado a la <xref:System.Windows.Forms.ComboBox>, <xref:System.Windows.Forms.ListBox>, o <xref:System.Windows.Forms.CheckedListBox> control mediante tres propiedades.</span><span class="sxs-lookup"><span data-stu-id="659cf-127">The **ItemTable** is connected to the <xref:System.Windows.Forms.ComboBox>, <xref:System.Windows.Forms.ListBox>, or <xref:System.Windows.Forms.CheckedListBox> control through three properties.</span></span> <span data-ttu-id="659cf-128">El `DataSource` propiedad contiene el nombre de esta tabla.</span><span class="sxs-lookup"><span data-stu-id="659cf-128">The `DataSource` property contains the name of this table.</span></span> <span data-ttu-id="659cf-129">El `DisplayMember` propiedad contiene la columna de datos de la tabla que desea mostrar en el control (el nombre de la comida).</span><span class="sxs-lookup"><span data-stu-id="659cf-129">The `DisplayMember` property contains the data column of that table that you want to display in the control (the food name).</span></span> <span data-ttu-id="659cf-130">El `ValueMember` propiedad contiene la columna de datos de la tabla con la información almacenada (número de identificación).</span><span class="sxs-lookup"><span data-stu-id="659cf-130">The `ValueMember` property contains the data column of that table with the stored information (the ID number).</span></span>  
  
 <span data-ttu-id="659cf-131">El **OrderDetailsTable** está conectado al control mediante su colección de enlaces, tiene acceso a través del <xref:System.Windows.Forms.Control.DataBindings%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="659cf-131">The **OrderDetailsTable** is connected to the control by its bindings collection, accessed through the <xref:System.Windows.Forms.Control.DataBindings%2A> property.</span></span> <span data-ttu-id="659cf-132">Cuando se agrega un objeto de enlace a la colección, se conecta una propiedad de control a un miembro de datos específica (la columna de números de Id.) en un origen de datos (el **OrderDetailsTable**).</span><span class="sxs-lookup"><span data-stu-id="659cf-132">When you add a binding object to the collection, you connect a control property to a specific data member (the column of ID numbers) in a data source (the **OrderDetailsTable**).</span></span> <span data-ttu-id="659cf-133">Cuando se realiza una selección en el control, la entrada de formulario se guarda en esta tabla.</span><span class="sxs-lookup"><span data-stu-id="659cf-133">When a selection is made in the control, this table is where the form input is saved.</span></span>  
  
### <a name="to-create-a-lookup-table"></a><span data-ttu-id="659cf-134">Para crear una tabla de búsqueda</span><span class="sxs-lookup"><span data-stu-id="659cf-134">To create a lookup table</span></span>  
  
1.  <span data-ttu-id="659cf-135">Agregue un control <xref:System.Windows.Forms.ComboBox>, <xref:System.Windows.Forms.ListBox> o <xref:System.Windows.Forms.CheckedListBox> al formulario.</span><span class="sxs-lookup"><span data-stu-id="659cf-135">Add a <xref:System.Windows.Forms.ComboBox>, <xref:System.Windows.Forms.ListBox>, or <xref:System.Windows.Forms.CheckedListBox> control to the form.</span></span>  
  
2.  <span data-ttu-id="659cf-136">Conéctese a su origen de datos.</span><span class="sxs-lookup"><span data-stu-id="659cf-136">Connect to your data source.</span></span>  
  
3.  <span data-ttu-id="659cf-137">Establezca a una relación de datos entre las dos tablas.</span><span class="sxs-lookup"><span data-stu-id="659cf-137">Establish a data relation between the two tables.</span></span> <span data-ttu-id="659cf-138">Consulte [Introducción a los objetos DataRelation](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/0k21zcyx(v=vs.120)).</span><span class="sxs-lookup"><span data-stu-id="659cf-138">See [Introduction to DataRelation Objects](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/0k21zcyx(v=vs.120)).</span></span>  
  
4.  <span data-ttu-id="659cf-139">Establezca las siguientes propiedades.</span><span class="sxs-lookup"><span data-stu-id="659cf-139">Set the following properties.</span></span> <span data-ttu-id="659cf-140">Puede establecerse en código o en el diseñador.</span><span class="sxs-lookup"><span data-stu-id="659cf-140">They can be set in code or in the designer.</span></span>  
  
    |<span data-ttu-id="659cf-141">Propiedad</span><span class="sxs-lookup"><span data-stu-id="659cf-141">Property</span></span>|<span data-ttu-id="659cf-142">Parámetro</span><span class="sxs-lookup"><span data-stu-id="659cf-142">Setting</span></span>|  
    |--------------|-------------|  
    |<xref:System.Windows.Forms.ListControl.DataSource%2A>|<span data-ttu-id="659cf-143">La tabla que contiene la información sobre qué número de identificador equivale a qué elemento.</span><span class="sxs-lookup"><span data-stu-id="659cf-143">The table that contains information about which ID number is equivalent to which item.</span></span> <span data-ttu-id="659cf-144">En el escenario anterior, se trata de `ItemTable`.</span><span class="sxs-lookup"><span data-stu-id="659cf-144">In the previous scenario, this is `ItemTable`.</span></span>|  
    |<xref:System.Windows.Forms.ListControl.DisplayMember%2A>|<span data-ttu-id="659cf-145">La columna de la tabla de origen de datos que desea mostrar en el control.</span><span class="sxs-lookup"><span data-stu-id="659cf-145">The column of the data source table that you want to display in the control.</span></span> <span data-ttu-id="659cf-146">En el escenario anterior, se trata de `"Name"` (para establecer en el código, utilice las comillas).</span><span class="sxs-lookup"><span data-stu-id="659cf-146">In the previous scenario, this is `"Name"` (to set in code, use quotation marks).</span></span>|  
    |<xref:System.Windows.Forms.ListControl.ValueMember%2A>|<span data-ttu-id="659cf-147">La columna de la tabla de origen de datos que contiene la información almacenada.</span><span class="sxs-lookup"><span data-stu-id="659cf-147">The column of the data source table that contains the stored information.</span></span> <span data-ttu-id="659cf-148">En el escenario anterior, se trata de `"ID"` (para establecer en el código, utilice las comillas).</span><span class="sxs-lookup"><span data-stu-id="659cf-148">In the previous scenario, this is `"ID"` (to set in code, use quotation marks).</span></span>|  
  
5.  <span data-ttu-id="659cf-149">En un procedimiento llame al método <xref:System.Windows.Forms.ControlBindingsCollection.Add%2A> de la clase <xref:System.Windows.Forms.ControlBindingsCollection> para enlazar la propiedad <xref:System.Windows.Forms.ListControl.SelectedValue%2A> del control a la tabla que registra la entrada de formulario.</span><span class="sxs-lookup"><span data-stu-id="659cf-149">In a procedure, call the <xref:System.Windows.Forms.ControlBindingsCollection.Add%2A> method of the <xref:System.Windows.Forms.ControlBindingsCollection> class to bind the control's <xref:System.Windows.Forms.ListControl.SelectedValue%2A> property to the table recording the form input.</span></span> <span data-ttu-id="659cf-150">También puede hacerlo en el diseñador en lugar de en el código, accediendo el control <xref:System.Windows.Forms.Control.DataBindings%2A> propiedad en el **propiedades** ventana.</span><span class="sxs-lookup"><span data-stu-id="659cf-150">You can also do this in the Designer instead of in code, by accessing the control's <xref:System.Windows.Forms.Control.DataBindings%2A> property in the **Properties** window.</span></span> <span data-ttu-id="659cf-151">En el escenario anterior, se trata de `OrderDetailsTable`, y la columna es `"ItemID"`.</span><span class="sxs-lookup"><span data-stu-id="659cf-151">In the previous scenario, this is `OrderDetailsTable`, and the column is `"ItemID"`.</span></span>  
  
    ```vb  
    ListBox1.DataBindings.Add("SelectedValue", OrderDetailsTable, "ItemID")  
    ```  
  
    ```csharp  
    listBox1.DataBindings.Add("SelectedValue", OrderDetailsTable, "ItemID");  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="659cf-152">Vea también</span><span class="sxs-lookup"><span data-stu-id="659cf-152">See also</span></span>

- [<span data-ttu-id="659cf-153">Enlace de datos y formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="659cf-153">Data Binding and Windows Forms</span></span>](../data-binding-and-windows-forms.md)
- [<span data-ttu-id="659cf-154">Información general sobre el control ListBox</span><span class="sxs-lookup"><span data-stu-id="659cf-154">ListBox Control Overview</span></span>](listbox-control-overview-windows-forms.md)
- [<span data-ttu-id="659cf-155">Información general sobre el control ComboBox</span><span class="sxs-lookup"><span data-stu-id="659cf-155">ComboBox Control Overview</span></span>](combobox-control-overview-windows-forms.md)
- [<span data-ttu-id="659cf-156">Información general sobre el control CheckedListBox</span><span class="sxs-lookup"><span data-stu-id="659cf-156">CheckedListBox Control Overview</span></span>](checkedlistbox-control-overview-windows-forms.md)
- [<span data-ttu-id="659cf-157">Controles de formularios Windows Forms usados para mostrar opciones</span><span class="sxs-lookup"><span data-stu-id="659cf-157">Windows Forms Controls Used to List Options</span></span>](windows-forms-controls-used-to-list-options.md)
