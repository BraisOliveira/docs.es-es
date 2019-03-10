---
title: 'Tutorial: Trabajar con el Control MaskedTextBox'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- input [Windows Forms], controlling to ensure validity
- MaskedTextBox control [Windows Forms], walkthroughs
- MaskedTextBox control [Windows Forms], validation
- user input [Windows Forms], controlling
- text [Windows Forms], controls for input
ms.assetid: df60565e-5447-4110-92a6-be1f6ff5faa3
ms.openlocfilehash: 9633f2f871d08b70d6286f510a9ba5cac78ae529
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2019
ms.locfileid: "57703093"
---
# <a name="walkthrough-working-with-the-maskedtextbox-control"></a><span data-ttu-id="00d85-102">Tutorial: Trabajar con el Control MaskedTextBox</span><span class="sxs-lookup"><span data-stu-id="00d85-102">Walkthrough: Working with the MaskedTextBox Control</span></span>
<span data-ttu-id="00d85-103">Las tareas ilustradas en este tutorial incluyen:</span><span class="sxs-lookup"><span data-stu-id="00d85-103">Tasks illustrated in this walkthrough include:</span></span>  
  
-   <span data-ttu-id="00d85-104">Inicializando el <xref:System.Windows.Forms.MaskedTextBox> control</span><span class="sxs-lookup"><span data-stu-id="00d85-104">Initializing the <xref:System.Windows.Forms.MaskedTextBox> control</span></span>  
  
-   <span data-ttu-id="00d85-105">Mediante el <xref:System.Windows.Forms.MaskedTextBox.MaskInputRejected> controlador de eventos para alertar al usuario cuando un carácter no es conforme a la máscara</span><span class="sxs-lookup"><span data-stu-id="00d85-105">Using the <xref:System.Windows.Forms.MaskedTextBox.MaskInputRejected> event handler to alert the user when a character does not conform to the mask</span></span>  
  
-   <span data-ttu-id="00d85-106">Asignar un tipo para el <xref:System.Windows.Forms.MaskedTextBox.ValidatingType%2A> propiedad y el uso de la <xref:System.Windows.Forms.MaskedTextBox.TypeValidationCompleted> controlador de eventos para alertar al usuario cuando el valor que se intenta confirmar no es válido para el tipo</span><span class="sxs-lookup"><span data-stu-id="00d85-106">Assigning a type to the <xref:System.Windows.Forms.MaskedTextBox.ValidatingType%2A> property and using the <xref:System.Windows.Forms.MaskedTextBox.TypeValidationCompleted> event handler to alert the user when the value they're attempting to commit is not valid for the type</span></span>  
  
## <a name="creating-the-project-and-adding-a-control"></a><span data-ttu-id="00d85-107">Crear el proyecto y agregar un Control</span><span class="sxs-lookup"><span data-stu-id="00d85-107">Creating the Project and Adding a Control</span></span>  
  
#### <a name="to-add-a-maskedtextbox-control-to-your-form"></a><span data-ttu-id="00d85-108">Para agregar un control MaskedTextBox al formulario</span><span class="sxs-lookup"><span data-stu-id="00d85-108">To add a MaskedTextBox control to your form</span></span>  
  
1.  <span data-ttu-id="00d85-109">Abra el formulario en el que desea colocar el <xref:System.Windows.Forms.MaskedTextBox> control.</span><span class="sxs-lookup"><span data-stu-id="00d85-109">Open the form on which you want to place the <xref:System.Windows.Forms.MaskedTextBox> control.</span></span>  
  
2.  <span data-ttu-id="00d85-110">Arrastre un <xref:System.Windows.Forms.MaskedTextBox> controlar desde la **cuadro de herramientas** al formulario.</span><span class="sxs-lookup"><span data-stu-id="00d85-110">Drag a <xref:System.Windows.Forms.MaskedTextBox> control from the **Toolbox** to your form.</span></span>  
  
3.  <span data-ttu-id="00d85-111">Haga clic en el control y elija **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="00d85-111">Right-click the control and choose **Properties**.</span></span> <span data-ttu-id="00d85-112">En el **propiedades** ventana, seleccione el **máscara** propiedad y haga clic en el **...**  () botón de puntos suspensivos junto al nombre de propiedad.</span><span class="sxs-lookup"><span data-stu-id="00d85-112">In the **Properties** window, select the **Mask** property and click the **...** (ellipsis) button next to the property name.</span></span>  
  
