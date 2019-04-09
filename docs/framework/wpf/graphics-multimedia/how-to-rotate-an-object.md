---
title: Filtrar Girar un objeto
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- graphics [WPF], rotating objects [WPF]
- rotating objects [WPF]
ms.assetid: ee3466cd-e66f-4e8f-8a5a-71d77bc1e390
ms.openlocfilehash: d1c4700a5dc8f6ed99043552999d8f014116da8f
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59189677"
---
# <a name="how-to-rotate-an-object"></a><span data-ttu-id="20764-102">Filtrar Girar un objeto</span><span class="sxs-lookup"><span data-stu-id="20764-102">How to: Rotate an Object</span></span>
<span data-ttu-id="20764-103">Este ejemplo muestra cómo girar un objeto.</span><span class="sxs-lookup"><span data-stu-id="20764-103">This example shows how to rotate an object.</span></span> <span data-ttu-id="20764-104">El ejemplo crea primero un <xref:System.Windows.Media.RotateTransform> y, a continuación, especifica su <xref:System.Windows.Media.RotateTransform.Angle%2A> en grados.</span><span class="sxs-lookup"><span data-stu-id="20764-104">The example first creates a <xref:System.Windows.Media.RotateTransform> and then specifies its <xref:System.Windows.Media.RotateTransform.Angle%2A> in degrees.</span></span>  
  
 <span data-ttu-id="20764-105">En el ejemplo siguiente se gira un <xref:System.Windows.Shapes.Polyline> objeto 45 grados sobre su esquina superior izquierda.</span><span class="sxs-lookup"><span data-stu-id="20764-105">The following example rotates a <xref:System.Windows.Shapes.Polyline> object 45 degrees about its upper-left corner.</span></span>  
  
