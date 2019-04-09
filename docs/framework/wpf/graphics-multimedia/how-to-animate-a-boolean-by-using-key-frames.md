---
title: Filtrar Animar un objeto Boolean mediante fotogramas clave
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Booleans [WPF], animating with key frames
- animation [WPF], Booleans with key frames
- key frames [WPF], animating Booleans with
ms.assetid: 4b0fac96-6231-4fcf-9775-4dd673ddc785
ms.openlocfilehash: 59a72916721cccbe66f704253f148828fa8cd418
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59175037"
---
# <a name="how-to-animate-a-boolean-by-using-key-frames"></a><span data-ttu-id="4e2b4-102">Filtrar Animar un objeto Boolean mediante fotogramas clave</span><span class="sxs-lookup"><span data-stu-id="4e2b4-102">How to: Animate a Boolean by Using Key Frames</span></span>
<span data-ttu-id="4e2b4-103">En este ejemplo se muestra cómo animar el valor de propiedad booleana de una <xref:System.Windows.Controls.Button> control mediante fotogramas clave.</span><span class="sxs-lookup"><span data-stu-id="4e2b4-103">This example shows how to animate the Boolean property value of a <xref:System.Windows.Controls.Button> control by using key frames.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4e2b4-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="4e2b4-104">Example</span></span>  
 <span data-ttu-id="4e2b4-105">En el ejemplo siguiente se usa el <xref:System.Windows.Media.Animation.BooleanAnimationUsingKeyFrames> clase se va a animar el <xref:System.Windows.UIElement.IsEnabled%2A> propiedad de un <xref:System.Windows.Controls.Button> control.</span><span class="sxs-lookup"><span data-stu-id="4e2b4-105">The following example uses the <xref:System.Windows.Media.Animation.BooleanAnimationUsingKeyFrames> class to animate the <xref:System.Windows.UIElement.IsEnabled%2A> property of a <xref:System.Windows.Controls.Button> control.</span></span> <span data-ttu-id="4e2b4-106">Todos los fotogramas clave en este ejemplo utilizan una instancia de la <xref:System.Windows.Media.Animation.DiscreteBooleanKeyFrame> clase.</span><span class="sxs-lookup"><span data-stu-id="4e2b4-106">All the key frames in this example use an instance of the <xref:System.Windows.Media.Animation.DiscreteBooleanKeyFrame> class.</span></span> <span data-ttu-id="4e2b4-107">Los fotogramas clave discretos como <xref:System.Windows.Media.Animation.DiscreteBooleanKeyFrame> crean saltos súbitos entre los valores, es decir, el movimiento de la animación es brusco.</span><span class="sxs-lookup"><span data-stu-id="4e2b4-107">Discrete key frames like <xref:System.Windows.Media.Animation.DiscreteBooleanKeyFrame> create sudden jumps between values, that is, the movement of the animation is jerky.</span></span>  
  
 [!code-csharp[keyframes_snip#BooleanAnimationUsingKeyFramesWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/BooleanAnimationUsingKeyFramesExample.cs#booleananimationusingkeyframeswholepage)]
 [!code-vb[keyframes_snip#BooleanAnimationUsingKeyFramesWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/booleananimationusingkeyframesexample.vb#booleananimationusingkeyframeswholepage)]
 [!code-xaml[keyframes_snip#BooleanAnimationUsingKeyFramesWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/BooleanAnimationUsingKeyFramesExample.xaml#booleananimationusingkeyframeswholepage)]  
  
 <span data-ttu-id="4e2b4-108">Para consultar el ejemplo completo, vea [Ejemplo de animación mediante fotogramas clave](https://go.microsoft.com/fwlink/?LinkID=160012).</span><span class="sxs-lookup"><span data-stu-id="4e2b4-108">For the complete sample, see [KeyFrame Animation Sample](https://go.microsoft.com/fwlink/?LinkID=160012).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4e2b4-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="4e2b4-109">See also</span></span>

- <xref:System.Windows.Media.Animation.BooleanAnimationUsingKeyFrames>
- <xref:System.Windows.UIElement.IsEnabled%2A>
- <xref:System.Windows.Controls.Button>
- [<span data-ttu-id="4e2b4-110">Información general sobre animaciones de fotogramas clave</span><span class="sxs-lookup"><span data-stu-id="4e2b4-110">Key-Frame Animations Overview</span></span>](key-frame-animations-overview.md)
- [<span data-ttu-id="4e2b4-111">Temas de procedimientos de fotogramas clave</span><span class="sxs-lookup"><span data-stu-id="4e2b4-111">Key-Frame How-to Topics</span></span>](key-frame-animation-how-to-topics.md)
