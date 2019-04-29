---
title: Procedimiento Transformar la escala de un modelo 3D
ms.date: 03/30/2017
helpviewer_keywords:
- scaling [WPF], 3-D objects
- 3-D objects [WPF], scaling
ms.assetid: f3fdfe33-f7dc-44b0-84a5-e43b89947f35
ms.openlocfilehash: 6d668de08201d819ce9f8752bedf6c388a6bc718
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61769335"
---
# <a name="how-to-transform-the-scale-of-a-3-d-model"></a><span data-ttu-id="3fb7d-102">Procedimiento Transformar la escala de un modelo 3D</span><span class="sxs-lookup"><span data-stu-id="3fb7d-102">How to: Transform the Scale of a 3-D Model</span></span>
<span data-ttu-id="3fb7d-103">En este ejemplo se muestra cómo escalar un objeto 3D.</span><span class="sxs-lookup"><span data-stu-id="3fb7d-103">This example shows how to scale a 3-D object.</span></span> <span data-ttu-id="3fb7d-104">Para escalar un objeto 3D, use un <xref:System.Windows.Media.Media3D.ScaleTransform3D>.</span><span class="sxs-lookup"><span data-stu-id="3fb7d-104">To scale a 3-D object, use a <xref:System.Windows.Media.Media3D.ScaleTransform3D>.</span></span> <span data-ttu-id="3fb7d-105">El <xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleX%2A>, <xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleY%2A>, y <xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleZ%2A> propiedades, cambie el tamaño del elemento por el factor que especifique.</span><span class="sxs-lookup"><span data-stu-id="3fb7d-105">The <xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleX%2A>, <xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleY%2A>, and <xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleZ%2A> properties resize the element by the factor you specify.</span></span> <span data-ttu-id="3fb7d-106">Por ejemplo, un <xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleX%2A> valor de 1,5 ajusta un objeto al 150 por ciento de su ancho original.</span><span class="sxs-lookup"><span data-stu-id="3fb7d-106">For example, a <xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleX%2A> value of 1.5 stretches an object to 150 percent of its original width.</span></span> <span data-ttu-id="3fb7d-107">Un <xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleY%2A> valor de 0,5 reduce el alto de un objeto en un 50%.</span><span class="sxs-lookup"><span data-stu-id="3fb7d-107">A <xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleY%2A> value of 0.5 shrinks the height of an object by 50 percent.</span></span> <span data-ttu-id="3fb7d-108">El código siguiente muestra mediante un <xref:System.Windows.Media.Media3D.ScaleTransform3D> como la transformación para un <xref:System.Windows.Media.Media3D.GeometryModel3D>.</span><span class="sxs-lookup"><span data-stu-id="3fb7d-108">The code below shows using a <xref:System.Windows.Media.Media3D.ScaleTransform3D> as the transform for a <xref:System.Windows.Media.Media3D.GeometryModel3D>.</span></span>  
  
 [!code-xaml[3DGallery_snip#ScaleTransform3DExampleInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/ScaleTransform3DExample.xaml#scaletransform3dexampleinline1)]  
  
## <a name="example"></a><span data-ttu-id="3fb7d-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="3fb7d-109">Example</span></span>  
 <span data-ttu-id="3fb7d-110">El código siguiente muestra el ejemplo completo.</span><span class="sxs-lookup"><span data-stu-id="3fb7d-110">The following code shows the entire sample.</span></span>  
  
 [!code-xaml[3DGallery_snip#ScaleTransform3DExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/ScaleTransform3DExample.xaml#scaletransform3dexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="3fb7d-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="3fb7d-111">See also</span></span>

- [<span data-ttu-id="3fb7d-112">Animar traslaciones 3D</span><span class="sxs-lookup"><span data-stu-id="3fb7d-112">Animate 3-D Translations</span></span>](how-to-animate-3-d-translations.md)
- [<span data-ttu-id="3fb7d-113">Crear una escena 3D</span><span class="sxs-lookup"><span data-stu-id="3fb7d-113">Create a 3-D Scene</span></span>](how-to-create-a-3-d-scene.md)
- [<span data-ttu-id="3fb7d-114">Información general sobre gráficos 3D</span><span class="sxs-lookup"><span data-stu-id="3fb7d-114">3-D Graphics Overview</span></span>](3-d-graphics-overview.md)
