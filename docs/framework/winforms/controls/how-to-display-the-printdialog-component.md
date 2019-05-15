---
title: Cómo mostrar el componente PrintDialog
ms.date: 03/30/2017
helpviewer_keywords:
- Print dialog box [Windows Forms], displaying
- PrintDialog component [Windows Forms], displaying
- printing [Windows Forms], displaying print dialog box
ms.assetid: 745a8db7-0526-4b21-b09d-18e13ed32014
ms.openlocfilehash: de0acc655bbcf0cfc017d594545fae56cc27f981
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "65637451"
---
# <a name="how-to-display-the-printdialog-component"></a><span data-ttu-id="1c804-102">Cómo mostrar el componente PrintDialog</span><span class="sxs-lookup"><span data-stu-id="1c804-102">How to display the PrintDialog component</span></span>

<span data-ttu-id="1c804-103">El <xref:System.Windows.Forms.PrintDialog> componente es el cuadro de diálogo de impresión de Windows estándar que muchos de los usuarios estarán familiarizados con.</span><span class="sxs-lookup"><span data-stu-id="1c804-103">The <xref:System.Windows.Forms.PrintDialog> component is the standard Windows print dialog box that many of your users will be familiar with.</span></span> <span data-ttu-id="1c804-104">Dado que los usuarios cómodos con él, le resultará beneficioso para su uso el <xref:System.Windows.Forms.PrintDialog> componente.</span><span class="sxs-lookup"><span data-stu-id="1c804-104">Because your users will be immediately comfortable with it, it would be beneficial for you to use the <xref:System.Windows.Forms.PrintDialog> component.</span></span>

## <a name="to-display-the-printdialog-component"></a><span data-ttu-id="1c804-105">Mostrar el componente PrintDialog</span><span class="sxs-lookup"><span data-stu-id="1c804-105">To display the PrintDialog component</span></span>

- <span data-ttu-id="1c804-106">Llame a la <xref:System.Windows.Forms.Form.ShowDialog%2A> método desde el código de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="1c804-106">Call the <xref:System.Windows.Forms.Form.ShowDialog%2A> method from within the code of your application.</span></span>

     <span data-ttu-id="1c804-107">Una vez que se muestre el componente, los usuarios interactuarán con él y establecerán las propiedades del trabajo de impresión.</span><span class="sxs-lookup"><span data-stu-id="1c804-107">Once the component is shown, users will interact with it, setting the properties of the print job.</span></span> <span data-ttu-id="1c804-108">Éstas se guardan en el <xref:System.Drawing.Printing.PrinterSettings> clase (y el <xref:System.Drawing.Printing.PageSettings> clase, si el usuario tiene acceso a la [componente PageSetupDialog](pagesetupdialog-component-windows-forms.md) a través de la <xref:System.Windows.Forms.PrintDialog> componente) asociado con ese trabajo de impresión.</span><span class="sxs-lookup"><span data-stu-id="1c804-108">These are saved in the  <xref:System.Drawing.Printing.PrinterSettings> class (and the <xref:System.Drawing.Printing.PageSettings> class, if the user accesses the [PageSetupDialog Component](pagesetupdialog-component-windows-forms.md) through the <xref:System.Windows.Forms.PrintDialog> component) associated with that print job.</span></span> <span data-ttu-id="1c804-109">A continuación, puede realizar llamadas a las propiedades que establecen para determinar los detalles del trabajo de impresión.</span><span class="sxs-lookup"><span data-stu-id="1c804-109">You can then make calls to the properties they set to determine the specifics of the print job.</span></span>

## <a name="see-also"></a><span data-ttu-id="1c804-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="1c804-110">See also</span></span>

- [<span data-ttu-id="1c804-111">Cómo: Crear trabajos de impresión estándar de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="1c804-111">How to: Create Standard Windows Forms Print Jobs</span></span>](../advanced/how-to-create-standard-windows-forms-print-jobs.md)
- [<span data-ttu-id="1c804-112">Cómo: Captura de datos de usuario de un componente PrintDialog en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="1c804-112">How to: Capture User Input from a PrintDialog at Run Time</span></span>](../advanced/how-to-capture-user-input-from-a-printdialog-at-run-time.md)
- [<span data-ttu-id="1c804-113">PrintPreviewDialog (control)</span><span class="sxs-lookup"><span data-stu-id="1c804-113">PrintPreviewDialog Control</span></span>](printpreviewdialog-control-windows-forms.md)
- [<span data-ttu-id="1c804-114">PrintDialog (componente)</span><span class="sxs-lookup"><span data-stu-id="1c804-114">PrintDialog Component</span></span>](printdialog-component-windows-forms.md)
- <span data-ttu-id="1c804-115">[Windows Forms Print Support](../advanced/windows-forms-print-support.md) (Funcionalidad para imprimir en Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="1c804-115">[Windows Forms Print Support](../advanced/windows-forms-print-support.md)</span></span>
- [<span data-ttu-id="1c804-116">Controles de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="1c804-116">Windows Forms Controls</span></span>](index.md)
