---
title: Procedimiento Pintar un área con un color sólido
ms.date: 03/30/2017
helpviewer_keywords:
- solid colors [WPF], painting with
- brushes [WPF], painting with solid colors
- painting [WPF], with solid colors
ms.assetid: 5d27d8a7-4bd7-4063-bdf3-2c5c0f19f9d3
ms.openlocfilehash: c85ba72c858d155f29875bb944824db1c44ffaab
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61922634"
---
# <a name="how-to-paint-an-area-with-a-solid-color"></a><span data-ttu-id="01932-102">Procedimiento Pintar un área con un color sólido</span><span class="sxs-lookup"><span data-stu-id="01932-102">How to: Paint an Area with a Solid Color</span></span>
<span data-ttu-id="01932-103">Para pintar un área con un color sólido, puede usar un pincel del sistema predefinidos, como <xref:System.Windows.Media.Brushes.Red%2A> o <xref:System.Windows.Media.Brushes.Blue%2A>, o bien puede crear un nuevo <xref:System.Windows.Media.SolidColorBrush> y describir su <xref:System.Windows.Media.SolidColorBrush.Color%2A> mediante valores alfabéticos, rojos, verde y azules.</span><span class="sxs-lookup"><span data-stu-id="01932-103">To paint an area with a solid color, you can use a predefined system brush, such as <xref:System.Windows.Media.Brushes.Red%2A> or <xref:System.Windows.Media.Brushes.Blue%2A>, or you can create a new <xref:System.Windows.Media.SolidColorBrush> and describe its <xref:System.Windows.Media.SolidColorBrush.Color%2A> using alpha, red, green, and blue values.</span></span> <span data-ttu-id="01932-104">En XAML, también puede pintar un área con un color sólido utilizando la notación hexadecimal.</span><span class="sxs-lookup"><span data-stu-id="01932-104">In XAML, you may also paint an area with a solid color by using hexidecimal notation.</span></span>  
  
 <span data-ttu-id="01932-105">Los ejemplos siguientes se usa cada una de estas técnicas para pintar un <xref:System.Windows.Shapes.Rectangle> azul.</span><span class="sxs-lookup"><span data-stu-id="01932-105">The following examples uses each of these techniques to paint a <xref:System.Windows.Shapes.Rectangle> blue.</span></span>  
  
## <a name="example"></a><span data-ttu-id="01932-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="01932-106">Example</span></span>  
 <span data-ttu-id="01932-107">**Utilizar un pincel predefinido**</span><span class="sxs-lookup"><span data-stu-id="01932-107">**Using a Predefined Brush**</span></span>  
  
 <span data-ttu-id="01932-108">En el ejemplo siguiente se usa el pincel predefinido <xref:System.Windows.Media.Brushes.Blue%2A> para pintar un rectángulo azul.</span><span class="sxs-lookup"><span data-stu-id="01932-108">In the following example uses the predefined brush <xref:System.Windows.Media.Brushes.Blue%2A> to paint a rectangle blue.</span></span>  
  
 [!code-xaml[brushsamples_snip#_graphicsmm_PredefinedBrush1](~/samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/SolidColorBrushExample.xaml#_graphicsmm_predefinedbrush1)]  
  
 [!code-csharp[brushsamples_procedural_snip#_graphicsmm_PredefinedBrush1](~/samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_procedural_snip/CSharp/SolidColorBrushExample.cs#_graphicsmm_predefinedbrush1)]  
  
 <span data-ttu-id="01932-109">**Utilizar la notación hexadecimal**</span><span class="sxs-lookup"><span data-stu-id="01932-109">**Using Hexadecimal Notation**</span></span>  
  
 <span data-ttu-id="01932-110">En el ejemplo siguiente se utiliza la notación hexadecimal de 8 dígitos para pintar un rectángulo azul.</span><span class="sxs-lookup"><span data-stu-id="01932-110">The next example uses 8-digit hexadecimal notation to paint a rectangle blue.</span></span>  
  
 [!code-xaml[brushsamples_snip#_graphicsmm_HexNotation8Digit1](~/samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/SolidColorBrushExample.xaml#_graphicsmm_hexnotation8digit1)]  
  
 <span data-ttu-id="01932-111">**Utilizar los valores ARGB**</span><span class="sxs-lookup"><span data-stu-id="01932-111">**Using ARGB Values**</span></span>  
  
 <span data-ttu-id="01932-112">El ejemplo siguiente se crea un <xref:System.Windows.Media.SolidColorBrush> y describe su <xref:System.Windows.Media.SolidColorBrush.Color%2A> utilizando los valores ARGB para el color azul.</span><span class="sxs-lookup"><span data-stu-id="01932-112">The next example creates a <xref:System.Windows.Media.SolidColorBrush> and describes its <xref:System.Windows.Media.SolidColorBrush.Color%2A> using the ARGB values for the color blue.</span></span>  
  
 [!code-xaml[brushsamples_snip#_graphicsmm_RgbNotation1](~/samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/SolidColorBrushExample.xaml#_graphicsmm_rgbnotation1)]  
  
 [!code-csharp[brushsamples_procedural_snip#_graphicsmm_RgbNotation1](~/samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_procedural_snip/CSharp/SolidColorBrushExample.cs#_graphicsmm_rgbnotation1)]  
  
 <span data-ttu-id="01932-113">Para conocer otras formas de describir colores, consulte el <xref:System.Windows.Media.Color> estructura.</span><span class="sxs-lookup"><span data-stu-id="01932-113">For other ways of describing color, see the <xref:System.Windows.Media.Color> structure.</span></span>  
  
 <span data-ttu-id="01932-114">**Temas relacionados**</span><span class="sxs-lookup"><span data-stu-id="01932-114">**Related Topics**</span></span>  
  
 <span data-ttu-id="01932-115">Para obtener más información acerca de <xref:System.Windows.Media.SolidColorBrush> y ejemplos adicionales, vea el [el dibujo con colores sólidos y degradados](painting-with-solid-colors-and-gradients-overview.md) información general.</span><span class="sxs-lookup"><span data-stu-id="01932-115">For more information about <xref:System.Windows.Media.SolidColorBrush> and additional examples, see the [Painting with Solid Colors and Gradients Overview](painting-with-solid-colors-and-gradients-overview.md) overview.</span></span>  
  
 <span data-ttu-id="01932-116">Este ejemplo de código forma parte de un ejemplo más extenso proporcionado para el <xref:System.Windows.Media.SolidColorBrush> clase.</span><span class="sxs-lookup"><span data-stu-id="01932-116">This code example is part of a larger example provided for the <xref:System.Windows.Media.SolidColorBrush> class.</span></span> <span data-ttu-id="01932-117">Para ver el ejemplo completo, consulte el [ejemplo de pinceles](https://go.microsoft.com/fwlink/?LinkID=159973).</span><span class="sxs-lookup"><span data-stu-id="01932-117">For the complete sample, see the [Brushes Sample](https://go.microsoft.com/fwlink/?LinkID=159973).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="01932-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="01932-118">See also</span></span>

- <xref:System.Windows.Media.Brushes>
