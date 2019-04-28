---
title: Procedimiento Animar un objeto a lo largo de un trazado (animación en matriz con acumulación de desplazamiento)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- offset accumulation [WPF]
- animation [WPF], objects along paths (matrix animation with offset accumulation)
- matrix animation with offset accumulation [WPF]
ms.assetid: 1bca90ef-9832-4128-8ed6-62908e7ec146
ms.openlocfilehash: 3e7b892e2a2215d26512850477844d71bce7fe09
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61922699"
---
# <a name="how-to-animate-an-object-along-a-path-matrix-animation-with-offset-accumulation"></a><span data-ttu-id="884a6-102">Procedimiento Animar un objeto a lo largo de un trazado (animación en matriz con acumulación de desplazamiento)</span><span class="sxs-lookup"><span data-stu-id="884a6-102">How to: Animate an Object Along a Path (Matrix Animation with Offset Accumulation)</span></span>
<span data-ttu-id="884a6-103">En este ejemplo se muestra cómo usar el <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> clase para animar un objeto a lo largo de una ruta de acceso y hacer que dicha animación su desplazamiento se acumulan los valores de medida que se repite.</span><span class="sxs-lookup"><span data-stu-id="884a6-103">This example shows how to use the <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> class to animate an object along a path and have that animation accumulate its offset values as it repeats.</span></span>  
  
## <a name="example"></a><span data-ttu-id="884a6-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="884a6-104">Example</span></span>  
 <span data-ttu-id="884a6-105">En el ejemplo siguiente se usa el <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> objeto que se va a animar el <xref:System.Windows.Media.MatrixTransform.Matrix%2A> propiedad de un <xref:System.Windows.Media.MatrixTransform> aplicada a un botón.</span><span class="sxs-lookup"><span data-stu-id="884a6-105">The following example uses the <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> object to animate the <xref:System.Windows.Media.MatrixTransform.Matrix%2A> property of a <xref:System.Windows.Media.MatrixTransform> applied to a button.</span></span> <span data-ttu-id="884a6-106">Como resultado, un botón se mueve a lo largo de un trazado curvo.</span><span class="sxs-lookup"><span data-stu-id="884a6-106">As a result, a button moves along a curved path.</span></span>  
  
 <span data-ttu-id="884a6-107">Además, el ejemplo establece la <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.IsOffsetCumulative%2A> propiedad `true`, lo que hace que el desplazamiento de la matriz animada se acumulen como la animación se repite.</span><span class="sxs-lookup"><span data-stu-id="884a6-107">In addition, the example sets the <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.IsOffsetCumulative%2A> property to `true`, which causes the offset of the animated matrix to accumulate as the animation repeats.</span></span> <span data-ttu-id="884a6-108">Dado que el desplazamiento se acumula, el botón se aleja por la pantalla cuando se repite la animación, en lugar de restablecerse a la posición inicial.</span><span class="sxs-lookup"><span data-stu-id="884a6-108">Because the offset accumulates, the button moves farther across the screen when the animation repeats, rather than resetting to the starting position.</span></span>  
  
 [!code-xaml[PathAnimationGallery_snippet#MatrixAnimationUsingPathOffsetCumulativeWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_snippet/CS/matrixanimationusingpathexampleoffsetcumulative.xaml#matrixanimationusingpathoffsetcumulativewholepage)]  
  
 [!code-csharp[PathAnimationGallery_procedural_snip#MatrixAnimationUsingPathOffsetCumulativeWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/CSharp/MatrixAnimationUsingPathExampleOffsetCumulative.cs#matrixanimationusingpathoffsetcumulativewholepage)]
 [!code-vb[PathAnimationGallery_procedural_snip#MatrixAnimationUsingPathOffsetCumulativeWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/VisualBasic/MatrixAnimationUsingPathExampleOffsetCumulative.vb#matrixanimationusingpathoffsetcumulativewholepage)]  
  
 <span data-ttu-id="884a6-109">Tenga en cuenta que, aunque el <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.IsOffsetCumulative%2A> propiedad hace que los valores de desplazamiento se acumulen con repeticiones, no hace que los valores de rotación se acumulen.</span><span class="sxs-lookup"><span data-stu-id="884a6-109">Note that, although the <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.IsOffsetCumulative%2A> property causes offset values to accumulate over repetitions, it doesn't cause rotation values to accumulate.</span></span> <span data-ttu-id="884a6-110">Para que los valores de rotación se acumulen, establezca la animación <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.DoesRotateWithTangent%2A> y <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.IsAngleCumulative%2A> propiedades a `true`.</span><span class="sxs-lookup"><span data-stu-id="884a6-110">To make rotation values accumulate, set the animation's <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.DoesRotateWithTangent%2A> and <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.IsAngleCumulative%2A> properties to `true`.</span></span>  
  
 <span data-ttu-id="884a6-111">Para obtener un ejemplo completo, vea [ejemplo de animación de trazado](https://go.microsoft.com/fwlink/?LinkID=160028).</span><span class="sxs-lookup"><span data-stu-id="884a6-111">For the complete sample, see [Path Animation Sample](https://go.microsoft.com/fwlink/?LinkID=160028).</span></span> <span data-ttu-id="884a6-112">Para obtener un ejemplo que muestra cómo animar una <xref:System.Windows.Media.Matrix> a lo largo de un trazado sin acumulación de desplazamiento de valor, vea [animar un objeto a lo largo de un trazado (animación en matriz)](how-to-animate-an-object-along-a-path-matrix-animation.md).</span><span class="sxs-lookup"><span data-stu-id="884a6-112">For an example showing how to animate a <xref:System.Windows.Media.Matrix> value along a path without offset accumulation, see [Animate an Object Along a Path (Matrix Animation)](how-to-animate-an-object-along-a-path-matrix-animation.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="884a6-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="884a6-113">See also</span></span>

- [<span data-ttu-id="884a6-114">Información general sobre animaciones</span><span class="sxs-lookup"><span data-stu-id="884a6-114">Animation Overview</span></span>](animation-overview.md)
- [<span data-ttu-id="884a6-115">Temas de procedimientos de animación de trazado</span><span class="sxs-lookup"><span data-stu-id="884a6-115">Path Animation How-to Topics</span></span>](path-animation-how-to-topics.md)
