---
title: Procedimiento Crear un arco elíptico
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [WPF], elliptical arcs
- elliptical arcs [WPF], creating
- arcs [WPF], elliptical
ms.assetid: 3dcfe502-3485-45de-99fb-d53a1367c484
ms.openlocfilehash: aae304b9963f3a8e5833b4d8ba0a54777a750225
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62003371"
---
# <a name="how-to-create-an-elliptical-arc"></a><span data-ttu-id="3557c-102">Procedimiento Crear un arco elíptico</span><span class="sxs-lookup"><span data-stu-id="3557c-102">How to: Create an Elliptical Arc</span></span>
<span data-ttu-id="3557c-103">En este ejemplo se muestra cómo dibujar un arco elíptico. Para crear un arco elíptico, utilice el <xref:System.Windows.Media.PathGeometry>, <xref:System.Windows.Media.PathFigure>, y <xref:System.Windows.Media.ArcSegment> clases.</span><span class="sxs-lookup"><span data-stu-id="3557c-103">This example shows how to draw an elliptical arc. To create an elliptical arc, use the <xref:System.Windows.Media.PathGeometry>, <xref:System.Windows.Media.PathFigure>, and <xref:System.Windows.Media.ArcSegment> classes.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3557c-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="3557c-104">Example</span></span>  
 <span data-ttu-id="3557c-105">En los ejemplos siguientes, se dibuja un arco elíptico desde (10,100) hasta (200,100).</span><span class="sxs-lookup"><span data-stu-id="3557c-105">In the following examples, an elliptical arc is drawn from (10,100) to (200,100).</span></span> <span data-ttu-id="3557c-106">El arco tiene un <xref:System.Windows.Media.ArcSegment.Size%2A> de 100 por 50 píxeles independientes del dispositivo un <xref:System.Windows.Media.ArcSegment.RotationAngle%2A> de 45 grados, un <xref:System.Windows.Media.ArcSegment.IsLargeArc%2A> de `true`y un <xref:System.Windows.Media.ArcSegment.SweepDirection%2A> de <xref:System.Windows.Media.SweepDirection.Counterclockwise>.</span><span class="sxs-lookup"><span data-stu-id="3557c-106">The arc has a <xref:System.Windows.Media.ArcSegment.Size%2A> of 100 by 50 device-independent pixels, a <xref:System.Windows.Media.ArcSegment.RotationAngle%2A> of 45 degrees, an <xref:System.Windows.Media.ArcSegment.IsLargeArc%2A> setting of `true`, and a <xref:System.Windows.Media.ArcSegment.SweepDirection%2A> of <xref:System.Windows.Media.SweepDirection.Counterclockwise>.</span></span>  
  
 <span data-ttu-id="3557c-107">[xaml]</span><span class="sxs-lookup"><span data-stu-id="3557c-107">[xaml]</span></span>  
  
 <span data-ttu-id="3557c-108">En [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], puede usar la sintaxis de atributo para describir una ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="3557c-108">In [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], you can use attribute syntax to describe a path.</span></span>  
  
 [!code-xaml[GeometrySample#56](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/geometryattributesyntaxexample.xaml#56)]  
  
 <span data-ttu-id="3557c-109">[xaml]</span><span class="sxs-lookup"><span data-stu-id="3557c-109">[xaml]</span></span>  
  
 <span data-ttu-id="3557c-110">(Tenga en cuenta que esta sintaxis de atributo se crea en realidad un <xref:System.Windows.Media.StreamGeometry>, una versión ligera de un <xref:System.Windows.Media.PathGeometry>.</span><span class="sxs-lookup"><span data-stu-id="3557c-110">(Note that this attribute syntax actually creates a <xref:System.Windows.Media.StreamGeometry>, a lighter-weight version of a <xref:System.Windows.Media.PathGeometry>.</span></span> <span data-ttu-id="3557c-111">Para más información, consulte la página [Sintaxis de marcado de trazados](path-markup-syntax.md)).</span><span class="sxs-lookup"><span data-stu-id="3557c-111">For more information, see the [Path Markup Syntax](path-markup-syntax.md) page.)</span></span>  
  
 <span data-ttu-id="3557c-112">En [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], también puede dibujar un arco elíptico explícitamente mediante etiquetas de objeto.</span><span class="sxs-lookup"><span data-stu-id="3557c-112">In [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], you can also draw an elliptical arc by explicitly using object tags.</span></span> <span data-ttu-id="3557c-113">La siguiente es equivalente al anterior [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] marcado.</span><span class="sxs-lookup"><span data-stu-id="3557c-113">The following is equivalent to the preceding [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] markup.</span></span>  
  
 [!code-xaml[GeometrySample#36](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/pathgeometryexample.xaml#36)]  
  
 <span data-ttu-id="3557c-114">Este ejemplo forma parte de un ejemplo mayor.</span><span class="sxs-lookup"><span data-stu-id="3557c-114">This example is part of a larger sample.</span></span> <span data-ttu-id="3557c-115">Para obtener un ejemplo completo, vea el [ejemplo de geometrías](https://go.microsoft.com/fwlink/?LinkID=159989).</span><span class="sxs-lookup"><span data-stu-id="3557c-115">For the complete sample, see the [Geometries Sample](https://go.microsoft.com/fwlink/?LinkID=159989).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3557c-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="3557c-116">See also</span></span>

- [<span data-ttu-id="3557c-117">Crear una curva Bézier cuadrática</span><span class="sxs-lookup"><span data-stu-id="3557c-117">Create a Quadratic Bezier Curve</span></span>](how-to-create-a-quadratic-bezier-curve.md)
- [<span data-ttu-id="3557c-118">Crear una curva Bézier cúbica</span><span class="sxs-lookup"><span data-stu-id="3557c-118">Create a Cubic Bezier Curve</span></span>](how-to-create-a-cubic-bezier-curve.md)
