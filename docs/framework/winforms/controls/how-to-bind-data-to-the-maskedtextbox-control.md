---
title: Procedimiento para enlazar datos al control MaskedTextBox
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- MaskedTextBox control [Windows Forms]
- data binding [Windows Forms], MaskedTextBox control [Windows Forms]
- MaskedTextBox control [Windows Forms], binding data
ms.assetid: 34b29f07-e8df-48d4-b08b-53fcca524708
ms.openlocfilehash: ebc8eaf63c6b5280961a80ef11afb919810dbdb8
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61761382"
---
# <a name="how-to-bind-data-to-the-maskedtextbox-control"></a><span data-ttu-id="dc36b-102">Procedimiento para enlazar datos al control MaskedTextBox</span><span class="sxs-lookup"><span data-stu-id="dc36b-102">How to: Bind Data to the MaskedTextBox Control</span></span>
<span data-ttu-id="dc36b-103">Puede enlazar datos a un <xref:System.Windows.Forms.MaskedTextBox> controlar igual que lo haría para cualquier otro control de Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="dc36b-103">You can bind data to a <xref:System.Windows.Forms.MaskedTextBox> control just as you can to any other Windows Forms control.</span></span> <span data-ttu-id="dc36b-104">Sin embargo, si el formato de los datos en la base de datos no coincide con el formato esperado por la definición de máscara, deberá volver a formatear los datos.</span><span class="sxs-lookup"><span data-stu-id="dc36b-104">However, if the format of your data in the database does not match the format expected by your mask definition, you will need to reformat the data.</span></span> <span data-ttu-id="dc36b-105">El siguiente procedimiento muestra cómo hacer esto mediante la <xref:System.Windows.Forms.Binding.Format> y <xref:System.Windows.Forms.Binding.Parse> eventos de la <xref:System.Windows.Forms.Binding> clase para mostrar el número de teléfono distinto y campos de la base de datos de extensión de teléfono como un único campo editable.</span><span class="sxs-lookup"><span data-stu-id="dc36b-105">The following procedure demonstrates how to do this using the <xref:System.Windows.Forms.Binding.Format> and <xref:System.Windows.Forms.Binding.Parse> events of the <xref:System.Windows.Forms.Binding> class to display separate phone number and phone extension database fields as a single editable field.</span></span>  
  
 <span data-ttu-id="dc36b-106">El procedimiento siguiente requiere que tienen acceso a una base de datos de SQL Server con la base de datos de ejemplo Northwind instalada.</span><span class="sxs-lookup"><span data-stu-id="dc36b-106">The following procedure requires that you have access to a SQL Server database with the Northwind sample database installed.</span></span>  
  
### <a name="to-bind-data-to-a-maskedtextbox-control"></a><span data-ttu-id="dc36b-107">Para enlazar datos a un control MaskedTextBox</span><span class="sxs-lookup"><span data-stu-id="dc36b-107">To bind data to a MaskedTextBox control</span></span>  
  
1. <span data-ttu-id="dc36b-108">Cree un nuevo proyecto de Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="dc36b-108">Create a new Windows Forms project.</span></span>  
  
2. <span data-ttu-id="dc36b-109">Arrastre dos <xref:System.Windows.Forms.TextBox> controles al formulario; Denomínelos `FirstName` y `LastName`.</span><span class="sxs-lookup"><span data-stu-id="dc36b-109">Drag two <xref:System.Windows.Forms.TextBox> controls onto your form; name them `FirstName` and `LastName`.</span></span>  
  
3. <span data-ttu-id="dc36b-110">Arrastre un <xref:System.Windows.Forms.MaskedTextBox> control al formulario; denomínelo `PhoneMask`.</span><span class="sxs-lookup"><span data-stu-id="dc36b-110">Drag a <xref:System.Windows.Forms.MaskedTextBox> control onto your form; name it `PhoneMask`.</span></span>  
  
4. <span data-ttu-id="dc36b-111">Establecer el <xref:System.Windows.Forms.MaskedTextBox.Mask%2A> propiedad de `PhoneMask` a `(000) 000-0000 x9999`.</span><span class="sxs-lookup"><span data-stu-id="dc36b-111">Set the <xref:System.Windows.Forms.MaskedTextBox.Mask%2A> property of `PhoneMask` to `(000) 000-0000 x9999`.</span></span>  
  
