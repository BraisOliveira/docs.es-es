---
title: Procedimiento Animar una propiedad mediante un objeto AnimationClock
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- animation [WPF], properties [WPF], with AnimationClocks
- AnimationClocks [WPF]
ms.assetid: e6542021-714c-4675-9567-04f1c7380834
ms.openlocfilehash: 13d91e8589c40d84ba374ffc613388e24407796a
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64591285"
---
# <a name="how-to-animate-a-property-by-using-an-animationclock"></a><span data-ttu-id="3d868-102">Procedimiento Animar una propiedad mediante un objeto AnimationClock</span><span class="sxs-lookup"><span data-stu-id="3d868-102">How to: Animate a Property by Using an AnimationClock</span></span>
<span data-ttu-id="3d868-103">En este ejemplo se muestra cómo usar <xref:System.Windows.Media.Animation.Clock> objetos que se va a animar una propiedad.</span><span class="sxs-lookup"><span data-stu-id="3d868-103">This example shows how to use <xref:System.Windows.Media.Animation.Clock> objects to animate a property.</span></span>  
  
 <span data-ttu-id="3d868-104">Hay tres maneras de animar una propiedad de dependencia:</span><span class="sxs-lookup"><span data-stu-id="3d868-104">There are three ways to animate a dependency property:</span></span>  
  
- <span data-ttu-id="3d868-105">Crear un <xref:System.Windows.Media.Animation.AnimationTimeline> y asociarlo a esa propiedad mediante el uso de un <xref:System.Windows.Media.Animation.Storyboard>.</span><span class="sxs-lookup"><span data-stu-id="3d868-105">Create an <xref:System.Windows.Media.Animation.AnimationTimeline> and associate it with that property by using a <xref:System.Windows.Media.Animation.Storyboard>.</span></span>  
  
- <span data-ttu-id="3d868-106">Utilice el objeto <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> método para aplicar una sola <xref:System.Windows.Media.Animation.AnimationTimeline> a una propiedad de destino.</span><span class="sxs-lookup"><span data-stu-id="3d868-106">Use the object's <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> method to apply a single <xref:System.Windows.Media.Animation.AnimationTimeline> to a target property.</span></span>  
  
- <span data-ttu-id="3d868-107">Crear un <xref:System.Windows.Media.Animation.AnimationClock> desde un <xref:System.Windows.Media.Animation.AnimationTimeline> y aplicarla a una propiedad.</span><span class="sxs-lookup"><span data-stu-id="3d868-107">Create an <xref:System.Windows.Media.Animation.AnimationClock> from an <xref:System.Windows.Media.Animation.AnimationTimeline> and apply it to a property.</span></span>  
  
 <span data-ttu-id="3d868-108"><xref:System.Windows.Media.Animation.Storyboard> los objetos y el <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> método le permiten animar propiedades sin crear ni distribuir los relojes directamente (para obtener ejemplos, vea [animar una propiedad utilizando un guión gráfico](how-to-animate-a-property-by-using-a-storyboard.md) y [animar una propiedad sin Utilizar un guión gráfico](how-to-animate-a-property-without-using-a-storyboard.md)); los relojes se crean y distribuyen automáticamente.</span><span class="sxs-lookup"><span data-stu-id="3d868-108"><xref:System.Windows.Media.Animation.Storyboard> objects and the <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> method enable you to animate properties without directly creating and distributing clocks (for examples, see [Animate a Property by Using a Storyboard](how-to-animate-a-property-by-using-a-storyboard.md) and [Animate a Property Without Using a Storyboard](how-to-animate-a-property-without-using-a-storyboard.md)); clocks are created and distributed for you automatically.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3d868-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="3d868-109">Example</span></span>  
 <span data-ttu-id="3d868-110">El ejemplo siguiente muestra cómo crear un <xref:System.Windows.Media.Animation.AnimationClock> y aplicarlo a dos propiedades similares.</span><span class="sxs-lookup"><span data-stu-id="3d868-110">The following example shows how to create an <xref:System.Windows.Media.Animation.AnimationClock> and apply it to two similar properties.</span></span>  
  
 [!code-csharp[timingbehaviors_procedural_snip#GraphicsMMCreateAnimationClockWholeClass](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_procedural_snip/CSharp/AnimationClockExample.cs#graphicsmmcreateanimationclockwholeclass)]
 [!code-vb[timingbehaviors_procedural_snip#GraphicsMMCreateAnimationClockWholeClass](~/samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_procedural_snip/visualbasic/animationclockexample.vb#graphicsmmcreateanimationclockwholeclass)]  
  
 <span data-ttu-id="3d868-111">Para obtener un ejemplo que muestra cómo controlar interactivamente un <xref:System.Windows.Media.Animation.Clock> después de iniciarse, vea [controlar interactivamente un reloj](how-to-interactively-control-a-clock.md).</span><span class="sxs-lookup"><span data-stu-id="3d868-111">For an example showing how to interactively control a <xref:System.Windows.Media.Animation.Clock> after it starts, see [Interactively Control a Clock](how-to-interactively-control-a-clock.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3d868-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="3d868-112">See also</span></span>

- [<span data-ttu-id="3d868-113">Animar una propiedad utilizando un guión gráfico</span><span class="sxs-lookup"><span data-stu-id="3d868-113">Animate a Property by Using a Storyboard</span></span>](how-to-animate-a-property-by-using-a-storyboard.md)
- [<span data-ttu-id="3d868-114">Animar una propiedad sin utilizar un guión gráfico</span><span class="sxs-lookup"><span data-stu-id="3d868-114">Animate a Property Without Using a Storyboard</span></span>](how-to-animate-a-property-without-using-a-storyboard.md)
- [<span data-ttu-id="3d868-115">Información general sobre técnicas de animación de propiedades</span><span class="sxs-lookup"><span data-stu-id="3d868-115">Property Animation Techniques Overview</span></span>](property-animation-techniques-overview.md)
