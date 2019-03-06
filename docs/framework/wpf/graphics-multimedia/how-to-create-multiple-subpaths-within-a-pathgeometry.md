---
title: Procedimiento Crear varios subtrazados en un PathGeometry
ms.date: 03/30/2017
helpviewer_keywords:
- multiple subpaths [WPF]
- graphics [WPF], subpaths
- subpaths [WPF]
ms.assetid: 104a862c-dde2-4e62-ac87-80660dd1681c
ms.openlocfilehash: 0b57d0441c1aa9d5972af1f1c6b989aacba7f87f
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2019
ms.locfileid: "57353379"
---
# <a name="how-to-create-multiple-subpaths-within-a-pathgeometry"></a><span data-ttu-id="627ac-102">Filtrar Crear varios subtrazados en un PathGeometry</span><span class="sxs-lookup"><span data-stu-id="627ac-102">How to: Create Multiple Subpaths Within a PathGeometry</span></span>
<span data-ttu-id="627ac-103">En este ejemplo se muestra cómo crear varios subtrazados en un <xref:System.Windows.Media.PathGeometry>.</span><span class="sxs-lookup"><span data-stu-id="627ac-103">This example shows how to create multiple subpaths in a <xref:System.Windows.Media.PathGeometry>.</span></span> <span data-ttu-id="627ac-104">Para crear varios subtrazados, cree un <xref:System.Windows.Media.PathFigure> para cada subtrazado.</span><span class="sxs-lookup"><span data-stu-id="627ac-104">To create multiple subpaths, you create a <xref:System.Windows.Media.PathFigure> for each subpath.</span></span>  
  
## <a name="example"></a><span data-ttu-id="627ac-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="627ac-105">Example</span></span>  
 <span data-ttu-id="627ac-106">El ejemplo siguiente crea dos subtrazados, cada uno de ellos un triángulo.</span><span class="sxs-lookup"><span data-stu-id="627ac-106">The following example creates two subpaths, each one a triangle.</span></span>  
  
 [!code-xaml[GeometrySample#38](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/pathgeometryexample.xaml#38)]  
  
 <span data-ttu-id="627ac-107">El ejemplo siguiente muestra cómo crear varios subtrazados mediante un <xref:System.Windows.Shapes.Path> y [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] sintaxis de atributo.</span><span class="sxs-lookup"><span data-stu-id="627ac-107">The following example shows how to create multiple subpaths by using a <xref:System.Windows.Shapes.Path> and [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] attribute syntax.</span></span> <span data-ttu-id="627ac-108">Cada `M` crea una subruta de acceso nuevo para que el ejemplo crea dos subtrazados cada dibuja un triángulo.</span><span class="sxs-lookup"><span data-stu-id="627ac-108">Each `M` creates a new subpath so that the example creates two subpaths that each draw a triangle.</span></span>  
  
 [!code-xaml[GeometrySample#58](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/geometryattributesyntaxexample.xaml#58)]  
  
 <span data-ttu-id="627ac-109">(Tenga en cuenta que esta sintaxis de atributo se crea en realidad un <xref:System.Windows.Media.StreamGeometry>, una versión ligera de un <xref:System.Windows.Media.PathGeometry>.</span><span class="sxs-lookup"><span data-stu-id="627ac-109">(Note that this attribute syntax actually creates a <xref:System.Windows.Media.StreamGeometry>, a lighter-weight version of a <xref:System.Windows.Media.PathGeometry>.</span></span> <span data-ttu-id="627ac-110">Para más información, consulte la página [Sintaxis de marcado de trazados](path-markup-syntax.md)).</span><span class="sxs-lookup"><span data-stu-id="627ac-110">For more information, see the [Path Markup Syntax](path-markup-syntax.md) page.)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="627ac-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="627ac-111">See also</span></span>
- [<span data-ttu-id="627ac-112">Información general sobre geometría</span><span class="sxs-lookup"><span data-stu-id="627ac-112">Geometry Overview</span></span>](geometry-overview.md)
