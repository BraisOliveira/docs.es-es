---
title: Filtrar Especificar el origen de una transformación utilizando valores relativos
ms.date: 03/30/2017
helpviewer_keywords:
- origins of Transforms [WPF]
- Transforms [WPF], origins of
- graphics [WPF], origins of Transforms
ms.assetid: f4dbc29d-93c7-41cd-96d8-5cfd8624b470
ms.openlocfilehash: bdcc17e2d9bf68170c10dd8e35670f3e072a527c
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2019
ms.locfileid: "57352573"
---
# <a name="how-to-specify-the-origin-of-a-transform-by-using-relative-values"></a><span data-ttu-id="0824b-102">Filtrar Especificar el origen de una transformación utilizando valores relativos</span><span class="sxs-lookup"><span data-stu-id="0824b-102">How to: Specify the Origin of a Transform by Using Relative Values</span></span>
<span data-ttu-id="0824b-103">En este ejemplo se muestra cómo utilizar valores relativos para especificar el origen de un <xref:System.Windows.UIElement.RenderTransform%2A> que se aplica a un <xref:System.Windows.FrameworkElement>.</span><span class="sxs-lookup"><span data-stu-id="0824b-103">This example shows how to use relative values to specify the origin of a <xref:System.Windows.UIElement.RenderTransform%2A> that is applied to a <xref:System.Windows.FrameworkElement>.</span></span>  
  
 <span data-ttu-id="0824b-104">Al girar, escalar o sesgar un <xref:System.Windows.FrameworkElement> utilizando el <xref:System.Windows.UIElement.RenderTransform%2A> propiedad, el valor predeterminado aplica la transformación a la esquina superior izquierda del elemento.</span><span class="sxs-lookup"><span data-stu-id="0824b-104">When you rotate, scale, or skew a <xref:System.Windows.FrameworkElement> by using the <xref:System.Windows.UIElement.RenderTransform%2A> property, the default setting applies the transform to the upper-left corner of the element.</span></span> <span data-ttu-id="0824b-105">Si desea girar, escalar o sesgar desde el centro del elemento, puede realizar la compensación estableciendo el centro de la transformación en el centro del elemento.</span><span class="sxs-lookup"><span data-stu-id="0824b-105">If you want to rotate, scale, or skew from the center of the element, you can compensate by setting the center of the transform to the center of the element.</span></span> <span data-ttu-id="0824b-106">Sin embargo, esa solución requiere que conozca el tamaño del elemento.</span><span class="sxs-lookup"><span data-stu-id="0824b-106">However, that solution requires that you know the size of the element.</span></span> <span data-ttu-id="0824b-107">Una manera más fácil de aplicar una transformación al centro de un elemento es establecer su <xref:System.Windows.UIElement.RenderTransformOrigin%2A> propiedad en (0,5, 0,5), en lugar de establecer un valor central en la propia transformación.</span><span class="sxs-lookup"><span data-stu-id="0824b-107">An easier way of applying a transform to the center of an element is to set its <xref:System.Windows.UIElement.RenderTransformOrigin%2A> property to (0.5, 0.5), instead of setting a center value on the transform itself.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0824b-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="0824b-108">Example</span></span>  
 <span data-ttu-id="0824b-109">En el ejemplo siguiente se usa un <xref:System.Windows.Media.RotateTransform> para girar un <xref:System.Windows.Controls.Button> 45 grados a la derecha.</span><span class="sxs-lookup"><span data-stu-id="0824b-109">The following example uses a <xref:System.Windows.Media.RotateTransform> to rotate a <xref:System.Windows.Controls.Button> 45 degrees clockwise.</span></span> <span data-ttu-id="0824b-110">Puesto que el ejemplo no especifica un centro, el botón gira sobre el punto (0, 0), que está en la esquina superior izquierda.</span><span class="sxs-lookup"><span data-stu-id="0824b-110">Because the example does not specify a center, the button rotates about the point (0, 0), which is its upper-left corner.</span></span> <span data-ttu-id="0824b-111">El <xref:System.Windows.Media.RotateTransform> se aplica a la <xref:System.Windows.UIElement.RenderTransform%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="0824b-111">The <xref:System.Windows.Media.RotateTransform> is applied to the <xref:System.Windows.UIElement.RenderTransform%2A> property.</span></span>  
  
 <span data-ttu-id="0824b-112">La siguiente ilustración muestra el resultado de la transformación del ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="0824b-112">The following illustration shows the transformation result for the example that follows.</span></span>  
  
 <span data-ttu-id="0824b-113">![Botón transformado mediante RenderTransform](./media/graphicsmm-rendertransformwithdefaultcenter.png "graphicsmm_RenderTransformWithDefaultCenter")</span><span class="sxs-lookup"><span data-stu-id="0824b-113">![A button transformed using RenderTransform](./media/graphicsmm-rendertransformwithdefaultcenter.png "graphicsmm_RenderTransformWithDefaultCenter")</span></span>  
