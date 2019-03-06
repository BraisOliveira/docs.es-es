---
title: Filtrar Utilizar desencadenadores de eventos para controlar un guión gráfico después de su inicio
ms.date: 03/30/2017
helpviewer_keywords:
- triggers [WPF], controlling Storyboards
- event triggers [WPF], controlling Storyboards
- Storyboards [WPF], controlling after start
ms.assetid: 3b115594-6a93-4972-b24d-61aa16f1c15f
ms.openlocfilehash: d0b25f56caf3f25b6e649c05ecf1cbe50046dd93
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2019
ms.locfileid: "57362375"
---
# <a name="how-to-use-event-triggers-to-control-a-storyboard-after-it-starts"></a><span data-ttu-id="950bd-102">Procedimiento Utilizar desencadenadores de eventos para controlar un guión gráfico después de su inicio</span><span class="sxs-lookup"><span data-stu-id="950bd-102">How to: Use Event Triggers to Control a Storyboard After It Starts</span></span>
<span data-ttu-id="950bd-103">En este ejemplo se muestra cómo controlar un <xref:System.Windows.Media.Animation.Storyboard> después de iniciarse.</span><span class="sxs-lookup"><span data-stu-id="950bd-103">This example shows how to control a <xref:System.Windows.Media.Animation.Storyboard> after it starts.</span></span> <span data-ttu-id="950bd-104">Para iniciar un <xref:System.Windows.Media.Animation.Storyboard> utilizando [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], utilice <xref:System.Windows.Media.Animation.BeginStoryboard>, que distribuye las animaciones a los objetos y propiedades que se animan y, a continuación, inicia el guión gráfico.</span><span class="sxs-lookup"><span data-stu-id="950bd-104">To start a <xref:System.Windows.Media.Animation.Storyboard> by using [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], use <xref:System.Windows.Media.Animation.BeginStoryboard>, which distributes the animations to the objects and properties they animate and then starts the storyboard.</span></span> <span data-ttu-id="950bd-105">Si da <xref:System.Windows.Media.Animation.BeginStoryboard> especificando un nombre de su <xref:System.Windows.Media.Animation.BeginStoryboard.Name%2A> propiedad, facilitar un guión gráfico controlable.</span><span class="sxs-lookup"><span data-stu-id="950bd-105">If you give <xref:System.Windows.Media.Animation.BeginStoryboard> a name by specifying its <xref:System.Windows.Media.Animation.BeginStoryboard.Name%2A> property, you make it a controllable storyboard.</span></span> <span data-ttu-id="950bd-106">A continuación, puede controlar interactivamente el guión gráfico después de iniciarse.</span><span class="sxs-lookup"><span data-stu-id="950bd-106">You can then interactively control the storyboard after it starts.</span></span>  
  
 <span data-ttu-id="950bd-107">Utilice las siguientes acciones de guión gráfico junto con <xref:System.Windows.EventTrigger> objetos que se va a controlar un guión gráfico.</span><span class="sxs-lookup"><span data-stu-id="950bd-107">Use the following storyboard actions together with <xref:System.Windows.EventTrigger> objects to control a storyboard.</span></span>  
  
-   <span data-ttu-id="950bd-108"><xref:System.Windows.Media.Animation.PauseStoryboard>: Pausa el guión gráfico.</span><span class="sxs-lookup"><span data-stu-id="950bd-108"><xref:System.Windows.Media.Animation.PauseStoryboard>: Pauses the storyboard.</span></span>  
  
-   <span data-ttu-id="950bd-109"><xref:System.Windows.Media.Animation.ResumeStoryboard>: Reanuda un guión gráfico en pausa.</span><span class="sxs-lookup"><span data-stu-id="950bd-109"><xref:System.Windows.Media.Animation.ResumeStoryboard>: Resumes a paused storyboard.</span></span>  
  
-   <span data-ttu-id="950bd-110"><xref:System.Windows.Media.Animation.SetStoryboardSpeedRatio>: Cambia la velocidad del guión gráfico.</span><span class="sxs-lookup"><span data-stu-id="950bd-110"><xref:System.Windows.Media.Animation.SetStoryboardSpeedRatio>: Changes the storyboard speed.</span></span>  
  
