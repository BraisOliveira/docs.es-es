---
title: Procedimiento Guardar, cargar e imprimir contenido de un control RichTextBox
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- saving RichTextBox controls [WPF]
- printing RichTextBox controls [WPF]
- loading RichTextBox controls [WPF]
- RichTextBox control [WPF], saving
- RichTextBox control [WPF], printing
- RichTextBox control [WPF], loading
ms.assetid: ffb113d3-c68a-47ca-8ac0-882283f38326
ms.openlocfilehash: 90581bee7815dafd44c3cae18a8af7394fee1e9a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61910603"
---
# <a name="how-to-save-load-and-print-richtextbox-content"></a><span data-ttu-id="afb4a-102">Procedimiento Guardar, cargar e imprimir contenido de un control RichTextBox</span><span class="sxs-lookup"><span data-stu-id="afb4a-102">How to: Save, Load, and Print RichTextBox Content</span></span>
<span data-ttu-id="afb4a-103">El ejemplo siguiente muestra cómo guardar el contenido de un <xref:System.Windows.Controls.RichTextBox> en un archivo, cargar ese contenido de nuevo en el <xref:System.Windows.Controls.RichTextBox>e imprimir el contenido.</span><span class="sxs-lookup"><span data-stu-id="afb4a-103">The following example shows how to save content of a <xref:System.Windows.Controls.RichTextBox> to a file, load that content back into the <xref:System.Windows.Controls.RichTextBox>, and print the contents.</span></span>  
  
## <a name="example"></a><span data-ttu-id="afb4a-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="afb4a-104">Example</span></span>  
 <span data-ttu-id="afb4a-105">A continuación, se muestra el marcado para el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="afb4a-105">Below is the markup for the example.</span></span>  
  
 [!code-xaml[RichTextBoxMiscSnippets_snip#SaveLoadPrintRTBExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/RichTextBoxMiscSnippets_snip/CSharp/SaveLoadPrintRTB.xaml#saveloadprintrtbexamplewholepage)]  
  
## <a name="example"></a><span data-ttu-id="afb4a-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="afb4a-106">Example</span></span>  
 <span data-ttu-id="afb4a-107">A continuación, se muestra el código subyacente para el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="afb4a-107">Below is the code behind for the example.</span></span>  
  
 [!code-csharp[RichTextBoxMiscSnippets_snip#SaveLoadPrintRTBCodeExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/RichTextBoxMiscSnippets_snip/CSharp/SaveLoadPrintRTB.xaml.cs#saveloadprintrtbcodeexamplewholepage)]
 [!code-vb[RichTextBoxMiscSnippets_snip#SaveLoadPrintRTBCodeExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/RichTextBoxMiscSnippets_snip/VisualBasic/SaveLoadPrintRTB.xaml.vb#saveloadprintrtbcodeexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="afb4a-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="afb4a-108">See also</span></span>

- <span data-ttu-id="afb4a-109">[RichTextBox Overview](richtextbox-overview.md) (Introducción a RichTextBox)</span><span class="sxs-lookup"><span data-stu-id="afb4a-109">[RichTextBox Overview](richtextbox-overview.md)</span></span>
- [<span data-ttu-id="afb4a-110">Información general sobre TextBox</span><span class="sxs-lookup"><span data-stu-id="afb4a-110">TextBox Overview</span></span>](textbox-overview.md)