5. <span data-ttu-id="dc36b-112">Agregue que el siguiente espacio de nombres se importa al formulario.</span><span class="sxs-lookup"><span data-stu-id="dc36b-112">Add the following namespace imports to the form.</span></span>  
  
    ```csharp  
    using System.Data.SqlClient;  
    ```  
  
    ```vb  
    Imports System.Data.SqlClient  
    ```  
  
6. <span data-ttu-id="dc36b-113">Haga clic en el formulario y elija **ver código**.</span><span class="sxs-lookup"><span data-stu-id="dc36b-113">Right-click the form and choose **View Code**.</span></span> <span data-ttu-id="dc36b-114">Coloque este código en cualquier lugar en la clase de formulario.</span><span class="sxs-lookup"><span data-stu-id="dc36b-114">Place this code anywhere in your form class.</span></span>  
  
    ```csharp  
    Binding currentBinding, phoneBinding;  
    DataSet employeesTable = new DataSet();  
    SqlConnection sc;  
    SqlDataAdapter dataConnect;  
  
    private void Form1_Load(object sender, EventArgs e)  
    {  
        DoMaskBinding();  
    }  
  
    private void DoMaskBinding()  
    {  
        try  
        {  
            sc = new SqlConnection("Data Source=CLIENTUE;Initial Catalog=NORTHWIND;Integrated Security=SSPI");  
            sc.Open();  
        }  
        catch (Exception ex)  
        {  
            MessageBox.Show(ex.Message);  
            return;  
        }  
  
        dataConnect = new SqlDataAdapter("SELECT * FROM Employees", sc);  
        dataConnect.Fill(employeesTable, "Employees");  
  
        // Now bind MaskedTextBox to appropriate field. Note that we must create the Binding objects  
        // before adding them to the control - otherwise, we won't get a Format event on the   
        // initial load.   
        try  
        {  
            currentBinding = new Binding("Text", employeesTable, "Employees.FirstName");  
            firstName.DataBindings.Add(currentBinding);  
  
            currentBinding = new Binding("Text", employeesTable, "Employees.LastName");  
            lastName.DataBindings.Add(currentBinding);  
  
            phoneBinding =new Binding("Text", employeesTable, "Employees.HomePhone");  
            // We must add the event handlers before we bind, or the Format event will not get called  
            // for the first record.  
            phoneBinding.Format += new ConvertEventHandler(phoneBinding_Format);  
            phoneBinding.Parse += new ConvertEventHandler(phoneBinding_Parse);  
            phoneMask.DataBindings.Add(phoneBinding);  
        }  
        catch (Exception ex)  
        {  
            MessageBox.Show(ex.Message);  
            return;  
        }  
    }  
    ```  
  
    ```vb  
    Dim WithEvents CurrentBinding, PhoneBinding As Binding  
    Dim EmployeesTable As New DataSet()  
    Dim sc As SqlConnection  
    Dim DataConnect As SqlDataAdapter  
  
    Private Sub Form1_Load(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles MyBase.Load  
        DoMaskedBinding()  
    End Sub  
  
    Private Sub DoMaskedBinding()  
        Try  
            sc = New SqlConnection("Data Source=SERVERNAME;Initial Catalog=NORTHWIND;Integrated Security=SSPI")  
            sc.Open()  
        Catch ex As Exception  
            MessageBox.Show(ex.Message)  
            Exit Sub  
        End Try  
  
        DataConnect = New SqlDataAdapter("SELECT * FROM Employees", sc)  
        DataConnect.Fill(EmployeesTable, "Employees")  
  
        ' Now bind MaskedTextBox to appropriate field. Note that we must create the Binding objects  
        ' before adding them to the control - otherwise, we won't get a Format event on the   
        ' initial load.  
        Try  
            CurrentBinding = New Binding("Text", EmployeesTable, "Employees.FirstName")  
            firstName.DataBindings.Add(CurrentBinding)  
            CurrentBinding = New Binding("Text", EmployeesTable, "Employees.LastName")  
            lastName.DataBindings.Add(CurrentBinding)  
            PhoneBinding = New Binding("Text", EmployeesTable, "Employees.HomePhone")  
            PhoneMask.DataBindings.Add(PhoneBinding)  
        Catch ex As Exception  
            MessageBox.Show(ex.Message)  
            Application.Exit()  
        End Try  
    End Sub  
    ```  
  