-   <span data-ttu-id="950bd-111"><xref:System.Windows.Media.Animation.SkipStoryboardToFill>: Avanza un guión gráfico hasta el final de su período de relleno, si lo tiene.</span><span class="sxs-lookup"><span data-stu-id="950bd-111"><xref:System.Windows.Media.Animation.SkipStoryboardToFill>: Advances a storyboard to the end of its fill period, if it has one.</span></span>  
  
-   <span data-ttu-id="950bd-112"><xref:System.Windows.Media.Animation.StopStoryboard>: Detiene el guión gráfico.</span><span class="sxs-lookup"><span data-stu-id="950bd-112"><xref:System.Windows.Media.Animation.StopStoryboard>: Stops the storyboard.</span></span>  
  
-   <span data-ttu-id="950bd-113"><xref:System.Windows.Media.Animation.RemoveStoryboard>: Quita el guión gráfico, liberando los recursos.</span><span class="sxs-lookup"><span data-stu-id="950bd-113"><xref:System.Windows.Media.Animation.RemoveStoryboard>: Removes the storyboard, freeing resources.</span></span>  
  
## <a name="example"></a><span data-ttu-id="950bd-114">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="950bd-114">Example</span></span>  
 <span data-ttu-id="950bd-115">El ejemplo siguiente utiliza acciones de guión gráfico controlable controlar interactivamente un guión gráfico.</span><span class="sxs-lookup"><span data-stu-id="950bd-115">The following example uses controllable storyboard actions to interactively control a storyboard.</span></span>  
  
 <span data-ttu-id="950bd-116">**Nota:** Para ver un ejemplo de controlar un guión gráfico mediante código, consulte [controlar un guión gráfico después de que se inicia utilizando sus métodos interactivos](how-to-control-a-storyboard-after-it-starts.md).</span><span class="sxs-lookup"><span data-stu-id="950bd-116">**Note:** To see an example of controlling a storyboard by using code, see [Control a Storyboard After It Starts Using Its Interactive Methods](how-to-control-a-storyboard-after-it-starts.md).</span></span>  
  
 [!code-xaml[timingbehaviors_snip#ControlStoryboardExampleUsingWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/ControlStoryboardExample.xaml#controlstoryboardexampleusingwholepage)]  
  
 <span data-ttu-id="950bd-117">Para obtener ejemplos adicionales, vea el [Animation Example Gallery](https://go.microsoft.com/fwlink/?LinkID=159969).</span><span class="sxs-lookup"><span data-stu-id="950bd-117">For additional examples, see the [Animation Example Gallery](https://go.microsoft.com/fwlink/?LinkID=159969).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="950bd-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="950bd-118">See also</span></span>
- <xref:System.Windows.Media.Animation.ResumeStoryboard>
- <xref:System.Windows.Media.Animation.SetStoryboardSpeedRatio>
- <xref:System.Windows.Media.Animation.SkipStoryboardToFill>
- <xref:System.Windows.Media.Animation.PauseStoryboard>
- <xref:System.Windows.Media.Animation.StopStoryboard>
- <xref:System.Windows.Media.Animation.SeekStoryboard>
- [<span data-ttu-id="950bd-119">Controlar un guión gráfico una vez iniciado usando métodos interactivos</span><span class="sxs-lookup"><span data-stu-id="950bd-119">Control a Storyboard After It Starts Using Its Interactive Methods</span></span>](how-to-control-a-storyboard-after-it-starts.md)
- [<span data-ttu-id="950bd-120">Información general sobre animaciones</span><span class="sxs-lookup"><span data-stu-id="950bd-120">Animation Overview</span></span>](animation-overview.md)
- [<span data-ttu-id="950bd-121">Información general sobre objetos Storyboard </span><span class="sxs-lookup"><span data-stu-id="950bd-121">Storyboards Overview</span></span>](storyboards-overview.md)