## <a name="example"></a><span data-ttu-id="20764-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="20764-106">Example</span></span>  
 [!code-xaml[Transforms_snip#RotatePolylineAboutTopLeft](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/RotateTransformExample.xaml#rotatepolylineabouttopleft)]  
  
 [!code-csharp[Transforms_Procedural_snip#RotatePolylineAboutTopLeft](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_Procedural_snip/CSharp/RotateTransformExample.cs#rotatepolylineabouttopleft)]
 [!code-vb[Transforms_Procedural_snip#RotatePolylineAboutTopLeft](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Transforms_Procedural_snip/VisualBasic/RotateTransformExample.vb#rotatepolylineabouttopleft)]  
  
 <span data-ttu-id="20764-107">El <xref:System.Windows.Media.RotateTransform.CenterX%2A> y <xref:System.Windows.Media.RotateTransform.CenterY%2A> propiedades de la <xref:System.Windows.Media.RotateTransform> especificar el punto sobre el que se gira el objeto.</span><span class="sxs-lookup"><span data-stu-id="20764-107">The <xref:System.Windows.Media.RotateTransform.CenterX%2A> and <xref:System.Windows.Media.RotateTransform.CenterY%2A> properties of the <xref:System.Windows.Media.RotateTransform> specify the point about which the object is rotated.</span></span> <span data-ttu-id="20764-108">Este punto central se expresa en el espacio de coordenadas del elemento que se transforma.</span><span class="sxs-lookup"><span data-stu-id="20764-108">This center point is expressed in the coordinate space of the element that is transformed.</span></span> <span data-ttu-id="20764-109">De forma predeterminada, la rotación se aplica a (0,0), que es la esquina superior izquierda del objeto que transformar.</span><span class="sxs-lookup"><span data-stu-id="20764-109">By default, the rotation is applied to (0,0), which is the upper-left corner of the object to transform.</span></span>  
  
 <span data-ttu-id="20764-110">El siguiente ejemplo se gira un <xref:System.Windows.Shapes.Polyline> objeto hacia la derecha 45 grados sobre el punto (25,50).</span><span class="sxs-lookup"><span data-stu-id="20764-110">The next example rotates a <xref:System.Windows.Shapes.Polyline> object clockwise 45 degrees about the point (25,50).</span></span>  
  
 [!code-xaml[Transforms_snip#RotatePolylineAboutCenter](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/RotateTransformExample.xaml#rotatepolylineaboutcenter)]  
  
 [!code-csharp[Transforms_Procedural_snip#RotatePolylineAboutCenter](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_Procedural_snip/CSharp/RotateTransformExample.cs#rotatepolylineaboutcenter)]
 [!code-vb[Transforms_Procedural_snip#RotatePolylineAboutCenter](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Transforms_Procedural_snip/VisualBasic/RotateTransformExample.vb#rotatepolylineaboutcenter)]  
  
 <span data-ttu-id="20764-111">La siguiente ilustración muestra el resultado de aplicar un <xref:System.Windows.Media.Transform> a los dos objetos.</span><span class="sxs-lookup"><span data-stu-id="20764-111">The following illustration shows the results of applying a <xref:System.Windows.Media.Transform> to the two objects.</span></span>  
  
 <span data-ttu-id="20764-112">![Rotaciones de 45 grados con diferentes puntos centrales](./media/wcpsdk-graphicsmm-rotatetransform45degrees.gif "wcpsdk_graphicsmm_rotatetransform45degrees")</span><span class="sxs-lookup"><span data-stu-id="20764-112">![45 degree rotations with different center points](./media/wcpsdk-graphicsmm-rotatetransform45degrees.gif "wcpsdk_graphicsmm_rotatetransform45degrees")</span></span>  
<span data-ttu-id="20764-113">Dos objetos que se giran 45 grados desde distintos centros de giro</span><span class="sxs-lookup"><span data-stu-id="20764-113">Two objects that rotate 45 degrees from different rotational centers</span></span>  
  
 <span data-ttu-id="20764-114">El <xref:System.Windows.Shapes.Polyline> en los ejemplos anteriores es un <xref:System.Windows.UIElement>.</span><span class="sxs-lookup"><span data-stu-id="20764-114">The <xref:System.Windows.Shapes.Polyline> in the previous examples is a <xref:System.Windows.UIElement>.</span></span> <span data-ttu-id="20764-115">Al aplicar un <xref:System.Windows.Media.Transform> a la <xref:System.Windows.UIElement.RenderTransform%2A> propiedad de un <xref:System.Windows.UIElement>, puede usar el <xref:System.Windows.UIElement.RenderTransformOrigin%2A> propiedad para especificar un origen para cada <xref:System.Windows.Media.Transform> que se aplican al elemento.</span><span class="sxs-lookup"><span data-stu-id="20764-115">When you apply a <xref:System.Windows.Media.Transform> to the <xref:System.Windows.UIElement.RenderTransform%2A> property of a <xref:System.Windows.UIElement>, you can use the <xref:System.Windows.UIElement.RenderTransformOrigin%2A> property to specify an origin for every <xref:System.Windows.Media.Transform> that you apply to the element.</span></span> <span data-ttu-id="20764-116">Dado que el <xref:System.Windows.UIElement.RenderTransformOrigin%2A> propiedad usa coordenadas relativas, puede aplicar una transformación al centro del elemento incluso si no conoce su tamaño.</span><span class="sxs-lookup"><span data-stu-id="20764-116">Because the <xref:System.Windows.UIElement.RenderTransformOrigin%2A> property uses relative coordinates, you can apply a transformation to the center of the element even if you do not know its size.</span></span> <span data-ttu-id="20764-117">Para obtener más información y para obtener un ejemplo, vea [especificar el origen de una transformación utilizando valores relativos](how-to-specify-the-origin-of-a-transform-by-using-relative-values.md).</span><span class="sxs-lookup"><span data-stu-id="20764-117">For more information and for an example, see [Specify the Origin of a Transform by Using Relative Values](how-to-specify-the-origin-of-a-transform-by-using-relative-values.md).</span></span>  
  
 <span data-ttu-id="20764-118">Para ver el ejemplo completo, consulte [Ejemplo de transformaciones 2D](https://go.microsoft.com/fwlink/?LinkID=158252).</span><span class="sxs-lookup"><span data-stu-id="20764-118">For the complete sample, see [2-D Transforms Sample](https://go.microsoft.com/fwlink/?LinkID=158252).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="20764-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="20764-119">See also</span></span>

- <xref:System.Windows.Media.Transform>
- [<span data-ttu-id="20764-120">Información general sobre transformaciones</span><span class="sxs-lookup"><span data-stu-id="20764-120">Transforms Overview</span></span>](transforms-overview.md)
- [<span data-ttu-id="20764-121">Temas "Cómo..."</span><span class="sxs-lookup"><span data-stu-id="20764-121">How-to Topics</span></span>](transformations-how-to-topics.md)
