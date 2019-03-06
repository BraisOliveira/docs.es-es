---
title: Procedimiento Sesgar un elemento
ms.date: 03/30/2017
helpviewer_keywords:
- skewing elements [WPF]
- graphics [WPF], skewing elements
- classes [WPF], SkewTransform
ms.assetid: 56b65f2f-dc6e-4238-923f-ca44ec53c52f
ms.openlocfilehash: fec3ec38a19b552e988d26ea57c6f9beed6ce06e
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2019
ms.locfileid: "57359381"
---
# <a name="how-to-skew-an-element"></a><span data-ttu-id="d6ccb-102">Filtrar Sesgar un elemento</span><span class="sxs-lookup"><span data-stu-id="d6ccb-102">How to: Skew an Element</span></span>
<span data-ttu-id="d6ccb-103">En este ejemplo se muestra cómo usar un <xref:System.Windows.Media.SkewTransform> para sesgar un elemento.</span><span class="sxs-lookup"><span data-stu-id="d6ccb-103">This example shows how to use a <xref:System.Windows.Media.SkewTransform> to skew an element.</span></span> <span data-ttu-id="d6ccb-104">Un sesgo, también conocido como distorsión, es una transformación que expande el espacio de coordenadas de una manera no uniforme.</span><span class="sxs-lookup"><span data-stu-id="d6ccb-104">A skew, which is also known as a shear, is a transformation that stretches the coordinate space in a non-uniform manner.</span></span> <span data-ttu-id="d6ccb-105">Un uso típico de un <xref:System.Windows.Media.SkewTransform> para simular [!INCLUDE[TLA#tla_3d](../../../../includes/tlasharptla-3d-md.md)] profundidad en [!INCLUDE[TLA#tla_2d](../../../../includes/tlasharptla-2d-md.md)] objetos.</span><span class="sxs-lookup"><span data-stu-id="d6ccb-105">One typical use of a <xref:System.Windows.Media.SkewTransform> is for simulating [!INCLUDE[TLA#tla_3d](../../../../includes/tlasharptla-3d-md.md)] depth in [!INCLUDE[TLA#tla_2d](../../../../includes/tlasharptla-2d-md.md)] objects.</span></span>  
  
 <span data-ttu-id="d6ccb-106">Use la <xref:System.Windows.Media.SkewTransform.CenterX%2A> y <xref:System.Windows.Media.SkewTransform.CenterY%2A> propiedades para especificar el centro de punto de la <xref:System.Windows.Media.SkewTransform>.</span><span class="sxs-lookup"><span data-stu-id="d6ccb-106">Use the <xref:System.Windows.Media.SkewTransform.CenterX%2A> and <xref:System.Windows.Media.SkewTransform.CenterY%2A> properties to specify the center point of the <xref:System.Windows.Media.SkewTransform>.</span></span>  
  
 <span data-ttu-id="d6ccb-107">Use la <xref:System.Windows.Media.SkewTransform.AngleX%2A> y <xref:System.Windows.Media.SkewTransform.AngleY%2A> propiedades para especificar el ángulo de sesgado de los ejes x y y y para sesgar el sistema de coordenadas actual a lo largo de estos ejes.</span><span class="sxs-lookup"><span data-stu-id="d6ccb-107">Use the <xref:System.Windows.Media.SkewTransform.AngleX%2A> and <xref:System.Windows.Media.SkewTransform.AngleY%2A> properties to specify the skew angle of the x-axis and y-axis, and to skew the current coordinate system along these axes.</span></span>  
  
 <span data-ttu-id="d6ccb-108">Para predecir el efecto de una transformación de sesgo, considere la posibilidad de que <xref:System.Windows.Media.SkewTransform.AngleX%2A> sesga los valores del eje x en relación con el sistema de coordenadas original.</span><span class="sxs-lookup"><span data-stu-id="d6ccb-108">To predict the effect of a skew transformation, consider that <xref:System.Windows.Media.SkewTransform.AngleX%2A> skews x-axis values relative to the original coordinate system.</span></span> <span data-ttu-id="d6ccb-109">Por lo tanto, para un <xref:System.Windows.Media.SkewTransform.AngleX%2A> de 30, el eje y gira 30 grados a través del origen y sesga los valores de x-30 grados desde ese origen.</span><span class="sxs-lookup"><span data-stu-id="d6ccb-109">Therefore, for an <xref:System.Windows.Media.SkewTransform.AngleX%2A> of 30, the y-axis rotates 30 degrees through the origin and skews the values in x- by 30 degrees from that origin.</span></span> <span data-ttu-id="d6ccb-110">Del mismo modo, un <xref:System.Windows.Media.SkewTransform.AngleY%2A> de 30 sesga los valores y de la forma 30 grados desde el origen.</span><span class="sxs-lookup"><span data-stu-id="d6ccb-110">Likewise, an <xref:System.Windows.Media.SkewTransform.AngleY%2A> of 30 skews the y- values of the shape by 30 degrees from the origin.</span></span> <span data-ttu-id="d6ccb-111">Tenga en cuenta que esto no tiene el mismo efecto que trasladar (mover) el sistema de coordenadas 30 grados en x o y.</span><span class="sxs-lookup"><span data-stu-id="d6ccb-111">Note that this is not the same effect as translating (moving) the coordinate system by 30 degrees in x- or y-.</span></span>  
  
 <span data-ttu-id="d6ccb-112">El ejemplo siguiente aplica un sesgo horizontal de 45 grados a un <xref:System.Windows.Shapes.Rectangle> desde un punto central de (0,0).</span><span class="sxs-lookup"><span data-stu-id="d6ccb-112">The following example applies a horizontal skew of 45 degrees to a <xref:System.Windows.Shapes.Rectangle> from a center point of (0,0).</span></span>  
  
## <a name="example"></a><span data-ttu-id="d6ccb-113">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d6ccb-113">Example</span></span>  
 [!code-xaml[transformsSample#41](~/samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/SkewTransformExample.xaml#41)]  
  
 <span data-ttu-id="d6ccb-114">El ejemplo siguiente aplica un sesgo horizontal de 45 grados a un <xref:System.Windows.Shapes.Rectangle> desde un punto central de (25,25).</span><span class="sxs-lookup"><span data-stu-id="d6ccb-114">The following example applies a horizontal skew of 45 degrees to a <xref:System.Windows.Shapes.Rectangle> from a center point of (25,25).</span></span>  
  
 [!code-xaml[transformsSample#42](~/samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/SkewTransformExample.xaml#42)]  
  
 <span data-ttu-id="d6ccb-115">El ejemplo siguiente aplica un sesgo vertical de 45 grados a un <xref:System.Windows.Shapes.Rectangle> desde un punto central de (25,25).</span><span class="sxs-lookup"><span data-stu-id="d6ccb-115">The following example applies a vertical skew of 45 degrees to a <xref:System.Windows.Shapes.Rectangle> from a center point of (25,25).</span></span>  
  
 [!code-xaml[transformsSample#43](~/samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/SkewTransformExample.xaml#43)]  
  
 <span data-ttu-id="d6ccb-116">La ilustración siguiente muestra los diferentes sesgos que se usan en este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="d6ccb-116">The following illustration shows the different skews that are used in this example.</span></span>  
  
 <span data-ttu-id="d6ccb-117">![Ejemplos de SkewTransform](./media/img-wcpsdk-graphicsmm-skewtransformexample.gif "img_wcpsdk_graphicsmm_skewtransformexample")</span><span class="sxs-lookup"><span data-stu-id="d6ccb-117">![SkewTransform examples](./media/img-wcpsdk-graphicsmm-skewtransformexample.gif "img_wcpsdk_graphicsmm_skewtransformexample")</span></span>  
<span data-ttu-id="d6ccb-118">Los tres ejemplos de SkewTransform ilustrados</span><span class="sxs-lookup"><span data-stu-id="d6ccb-118">The three SkewTransform examples illustrated</span></span>  
  
 <span data-ttu-id="d6ccb-119">Para ver el ejemplo completo, consulte [Ejemplo de transformaciones 2D](https://go.microsoft.com/fwlink/?LinkID=158252).</span><span class="sxs-lookup"><span data-stu-id="d6ccb-119">For the complete sample, see [2-D Transforms Sample](https://go.microsoft.com/fwlink/?LinkID=158252).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d6ccb-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="d6ccb-120">See also</span></span>
- <xref:System.Windows.Media.Transform>
- <xref:System.Windows.Media.SkewTransform>
- [<span data-ttu-id="d6ccb-121">Información general sobre transformaciones</span><span class="sxs-lookup"><span data-stu-id="d6ccb-121">Transforms Overview</span></span>](transforms-overview.md)
- [<span data-ttu-id="d6ccb-122">Temas "Cómo..."</span><span class="sxs-lookup"><span data-stu-id="d6ccb-122">How-to Topics</span></span>](transformations-how-to-topics.md)
