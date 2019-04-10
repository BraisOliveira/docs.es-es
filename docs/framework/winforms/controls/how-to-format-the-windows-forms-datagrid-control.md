---
title: Filtrar para dar formato al control DataGrid de formularios Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- columns [Windows Forms], DataGrid control
- colors [Windows Forms], applying to DataGrid controls
- DataGrid control [Windows Forms], formatting
- columns [Windows Forms], formatting in DataGrid control
- DataGrid control [Windows Forms], default styles
- tables [Windows Forms], formatting in DataGrid control
- formatting [Windows Forms]
ms.assetid: a50fcc3b-8abf-47ec-9029-7f268af4ddb1
ms.openlocfilehash: 8e5c41d6f146e6abef8d7670e6191b587ac86c92
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/09/2019
ms.locfileid: "59336127"
---
# <a name="how-to-format-the-windows-forms-datagrid-control"></a><span data-ttu-id="29d67-102">Filtrar para dar formato al control DataGrid de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="29d67-102">How to: Format the Windows Forms DataGrid Control</span></span>
> [!NOTE]
>  <span data-ttu-id="29d67-103">El control <xref:System.Windows.Forms.DataGridView> reemplaza y agrega funcionalidad al control <xref:System.Windows.Forms.DataGrid>; sin embargo, el control <xref:System.Windows.Forms.DataGrid> se conserva a efectos de compatibilidad con versiones anteriores y uso futuro, en su caso.</span><span class="sxs-lookup"><span data-stu-id="29d67-103">The <xref:System.Windows.Forms.DataGridView> control replaces and adds functionality to the <xref:System.Windows.Forms.DataGrid> control; however, the <xref:System.Windows.Forms.DataGrid> control is retained for both backward compatibility and future use, if you choose.</span></span> <span data-ttu-id="29d67-104">Para obtener más información, consulte [Differences Between the Windows Forms DataGridView and DataGrid Controls](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md) (Diferencias entre los controles DataGridView y DataGrid de formularios Windows Forms).</span><span class="sxs-lookup"><span data-stu-id="29d67-104">For more information, see [Differences Between the Windows Forms DataGridView and DataGrid Controls](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).</span></span>  
  
 <span data-ttu-id="29d67-105">Aplicar colores diferentes para distintas partes de un <xref:System.Windows.Forms.DataGrid> control puede ayudar a que la información sea más fácil leer e interpretar.</span><span class="sxs-lookup"><span data-stu-id="29d67-105">Applying different colors to various parts of a <xref:System.Windows.Forms.DataGrid> control can help to make the information in it easier to read and interpret.</span></span> <span data-ttu-id="29d67-106">Color puede aplicarse a las filas y columnas.</span><span class="sxs-lookup"><span data-stu-id="29d67-106">Color can be applied to rows and columns.</span></span> <span data-ttu-id="29d67-107">Las filas y columnas también se oculta o se muestra a su entera discreción.</span><span class="sxs-lookup"><span data-stu-id="29d67-107">Rows and columns can also be hidden or shown at your discretion.</span></span>  
  
 <span data-ttu-id="29d67-108">Hay tres aspectos básicos del formato el <xref:System.Windows.Forms.DataGrid> control.</span><span class="sxs-lookup"><span data-stu-id="29d67-108">There are three basic aspects of formatting the <xref:System.Windows.Forms.DataGrid> control.</span></span> <span data-ttu-id="29d67-109">Puede establecer propiedades para establecer un estilo predeterminado en el que se muestran los datos.</span><span class="sxs-lookup"><span data-stu-id="29d67-109">You can set properties to establish a default style in which data is displayed.</span></span> <span data-ttu-id="29d67-110">Desde esa base, a continuación, puede personalizar la manera en que se muestren determinadas tablas en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="29d67-110">From that base, you can then customize the way certain tables are displayed at run time.</span></span> <span data-ttu-id="29d67-111">Por último, puede modificar las columnas que se muestran en la cuadrícula de datos, así como los colores y otras opciones de formato se muestra.</span><span class="sxs-lookup"><span data-stu-id="29d67-111">Finally, you can modify which columns are displayed in the data grid as well as the colors and other formatting that is shown.</span></span>  
  
 <span data-ttu-id="29d67-112">Como paso inicial para dar formato a una cuadrícula de datos, puede establecer las propiedades de la <xref:System.Windows.Forms.DataGrid> propio.</span><span class="sxs-lookup"><span data-stu-id="29d67-112">As an initial step in formatting a data grid, you can set the properties of the <xref:System.Windows.Forms.DataGrid> itself.</span></span> <span data-ttu-id="29d67-113">Estas opciones de color y el formato forman una base desde la que puede realizar, a continuación, cambia en función de las tablas de datos y las columnas mostradas.</span><span class="sxs-lookup"><span data-stu-id="29d67-113">These color and format choices form a base from which you can then make changes depending on the data tables and columns displayed.</span></span>  
  
