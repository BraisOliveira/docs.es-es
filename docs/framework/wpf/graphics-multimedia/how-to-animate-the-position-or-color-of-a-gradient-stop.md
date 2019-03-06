---
title: Filtrar Animar la posición o color de un punto de degradado
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- position [WPF], animating
- animation [WPF], position of GradientStop objects
- GradientStop objects [WPF], animating color of
- colors [WPF], animating
- animation [WPF], color of GradientStop objects
- GradientStop objects [WPF], animating position of
ms.assetid: 6f5b8b47-6c32-4b8e-98ee-fdf6515ec843
ms.openlocfilehash: 6d8c1bb5cd133b2ee9d50a7e851d2ca3b4fff023
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2019
ms.locfileid: "57368891"
---
# <a name="how-to-animate-the-position-or-color-of-a-gradient-stop"></a><span data-ttu-id="b8dd4-102">Filtrar Animar la posición o color de un punto de degradado</span><span class="sxs-lookup"><span data-stu-id="b8dd4-102">How to: Animate the Position or Color of a Gradient Stop</span></span>
<span data-ttu-id="b8dd4-103">En este ejemplo se muestra cómo animar la <xref:System.Windows.Media.GradientStop.Color%2A> y <xref:System.Windows.Media.GradientStop.Offset%2A> de <xref:System.Windows.Media.GradientStop> objetos.</span><span class="sxs-lookup"><span data-stu-id="b8dd4-103">This example shows how to animate the <xref:System.Windows.Media.GradientStop.Color%2A> and <xref:System.Windows.Media.GradientStop.Offset%2A> of <xref:System.Windows.Media.GradientStop> objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b8dd4-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="b8dd4-104">Example</span></span>  
 <span data-ttu-id="b8dd4-105">En el ejemplo siguiente se anima tres puntos de degradado dentro de un <xref:System.Windows.Media.LinearGradientBrush>.</span><span class="sxs-lookup"><span data-stu-id="b8dd4-105">The following example animates three gradient stops inside a <xref:System.Windows.Media.LinearGradientBrush>.</span></span> <span data-ttu-id="b8dd4-106">En el ejemplo se utiliza tres animaciones, cada uno de los cuales anima un delimitador de degradado diferentes:</span><span class="sxs-lookup"><span data-stu-id="b8dd4-106">The example uses three animations, each of which animates a different gradient stop:</span></span>  
  
-   <span data-ttu-id="b8dd4-107">La primera animación, un <xref:System.Windows.Media.Animation.DoubleAnimation>, anima el delimitador de degradado primera <xref:System.Windows.Media.GradientStop.Offset%2A> de 0,0 a 1,0 y luego volver a 0,0.</span><span class="sxs-lookup"><span data-stu-id="b8dd4-107">The first animation, a <xref:System.Windows.Media.Animation.DoubleAnimation>, animates the first gradient stop's <xref:System.Windows.Media.GradientStop.Offset%2A> from 0.0 to 1.0 and then back to 0.0.</span></span> <span data-ttu-id="b8dd4-108">Como resultado, el primer color del degradado cambia del lado izquierdo a la derecha del rectángulo y, a continuación, realizar una copia en el lado izquierdo.</span><span class="sxs-lookup"><span data-stu-id="b8dd4-108">As a result, the first color in the gradient shifts from the left side to the right side of the rectangle and then back to the left side.</span></span>  
  
-   <span data-ttu-id="b8dd4-109">La segunda animación, un <xref:System.Windows.Media.Animation.ColorAnimation>, anima el delimitador de degradado segundo <xref:System.Windows.Media.GradientStop.Color%2A> desde <xref:System.Windows.Media.Colors.Purple%2A> a <xref:System.Windows.Media.Colors.Yellow%2A> y luego volver a <xref:System.Windows.Media.Colors.Purple%2A>.</span><span class="sxs-lookup"><span data-stu-id="b8dd4-109">The second animation, a <xref:System.Windows.Media.Animation.ColorAnimation>, animates the second gradient stop's <xref:System.Windows.Media.GradientStop.Color%2A> from <xref:System.Windows.Media.Colors.Purple%2A> to <xref:System.Windows.Media.Colors.Yellow%2A> and then back to <xref:System.Windows.Media.Colors.Purple%2A>.</span></span> <span data-ttu-id="b8dd4-110">Como resultado, el color medio del degradado cambia de color púrpura a amarillo y volver a púrpura.</span><span class="sxs-lookup"><span data-stu-id="b8dd4-110">As a result, the middle color in the gradient changes from purple to yellow and back to purple.</span></span>  
  
-   <span data-ttu-id="b8dd4-111">La tercera animación, otro <xref:System.Windows.Media.Animation.ColorAnimation>, anima la opacidad del tercer delimitador de degradado <xref:System.Windows.Media.GradientStop.Color%2A> por -1 y, a continuación, realice una copia.</span><span class="sxs-lookup"><span data-stu-id="b8dd4-111">The third animation, another <xref:System.Windows.Media.Animation.ColorAnimation>, animates the opacity of the third gradient stop's <xref:System.Windows.Media.GradientStop.Color%2A> by -1 and then back.</span></span> <span data-ttu-id="b8dd4-112">Como resultado, el tercer color de degradado que desaparece y, a continuación, se convierte en opaco.</span><span class="sxs-lookup"><span data-stu-id="b8dd4-112">As a result, the third color in the gradient fades away and then becomes opaque again.</span></span>  
  
 [!code-csharp[BrushesIntroduction_snip#GraphicsMMGradientAnimationExamplesWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/GradientStopAnimationExample.cs#graphicsmmgradientanimationexampleswholepage)]
 [!code-vb[BrushesIntroduction_snip#GraphicsMMGradientAnimationExamplesWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/gradientstopanimationexample.vb#graphicsmmgradientanimationexampleswholepage)]
 [!code-xaml[BrushesIntroduction_snip#GraphicsMMGradientAnimationExamplesWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/GradientStopAnimationExample.xaml#graphicsmmgradientanimationexampleswholepage)]  
  
 <span data-ttu-id="b8dd4-113">Aunque este ejemplo usa un <xref:System.Windows.Media.LinearGradientBrush>, el proceso es el mismo para animar <xref:System.Windows.Media.GradientStop> objetos dentro de un <xref:System.Windows.Media.RadialGradientBrush>.</span><span class="sxs-lookup"><span data-stu-id="b8dd4-113">Although this example uses a <xref:System.Windows.Media.LinearGradientBrush>, the process is the same for animating <xref:System.Windows.Media.GradientStop> objects inside a <xref:System.Windows.Media.RadialGradientBrush>.</span></span>  
  
 <span data-ttu-id="b8dd4-114">Para obtener ejemplos adicionales, vea el [Brushes Sample](https://go.microsoft.com/fwlink/?LinkID=159973).</span><span class="sxs-lookup"><span data-stu-id="b8dd4-114">For additional examples, see the [Brushes Sample](https://go.microsoft.com/fwlink/?LinkID=159973).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b8dd4-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="b8dd4-115">See also</span></span>
- <xref:System.Windows.Media.GradientStop>
- [<span data-ttu-id="b8dd4-116">Información general sobre animaciones</span><span class="sxs-lookup"><span data-stu-id="b8dd4-116">Animation Overview</span></span>](animation-overview.md)
- [<span data-ttu-id="b8dd4-117">Información general sobre objetos Storyboard </span><span class="sxs-lookup"><span data-stu-id="b8dd4-117">Storyboards Overview</span></span>](storyboards-overview.md)