4.  <span data-ttu-id="00d85-113">En el **máscara de entrada** cuadro de diálogo, seleccione el **fecha corta** enmascarar y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="00d85-113">In the **Input Mask** dialog box, select the **Short Date** mask and click **OK**.</span></span>  
  
5.  <span data-ttu-id="00d85-114">En el **propiedades** ventana conjunto el <xref:System.Windows.Forms.MaskedTextBox.BeepOnError%2A> propiedad `true`.</span><span class="sxs-lookup"><span data-stu-id="00d85-114">In the **Properties** window set the <xref:System.Windows.Forms.MaskedTextBox.BeepOnError%2A> property to `true`.</span></span> <span data-ttu-id="00d85-115">Esta propiedad hace que un bip breve sonido cada vez que el usuario trata de un carácter que infringe la definición de la máscara de entrada.</span><span class="sxs-lookup"><span data-stu-id="00d85-115">This property causes a short beep to sound every time the user attempts to input a character that violates the mask definition.</span></span>  
  
 <span data-ttu-id="00d85-116">Para obtener un resumen de los caracteres compatibles con la propiedad de máscara, consulte la sección Comentarios de la <xref:System.Windows.Forms.MaskedTextBox.Mask%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="00d85-116">For a summary of the characters that the Mask property supports, see the Remarks section of the <xref:System.Windows.Forms.MaskedTextBox.Mask%2A> property.</span></span>  
  
## <a name="alert-the-user-to-input-errors"></a><span data-ttu-id="00d85-117">Alertar al usuario para errores de entrada</span><span class="sxs-lookup"><span data-stu-id="00d85-117">Alert the User to Input Errors</span></span>  
  
#### <a name="add-a-balloon-tip-for-rejected-mask-input"></a><span data-ttu-id="00d85-118">Agregar un globo de sugerencias para la entrada de máscara rechazadas</span><span class="sxs-lookup"><span data-stu-id="00d85-118">Add a balloon tip for rejected mask input</span></span>  
  
1.  <span data-ttu-id="00d85-119">Vuelva a la **cuadro de herramientas** y agregue un <xref:System.Windows.Forms.ToolTip> al formulario.</span><span class="sxs-lookup"><span data-stu-id="00d85-119">Return to the **Toolbox** and add a <xref:System.Windows.Forms.ToolTip> to your form.</span></span>  
  
2.  <span data-ttu-id="00d85-120">Crear un controlador de eventos para el <xref:System.Windows.Forms.MaskedTextBox.MaskInputRejected> eventos que provoca la <xref:System.Windows.Forms.ToolTip> cuando se produce un error de entrada.</span><span class="sxs-lookup"><span data-stu-id="00d85-120">Create an event handler for the <xref:System.Windows.Forms.MaskedTextBox.MaskInputRejected> event that raises the <xref:System.Windows.Forms.ToolTip> when an input error occurs.</span></span> <span data-ttu-id="00d85-121">El globo de sugerencias permanece visible durante cinco segundos, o hasta que el usuario hace clic en él.</span><span class="sxs-lookup"><span data-stu-id="00d85-121">The balloon tip remains visible for five seconds, or until the user clicks it.</span></span>  
  
    ```csharp  
    public void Form1_Load(Object sender, EventArgs e)   
    {  
        ... // Other initialization code  
        maskedTextBox1.Mask = "00/00/0000";  
        maskedTextBox1.MaskInputRejected += new MaskInputRejectedEventHandler(maskedTextBox1_MaskInputRejected)  
    }  
  
    void maskedTextBox1_MaskInputRejected(object sender, MaskInputRejectedEventArgs e)  
    {  
        toolTip1.ToolTipTitle = "Invalid Input";  
        toolTip1.Show("We're sorry, but only digits (0-9) are allowed in dates.", maskedTextBox1, maskedTextBox1.Location, 5000);  
    }  
    ```  
  
    ```vb  
    Private Sub Form1_Load(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles MyBase.Load  
        Me.ToolTip1.IsBalloon = True  
        Me.MaskedTextBox1.Mask = "00/00/0000"  
    End Sub  
  
    Private Sub MaskedTextBox1_MaskInputRejected(sender as Object, e as MaskInputRejectedEventArgs) Handles MaskedTextBox1.MaskInputRejected  
        ToolTip1.ToolTipTitle = "Invalid Input"  
        ToolTip1.Show("We're sorry, but only digits (0-9) are allowed in dates.", MaskedTextBox1, 5000)  
    End Sub  
    ```  
  
