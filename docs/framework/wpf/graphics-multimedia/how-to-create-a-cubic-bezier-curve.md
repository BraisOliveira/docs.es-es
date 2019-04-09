---
title: Filtrar Crear una curva Bézier cúbica
ms.date: 03/30/2017
helpviewer_keywords:
- curves [WPF], cubic Bezier
- Bezier curves [WPF], cubic
- graphics [WPF], cubic Bezier curves
- cubic Bezier curves [WPF]
ms.assetid: 450a3a77-7c57-48b0-a008-0f6051add980
ms.openlocfilehash: 36544abc774b7fe82c2ff47483cfedd6fb13e344
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59115575"
---
# <a name="how-to-create-a-cubic-bezier-curve"></a><span data-ttu-id="b0ff2-102">Filtrar Crear una curva Bézier cúbica</span><span class="sxs-lookup"><span data-stu-id="b0ff2-102">How to: Create a Cubic Bezier Curve</span></span>
<span data-ttu-id="b0ff2-103">En este ejemplo se muestra cómo crear una curva Bézier cúbica.</span><span class="sxs-lookup"><span data-stu-id="b0ff2-103">This example shows how to create a cubic Bezier curve.</span></span> <span data-ttu-id="b0ff2-104">Para crear una curva Bézier cúbica, use el <xref:System.Windows.Media.PathGeometry>, <xref:System.Windows.Media.PathFigure>, y <xref:System.Windows.Media.BezierSegment> clases.</span><span class="sxs-lookup"><span data-stu-id="b0ff2-104">To create a cubic Bezier curve, use the <xref:System.Windows.Media.PathGeometry>, <xref:System.Windows.Media.PathFigure>, and <xref:System.Windows.Media.BezierSegment> classes.</span></span>  <span data-ttu-id="b0ff2-105">Para mostrar la geometría resultante, utilice un <xref:System.Windows.Shapes.Path> elemento, o utilizarlo con un <xref:System.Windows.Media.GeometryDrawing> o <xref:System.Windows.Media.DrawingContext>.</span><span class="sxs-lookup"><span data-stu-id="b0ff2-105">To display the resulting geometry, use a <xref:System.Windows.Shapes.Path> element, or use it with a <xref:System.Windows.Media.GeometryDrawing> or a <xref:System.Windows.Media.DrawingContext>.</span></span> <span data-ttu-id="b0ff2-106">En los ejemplos siguientes, se dibuja una curva Bézier cúbica desde (10, 100) a (300, 100).</span><span class="sxs-lookup"><span data-stu-id="b0ff2-106">In the following examples, a cubic Bezier curve is drawn from (10, 100) to (300, 100).</span></span> <span data-ttu-id="b0ff2-107">La curva tiene puntos de control de (100, 0) y (200, 200).</span><span class="sxs-lookup"><span data-stu-id="b0ff2-107">The curve has control points of (100, 0) and (200, 200).</span></span>  
  
## <a name="example"></a><span data-ttu-id="b0ff2-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="b0ff2-108">Example</span></span>  
 <span data-ttu-id="b0ff2-109">[xaml]</span><span class="sxs-lookup"><span data-stu-id="b0ff2-109">[xaml]</span></span>  
  
 <span data-ttu-id="b0ff2-110">En [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], puede utilizar la sintaxis de marcado abreviada para describir una ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="b0ff2-110">In [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], you may use abbreviated markup syntax to describe a path.</span></span>  
  
 [!code-xaml[GeometrySample#53](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/geometryattributesyntaxexample.xaml#53)]  
  
 <span data-ttu-id="b0ff2-111">[xaml]</span><span class="sxs-lookup"><span data-stu-id="b0ff2-111">[xaml]</span></span>  
  
 <span data-ttu-id="b0ff2-112">En [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], también puede dibujar una curva Bézier cúbica mediante etiquetas de objeto.</span><span class="sxs-lookup"><span data-stu-id="b0ff2-112">In [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], you can also draw a cubic Bezier curve using object tags.</span></span> <span data-ttu-id="b0ff2-113">El siguiente ejemplo es equivalente al ejemplo anterior de [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b0ff2-113">The following is equivalent to the previous [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] example.</span></span>  
  
 [!code-xaml[GeometrySample#33](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/pathgeometryexample.xaml#33)]  
  
 <span data-ttu-id="b0ff2-114">Este ejemplo forma parte de un ejemplo más extenso; para obtener el ejemplo completo, vea [Ejemplo de geometrías](https://go.microsoft.com/fwlink/?LinkID=159989).</span><span class="sxs-lookup"><span data-stu-id="b0ff2-114">This example is part of larger sample; for the complete sample, see the [Geometries Sample](https://go.microsoft.com/fwlink/?LinkID=159989).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b0ff2-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="b0ff2-115">See also</span></span>

- [<span data-ttu-id="b0ff2-116">Crear un arco elíptico</span><span class="sxs-lookup"><span data-stu-id="b0ff2-116">Create an Elliptical Arc</span></span>](how-to-create-an-elliptical-arc.md)
- [<span data-ttu-id="b0ff2-117">Crear un LineSegment en una clase PathGeometry</span><span class="sxs-lookup"><span data-stu-id="b0ff2-117">Create a LineSegment in a PathGeometry</span></span>](how-to-create-a-linesegment-in-a-pathgeometry.md)
- [<span data-ttu-id="b0ff2-118">Crear una curva Bézier cúbica</span><span class="sxs-lookup"><span data-stu-id="b0ff2-118">Create a Cubic Bezier Curve</span></span>](how-to-create-a-cubic-bezier-curve.md)
- [<span data-ttu-id="b0ff2-119">Crear una curva Bézier cuadrática</span><span class="sxs-lookup"><span data-stu-id="b0ff2-119">Create a Quadratic Bezier Curve</span></span>](how-to-create-a-quadratic-bezier-curve.md)
