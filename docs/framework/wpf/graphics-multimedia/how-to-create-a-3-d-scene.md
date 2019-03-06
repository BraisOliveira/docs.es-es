---
title: Filtrar Crear una escena 3D
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- scenes [WPF], 3-D
- 3-D scenes
ms.assetid: adb4a598-71a2-4dd5-b677-ea3fc11b78b2
ms.openlocfilehash: 8c9aec78bdda4f9f122b6dbefe0956ba649adf22
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2019
ms.locfileid: "57370753"
---
# <a name="how-to-create-a-3-d-scene"></a><span data-ttu-id="d7e05-102">Procedimiento Crear una escena 3D</span><span class="sxs-lookup"><span data-stu-id="d7e05-102">How to: Create a 3-D Scene</span></span>
<span data-ttu-id="d7e05-103">En este ejemplo se muestra cómo crear un objeto 3D que parece una hoja de papel que se ha girado plana.</span><span class="sxs-lookup"><span data-stu-id="d7e05-103">This example shows how to create a 3-D object that looks like a flat sheet of paper which has been rotated.</span></span> <span data-ttu-id="d7e05-104">Un <xref:System.Windows.Controls.Viewport3D> junto con los siguientes componentes se usan para crear esta escena 3D sencilla:</span><span class="sxs-lookup"><span data-stu-id="d7e05-104">A <xref:System.Windows.Controls.Viewport3D> along with the following components are used to create this simple 3-D scene:</span></span>  
  
-   <span data-ttu-id="d7e05-105">Se crea una cámara mediante un <xref:System.Windows.Media.Media3D.PerspectiveCamera>.</span><span class="sxs-lookup"><span data-stu-id="d7e05-105">A camera is created using a <xref:System.Windows.Media.Media3D.PerspectiveCamera>.</span></span> <span data-ttu-id="d7e05-106">La cámara especifica qué parte de la escena 3D es visible.</span><span class="sxs-lookup"><span data-stu-id="d7e05-106">The camera specifies what part of the 3-D scene is viewable.</span></span>  
  
-   <span data-ttu-id="d7e05-107">Se crea una malla para especificar la forma del objeto 3D (hoja de papel) mediante el <xref:System.Windows.Media.Media3D.GeometryModel3D.Geometry%2A> propiedad de <xref:System.Windows.Media.Media3D.GeometryModel3D>.</span><span class="sxs-lookup"><span data-stu-id="d7e05-107">A mesh is created to specify the shape of 3-D object (sheet of paper) using the <xref:System.Windows.Media.Media3D.GeometryModel3D.Geometry%2A> property of <xref:System.Windows.Media.Media3D.GeometryModel3D>.</span></span>  
  
-   <span data-ttu-id="d7e05-108">Se especifica el material que se mostrará en la superficie del objeto (degradado lineal en este ejemplo) mediante el <xref:System.Windows.Media.Media3D.GeometryModel3D.Material%2A> propiedad de <xref:System.Windows.Media.Media3D.GeometryModel3D>.</span><span class="sxs-lookup"><span data-stu-id="d7e05-108">A material is specified to be displayed on the surface of the object (linear gradient in this sample) using the <xref:System.Windows.Media.Media3D.GeometryModel3D.Material%2A> property of <xref:System.Windows.Media.Media3D.GeometryModel3D>.</span></span>  
  
-   <span data-ttu-id="d7e05-109">Se crea una luz para destacar del objeto mediante <xref:System.Windows.Media.Media3D.DirectionalLight>.</span><span class="sxs-lookup"><span data-stu-id="d7e05-109">A light is created to shine on the object using <xref:System.Windows.Media.Media3D.DirectionalLight>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d7e05-110">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d7e05-110">Example</span></span>  
 <span data-ttu-id="d7e05-111">El código siguiente muestra cómo crear una escena 3D en XAML.</span><span class="sxs-lookup"><span data-stu-id="d7e05-111">The code below shows how to create a 3-D scene in XAML.</span></span>  
  
 [!code-xaml[3DGallery_snip#Basic3DShapeExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/Basic3DShapeExample.xaml#basic3dshapeexamplewholepage)]  
  
## <a name="example"></a><span data-ttu-id="d7e05-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d7e05-112">Example</span></span>  
 <span data-ttu-id="d7e05-113">El código siguiente muestra cómo crear la misma escena 3D en el código de procedimiento.</span><span class="sxs-lookup"><span data-stu-id="d7e05-113">The code below shows how to create the same 3-D scene in procedural code.</span></span>  
  
 [!code-csharp[3DGallery_procedural_snip#Basic3DShapeCodeExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_procedural_snip/CSharp/Basic3DShapeExample.cs#basic3dshapecodeexamplewholepage)]
 [!code-vb[3DGallery_procedural_snip#Basic3DShapeCodeExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/3DGallery_procedural_snip/visualbasic/basic3dshapeexample.vb#basic3dshapecodeexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="d7e05-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="d7e05-114">See also</span></span>
- [<span data-ttu-id="d7e05-115">Información general sobre gráficos 3D</span><span class="sxs-lookup"><span data-stu-id="d7e05-115">3-D Graphics Overview</span></span>](3-d-graphics-overview.md)
