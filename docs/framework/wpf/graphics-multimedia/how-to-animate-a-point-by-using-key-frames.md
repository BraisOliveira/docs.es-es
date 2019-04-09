---
title: Filtrar Animar un punto mediante fotogramas clave
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- key frames [WPF], animating Points with
- Points [WPF], animating with key frames
- animation [WPF], Points with key frames
ms.assetid: d2e2ef10-0773-4133-856e-d41c09f60ded
ms.openlocfilehash: 2e34ba035c8d7f9132915a9269d545f32033cbed
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59132592"
---
# <a name="how-to-animate-a-point-by-using-key-frames"></a><span data-ttu-id="8a29b-102">Filtrar Animar un punto mediante fotogramas clave</span><span class="sxs-lookup"><span data-stu-id="8a29b-102">How to: Animate a Point by Using Key Frames</span></span>
<span data-ttu-id="8a29b-103">En este ejemplo se muestra cómo usar el <xref:System.Windows.Media.Animation.PointAnimationUsingKeyFrames> clase para animar un <xref:System.Windows.Point>.</span><span class="sxs-lookup"><span data-stu-id="8a29b-103">This example shows how to use the <xref:System.Windows.Media.Animation.PointAnimationUsingKeyFrames> class to animate a <xref:System.Windows.Point>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8a29b-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="8a29b-104">Example</span></span>  
 <span data-ttu-id="8a29b-105">En el ejemplo siguiente se mueve una elipse a lo largo de un trazado triangular.</span><span class="sxs-lookup"><span data-stu-id="8a29b-105">The following example moves an ellipse along a triangular path.</span></span> <span data-ttu-id="8a29b-106">El ejemplo se usa el <xref:System.Windows.Media.Animation.PointAnimationUsingKeyFrames> clase se va a animar el <xref:System.Windows.Media.EllipseGeometry.Center%2A> propiedad de un <xref:System.Windows.Media.EllipseGeometry>.</span><span class="sxs-lookup"><span data-stu-id="8a29b-106">The example uses the <xref:System.Windows.Media.Animation.PointAnimationUsingKeyFrames> class to animate the <xref:System.Windows.Media.EllipseGeometry.Center%2A> property of an <xref:System.Windows.Media.EllipseGeometry>.</span></span> <span data-ttu-id="8a29b-107">Esta animación utiliza tres fotogramas clave de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="8a29b-107">This animation uses three key frames in the following manner:</span></span>  
  
1.  <span data-ttu-id="8a29b-108">Durante el primer medio segundo, utiliza una instancia de la <xref:System.Windows.Media.Animation.LinearPointKeyFrame> clase para mover la elipse a lo largo de una ruta de acceso a un ritmo constante desde su posición inicial.</span><span class="sxs-lookup"><span data-stu-id="8a29b-108">During the first half second, uses an instance of the <xref:System.Windows.Media.Animation.LinearPointKeyFrame> class to move the ellipse along a path at a steady rate from its starting position.</span></span> <span data-ttu-id="8a29b-109">Los fotogramas clave lineales como <xref:System.Windows.Media.Animation.LinearPointKeyFrame> crean una interpolación lineal suave entre valores.</span><span class="sxs-lookup"><span data-stu-id="8a29b-109">Linear key frames like <xref:System.Windows.Media.Animation.LinearPointKeyFrame> create a smooth linear interpolation between values.</span></span>  
  
2.  <span data-ttu-id="8a29b-110">Durante el fin de la siguiente medio segundo, utiliza una instancia de la <xref:System.Windows.Media.Animation.DiscretePointKeyFrame> clase para mover repentinamente la elipse a lo largo de la ruta de acceso a la siguiente posición.</span><span class="sxs-lookup"><span data-stu-id="8a29b-110">During the end of the next half second, uses an instance of the <xref:System.Windows.Media.Animation.DiscretePointKeyFrame> class to suddenly move the ellipse along the path to the next position.</span></span> <span data-ttu-id="8a29b-111">Los fotogramas clave discretos como <xref:System.Windows.Media.Animation.DiscretePointKeyFrame> crean saltos súbitos entre los valores.</span><span class="sxs-lookup"><span data-stu-id="8a29b-111">Discrete key frames like <xref:System.Windows.Media.Animation.DiscretePointKeyFrame> create sudden jumps between values.</span></span>  
  
