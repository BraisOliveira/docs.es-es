---
title: Procedimiento Animar los cambios de tamaño mediante fotogramas clave
ms.date: 03/30/2017
helpviewer_keywords:
- key frames [WPF], animating size changes with
- animation [WPF], size changes with key frames
- size changes [WPF], animating with key frames
ms.assetid: 86bd2950-d4c9-4ec4-aa8d-7dc3ccadded4
ms.openlocfilehash: 0629b6600444bd172af451fd7e970bff894d8047
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61789264"
---
# <a name="how-to-animate-size-changes-by-using-key-frames"></a><span data-ttu-id="212e9-102">Procedimiento Animar los cambios de tamaño mediante fotogramas clave</span><span class="sxs-lookup"><span data-stu-id="212e9-102">How to: Animate Size Changes by Using Key Frames</span></span>
<span data-ttu-id="212e9-103">En este ejemplo se muestra cómo animar los cambios del tamaño mediante fotogramas clave.</span><span class="sxs-lookup"><span data-stu-id="212e9-103">This example shows how to animate size changes by using key frames.</span></span>  
  
## <a name="example"></a><span data-ttu-id="212e9-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="212e9-104">Example</span></span>  
 <span data-ttu-id="212e9-105">En el ejemplo siguiente se usa el <xref:System.Windows.Media.Animation.SizeAnimationUsingKeyFrames> clase se va a animar el <xref:System.Windows.Media.ArcSegment.Size%2A> propiedad de un <xref:System.Windows.Media.ArcSegment>.</span><span class="sxs-lookup"><span data-stu-id="212e9-105">The following example uses the <xref:System.Windows.Media.Animation.SizeAnimationUsingKeyFrames> class to animate the <xref:System.Windows.Media.ArcSegment.Size%2A> property of an <xref:System.Windows.Media.ArcSegment>.</span></span> <span data-ttu-id="212e9-106">Esta animación utiliza tres fotogramas clave de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="212e9-106">This animation uses three key frames in the following manner:</span></span>  
  
1. <span data-ttu-id="212e9-107">Durante el primer medio segundo de la animación, usa una instancia de la <xref:System.Windows.Media.Animation.LinearSizeKeyFrame> clase para aumentar gradualmente el tamaño del arco. Los fotogramas clave lineales como <xref:System.Windows.Media.Animation.LinearSizeKeyFrame> crean una transición lineal suave entre valores.</span><span class="sxs-lookup"><span data-stu-id="212e9-107">During the first half second of the animation, uses an instance of the <xref:System.Windows.Media.Animation.LinearSizeKeyFrame> class to gradually increase the size of the arc. Linear key frames like <xref:System.Windows.Media.Animation.LinearSizeKeyFrame> create a smooth linear transition between values.</span></span>  
  
2. <span data-ttu-id="212e9-108">Al final de la siguiente medio segundo, utiliza una instancia de la <xref:System.Windows.Media.Animation.DiscreteSizeKeyFrame> clase, de repente, aumentar el tamaño del arco. Los fotogramas clave discretos como <xref:System.Windows.Media.Animation.DiscreteSizeKeyFrame> crean saltos súbitos entre los valores, es decir, los cambios de tamaño se producen de repente y no son sutiles.</span><span class="sxs-lookup"><span data-stu-id="212e9-108">At the end of the next half second, uses an instance of the <xref:System.Windows.Media.Animation.DiscreteSizeKeyFrame> class to suddenly increase the size of the arc. Discrete key frames like <xref:System.Windows.Media.Animation.DiscreteSizeKeyFrame> create sudden jumps between values, that is, the size changes occur suddenly and are not subtle.</span></span>  
  
3. <span data-ttu-id="212e9-109">A través de los dos últimos segundos, utiliza una instancia de la <xref:System.Windows.Media.Animation.SplineSizeKeyFrame> clase para aumentar el tamaño del arco. Los fotogramas clave spline como <xref:System.Windows.Media.Animation.SplineSizeKeyFrame> crean una transición variable entre los valores según los valores de la <xref:System.Windows.Media.Animation.SplineSizeKeyFrame.KeySpline%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="212e9-109">Over the final two seconds, uses an instance of the <xref:System.Windows.Media.Animation.SplineSizeKeyFrame> class to increase the size of the arc. Spline key frames like <xref:System.Windows.Media.Animation.SplineSizeKeyFrame> create a variable transition between values according to the values of the <xref:System.Windows.Media.Animation.SplineSizeKeyFrame.KeySpline%2A> property.</span></span> <span data-ttu-id="212e9-110">En este ejemplo, el tamaño del arco aumenta lentamente al principio y va aumentando exponencialmente hacia el final del segmento temporal.</span><span class="sxs-lookup"><span data-stu-id="212e9-110">In this example, the size of the arc increases slowly at first and then increases exponentially toward the end of the time segment.</span></span>  
  
 [!code-xaml[keyframes_snip#SizeAnimationUsingKeyFramesWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/SizeAnimationUsingKeyFramesExample.xaml#sizeanimationusingkeyframeswholepage)]  
  
 <span data-ttu-id="212e9-111">Para consultar el ejemplo completo, vea [Ejemplo de animación mediante fotogramas clave](https://go.microsoft.com/fwlink/?LinkID=160012).</span><span class="sxs-lookup"><span data-stu-id="212e9-111">For the complete sample, see [KeyFrame Animation Sample](https://go.microsoft.com/fwlink/?LinkID=160012).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="212e9-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="212e9-112">See also</span></span>

- <xref:System.Windows.Media.Animation.SizeAnimationUsingKeyFrames>
- <xref:System.Windows.Media.ArcSegment.Size%2A>
- <xref:System.Windows.Media.ArcSegment>
- <xref:System.Windows.Media.Animation.LinearSizeKeyFrame>
- <xref:System.Windows.Media.Animation.DiscreteSizeKeyFrame>
- <xref:System.Windows.Media.Animation.SplineSizeKeyFrame>
- [<span data-ttu-id="212e9-113">Información general sobre animaciones de fotogramas clave</span><span class="sxs-lookup"><span data-stu-id="212e9-113">Key-Frame Animations Overview</span></span>](key-frame-animations-overview.md)
- [<span data-ttu-id="212e9-114">Temas de procedimientos de fotogramas clave</span><span class="sxs-lookup"><span data-stu-id="212e9-114">Key-Frame How-to Topics</span></span>](key-frame-animation-how-to-topics.md)
