---
title: Procedimiento Colocar el cursor al principio o al final del texto de un control TextBox
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- positioning cursor [WPF]
- TextBox control [WPF], positioning cursor
- cursor [WPF], positioning
ms.assetid: c771a0b8-c6b4-4240-aecd-a21d0ba51a2e
ms.openlocfilehash: 3d7da5daf09e06938b8366e0f5f98a599cae4571
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61770622"
---
# <a name="how-to-position-the-cursor-at-the-beginning-or-end-of-text-in-a-textbox-control"></a><span data-ttu-id="cd70e-102">Procedimiento Colocar el cursor al principio o al final del texto de un control TextBox</span><span class="sxs-lookup"><span data-stu-id="cd70e-102">How to: Position the Cursor at the Beginning or End of Text in a TextBox Control</span></span>
<span data-ttu-id="cd70e-103">En este ejemplo se muestra cómo colocar el cursor al principio o al final del contenido de texto de un <xref:System.Windows.Controls.TextBox> control.</span><span class="sxs-lookup"><span data-stu-id="cd70e-103">This example shows how to position the cursor at the beginning or end of the text contents of a <xref:System.Windows.Controls.TextBox> control.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cd70e-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="cd70e-104">Example</span></span>  
 <span data-ttu-id="cd70e-105">La siguiente [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] código describe una <xref:System.Windows.Controls.TextBox> controlar y le asigna un nombre.</span><span class="sxs-lookup"><span data-stu-id="cd70e-105">The following [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] code describes a <xref:System.Windows.Controls.TextBox> control and assigns it a Name.</span></span>  
  
 [!code-xaml[TextBox_MiscCode#_MoveCursorXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml#_movecursorxaml)]  
  
## <a name="example"></a><span data-ttu-id="cd70e-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="cd70e-106">Example</span></span>  
 <span data-ttu-id="cd70e-107">Para colocar el cursor al principio del contenido de un <xref:System.Windows.Controls.TextBox> control, llame a la <xref:System.Windows.Controls.TextBox.Select%2A> método y especificar la selección de inicio la posición 0 y una longitud de selección de 0.</span><span class="sxs-lookup"><span data-stu-id="cd70e-107">To position the cursor at the beginning of the contents of a <xref:System.Windows.Controls.TextBox> control, call the <xref:System.Windows.Controls.TextBox.Select%2A> method and specify the selection start position of 0, and a selection length of 0.</span></span>  
  
 [!code-csharp[TextBox_MiscCode#_CursorToStart](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml.cs#_cursortostart)]
 [!code-vb[TextBox_MiscCode#_CursorToStart](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextBox_MiscCode/VisualBasic/Window1.xaml.vb#_cursortostart)]  
  
## <a name="example"></a><span data-ttu-id="cd70e-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="cd70e-108">Example</span></span>  
 <span data-ttu-id="cd70e-109">Para colocar el cursor al final del contenido de un <xref:System.Windows.Controls.TextBox> control, llame a la <xref:System.Windows.Controls.TextBox.Select%2A> método y especificar la posición inicial igual a la longitud del contenido de texto y una longitud de selección de 0.</span><span class="sxs-lookup"><span data-stu-id="cd70e-109">To position the cursor at the end of the contents of a <xref:System.Windows.Controls.TextBox> control, call the <xref:System.Windows.Controls.TextBox.Select%2A> method and specify the selection start position equal to the  length of the text content, and a selection length of 0.</span></span>  
  
 [!code-csharp[TextBox_MiscCode#_CursorToEnd](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml.cs#_cursortoend)]
 [!code-vb[TextBox_MiscCode#_CursorToEnd](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextBox_MiscCode/VisualBasic/Window1.xaml.vb#_cursortoend)]  
  
## <a name="see-also"></a><span data-ttu-id="cd70e-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="cd70e-110">See also</span></span>

- [<span data-ttu-id="cd70e-111">Información general sobre TextBox</span><span class="sxs-lookup"><span data-stu-id="cd70e-111">TextBox Overview</span></span>](textbox-overview.md)
- <span data-ttu-id="cd70e-112">[RichTextBox Overview](richtextbox-overview.md) (Introducción a RichTextBox)</span><span class="sxs-lookup"><span data-stu-id="cd70e-112">[RichTextBox Overview](richtextbox-overview.md)</span></span>