3.  <span data-ttu-id="8a29b-112">Durante los dos últimos segundos, utiliza una instancia de la <xref:System.Windows.Media.Animation.SplinePointKeyFrame> clase para devolver la elipse a su posición inicial.</span><span class="sxs-lookup"><span data-stu-id="8a29b-112">During the final two seconds, uses an instance of the <xref:System.Windows.Media.Animation.SplinePointKeyFrame> class to move the ellipse back to its starting position.</span></span> <span data-ttu-id="8a29b-113">Los fotogramas clave spline como <xref:System.Windows.Media.Animation.SplinePointKeyFrame> crean una transición variable entre los valores según los valores de la <xref:System.Windows.Media.Animation.SplinePointKeyFrame.KeySpline%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="8a29b-113">Spline key frames like <xref:System.Windows.Media.Animation.SplinePointKeyFrame> create a variable transition between values according to the values of the <xref:System.Windows.Media.Animation.SplinePointKeyFrame.KeySpline%2A> property.</span></span> <span data-ttu-id="8a29b-114">En este ejemplo, la animación comienza despacio y se acelera exponencialmente hacia el final del segmento temporal.</span><span class="sxs-lookup"><span data-stu-id="8a29b-114">In this example, the animation begins slowly and speeds up exponentially toward the end of the time segment.</span></span>  
  
 [!code-csharp[keyframes_snip#PointAnimationUsingKeyFramesWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/PointAnimationUsingKeyFramesExample.cs#pointanimationusingkeyframeswholepage)]
 [!code-vb[keyframes_snip#PointAnimationUsingKeyFramesWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/pointanimationusingkeyframesexample.vb#pointanimationusingkeyframeswholepage)]
 [!code-xaml[keyframes_snip#PointAnimationUsingKeyFramesWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/PointAnimationUsingKeyFramesExample.xaml#pointanimationusingkeyframeswholepage)]  
  
 <span data-ttu-id="8a29b-115">Para consultar el ejemplo completo, vea [Ejemplo de animación mediante fotogramas clave](https://go.microsoft.com/fwlink/?LinkID=160012).</span><span class="sxs-lookup"><span data-stu-id="8a29b-115">For the complete sample, see [KeyFrame Animation Sample](https://go.microsoft.com/fwlink/?LinkID=160012).</span></span>  
  
 <span data-ttu-id="8a29b-116">Para mantener la coherencia con otros ejemplos de animación, las versiones de código de este ejemplo utiliza un <xref:System.Windows.Media.Animation.Storyboard> objeto al que aplicar el <xref:System.Windows.Media.Animation.PointAnimationUsingKeyFrames>.</span><span class="sxs-lookup"><span data-stu-id="8a29b-116">For consistency with other animation examples, the code versions of this example use a <xref:System.Windows.Media.Animation.Storyboard> object to apply the <xref:System.Windows.Media.Animation.PointAnimationUsingKeyFrames>.</span></span> <span data-ttu-id="8a29b-117">Sin embargo, al aplicar una animación única en código, resulta más fácil de usar el <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> método en lugar de usar un <xref:System.Windows.Media.Animation.Storyboard>.</span><span class="sxs-lookup"><span data-stu-id="8a29b-117">However, when applying a single animation in code, it's simpler to use the <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> method instead of using a <xref:System.Windows.Media.Animation.Storyboard>.</span></span> <span data-ttu-id="8a29b-118">Para obtener un ejemplo, vea [Animar una propiedad sin utilizar un guión gráfico](how-to-animate-a-property-without-using-a-storyboard.md).</span><span class="sxs-lookup"><span data-stu-id="8a29b-118">For an example, see [Animate a Property Without Using a Storyboard](how-to-animate-a-property-without-using-a-storyboard.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8a29b-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="8a29b-119">See also</span></span>

- <xref:System.Windows.Media.Animation.PointAnimationUsingKeyFrames>
- <xref:System.Windows.Media.EllipseGeometry.Center%2A?displayProperty=nameWithType>
- <xref:System.Windows.Media.EllipseGeometry>
- [<span data-ttu-id="8a29b-120">Información general sobre animaciones de fotogramas clave</span><span class="sxs-lookup"><span data-stu-id="8a29b-120">Key-Frame Animations Overview</span></span>](key-frame-animations-overview.md)
- [<span data-ttu-id="8a29b-121">Temas de procedimientos de fotogramas clave</span><span class="sxs-lookup"><span data-stu-id="8a29b-121">Key-Frame How-to Topics</span></span>](key-frame-animation-how-to-topics.md)