### <a name="to-establish-a-default-style-for-the-datagrid-control"></a><span data-ttu-id="29d67-114">Para establecer un estilo predeterminado para el control DataGrid</span><span class="sxs-lookup"><span data-stu-id="29d67-114">To establish a default style for the DataGrid control</span></span>  
  
1. <span data-ttu-id="29d67-115">Establezca las propiedades siguientes según corresponda:</span><span class="sxs-lookup"><span data-stu-id="29d67-115">Set the following properties as appropriate:</span></span>  
  
    |<span data-ttu-id="29d67-116">Propiedad</span><span class="sxs-lookup"><span data-stu-id="29d67-116">Property</span></span>|<span data-ttu-id="29d67-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="29d67-117">Description</span></span>|  
    |--------------|-----------------|  
    |<xref:System.Windows.Forms.DataGrid.AlternatingBackColor%2A>|<span data-ttu-id="29d67-118">El <xref:System.Windows.Forms.DataGrid.BackColor%2A> propiedad define el color de las filas impares de la cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="29d67-118">The <xref:System.Windows.Forms.DataGrid.BackColor%2A> property defines the color of the even-numbered rows of the grid.</span></span> <span data-ttu-id="29d67-119">Al establecer el <xref:System.Windows.Forms.DataGrid.AlternatingBackColor%2A> propiedad a un color diferente, todas las demás filas se establece en este nuevo color (filas 1, 3, 5 y así sucesivamente).</span><span class="sxs-lookup"><span data-stu-id="29d67-119">When you set the <xref:System.Windows.Forms.DataGrid.AlternatingBackColor%2A> property to a different color, every other row is set to this new color (rows 1, 3, 5, and so on).</span></span>|  
    |<xref:System.Windows.Forms.DataGrid.BackColor%2A>|<span data-ttu-id="29d67-120">El color de fondo de las filas impares de la cuadrícula (filas 0, 2, 4, 6 y así sucesivamente).</span><span class="sxs-lookup"><span data-stu-id="29d67-120">The background color of the even-numbered rows of the grid (rows 0, 2, 4, 6, and so on).</span></span>|  
    |<xref:System.Windows.Forms.DataGrid.BackgroundColor%2A>|<span data-ttu-id="29d67-121">Mientras que la <xref:System.Windows.Forms.DataGrid.BackColor%2A> y <xref:System.Windows.Forms.DataGrid.AlternatingBackColor%2A> propiedades determinan el color de las filas de la cuadrícula, la <xref:System.Windows.Forms.DataGrid.BackgroundColor%2A> propiedad determina el color de la área que no, que solo está visible cuando la cuadrícula se desplaza hasta la parte inferior, o si sólo unas pocas filas se encuentran en la cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="29d67-121">Whereas the <xref:System.Windows.Forms.DataGrid.BackColor%2A> and <xref:System.Windows.Forms.DataGrid.AlternatingBackColor%2A> properties determines the color of rows in the grid, the <xref:System.Windows.Forms.DataGrid.BackgroundColor%2A> property determines the color of the nonrow area, which is only visible when the grid is scrolled to the bottom, or if only a few rows are contained in the grid.</span></span>|  
    |<xref:System.Windows.Forms.DataGrid.BorderStyle%2A>|<span data-ttu-id="29d67-122">Estilo de borde de la cuadrícula, uno de los <xref:System.Windows.Forms.BorderStyle> valores de enumeración.</span><span class="sxs-lookup"><span data-stu-id="29d67-122">The grid's border style, one of the <xref:System.Windows.Forms.BorderStyle> enumeration values.</span></span>|  
    |<xref:System.Windows.Forms.DataGrid.CaptionBackColor%2A>|<span data-ttu-id="29d67-123">El color de fondo del título de ventana de la cuadrícula que aparece justo encima de la cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="29d67-123">The background color of the grid's window caption which appears immediately above the grid.</span></span>|  
    |<xref:System.Windows.Forms.DataGrid.CaptionFont%2A>|<span data-ttu-id="29d67-124">La fuente del título en la parte superior de la cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="29d67-124">The font of the caption at the top of the grid.</span></span>|  
    |<xref:System.Windows.Forms.DataGrid.CaptionForeColor%2A>|<span data-ttu-id="29d67-125">El color de fondo del título de ventana de la cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="29d67-125">The background color of the grid's window caption.</span></span>|  
    |<xref:System.Windows.Forms.Control.Font%2A>|<span data-ttu-id="29d67-126">La fuente utilizada para mostrar el texto en la cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="29d67-126">The font used to display the text in the grid.</span></span>|  
    |<xref:System.Windows.Forms.DataGrid.ForeColor%2A>|<span data-ttu-id="29d67-127">El color de la fuente que aparecen en los datos de las filas de la cuadrícula de datos.</span><span class="sxs-lookup"><span data-stu-id="29d67-127">The color of the font displayed by the data in the rows of the data grid.</span></span>|  
    |<xref:System.Windows.Forms.DataGrid.GridLineColor%2A>|<span data-ttu-id="29d67-128">El color de las líneas de cuadrícula de la cuadrícula de datos.</span><span class="sxs-lookup"><span data-stu-id="29d67-128">The color of the grid lines of the data grid.</span></span>|  
    |<xref:System.Windows.Forms.DataGrid.GridLineStyle%2A>|<span data-ttu-id="29d67-129">El estilo de las líneas que separan las celdas de la cuadrícula, uno de los <xref:System.Windows.Forms.DataGridLineStyle> valores de enumeración.</span><span class="sxs-lookup"><span data-stu-id="29d67-129">The style of the lines separating the cells of the grid, one of the <xref:System.Windows.Forms.DataGridLineStyle> enumeration values.</span></span>|  
    |<xref:System.Windows.Forms.DataGrid.HeaderBackColor%2A>|<span data-ttu-id="29d67-130">El color de fondo de los encabezados de fila y columna.</span><span class="sxs-lookup"><span data-stu-id="29d67-130">The background color of row and column headers.</span></span>|  
    |<xref:System.Windows.Forms.DataGrid.HeaderFont%2A>|<span data-ttu-id="29d67-131">La fuente utilizada para los encabezados de columna.</span><span class="sxs-lookup"><span data-stu-id="29d67-131">The font used for the column headers.</span></span>|  
    |<xref:System.Windows.Forms.DataGrid.HeaderForeColor%2A>|<span data-ttu-id="29d67-132">El color de primer plano de los encabezados de columna de la cuadrícula, incluido el texto de encabezado de columna y los glifos más/menos (para expandir las filas cuando se muestran varias tablas relacionadas).</span><span class="sxs-lookup"><span data-stu-id="29d67-132">The foreground color of the grid's column headers, including the column header text and the plus/minus glyphs (to expand rows when multiple related tables are displayed).</span></span>|  
    |<xref:System.Windows.Forms.DataGrid.LinkColor%2A>|<span data-ttu-id="29d67-133">El color del texto de todos los vínculos en la cuadrícula de datos, incluidos los vínculos a las tablas secundarias, el nombre de la relación y así sucesivamente.</span><span class="sxs-lookup"><span data-stu-id="29d67-133">The color of text of all the links in the data grid, including links to child tables, the relation name, and so on.</span></span>|  
    |<xref:System.Windows.Forms.DataGrid.ParentRowsBackColor%2A>|<span data-ttu-id="29d67-134">En una tabla secundaria, este es el color de fondo de las filas primarias.</span><span class="sxs-lookup"><span data-stu-id="29d67-134">In a child table, this is the background color of the parent rows.</span></span>|  
    |<xref:System.Windows.Forms.DataGrid.ParentRowsForeColor%2A>|<span data-ttu-id="29d67-135">En una tabla secundaria, este es el color de primer plano de las filas primarias.</span><span class="sxs-lookup"><span data-stu-id="29d67-135">In a child table, this is the foreground color of the parent rows.</span></span>|  
    |<xref:System.Windows.Forms.DataGrid.ParentRowsLabelStyle%2A>|<span data-ttu-id="29d67-136">Determina si los nombres de tabla y columna se muestran en la fila primaria, por medio de la <xref:System.Windows.Forms.DataGridParentRowsLabelStyle> enumeración.</span><span class="sxs-lookup"><span data-stu-id="29d67-136">Determines whether the table and column names are displayed in the parent row, by means of the <xref:System.Windows.Forms.DataGridParentRowsLabelStyle> enumeration.</span></span>|  
    |<xref:System.Windows.Forms.DataGrid.PreferredColumnWidth%2A>|<span data-ttu-id="29d67-137">Ancho predeterminado (en píxeles) de las columnas de la cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="29d67-137">The default width (in pixels) of columns in the grid.</span></span> <span data-ttu-id="29d67-138">Establezca esta propiedad antes de restablecer la <xref:System.Windows.Forms.DataGrid.DataSource%2A> y <xref:System.Windows.Forms.DataGrid.DataMember%2A> propiedades (ya sea por separado, o a través del <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> método), o la propiedad no tiene ningún efecto.</span><span class="sxs-lookup"><span data-stu-id="29d67-138">Set this property before resetting the <xref:System.Windows.Forms.DataGrid.DataSource%2A> and <xref:System.Windows.Forms.DataGrid.DataMember%2A> properties (either separately, or through the <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> method), or the property will have no effect.</span></span><br /><br /> <span data-ttu-id="29d67-139">No se puede establecer la propiedad en un valor menor que 0.</span><span class="sxs-lookup"><span data-stu-id="29d67-139">The property cannot be set to a value less than 0.</span></span>|  
    |<xref:System.Windows.Forms.DataGrid.PreferredRowHeight%2A>|<span data-ttu-id="29d67-140">El alto de fila (en píxeles) de filas en la cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="29d67-140">The row height (in pixels) of rows in the grid.</span></span> <span data-ttu-id="29d67-141">Establezca esta propiedad antes de restablecer la <xref:System.Windows.Forms.DataGrid.DataSource%2A> y <xref:System.Windows.Forms.DataGrid.DataMember%2A> propiedades (ya sea por separado, o a través del <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> método), o la propiedad no tiene ningún efecto.</span><span class="sxs-lookup"><span data-stu-id="29d67-141">Set this property before resetting the <xref:System.Windows.Forms.DataGrid.DataSource%2A> and <xref:System.Windows.Forms.DataGrid.DataMember%2A> properties (either separately, or through the <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> method), or the property will have no effect.</span></span><br /><br /> <span data-ttu-id="29d67-142">No se puede establecer la propiedad en un valor menor que 0.</span><span class="sxs-lookup"><span data-stu-id="29d67-142">The property cannot be set to a value less than 0.</span></span>|  
    |<xref:System.Windows.Forms.DataGrid.RowHeaderWidth%2A>|<span data-ttu-id="29d67-143">El ancho de los encabezados de fila de la cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="29d67-143">The width of the row headers of the grid.</span></span>|  
    |<xref:System.Windows.Forms.DataGrid.SelectionBackColor%2A>|<span data-ttu-id="29d67-144">Cuando se selecciona una celda o fila, este es el color de fondo.</span><span class="sxs-lookup"><span data-stu-id="29d67-144">When a row or cell is selected, this is the background color.</span></span>|  
    |<xref:System.Windows.Forms.DataGrid.SelectionForeColor%2A>|<span data-ttu-id="29d67-145">Cuando se selecciona una celda o fila, este es el color de primer plano.</span><span class="sxs-lookup"><span data-stu-id="29d67-145">When a row or cell is selected, this is the foreground color.</span></span>|  
  
    > [!NOTE]
    >  <span data-ttu-id="29d67-146">Tenga en cuenta que, al personalizar los colores de los controles, que es posible que el control sea inaccesible debido a la elección de color deficiente (por ejemplo, rojo y verde).</span><span class="sxs-lookup"><span data-stu-id="29d67-146">Keep in mind, when customizing the colors of controls, that it is possible to make the control inaccessible, due to poor color choice (for example, red and green).</span></span> <span data-ttu-id="29d67-147">Utilice los colores disponibles en el **colores del sistema** paleta para evitar este problema.</span><span class="sxs-lookup"><span data-stu-id="29d67-147">Use the colors available on the **System Colors** palette to avoid this issue.</span></span>  
  
     <span data-ttu-id="29d67-148">Los procedimientos siguientes suponen que el formulario tiene un <xref:System.Windows.Forms.DataGrid> control enlazado a una tabla de datos.</span><span class="sxs-lookup"><span data-stu-id="29d67-148">The following procedures assume your form has a <xref:System.Windows.Forms.DataGrid> control bound to a data table.</span></span> <span data-ttu-id="29d67-149">Para obtener más información, consulte [enlazar el DataGrid Control de Windows Forms a un origen de datos](how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md).</span><span class="sxs-lookup"><span data-stu-id="29d67-149">For more information, see [Binding the Windows Forms DataGrid Control to a Data Source](how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md).</span></span>  
  
