---
title: Procedimiento Establecer el foco en un control TextBox
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- focus [WPF], setting
- TextBox control [WPF], setting focus
ms.assetid: 24b61b45-dc2d-425e-9839-b017af7ab86f
ms.openlocfilehash: f4ba367ea9bdfcd6dbab7a5015472ec33adfe46f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62024357"
---
# <a name="how-to-set-focus-in-a-textbox-control"></a><span data-ttu-id="35e91-102">Procedimiento Establecer el foco en un control TextBox</span><span class="sxs-lookup"><span data-stu-id="35e91-102">How to: Set Focus in a TextBox Control</span></span>
<span data-ttu-id="35e91-103">En este ejemplo se muestra cómo usar el <xref:System.Windows.UIElement.Focus%2A> método para establecer el foco en un <xref:System.Windows.Controls.TextBox> control.</span><span class="sxs-lookup"><span data-stu-id="35e91-103">This example shows how to use the <xref:System.Windows.UIElement.Focus%2A> method to set focus on a <xref:System.Windows.Controls.TextBox> control.</span></span>  
  
## <a name="example"></a><span data-ttu-id="35e91-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="35e91-104">Example</span></span>  
 <span data-ttu-id="35e91-105">La siguiente [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] en el ejemplo se describe una sencilla <xref:System.Windows.Controls.TextBox> control denominado *tbFocusMe*</span><span class="sxs-lookup"><span data-stu-id="35e91-105">The following [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] example describes a simple <xref:System.Windows.Controls.TextBox> control named *tbFocusMe*</span></span>  
  
 [!code-xaml[TextBox_MiscCode#_TextBoxFocusXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml#_textboxfocusxaml)]  
  
## <a name="example"></a><span data-ttu-id="35e91-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="35e91-106">Example</span></span>  
 <span data-ttu-id="35e91-107">El ejemplo siguiente se llama el <xref:System.Windows.UIElement.Focus%2A> método para establecer el foco en el <xref:System.Windows.Controls.TextBox> control con el nombre *tbFocusMe*.</span><span class="sxs-lookup"><span data-stu-id="35e91-107">The following example calls the <xref:System.Windows.UIElement.Focus%2A> method to set the focus on the <xref:System.Windows.Controls.TextBox> control with the Name *tbFocusMe*.</span></span>  
  
 [!code-csharp[TextBox_MiscCode#_FocusTextBox](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml.cs#_focustextbox)]
 [!code-vb[TextBox_MiscCode#_FocusTextBox](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextBox_MiscCode/VisualBasic/Window1.xaml.vb#_focustextbox)]  
  
## <a name="see-also"></a><span data-ttu-id="35e91-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="35e91-108">See also</span></span>

- <xref:System.Windows.UIElement.Focusable%2A>
- <xref:System.Windows.UIElement.IsFocused%2A>
- [<span data-ttu-id="35e91-109">Información general sobre TextBox</span><span class="sxs-lookup"><span data-stu-id="35e91-109">TextBox Overview</span></span>](textbox-overview.md)
- <span data-ttu-id="35e91-110">[RichTextBox Overview](richtextbox-overview.md) (Introducción a RichTextBox)</span><span class="sxs-lookup"><span data-stu-id="35e91-110">[RichTextBox Overview](richtextbox-overview.md)</span></span>