7. <span data-ttu-id="dc36b-115">Agregar controladores de eventos para el <xref:System.Windows.Forms.Binding.Format> y <xref:System.Windows.Forms.Binding.Parse> eventos para combinar y separar la `PhoneNumber` y `Extension` campos desde el límite <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="dc36b-115">Add event handlers for the <xref:System.Windows.Forms.Binding.Format> and <xref:System.Windows.Forms.Binding.Parse> events to combine and separate the `PhoneNumber` and `Extension` fields from the bound <xref:System.Data.DataSet>.</span></span>  
  
    ```csharp  
    private void phoneBinding_Format(Object sender, ConvertEventArgs e)  
    {  
        String ext;  
  
        DataRowView currentRow = (DataRowView)BindingContext[employeesTable, "Employees"].Current;  
        if (currentRow["Extension"] == null)   
        {  
            ext = "";  
        } else   
        {  
            ext = currentRow["Extension"].ToString();  
        }  
  
        e.Value = e.Value.ToString().Trim() + " x" + ext;  
    }  
  
    private void phoneBinding_Parse(Object sender, ConvertEventArgs e)  
    {  
        String phoneNumberAndExt = e.Value.ToString();  
  
        int extIndex = phoneNumberAndExt.IndexOf("x");  
        String ext = phoneNumberAndExt.Substring(extIndex).Trim();  
        String phoneNumber = phoneNumberAndExt.Substring(0, extIndex).Trim();  
  
        //Get the current binding object, and set the new extension manually.   
        DataRowView currentRow = (DataRowView)BindingContext[employeesTable, "Employees"].Current;  
        // Remove the "x" from the extension.  
        currentRow["Extension"] = ext.Substring(1);  
  
        //Return the phone number.  
        e.Value = phoneNumber;  
    }  
    ```  
  
    ```vb  
    Private Sub PhoneBinding_Format(ByVal sender As Object, ByVal e As ConvertEventArgs) Handles PhoneBinding.Format  
        Dim Ext As String  
  
        Dim CurrentRow As DataRowView = CType(Me.BindingContext(EmployeesTable, "Employees").Current, DataRowView)  
        If (CurrentRow("Extension") Is Nothing) Then  
            Ext = ""  
        Else  
            Ext = CurrentRow("Extension").ToString()  
        End If  
  
        e.Value = e.Value.ToString().Trim() & " x" & Ext  
    End Sub  
  
    Private Sub PhoneBinding_Parse(ByVal sender As Object, ByVal e As ConvertEventArgs) Handles PhoneBinding.Parse  
        Dim PhoneNumberAndExt As String = e.Value.ToString()  
  
        Dim ExtIndex As Integer = PhoneNumberAndExt.IndexOf("x")  
        Dim Ext As String = PhoneNumberAndExt.Substring(ExtIndex).Trim()  
        Dim PhoneNumber As String = PhoneNumberAndExt.Substring(0, ExtIndex).Trim()  
  
        ' Get the current binding object, and set the new extension manually.   
        Dim CurrentRow As DataRowView = CType(Me.BindingContext(EmployeesTable, "Employees").Current, DataRowView)  
        ' Remove the "x" from the extension.  
        CurrentRow("Extension") = CObj(Ext.Substring(1))  
  
        ' Return the phone number.  
        e.Value = PhoneNumber  
    End Sub  
    ```  
  
