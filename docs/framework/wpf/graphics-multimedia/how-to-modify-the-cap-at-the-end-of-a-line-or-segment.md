---
title: Filtrar Modificar el extremo en el final de una línea o segmento
ms.date: 03/30/2017
helpviewer_keywords:
- Shape elements [WPF], ends
- Shape elements [WPF], caps
- graphics [WPF], Shape caps
ms.assetid: f4bf3416-b3d8-4568-b98e-3eda8f6dbf7a
ms.openlocfilehash: ba61b30b4ff575bb504f792f8990bbfc64a6c33e
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2019
ms.locfileid: "57371481"
---
# <a name="how-to-modify-the-cap-at-the-end-of-a-line-or-segment"></a><span data-ttu-id="3ce2f-102">Filtrar Modificar el extremo en el final de una línea o segmento</span><span class="sxs-lookup"><span data-stu-id="3ce2f-102">How to: Modify the Cap at the End of a Line or Segment</span></span>
<span data-ttu-id="3ce2f-103">En este ejemplo se muestra cómo modificar la forma al principio o al final de una abierta <xref:System.Windows.Shapes.Shape> elemento.</span><span class="sxs-lookup"><span data-stu-id="3ce2f-103">This example shows how to modify the shape at the start or end of an open <xref:System.Windows.Shapes.Shape> element.</span></span> <span data-ttu-id="3ce2f-104">Para cambiar el límite del principio de abierto <xref:System.Windows.Shapes.Shape>, use su <xref:System.Windows.Shapes.Shape.StrokeStartLineCap%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="3ce2f-104">To change the cap at the beginning of an open <xref:System.Windows.Shapes.Shape>, use its <xref:System.Windows.Shapes.Shape.StrokeStartLineCap%2A> property.</span></span> <span data-ttu-id="3ce2f-105">Para cambiar el límite al final de una abierta <xref:System.Windows.Shapes.Shape>, use su <xref:System.Windows.Shapes.Shape.StrokeEndLineCap%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="3ce2f-105">To change the cap at the end of an open <xref:System.Windows.Shapes.Shape>, use its <xref:System.Windows.Shapes.Shape.StrokeEndLineCap%2A> property.</span></span> <span data-ttu-id="3ce2f-106">Para ver los extremos de línea disponibles, consulte el <xref:System.Windows.Media.PenLineCap> enumeración.</span><span class="sxs-lookup"><span data-stu-id="3ce2f-106">To view the available line caps, see the <xref:System.Windows.Media.PenLineCap> enumeration.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3ce2f-107">Esta propiedad solo afecta a una forma abierta, como un <xref:System.Windows.Shapes.Line>, un <xref:System.Windows.Shapes.Polyline>, o una apertura <xref:System.Windows.Shapes.Path> elemento.</span><span class="sxs-lookup"><span data-stu-id="3ce2f-107">This property only affects an open shape, such as a <xref:System.Windows.Shapes.Line>, a <xref:System.Windows.Shapes.Polyline>, or an open <xref:System.Windows.Shapes.Path> element.</span></span>  
  
 <span data-ttu-id="3ce2f-108">En el ejemplo siguiente se dibuja cuatro <xref:System.Windows.Shapes.Polyline> elementos y utiliza un conjunto diferente de las formas en los extremos de cada uno.</span><span class="sxs-lookup"><span data-stu-id="3ce2f-108">The following example draws four <xref:System.Windows.Shapes.Polyline> elements and uses a different set of shapes on the ends of each.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3ce2f-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="3ce2f-109">Example</span></span>  
 [!code-xaml[drawingwithshapeelements#ShapeLineCaps1](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/linecapsandjoinsexample.xaml#shapelinecaps1)]  
  
 <span data-ttu-id="3ce2f-110">Este ejemplo forma parte de un ejemplo más extenso; Para obtener un ejemplo completo, vea [Shape Elements Sample](https://go.microsoft.com/fwlink/?LinkID=160037).</span><span class="sxs-lookup"><span data-stu-id="3ce2f-110">This example is part of a larger sample; for the complete sample, see [Shape Elements Sample](https://go.microsoft.com/fwlink/?LinkID=160037).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3ce2f-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="3ce2f-111">See also</span></span>
- <xref:System.Windows.Shapes.Polyline>
- <xref:System.Windows.Media.PenLineCap>
