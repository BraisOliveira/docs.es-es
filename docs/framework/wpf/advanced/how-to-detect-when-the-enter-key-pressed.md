---
title: Filtrar Detectar cuando la escriba tecla presionada
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Enter key [WPF], detecting
- keys [WPF], Enter
ms.assetid: a66f39d2-ef4a-43a5-b454-a4ea0fe88655
ms.openlocfilehash: a99da5804bbc31897198b9b6d9e21da9f17dfe26
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59204619"
---
# <a name="how-to-detect-when-the-enter-key-pressed"></a><span data-ttu-id="2217a-102">Filtrar Detectar cuando la escriba tecla presionada</span><span class="sxs-lookup"><span data-stu-id="2217a-102">How to: Detect When the Enter Key Pressed</span></span>
<span data-ttu-id="2217a-103">En este ejemplo se muestra cómo detectar cuándo el <xref:System.Windows.Input.Key.Enter> se presiona la tecla del teclado.</span><span class="sxs-lookup"><span data-stu-id="2217a-103">This example shows how to detect when the <xref:System.Windows.Input.Key.Enter> key is pressed on the keyboard.</span></span>  
  
 <span data-ttu-id="2217a-104">Este ejemplo consta de un [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] archivo y un archivo de código subyacente.</span><span class="sxs-lookup"><span data-stu-id="2217a-104">This example consists of a [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] file and a code-behind file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2217a-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="2217a-105">Example</span></span>  
 <span data-ttu-id="2217a-106">Cuando el usuario presiona el <xref:System.Windows.Input.Key.Enter> clave en el <xref:System.Windows.Controls.TextBox>, la entrada en el cuadro de texto aparece en otra área de la [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2217a-106">When the user presses the <xref:System.Windows.Input.Key.Enter> key in the <xref:System.Windows.Controls.TextBox>, the input in the text box appears in another area of the [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)].</span></span>  
  
 <span data-ttu-id="2217a-107">La siguiente [!INCLUDE[TLA2#tla_titlexaml](../../../../includes/tla2sharptla-titlexaml-md.md)] crea la interfaz de usuario, que consta de un <xref:System.Windows.Controls.StackPanel>, un <xref:System.Windows.Controls.TextBlock>y un <xref:System.Windows.Controls.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="2217a-107">The following [!INCLUDE[TLA2#tla_titlexaml](../../../../includes/tla2sharptla-titlexaml-md.md)] creates the user interface, which consists of a <xref:System.Windows.Controls.StackPanel>, a <xref:System.Windows.Controls.TextBlock>, and a <xref:System.Windows.Controls.TextBox>.</span></span>  
  
 [!code-xaml[keydown#KeyDownUI](~/samples/snippets/csharp/VS_Snippets_Wpf/KeyDown/CSharp/Window1.xaml#keydownui)]  
  
 <span data-ttu-id="2217a-108">El código subyacente siguiente crea el <xref:System.Windows.UIElement.KeyDown> controlador de eventos.</span><span class="sxs-lookup"><span data-stu-id="2217a-108">The following code behind creates the <xref:System.Windows.UIElement.KeyDown> event handler.</span></span>  <span data-ttu-id="2217a-109">Si es la clave que se presiona el <xref:System.Windows.Input.Key.Enter> clave, se muestra un mensaje en el <xref:System.Windows.Controls.TextBlock>.</span><span class="sxs-lookup"><span data-stu-id="2217a-109">If the key that is pressed is the <xref:System.Windows.Input.Key.Enter> key, a message is displayed in the <xref:System.Windows.Controls.TextBlock>.</span></span>  
  
 [!code-csharp[keydown#KeyDownSample](~/samples/snippets/csharp/VS_Snippets_Wpf/KeyDown/CSharp/Window1.xaml.cs#keydownsample)]
 [!code-vb[keydown#KeyDownSample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/KeyDown/VisualBasic/Window1.xaml.vb#keydownsample)]  
  
## <a name="see-also"></a><span data-ttu-id="2217a-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="2217a-110">See also</span></span>

- [<span data-ttu-id="2217a-111">Información general sobre acciones del usuario</span><span class="sxs-lookup"><span data-stu-id="2217a-111">Input Overview</span></span>](input-overview.md)
- [<span data-ttu-id="2217a-112">Información general sobre eventos enrutados</span><span class="sxs-lookup"><span data-stu-id="2217a-112">Routed Events Overview</span></span>](routed-events-overview.md)