<span data-ttu-id="0824b-114">Giro hacia la derecha de 45 grados utilizando la propiedad RenderTransform</span><span class="sxs-lookup"><span data-stu-id="0824b-114">A 45 degree clockwise rotation by using the RenderTransform property</span></span>  
  
 [!code-xaml[Transforms_snip#GraphicsMMRotateButtonExample1](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/ButtonRotateTransformExample.xaml#graphicsmmrotatebuttonexample1)]  
  
 <span data-ttu-id="0824b-115">El ejemplo siguiente se usa también un <xref:System.Windows.Media.RotateTransform> para girar un <xref:System.Windows.Controls.Button> 45 grados a la derecha; sin embargo, este ejemplo se establece la <xref:System.Windows.UIElement.RenderTransformOrigin%2A> del botón en (0,5, 0,5).</span><span class="sxs-lookup"><span data-stu-id="0824b-115">The following example also uses a <xref:System.Windows.Media.RotateTransform> to rotate a <xref:System.Windows.Controls.Button> 45 degrees clockwise; however, this example sets the <xref:System.Windows.UIElement.RenderTransformOrigin%2A> of the button to (0.5, 0.5).</span></span> <span data-ttu-id="0824b-116">Como resultado, la rotación se aplica al centro del botón en lugar de a la esquina superior izquierda.</span><span class="sxs-lookup"><span data-stu-id="0824b-116">As a result, the rotation is applied to the center of the button instead of to the upper-left corner.</span></span>  
  
 <span data-ttu-id="0824b-117">La siguiente ilustración muestra el resultado de la transformación del ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="0824b-117">The following illustration shows the transformation result for the example that follows.</span></span>  
  
 <span data-ttu-id="0824b-118">![Botón transformado alrededor de su centro](./media/graphicsmm-rendertransformrelativecenter.png "graphicsmm_RenderTransformRelativeCenter")</span><span class="sxs-lookup"><span data-stu-id="0824b-118">![A button transformed about its center](./media/graphicsmm-rendertransformrelativecenter.png "graphicsmm_RenderTransformRelativeCenter")</span></span>  
<span data-ttu-id="0824b-119">Una rotación de 45 grados utilizando la propiedad RenderTransform con un valor de RenderTransformOrigin de (0,5, 0,5)</span><span class="sxs-lookup"><span data-stu-id="0824b-119">A 45 degree rotation by using the RenderTransform property with a RenderTransformOrigin of (0.5, 0.5)</span></span>  
  
 [!code-xaml[Transforms_snip#GraphicsMMRotateButtonExample2](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/ButtonRotateTransformExample.xaml#graphicsmmrotatebuttonexample2)]  
  
 <span data-ttu-id="0824b-120">Para obtener más información acerca de la transformación <xref:System.Windows.FrameworkElement> objetos, vea el [información general sobre transformaciones](transforms-overview.md).</span><span class="sxs-lookup"><span data-stu-id="0824b-120">For more information about transforming <xref:System.Windows.FrameworkElement> objects, see the [Transforms Overview](transforms-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0824b-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="0824b-121">See also</span></span>
- <xref:System.Windows.Media.Transform>
- [<span data-ttu-id="0824b-122">Información general sobre transformaciones</span><span class="sxs-lookup"><span data-stu-id="0824b-122">Transforms Overview</span></span>](transforms-overview.md)
- [<span data-ttu-id="0824b-123">Temas "Cómo..."</span><span class="sxs-lookup"><span data-stu-id="0824b-123">How-to Topics</span></span>](transformations-how-to-topics.md)
