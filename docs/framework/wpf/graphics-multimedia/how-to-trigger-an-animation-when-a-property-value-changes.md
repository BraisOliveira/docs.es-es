---
title: Procedimiento Activar una animación al cambiar el valor de una propiedad
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], starting when property values change
- triggering animation [WPF]
- Storyboards [WPF], starting when property values change
ms.assetid: 12399c21-0300-4f4f-9e3a-d92d9907e5f5
ms.openlocfilehash: 7e3eecedf7d464eeb8e4f60f2f05fa06d2e23e09
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61769309"
---
# <a name="how-to-trigger-an-animation-when-a-property-value-changes"></a><span data-ttu-id="09ad0-102">Procedimiento Activar una animación al cambiar el valor de una propiedad</span><span class="sxs-lookup"><span data-stu-id="09ad0-102">How to: Trigger an Animation When a Property Value Changes</span></span>
<span data-ttu-id="09ad0-103">En este ejemplo se muestra cómo usar un <xref:System.Windows.Trigger> para iniciar un <xref:System.Windows.Media.Animation.Storyboard> cuando cambia un valor de propiedad.</span><span class="sxs-lookup"><span data-stu-id="09ad0-103">This example shows how to use a <xref:System.Windows.Trigger> to start a <xref:System.Windows.Media.Animation.Storyboard> when a property value changes.</span></span> <span data-ttu-id="09ad0-104">Puede usar un <xref:System.Windows.Trigger> dentro de un <xref:System.Windows.Style>, <xref:System.Windows.Controls.ControlTemplate>, o <xref:System.Windows.DataTemplate>.</span><span class="sxs-lookup"><span data-stu-id="09ad0-104">You can use a <xref:System.Windows.Trigger> inside a <xref:System.Windows.Style>, <xref:System.Windows.Controls.ControlTemplate>, or <xref:System.Windows.DataTemplate>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="09ad0-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="09ad0-105">Example</span></span>  
 <span data-ttu-id="09ad0-106">En el ejemplo siguiente se usa un <xref:System.Windows.Trigger> para animar la <xref:System.Windows.UIElement.Opacity%2A> de un <xref:System.Windows.Controls.Button> cuando su <xref:System.Windows.UIElement.IsMouseOver%2A> propiedad pasa a ser `true`.</span><span class="sxs-lookup"><span data-stu-id="09ad0-106">The following example uses a <xref:System.Windows.Trigger> to animate the <xref:System.Windows.UIElement.Opacity%2A> of a <xref:System.Windows.Controls.Button> when its <xref:System.Windows.UIElement.IsMouseOver%2A> property becomes `true`.</span></span>  
  
 [!code-xaml[AnimatePropertyStoryboards#PropertyTriggerExample](~/samples/snippets/xaml/VS_Snippets_Wpf/AnimatePropertyStoryboards/XAML/PropertyTriggerExample.xaml#propertytriggerexample)]  
  
 <span data-ttu-id="09ad0-107">Las animaciones aplicadas por la propiedad <xref:System.Windows.Trigger> se comportan los objetos en un modo más complejo que <xref:System.Windows.EventTrigger> animaciones o animaciones a usar <xref:System.Windows.Media.Animation.Storyboard> métodos.</span><span class="sxs-lookup"><span data-stu-id="09ad0-107">Animations applied by property <xref:System.Windows.Trigger> objects behave in a more complex fashion than <xref:System.Windows.EventTrigger> animations or animations started using <xref:System.Windows.Media.Animation.Storyboard> methods.</span></span>  <span data-ttu-id="09ad0-108">Se "continúan" con animaciones definida por otros <xref:System.Windows.Trigger> objetos, pero se crean con <xref:System.Windows.EventTrigger> y animaciones activadas por métodos.</span><span class="sxs-lookup"><span data-stu-id="09ad0-108">They "handoff" with animations defined by other <xref:System.Windows.Trigger> objects, but compose with <xref:System.Windows.EventTrigger> and method-triggered animations.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="09ad0-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="09ad0-109">See also</span></span>

- <xref:System.Windows.Trigger>
- [<span data-ttu-id="09ad0-110">Información general sobre técnicas de animación de propiedades</span><span class="sxs-lookup"><span data-stu-id="09ad0-110">Property Animation Techniques Overview</span></span>](property-animation-techniques-overview.md)
- [<span data-ttu-id="09ad0-111">Información general sobre objetos Storyboard </span><span class="sxs-lookup"><span data-stu-id="09ad0-111">Storyboards Overview</span></span>](storyboards-overview.md)
