---
title: Filtrar Agregar adornos a elementos secundarios de un panel
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- adorners [WPF], binding to children of Panels
- Panel control [WPF], binding adorners to children
ms.assetid: 4cc9b972-b472-4e5c-bdf3-3702d7fbb1f5
ms.openlocfilehash: 9f840180edf55c3e10e6859dfc2b9f4b6495b878
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2019
ms.locfileid: "57358202"
---
# <a name="how-to-adorn-the-children-of-a-panel"></a><span data-ttu-id="dd1af-102">Procedimiento Agregar adornos a elementos secundarios de un panel</span><span class="sxs-lookup"><span data-stu-id="dd1af-102">How to: Adorn the Children of a Panel</span></span>
<span data-ttu-id="dd1af-103">En este ejemplo se muestra cómo enlazar mediante programación un adorno a los elementos secundarios de un determinado <xref:System.Windows.Controls.Panel>.</span><span class="sxs-lookup"><span data-stu-id="dd1af-103">This example shows how to programmatically bind an adorner to the children of a specified <xref:System.Windows.Controls.Panel>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="dd1af-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="dd1af-104">Example</span></span>  
 <span data-ttu-id="dd1af-105">Para enlazar un adorno a los elementos secundarios de un <xref:System.Windows.Controls.Panel>, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="dd1af-105">To bind an adorner to the children of a <xref:System.Windows.Controls.Panel>, follow these steps:</span></span>  
  
1.  <span data-ttu-id="dd1af-106">Declarar un nuevo <xref:System.Windows.Documents.AdornerLayer> objeto y llamar a la `static` <xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A> método para buscar una capa de adornos para el elemento cuyos elementos secundarios desea adornar.</span><span class="sxs-lookup"><span data-stu-id="dd1af-106">Declare a new <xref:System.Windows.Documents.AdornerLayer> object and call the `static`<xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A> method to find an adorner layer for the element whose children are to be adorned.</span></span>  
  
2.  <span data-ttu-id="dd1af-107">Enumere los elementos secundarios del elemento primario y llamada la <xref:System.Windows.Documents.AdornerLayer.Add%2A> método para enlazar un adorno a cada elemento secundario.</span><span class="sxs-lookup"><span data-stu-id="dd1af-107">Enumerate through the children of the parent element and call the <xref:System.Windows.Documents.AdornerLayer.Add%2A> method to bind an adorner to each child element.</span></span>  
  
 <span data-ttu-id="dd1af-108">El ejemplo siguiente enlaza el adorno SimpleCircleAdorner (mostrado anteriormente) a los elementos secundarios de un <xref:System.Windows.Controls.StackPanel> denominado *myStackPanel*.</span><span class="sxs-lookup"><span data-stu-id="dd1af-108">The following example binds a SimpleCircleAdorner (shown above) to the children of a <xref:System.Windows.Controls.StackPanel> named *myStackPanel*.</span></span>  
  
 [!code-csharp[Adorners_SimpleCircleAdorner#_AdornChildren](~/samples/snippets/csharp/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/CSharp/Window1.xaml.cs#_adornchildren)]
 [!code-vb[Adorners_SimpleCircleAdorner#_AdornChildren](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/VisualBasic/Window1.xaml.vb#_adornchildren)]  
  
> [!NOTE]
>  <span data-ttu-id="dd1af-109">En la actualidad, no se admite el uso de [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] para enlazar un adorno a otro elemento.</span><span class="sxs-lookup"><span data-stu-id="dd1af-109">Using [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] to bind an adorner to another element is currently not supported.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dd1af-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="dd1af-110">See also</span></span>
- [<span data-ttu-id="dd1af-111">Información general sobre adornos</span><span class="sxs-lookup"><span data-stu-id="dd1af-111">Adorners Overview</span></span>](adorners-overview.md)