## <a name="alert-the-user-to-a-type-that-is-not-valid"></a><span data-ttu-id="00d85-122">Alertar al usuario a un tipo que no es válido</span><span class="sxs-lookup"><span data-stu-id="00d85-122">Alert the User to a Type that Is Not Valid</span></span>  
  
#### <a name="add-a-balloon-tip-for-invalid-data-types"></a><span data-ttu-id="00d85-123">Agregar un globo de sugerencias para los tipos de datos no válidos</span><span class="sxs-lookup"><span data-stu-id="00d85-123">Add a balloon tip for invalid data types</span></span>  
  
1.  <span data-ttu-id="00d85-124">En el formulario <xref:System.Windows.Forms.Form.Load> controlador de eventos, asigne un <xref:System.Type> objeto que representa el <xref:System.DateTime> escriba a la <xref:System.Windows.Forms.MaskedTextBox> del control <xref:System.Windows.Forms.MaskedTextBox.ValidatingType%2A> propiedad:</span><span class="sxs-lookup"><span data-stu-id="00d85-124">In your form's <xref:System.Windows.Forms.Form.Load> event handler, assign a <xref:System.Type> object representing the <xref:System.DateTime> type to the <xref:System.Windows.Forms.MaskedTextBox> control's <xref:System.Windows.Forms.MaskedTextBox.ValidatingType%2A> property:</span></span>  
  
    ```csharp  
    private void Form1_Load(Object sender, EventArgs e)  
    {  
        // Other code  
        maskedTextBox1.ValidatingType = typeof(System.DateTime);  
        maskedTextBox1.TypeValidationCompleted += new TypeValidationEventHandler(maskedTextBox1_TypeValidationCompleted);  
    }  
    ```  
  
    ```vb  
    Private Sub Form1_Load(sender as Object, e as EventArgs)  
        // Other code  
        MaskedTextBox1.ValidatingType = GetType(System.DateTime)  
    End Sub  
    ```  
  
2.  <span data-ttu-id="00d85-125">Agregue un controlador de eventos para el evento <xref:System.Windows.Forms.MaskedTextBox.TypeValidationCompleted>:</span><span class="sxs-lookup"><span data-stu-id="00d85-125">Add an event handler for the <xref:System.Windows.Forms.MaskedTextBox.TypeValidationCompleted> event:</span></span>  
  
    ```csharp  
    public void maskedTextBox1_TypeValidationCompleted(object sender, TypeValidationEventArgs e)  
    {  
        if (!e.IsValidInput)  
        {  
           toolTip1.ToolTipTitle = "Invalid Date Value";  
           toolTip1.Show("We're sorry, but the value you entered is not a valid date. Please change the value.", maskedTextBox1, 5000);  
           e.Cancel = true;  
        }  
    }  
    ```  
  
    ```vb  
    Public Sub MaskedTextBox1_TypeValidationCompleted(sender as Object, e as TypeValidationEventArgs)  
        If Not e.IsValidInput Then  
           ToolTip1.ToolTipTitle = "Invalid Date Value"  
           ToolTip1.Show("We're sorry, but the value you entered is not a valid date. Please change the value.", maskedTextBox1, 5000)  
           e.Cancel = True  
        End If  
    End Sub  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="00d85-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="00d85-126">See also</span></span>
- <xref:System.Windows.Forms.MaskedTextBox>
- [<span data-ttu-id="00d85-127">MaskedTextBox (control)</span><span class="sxs-lookup"><span data-stu-id="00d85-127">MaskedTextBox Control</span></span>](maskedtextbox-control-windows-forms.md)
