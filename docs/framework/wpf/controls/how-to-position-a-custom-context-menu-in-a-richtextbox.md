---
title: Filtrar Colocar un menú contextual personalizado en un control RichTextBox
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- custom context menus [WPF], positioning
- positioning custom context menus [WPF]
- RichTextBox control [WPF], positioning custom context menus
- context menus [WPF], positioning
ms.assetid: bf77c930-a546-4573-9a56-9af345ba189a
ms.openlocfilehash: f9407f59c3daafd09fa5b84006f33ef2f3ebd31f
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59209429"
---
# <a name="how-to-position-a-custom-context-menu-in-a-richtextbox"></a><span data-ttu-id="00ca7-102">Filtrar Colocar un menú contextual personalizado en un control RichTextBox</span><span class="sxs-lookup"><span data-stu-id="00ca7-102">How to: Position a Custom Context Menu in a RichTextBox</span></span>
<span data-ttu-id="00ca7-103">En este ejemplo se muestra cómo colocar un menú contextual personalizado para un <xref:System.Windows.Controls.RichTextBox>.</span><span class="sxs-lookup"><span data-stu-id="00ca7-103">This example shows how to position a custom context menu for a <xref:System.Windows.Controls.RichTextBox>.</span></span>  
  
 <span data-ttu-id="00ca7-104">Cuando se implementa un menú contextual personalizado para un control **RichTextBox**, es responsable del control de la posición del menú contextual.</span><span class="sxs-lookup"><span data-stu-id="00ca7-104">When you implement a custom context menu for a **RichTextBox**, you are responsible for handling the placement of the context menu.</span></span>  <span data-ttu-id="00ca7-105">De forma predeterminada, se abre un menú contextual personalizado en el centro del control **RichTextBox**.</span><span class="sxs-lookup"><span data-stu-id="00ca7-105">By default, a custom context menu is opened at the center of the **RichTextBox**.</span></span>  
  
## <a name="example"></a><span data-ttu-id="00ca7-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="00ca7-106">Example</span></span>  
 <span data-ttu-id="00ca7-107">Para invalidar el comportamiento de colocación predeterminado, agregue un agente de escucha para el <xref:System.Windows.FrameworkContentElement.ContextMenuOpening> eventos.</span><span class="sxs-lookup"><span data-stu-id="00ca7-107">To override the default placement behavior, add a listener for the <xref:System.Windows.FrameworkContentElement.ContextMenuOpening> event.</span></span>  <span data-ttu-id="00ca7-108">En el ejemplo siguiente se muestra hacer esto mediante programación.</span><span class="sxs-lookup"><span data-stu-id="00ca7-108">The following example shows how to do this programmatically.</span></span>  
  
 [!code-csharp[RichTextBox_ContextMenu#_AddListener](~/samples/snippets/csharp/VS_Snippets_Wpf/RichTextBox_ContextMenu/CSharp/app.xaml.cs#_addlistener)]
 [!code-vb[RichTextBox_ContextMenu#_AddListener](~/samples/snippets/visualbasic/VS_Snippets_Wpf/RichTextBox_ContextMenu/VisualBasic/app.xaml.vb#_addlistener)]  
  
## <a name="example"></a><span data-ttu-id="00ca7-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="00ca7-109">Example</span></span>  
 <span data-ttu-id="00ca7-110">El ejemplo siguiente muestra una implementación correspondiente <xref:System.Windows.FrameworkContentElement.ContextMenuOpening> escucha de eventos.</span><span class="sxs-lookup"><span data-stu-id="00ca7-110">The following example shows an implementation the corresponding <xref:System.Windows.FrameworkContentElement.ContextMenuOpening> event listener.</span></span>  
  
 [!code-csharp[RichTextBox_ContextMenu#_ListenerBody](~/samples/snippets/csharp/VS_Snippets_Wpf/RichTextBox_ContextMenu/CSharp/app.xaml.cs#_listenerbody)]
 [!code-vb[RichTextBox_ContextMenu#_ListenerBody](~/samples/snippets/visualbasic/VS_Snippets_Wpf/RichTextBox_ContextMenu/VisualBasic/app.xaml.vb#_listenerbody)]  
  
## <a name="see-also"></a><span data-ttu-id="00ca7-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="00ca7-111">See also</span></span>

- [<span data-ttu-id="00ca7-112">Información general sobre el control RichTextBox</span><span class="sxs-lookup"><span data-stu-id="00ca7-112">RichTextBox Overview</span></span>](richtextbox-overview.md)
- [<span data-ttu-id="00ca7-113">Información general sobre TextBox</span><span class="sxs-lookup"><span data-stu-id="00ca7-113">TextBox Overview</span></span>](textbox-overview.md)
