---
title: Procedimiento Mejorar el rendimiento al almacenar en caché un elemento de la representación
ms.date: 03/30/2017
helpviewer_keywords:
- rendering performance [WPF], caching an element
- BitmapCache [WPF], improving rendering performance
- CacheMode [WPF], improving rendering performance
- performance [WPF], caching an element
- UIElement [WPF], caching
ms.assetid: 4739c1fc-60ba-4c46-aba6-f6c1a2688f19
ms.openlocfilehash: b5e39541fdf031b19e9e74483c0de94295e788d7
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2019
ms.locfileid: "57375238"
---
# <a name="how-to-improve-rendering-performance-by-caching-an-element"></a><span data-ttu-id="552a9-102">Procedimiento Mejorar el rendimiento al almacenar en caché un elemento de la representación</span><span class="sxs-lookup"><span data-stu-id="552a9-102">How to: Improve Rendering Performance by Caching an Element</span></span>
<span data-ttu-id="552a9-103">Use la <xref:System.Windows.Media.BitmapCache> clase para mejorar el rendimiento de la representación de un complejo <xref:System.Windows.UIElement>.</span><span class="sxs-lookup"><span data-stu-id="552a9-103">Use the <xref:System.Windows.Media.BitmapCache> class to improve rendering performance of a complex <xref:System.Windows.UIElement>.</span></span> <span data-ttu-id="552a9-104">Para almacenar en caché un elemento, crear una nueva instancia de la <xref:System.Windows.Media.BitmapCache> clase y se asigna a la propiedad del elemento <xref:System.Windows.UIElement.CacheMode%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="552a9-104">To cache an element, create a new instance of the <xref:System.Windows.Media.BitmapCache> class and assign it to the element's <xref:System.Windows.UIElement.CacheMode%2A> property.</span></span> <span data-ttu-id="552a9-105">Puede volver a usar un <xref:System.Windows.Media.BitmapCache> eficazmente en un <xref:System.Windows.Media.BitmapCacheBrush>.</span><span class="sxs-lookup"><span data-stu-id="552a9-105">You can reuse a <xref:System.Windows.Media.BitmapCache> efficiently in a <xref:System.Windows.Media.BitmapCacheBrush>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="552a9-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="552a9-106">Example</span></span>  
 <span data-ttu-id="552a9-107">El ejemplo de código siguiente muestra cómo crear un elemento complejo y lo almacena en caché como un mapa de bits, lo que mejora el rendimiento cuando se anima el elemento.</span><span class="sxs-lookup"><span data-stu-id="552a9-107">The following code example shows how to create a complex element and cache it as a bitmap, which improves performance when the element is animated.</span></span> <span data-ttu-id="552a9-108">El elemento es un lienzo que contiene formas geométricas con muchos vértices.</span><span class="sxs-lookup"><span data-stu-id="552a9-108">The element is a canvas that holds shape geometries with many vertices.</span></span> <span data-ttu-id="552a9-109">Un <xref:System.Windows.Media.BitmapCache> no tiene valor predeterminado se asigna valores a la <xref:System.Windows.UIElement.CacheMode%2A> del lienzo, y una animación muestra la escala sin problemas del mapa de bits almacenado en caché.</span><span class="sxs-lookup"><span data-stu-id="552a9-109">A <xref:System.Windows.Media.BitmapCache> with default values is assigned to the <xref:System.Windows.UIElement.CacheMode%2A> of the canvas, and an animation shows the smooth scaling of the cached bitmap.</span></span>  
  
 [!code-xaml[System.Windows.Media.BitmapCache#_BitmapCacheXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/system.windows.media.bitmapcache/cs/window1.xaml#_bitmapcachexaml)]  
  
## <a name="see-also"></a><span data-ttu-id="552a9-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="552a9-110">See also</span></span>
- <xref:System.Windows.Media.BitmapCache>
- <xref:System.Windows.Media.BitmapCacheBrush>
- <xref:System.Windows.UIElement.CacheMode%2A>
- [<span data-ttu-id="552a9-111">Cómo: Usar un elemento almacenado en caché como pincel</span><span class="sxs-lookup"><span data-stu-id="552a9-111">How to: Use a Cached Element as a Brush</span></span>](how-to-use-a-cached-element-as-a-brush.md)