### <a name="to-set-the-table-and-column-style-of-a-data-table-programmatically"></a><span data-ttu-id="29d67-150">Para establecer el estilo de tabla y columna de una tabla de datos mediante programación</span><span class="sxs-lookup"><span data-stu-id="29d67-150">To set the table and column style of a data table programmatically</span></span>  
  
1. <span data-ttu-id="29d67-151">Cree un nuevo estilo de tabla y establezca sus propiedades.</span><span class="sxs-lookup"><span data-stu-id="29d67-151">Create a new table style and set its properties.</span></span>  
  
2. <span data-ttu-id="29d67-152">Cree un estilo de columna y establezca sus propiedades.</span><span class="sxs-lookup"><span data-stu-id="29d67-152">Create a column style and set its properties.</span></span>  
  
3. <span data-ttu-id="29d67-153">Agregar el estilo de columna a la colección de estilos de columna del estilo de tabla.</span><span class="sxs-lookup"><span data-stu-id="29d67-153">Add the column style to the table style's column styles collection.</span></span>  
  
4. <span data-ttu-id="29d67-154">Agregar el estilo de tabla a la colección de estilos de tabla de la cuadrícula de datos.</span><span class="sxs-lookup"><span data-stu-id="29d67-154">Add the table style to the data grid's table styles collection.</span></span>  
  
