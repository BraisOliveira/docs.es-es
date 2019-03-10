---
title: Procedimiento Utilizar una tabla de reasignación de colores
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- color tables [Windows Forms], remapping colors with
- custom colors [Windows Forms], creating with color remap table
- color remap tables [Windows Forms], using
ms.assetid: 977df1ce-8665-42d4-9fb1-ef7f0ff63419
ms.openlocfilehash: 72965d6968aab256579929acc00e629bcd3c71f0
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2019
ms.locfileid: "57707343"
---
# <a name="how-to-use-a-color-remap-table"></a><span data-ttu-id="a67bf-102">Filtrar Utilizar una tabla de reasignación de colores</span><span class="sxs-lookup"><span data-stu-id="a67bf-102">How to: Use a Color Remap Table</span></span>
<span data-ttu-id="a67bf-103">Reasignación es el proceso de convertir los colores de una imagen según una tabla de reasignación de colores.</span><span class="sxs-lookup"><span data-stu-id="a67bf-103">Remapping is the process of converting the colors in an image according to a color remap table.</span></span> <span data-ttu-id="a67bf-104">La tabla de reasignación de colores es una matriz de <xref:System.Drawing.Imaging.ColorMap> objetos.</span><span class="sxs-lookup"><span data-stu-id="a67bf-104">The color remap table is an array of <xref:System.Drawing.Imaging.ColorMap> objects.</span></span> <span data-ttu-id="a67bf-105">Cada <xref:System.Drawing.Imaging.ColorMap> objeto de la matriz tiene un <xref:System.Drawing.Imaging.ColorMap.OldColor%2A> propiedad y un <xref:System.Drawing.Imaging.ColorMap.NewColor%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="a67bf-105">Each <xref:System.Drawing.Imaging.ColorMap> object in the array has an <xref:System.Drawing.Imaging.ColorMap.OldColor%2A> property and a <xref:System.Drawing.Imaging.ColorMap.NewColor%2A> property.</span></span>  
  
 <span data-ttu-id="a67bf-106">Cuando [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] dibuja una imagen, cada píxel de la imagen se compara con la matriz de colores antiguos.</span><span class="sxs-lookup"><span data-stu-id="a67bf-106">When [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] draws an image, each pixel of the image is compared to the array of old colors.</span></span> <span data-ttu-id="a67bf-107">Si el color de un píxel coincide con un color antiguo, su color cambia al color nuevo correspondiente.</span><span class="sxs-lookup"><span data-stu-id="a67bf-107">If a pixel's color matches an old color, its color is changed to the corresponding new color.</span></span> <span data-ttu-id="a67bf-108">Los colores cambian para la representación, los valores de color de la imagen en Sí (almacenado en un <xref:System.Drawing.Image> o <xref:System.Drawing.Bitmap> objeto) no cambian.</span><span class="sxs-lookup"><span data-stu-id="a67bf-108">The colors are changed only for rendering — the color values of the image itself (stored in an <xref:System.Drawing.Image> or <xref:System.Drawing.Bitmap> object) are not changed.</span></span>  
  
 <span data-ttu-id="a67bf-109">Para dibujar una imagen reasignada, inicialice una matriz de <xref:System.Drawing.Imaging.ColorMap> objetos.</span><span class="sxs-lookup"><span data-stu-id="a67bf-109">To draw a remapped image, initialize an array of <xref:System.Drawing.Imaging.ColorMap> objects.</span></span> <span data-ttu-id="a67bf-110">Pasar esa matriz a la <xref:System.Drawing.Imaging.ImageAttributes.SetRemapTable%2A> método de un <xref:System.Drawing.Imaging.ImageAttributes> de objetos y, a continuación, pasar la <xref:System.Drawing.Imaging.ImageAttributes> de objeto para el <xref:System.Drawing.Graphics.DrawImage%2A> método de un <xref:System.Drawing.Graphics> objeto.</span><span class="sxs-lookup"><span data-stu-id="a67bf-110">Pass that array to the <xref:System.Drawing.Imaging.ImageAttributes.SetRemapTable%2A> method of an <xref:System.Drawing.Imaging.ImageAttributes> object, and then pass the <xref:System.Drawing.Imaging.ImageAttributes> object to the <xref:System.Drawing.Graphics.DrawImage%2A> method of a <xref:System.Drawing.Graphics> object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a67bf-111">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a67bf-111">Example</span></span>  
 <span data-ttu-id="a67bf-112">En el ejemplo siguiente se crea un <xref:System.Drawing.Image> objeto a partir del archivo RemapInput.bmp.</span><span class="sxs-lookup"><span data-stu-id="a67bf-112">The following example creates an <xref:System.Drawing.Image> object from the file RemapInput.bmp.</span></span> <span data-ttu-id="a67bf-113">El código crea una tabla de reasignación de colores que consta de una sola <xref:System.Drawing.Imaging.ColorMap> objeto.</span><span class="sxs-lookup"><span data-stu-id="a67bf-113">The code creates a color remap table that consists of a single <xref:System.Drawing.Imaging.ColorMap> object.</span></span> <span data-ttu-id="a67bf-114">El <xref:System.Drawing.Imaging.ColorMap.OldColor%2A> propiedad de la `ColorRemap` objeto está en rojo y el <xref:System.Drawing.Imaging.ColorMap.NewColor%2A> propiedad es azul.</span><span class="sxs-lookup"><span data-stu-id="a67bf-114">The <xref:System.Drawing.Imaging.ColorMap.OldColor%2A> property of the `ColorRemap` object is red, and the <xref:System.Drawing.Imaging.ColorMap.NewColor%2A> property is blue.</span></span> <span data-ttu-id="a67bf-115">La imagen es una vez dibujada sin reasignación y otra vez con reasignación.</span><span class="sxs-lookup"><span data-stu-id="a67bf-115">The image is drawn once without remapping and once with remapping.</span></span> <span data-ttu-id="a67bf-116">El proceso de reasignación cambia todos los píxeles de rojo a azul.</span><span class="sxs-lookup"><span data-stu-id="a67bf-116">The remapping process changes all the red pixels to blue.</span></span>  
  
 <span data-ttu-id="a67bf-117">La siguiente ilustración muestra la imagen original a la izquierda y la imagen reasignada a la derecha.</span><span class="sxs-lookup"><span data-stu-id="a67bf-117">The following illustration shows the original image on the left and the remapped image on the right.</span></span>  
  
 <span data-ttu-id="a67bf-118">![Reasignación de colores](./media/colortrans7.png "colortrans7")</span><span class="sxs-lookup"><span data-stu-id="a67bf-118">![Color ReMap](./media/colortrans7.png "colortrans7")</span></span>  
  
 [!code-csharp[System.Drawing.RecoloringImages#31](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.RecoloringImages/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.RecoloringImages#31](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.RecoloringImages/VB/Class1.vb#31)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="a67bf-119">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="a67bf-119">Compiling the Code</span></span>  
 <span data-ttu-id="a67bf-120">El ejemplo anterior está diseñado para su uso con Windows Forms y requiere <xref:System.Windows.Forms.PaintEventArgs>`e`, que es un parámetro del controlador de eventos <xref:System.Windows.Forms.Control.Paint>.</span><span class="sxs-lookup"><span data-stu-id="a67bf-120">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs>`e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a67bf-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="a67bf-121">See also</span></span>
- [<span data-ttu-id="a67bf-122">Cambiar el color de las imágenes</span><span class="sxs-lookup"><span data-stu-id="a67bf-122">Recoloring Images</span></span>](recoloring-images.md)
- [<span data-ttu-id="a67bf-123">Imágenes, mapas de bits y metarchivos</span><span class="sxs-lookup"><span data-stu-id="a67bf-123">Images, Bitmaps, and Metafiles</span></span>](images-bitmaps-and-metafiles.md)
