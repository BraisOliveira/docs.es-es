---
title: Procedimiento para mostrar la vista preliminar en aplicaciones de formularios Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- print preview [Windows Forms], displaying
- printing [Windows Forms], print preview
- examples [Windows Forms], print preview
ms.assetid: e394134c-0886-4517-bd8d-edc4a3749eb5
ms.openlocfilehash: 22247c941eff575f0f3e5683e46376054ba13bb5
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59154367"
---
# <a name="how-to-display-print-preview-in-windows-forms-applications"></a><span data-ttu-id="f1a50-102">Procedimiento para mostrar la vista preliminar en aplicaciones de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f1a50-102">How to: Display Print Preview in Windows Forms Applications</span></span>
<span data-ttu-id="f1a50-103">Puede usar el <xref:System.Windows.Forms.PrintPreviewDialog> control para permitir que los usuarios mostrar un documento, a menudo antes de que se imprimen.</span><span class="sxs-lookup"><span data-stu-id="f1a50-103">You can use the <xref:System.Windows.Forms.PrintPreviewDialog> control to enable users to display a document, often before it is to be printed.</span></span>  
  
 <span data-ttu-id="f1a50-104">Para ello, deberá especificar una instancia de la <xref:System.Drawing.Printing.PrintDocument> clase; se trata de imprimir el documento.</span><span class="sxs-lookup"><span data-stu-id="f1a50-104">To do this, you need to specify an instance of the <xref:System.Drawing.Printing.PrintDocument> class; this is the document to be printed.</span></span> <span data-ttu-id="f1a50-105">Para obtener más información sobre el uso de vista previa de impresión con la <xref:System.Drawing.Printing.PrintDocument> componente, vea [Cómo: Impresión en Windows Forms a través de la vista previa de impresión](../advanced/how-to-print-in-windows-forms-using-print-preview.md).</span><span class="sxs-lookup"><span data-stu-id="f1a50-105">For more information about using print preview with the <xref:System.Drawing.Printing.PrintDocument> component, see [How to: Print in Windows Forms Using Print Preview](../advanced/how-to-print-in-windows-forms-using-print-preview.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f1a50-106">Para usar el <xref:System.Windows.Forms.PrintPreviewDialog> control en tiempo de ejecución, los usuarios deben tener una impresora instalada en su equipo, ya sea localmente o a través de una red, ya que es parcialmente la <xref:System.Windows.Forms.PrintPreviewDialog> componente determina el aspecto de un documento cuando se imprima.</span><span class="sxs-lookup"><span data-stu-id="f1a50-106">To use the <xref:System.Windows.Forms.PrintPreviewDialog> control at run time, users must have a printer installed on their computer, either locally or through a network, as this is partly how the <xref:System.Windows.Forms.PrintPreviewDialog> component determines how a document will look when printed.</span></span>  
  
 <span data-ttu-id="f1a50-107">El <xref:System.Windows.Forms.PrintPreviewDialog> control usa el <xref:System.Drawing.Printing.PrinterSettings> clase.</span><span class="sxs-lookup"><span data-stu-id="f1a50-107">The <xref:System.Windows.Forms.PrintPreviewDialog> control uses the <xref:System.Drawing.Printing.PrinterSettings> class.</span></span> <span data-ttu-id="f1a50-108">Además, el <xref:System.Windows.Forms.PrintPreviewDialog> control usa el <xref:System.Drawing.Printing.PageSettings> (clase), al igual que el <xref:System.Windows.Forms.PrintPreviewDialog> componente.</span><span class="sxs-lookup"><span data-stu-id="f1a50-108">Additionally, the <xref:System.Windows.Forms.PrintPreviewDialog> control uses the <xref:System.Drawing.Printing.PageSettings> class, just as the <xref:System.Windows.Forms.PrintPreviewDialog> component does.</span></span> <span data-ttu-id="f1a50-109">El documento de impresión especificado en el <xref:System.Windows.Forms.PrintPreviewDialog> del control <xref:System.Windows.Forms.PrintPreviewControl.Document%2A> propiedad hace referencia a las instancias de ambos el <xref:System.Drawing.Printing.PrinterSettings> y <xref:System.Drawing.Printing.PageSettings> clases y estos se utilizan para representar el documento en la ventana Vista previa.</span><span class="sxs-lookup"><span data-stu-id="f1a50-109">The print document specified in the <xref:System.Windows.Forms.PrintPreviewDialog> control's <xref:System.Windows.Forms.PrintPreviewControl.Document%2A> property refers to instances of both the <xref:System.Drawing.Printing.PrinterSettings> and <xref:System.Drawing.Printing.PageSettings> classes, and these are used to render the document in the preview window.</span></span>  
  
### <a name="to-view-pages-using-the-printpreviewdialog-control"></a><span data-ttu-id="f1a50-110">Para ver las páginas mediante el control PrintPreviewDialog</span><span class="sxs-lookup"><span data-stu-id="f1a50-110">To view pages using the PrintPreviewDialog control</span></span>  
  
-   <span data-ttu-id="f1a50-111">Use el método <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> para mostrar el cuadro de diálogo, especificando el <xref:System.Drawing.Printing.PrintDocument> que se va a usar.</span><span class="sxs-lookup"><span data-stu-id="f1a50-111">Use the <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> method to display the dialog box, specifying the <xref:System.Drawing.Printing.PrintDocument> to use.</span></span>  
  
     <span data-ttu-id="f1a50-112">En el ejemplo de código siguiente, la <xref:System.Windows.Forms.Button> del control <xref:System.Windows.Forms.Control.Click> controlador de eventos abre una instancia de la <xref:System.Windows.Forms.PrintPreviewDialog> control.</span><span class="sxs-lookup"><span data-stu-id="f1a50-112">In the following code example, the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Click> event handler opens an instance of the <xref:System.Windows.Forms.PrintPreviewDialog> control.</span></span> <span data-ttu-id="f1a50-113">El documento de impresión se especifica en el <xref:System.Windows.Forms.PrintDialog.Document%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="f1a50-113">The print document is specified in the <xref:System.Windows.Forms.PrintDialog.Document%2A> property.</span></span> <span data-ttu-id="f1a50-114">En el ejemplo siguiente, no se especifica ningún documento para imprimirlo.</span><span class="sxs-lookup"><span data-stu-id="f1a50-114">In the example below, no print document is specified.</span></span>  
  
     <span data-ttu-id="f1a50-115">El ejemplo requiere que el formulario tiene un <xref:System.Windows.Forms.Button> (control), un <xref:System.Drawing.Printing.PrintDocument> componente denominado `myDocument`y un <xref:System.Windows.Forms.PrintPreviewDialog> control.</span><span class="sxs-lookup"><span data-stu-id="f1a50-115">The example requires that your form has a <xref:System.Windows.Forms.Button> control, a <xref:System.Drawing.Printing.PrintDocument> component named `myDocument`, and a <xref:System.Windows.Forms.PrintPreviewDialog> control.</span></span>  
  
    ```vb  
    Private Sub Button1_Click(ByVal sender As System.Object, _  
       ByVal e As System.EventArgs) Handles Button1.Click  
       ' The print document 'myDocument' used below  
       ' is merely for an example.  
       ' You will have to specify your own print document.  
       PrintPreviewDialog1.Document = myDocument  
       PrintPreviewDialog1.ShowDialog()  
    End Sub  
    ```  
  
    ```csharp  
    private void button1_Click(object sender, System.EventArgs e)  
    {  
       // The print document 'myDocument' used below  
       // is merely for an example.  
       // You will have to specify your own print document.  
       printPreviewDialog1.Document = myDocument;  
       printPreviewDialog1.ShowDialog();  
    }  
    ```  
  
    ```cpp  
    private:  
       void button1_Click(System::Object ^ sender,  
          System::EventArgs ^ e)  
       {  
          // The print document 'myDocument' used below  
          // is merely for an example.  
          // You will have to specify your own print document.  
          printPreviewDialog1->Document = myDocument;  
          printPreviewDialog1->ShowDialog();  
       }  
    ```  
  
     <span data-ttu-id="f1a50-116">(Visual C#, [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) coloque el código siguiente en el constructor del formulario para registrar el controlador de eventos.</span><span class="sxs-lookup"><span data-stu-id="f1a50-116">(Visual C#, [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) Place the following code in the form's constructor to register the event handler.</span></span>  
  
    ```csharp  
    this.button1.Click += new System.EventHandler(this.button1_Click);  
    ```  
  
    ```cpp  
    this->button1->Click += gcnew  
       System::EventHandler(this, &Form1::button1_Click);  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="f1a50-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="f1a50-117">See also</span></span>

- [<span data-ttu-id="f1a50-118">PrintDocument (Componente, Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="f1a50-118">PrintDocument Component</span></span>](printdocument-component-windows-forms.md)
- [<span data-ttu-id="f1a50-119">PrintPreviewDialog (control)</span><span class="sxs-lookup"><span data-stu-id="f1a50-119">PrintPreviewDialog Control</span></span>](printpreviewdialog-control-windows-forms.md)
- <span data-ttu-id="f1a50-120">[Windows Forms Print Support](../advanced/windows-forms-print-support.md) (Funcionalidad para imprimir en Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="f1a50-120">[Windows Forms Print Support](../advanced/windows-forms-print-support.md)</span></span>
- [<span data-ttu-id="f1a50-121">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f1a50-121">Windows Forms</span></span>](../index.md)