5. <span data-ttu-id="29d67-155">En el ejemplo siguiente, cree una instancia de un nuevo <xref:System.Windows.Forms.DataGridTableStyle> y establezca su <xref:System.Windows.Forms.DataGridTableStyle.MappingName%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="29d67-155">In the example below, create an instance of a new <xref:System.Windows.Forms.DataGridTableStyle> and set its <xref:System.Windows.Forms.DataGridTableStyle.MappingName%2A> property.</span></span>  
  
6. <span data-ttu-id="29d67-156">Crear una nueva instancia de un **GridColumnStyle** y establezca su **MappingName** (y otras propiedades de diseño y presentación).</span><span class="sxs-lookup"><span data-stu-id="29d67-156">Create a new instance of a **GridColumnStyle** and set its **MappingName** (and some other layout and display properties).</span></span>  
  
7. <span data-ttu-id="29d67-157">Repita los pasos del 2 al 6 para cada estilo de columna que desea crear.</span><span class="sxs-lookup"><span data-stu-id="29d67-157">Repeat steps 2 through 6 for each column style you want to create.</span></span>  
  
     <span data-ttu-id="29d67-158">El ejemplo siguiente se muestra cómo un <xref:System.Windows.Forms.DataGridTextBoxColumn> se crea, porque es un nombre que se mostrará en la columna.</span><span class="sxs-lookup"><span data-stu-id="29d67-158">The following example illustrates how a <xref:System.Windows.Forms.DataGridTextBoxColumn> is created, because a name is to be displayed in the column.</span></span> <span data-ttu-id="29d67-159">Además, agrega el estilo de columna la <xref:System.Windows.Forms.GridColumnStylesCollection> del estilo de tabla, y agregar el estilo de tabla a la <xref:System.Windows.Forms.GridTableStylesCollection> de la cuadrícula de datos.</span><span class="sxs-lookup"><span data-stu-id="29d67-159">Additionally, you add the column style to the <xref:System.Windows.Forms.GridColumnStylesCollection> of the table style, and you add the table style to the <xref:System.Windows.Forms.GridTableStylesCollection> of the data grid.</span></span>  
  
    ```vb  
    Private Sub CreateAuthorFirstNameColumn()  
       ' Add a GridTableStyle and set the MappingName   
       ' to the name of the DataTable.  
       Dim TSAuthors As New DataGridTableStyle()  
       TSAuthors.MappingName = "Authors"  
  
       ' Add a GridColumnStyle and set the MappingName   
       ' to the name of a DataColumn in the DataTable.   
       ' Set the HeaderText and Width properties.   
       Dim TCFirstName As New DataGridTextBoxColumn()  
       TCFirstName.MappingName = "AV_FName"  
       TCFirstName.HeaderText = "First Name"  
       TCFirstName.Width = 75  
       TSAuthors.GridColumnStyles.Add(TCFirstName)  
  
       ' Add the DataGridTableStyle instance to   
       ' the GridTableStylesCollection.   
       myDataGrid.TableStyles.Add(TSAuthors)  
    End Sub  
    ```  
  
    ```csharp  
    private void addCustomDataTableStyle()  
    {  
       // Add a GridTableStyle and set the MappingName   
       // to the name of the DataTable.  
       DataGridTableStyle TSAuthors = new DataGridTableStyle();  
       TSAuthors.MappingName = "Authors";  
  
       // Add a GridColumnStyle and set the MappingName   
       // to the name of a DataColumn in the DataTable.   
       // Set the HeaderText and Width properties.   
       DataGridColumnStyle TCFirstName = new DataGridTextBoxColumn();  
       TCFirstName.MappingName = " AV_FName";  
       TCFirstName.HeaderText = "First Name";  
       TCFirstName.Width = 75;  
       TSAuthors.GridColumnStyles.Add(TCFirstName);  
  
       // Add the DataGridTableStyle instance to   
       // the GridTableStylesCollection.   
       dataGrid1.TableStyles.Add(TSAuthors);  
    }  
    ```  
  
    ```cpp  
    private:  
       void addCustomDataTableStyle()  
       {  
          // Add a GridTableStyle and set the MappingName   
          // to the name of the DataTable.  
          DataGridTableStyle^ TSAuthors = new DataGridTableStyle();  
          TSAuthors->MappingName = "Authors";  
  
          // Add a GridColumnStyle and set the MappingName   
          // to the name of a DataColumn in the DataTable.   
          // Set the HeaderText and Width properties.   
          DataGridColumnStyle^ TCFirstName = gcnew DataGridTextBoxColumn();  
          TCFirstName->MappingName = "AV_FName";  
          TCFirstName->HeaderText = "First Name";  
          TCFirstName->Width = 75;  
          TSAuthors->GridColumnStyles->Add(TCFirstName);  
  
          // Add the DataGridTableStyle instance to   
          // the GridTableStylesCollection.   
          dataGrid1->TableStyles->Add(TSAuthors);  
       }  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="29d67-160">Vea también</span><span class="sxs-lookup"><span data-stu-id="29d67-160">See also</span></span>

- <xref:System.Windows.Forms.GridTableStylesCollection>
- <xref:System.Windows.Forms.GridColumnStylesCollection>
- <xref:System.Windows.Forms.DataGrid>
- [<span data-ttu-id="29d67-161">Filtrar para eliminar u ocultar columnas del control DataGrid de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="29d67-161">How to: Delete or Hide Columns in the Windows Forms DataGrid Control</span></span>](how-to-delete-or-hide-columns-in-the-windows-forms-datagrid-control.md)
- [<span data-ttu-id="29d67-162">Control DataGrid</span><span class="sxs-lookup"><span data-stu-id="29d67-162">DataGrid Control</span></span>](datagrid-control-windows-forms.md)
