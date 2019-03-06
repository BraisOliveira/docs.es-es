---
title: Filtrar Usar colores del sistema en un degradado
ms.date: 03/30/2017
helpviewer_keywords:
- gradients [WPF], system colors in
- system colors in gradients [WPF]
ms.assetid: 11942e7e-6300-4b50-8ed1-f50e8d20e7d2
ms.openlocfilehash: 3148a5901ccf64194717e26664ab8b9cbd57db2a
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2019
ms.locfileid: "57365963"
---
# <a name="how-to-use-system-colors-in-a-gradient"></a><span data-ttu-id="694ed-102">Filtrar Usar colores del sistema en un degradado</span><span class="sxs-lookup"><span data-stu-id="694ed-102">How to: Use System Colors in a Gradient</span></span>
<span data-ttu-id="694ed-103">Para utilizar un color del sistema en un degradado, se utiliza el  *\<SystemColor >* Color y  *\<SystemColor >* ColorKey propiedades estáticas de la <xref:System.Windows.SystemColors> clase para obtener una referencia al color, donde  *\<SystemColor >* es el nombre del color del sistema deseado.</span><span class="sxs-lookup"><span data-stu-id="694ed-103">To use a system color in a gradient, you use the *\<SystemColor>* Color and *\<SystemColor>* ColorKey static properties of the <xref:System.Windows.SystemColors> class to obtain a reference to the color, where *\<SystemColor>* is the name of the desired system color.</span></span> <span data-ttu-id="694ed-104">Use la  *\<SystemColor >* propiedades de ColorKey cuando desee crear una referencia dinámica que se actualiza automáticamente a medida que cambia el tema del sistema.</span><span class="sxs-lookup"><span data-stu-id="694ed-104">Use the *\<SystemColor>* ColorKey properties when you want to create a dynamic reference that updates automatically as the system theme changes.</span></span> <span data-ttu-id="694ed-105">En caso contrario, use el  *\<SystemColor >* propiedades de Color.</span><span class="sxs-lookup"><span data-stu-id="694ed-105">Otherwise, use the *\<SystemColor>* Color properties.</span></span>  
  
## <a name="example"></a><span data-ttu-id="694ed-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="694ed-106">Example</span></span>  
 <span data-ttu-id="694ed-107">En el siguiente ejemplo se usan recursos de color del sistema dinámico para crear un degradado.</span><span class="sxs-lookup"><span data-stu-id="694ed-107">The following example uses dynamic system color resources to create a gradient.</span></span>  
  
 [!code-xaml[brushsamples_snip#GraphicsMMDynamicSystemColorGradientExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/DynamicSystemColorExample.xaml#graphicsmmdynamicsystemcolorgradientexamplewholepage)]  
  
 <span data-ttu-id="694ed-108">En el siguiente ejemplo se usan recursos de color del sistema estático para crear un degradado.</span><span class="sxs-lookup"><span data-stu-id="694ed-108">The next example uses static system color resources to create a gradient.</span></span>  
  
 [!code-xaml[brushsamples_snip#GraphicsMMStaticSystemColorGradientExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/StaticSystemColorExample.xaml#graphicsmmstaticsystemcolorgradientexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="694ed-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="694ed-109">See also</span></span>
- <xref:System.Windows.SystemColors>
- [<span data-ttu-id="694ed-110">Pintar un área con un pincel del sistema</span><span class="sxs-lookup"><span data-stu-id="694ed-110">Paint an Area with a System Brush</span></span>](how-to-paint-an-area-with-a-system-brush.md)
- [<span data-ttu-id="694ed-111">Información general sobre el dibujo con colores sólidos y degradados</span><span class="sxs-lookup"><span data-stu-id="694ed-111">Painting with Solid Colors and Gradients Overview</span></span>](painting-with-solid-colors-and-gradients-overview.md)