8. <span data-ttu-id="dc36b-116">Agregue dos <xref:System.Windows.Forms.Button> controles al formulario.</span><span class="sxs-lookup"><span data-stu-id="dc36b-116">Add two <xref:System.Windows.Forms.Button> controls to the form.</span></span> <span data-ttu-id="dc36b-117">Denomínelos `previousButton` y `nextButton`.</span><span class="sxs-lookup"><span data-stu-id="dc36b-117">Name them `previousButton` and `nextButton`.</span></span> <span data-ttu-id="dc36b-118">Haga doble clic en cada botón para agregar un <xref:System.Windows.Forms.Control.Click> controlador de eventos y rellene los controladores de eventos, como se muestra en el siguiente ejemplo de código.</span><span class="sxs-lookup"><span data-stu-id="dc36b-118">Double-click each button to add a <xref:System.Windows.Forms.Control.Click> event handler, and fill in the event handlers as shown in the following code example.</span></span>  
  
    ```csharp  
    private void previousButton_Click(object sender, EventArgs e)  
    {  
        BindingContext[employeesTable, "Employees"].Position = BindingContext[employeesTable, "Employees"].Position - 1;  
    }  
  
    private void nextButton_Click(object sender, EventArgs e)  
    {  
        BindingContext[employeesTable, "Employees"].Position = BindingContext[employeesTable, "Employees"].Position + 1;  
    }  
    ```  
  
    ```vb  
    Private Sub PreviousButton_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles PreviousButton.Click  
        Me.BindingContext(EmployeesTable, "Employees").Position = Me.BindingContext(EmployeesTable, "Employees").Position - 1  
    End Sub  
  
    Private Sub NextButton_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles NextButton.Click  
        Me.BindingContext(EmployeesTable, "Employees").Position = Me.BindingContext(EmployeesTable, "Employees").Position + 1  
    End Sub  
    ```  
  
9. <span data-ttu-id="dc36b-119">Ejecute el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="dc36b-119">Run the sample.</span></span> <span data-ttu-id="dc36b-120">Edite los datos y use el **anterior** y **siguiente** botones para ver que los datos se guardan correctamente a la <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="dc36b-120">Edit the data, and use the **Previous** and **Next** buttons to see that the data is properly persisted to the <xref:System.Data.DataSet>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="dc36b-121">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="dc36b-121">Example</span></span>  
 <span data-ttu-id="dc36b-122">El ejemplo de código siguiente es la lista que resultan de completar el procedimiento anterior de código completo.</span><span class="sxs-lookup"><span data-stu-id="dc36b-122">The following code example is the full code listing that results from completing the previous procedure.</span></span>  
  
 [!code-cpp[MaskedTextBoxData#1](~/samples/snippets/cpp/VS_Snippets_Winforms/MaskedTextBoxData/cpp/form1.cpp#1)]
 [!code-csharp[MaskedTextBoxData#1](~/samples/snippets/csharp/VS_Snippets_Winforms/MaskedTextBoxData/CS/form1.cs#1)]
 [!code-vb[MaskedTextBoxData#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/MaskedTextBoxData/VB/form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="dc36b-123">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="dc36b-123">Compiling the Code</span></span>  
  
- <span data-ttu-id="dc36b-124">Crear un objeto Visual C# o proyecto de Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="dc36b-124">Create a Visual C# or Visual Basic project.</span></span>  
  
- <span data-ttu-id="dc36b-125">Agregar el <xref:System.Windows.Forms.TextBox> y <xref:System.Windows.Forms.MaskedTextBox> controles al formulario, como se describe en el procedimiento anterior.</span><span class="sxs-lookup"><span data-stu-id="dc36b-125">Add the <xref:System.Windows.Forms.TextBox> and <xref:System.Windows.Forms.MaskedTextBox> controls to the form, as described in the previous procedure.</span></span>  
  
- <span data-ttu-id="dc36b-126">Abra el archivo de código fuente para el formulario del proyecto predeterminado.</span><span class="sxs-lookup"><span data-stu-id="dc36b-126">Open the source code file for the project's default form.</span></span>  
  
- <span data-ttu-id="dc36b-127">Reemplace el código fuente en este archivo con el código que aparece en la sección "Código" anterior.</span><span class="sxs-lookup"><span data-stu-id="dc36b-127">Replace the source code in this file with the code listed in the previous "Code" section.</span></span>  
  
- <span data-ttu-id="dc36b-128">Compile la aplicación.</span><span class="sxs-lookup"><span data-stu-id="dc36b-128">Compile the application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dc36b-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="dc36b-129">See also</span></span>

- [<span data-ttu-id="dc36b-130">Tutorial: Trabajar con el Control MaskedTextBox</span><span class="sxs-lookup"><span data-stu-id="dc36b-130">Walkthrough: Working with the MaskedTextBox Control</span></span>](walkthrough-working-with-the-maskedtextbox-control.md)
