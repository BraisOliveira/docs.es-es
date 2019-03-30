---
title: Filtrar Recortar y escalar imágenes
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- images [Windows Forms], cropping
- images [Windows Forms], scaling
ms.assetid: 053e3360-bca0-4b25-9afa-0e77a6f17b03
ms.openlocfilehash: ff0567dca0fd86736e02a9dd827ec15df8bf2df8
ms.sourcegitcommit: 15ab532fd5e1f8073a4b678922d93b68b521bfa0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/29/2019
ms.locfileid: "58654502"
---
# <a name="how-to-crop-and-scale-images"></a><span data-ttu-id="4dea2-102">Filtrar Recortar y escalar imágenes</span><span class="sxs-lookup"><span data-stu-id="4dea2-102">How to: Crop and Scale Images</span></span>
<span data-ttu-id="4dea2-103">El <xref:System.Drawing.Graphics> clase proporciona varios <xref:System.Drawing.Graphics.DrawImage%2A> métodos, algunos de los cuales tienen parámetros de rectángulo de origen y destino que pueden usar para recortar y escalar imágenes.</span><span class="sxs-lookup"><span data-stu-id="4dea2-103">The <xref:System.Drawing.Graphics> class provides several <xref:System.Drawing.Graphics.DrawImage%2A> methods, some of which have source and destination rectangle parameters that you can use to crop and scale images.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4dea2-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="4dea2-104">Example</span></span>  
 <span data-ttu-id="4dea2-105">En el ejemplo siguiente se crea un <xref:System.Drawing.Image> objeto desde el archivo de disco Apple.gif.</span><span class="sxs-lookup"><span data-stu-id="4dea2-105">The following example constructs an <xref:System.Drawing.Image> object from the disk file Apple.gif.</span></span> <span data-ttu-id="4dea2-106">El código dibuja la imagen completa en su tamaño original.</span><span class="sxs-lookup"><span data-stu-id="4dea2-106">The code draws the entire apple image in its original size.</span></span> <span data-ttu-id="4dea2-107">El código, a continuación, llama a la <xref:System.Drawing.Graphics.DrawImage%2A> método de un <xref:System.Drawing.Graphics> objeto que se va a dibujar una parte de la imagen de apple en un rectángulo de destino es mayor que la imagen original.</span><span class="sxs-lookup"><span data-stu-id="4dea2-107">The code then calls the <xref:System.Drawing.Graphics.DrawImage%2A> method of a <xref:System.Drawing.Graphics> object to draw a portion of the apple image in a destination rectangle that is larger than the original apple image.</span></span>  
  
 <span data-ttu-id="4dea2-108">El <xref:System.Drawing.Graphics.DrawImage%2A> método determina qué parte de la manzana que se va a dibujar observando el rectángulo de origen, que se especifica mediante el tercero, cuarto, quinto y sexto argumentos.</span><span class="sxs-lookup"><span data-stu-id="4dea2-108">The <xref:System.Drawing.Graphics.DrawImage%2A> method determines which portion of the apple to draw by looking at the source rectangle, which is specified by the third, fourth, fifth, and sixth arguments.</span></span> <span data-ttu-id="4dea2-109">En este caso, se recorta el apple al 75 por ciento de su ancho y el 75 por ciento de su alto.</span><span class="sxs-lookup"><span data-stu-id="4dea2-109">In this case, the apple is cropped to 75 percent of its width and 75 percent of its height.</span></span>  
  
 <span data-ttu-id="4dea2-110">El <xref:System.Drawing.Graphics.DrawImage%2A> método determina dónde se va a dibujar la manzana recortada y qué tamaño observando el rectángulo de destino, que es especificado por el segundo argumento.</span><span class="sxs-lookup"><span data-stu-id="4dea2-110">The <xref:System.Drawing.Graphics.DrawImage%2A> method determines where to draw the cropped apple and how big to make the cropped apple by looking at the destination rectangle, which is specified by the second argument.</span></span> <span data-ttu-id="4dea2-111">En este caso, el rectángulo de destino es el 30 por ciento más ancho y el 30 por ciento más alta de la imagen original.</span><span class="sxs-lookup"><span data-stu-id="4dea2-111">In this case, the destination rectangle is 30 percent wider and 30 percent taller than the original image.</span></span>  
  
 <span data-ttu-id="4dea2-112">La ilustración siguiente muestra la manzana original y la escala y recorta apple.</span><span class="sxs-lookup"><span data-stu-id="4dea2-112">The following illustration shows the original apple and the scaled, cropped apple.</span></span>  
  
 ![Captura de pantalla de una imagen original y la misma imagen recortada.](./media/how-to-crop-and-scale-images/original-image-cropped-image.png)  
  
 [!code-csharp[System.Drawing.WorkingWithImages#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.WorkingWithImages#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#11)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="4dea2-114">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="4dea2-114">Compiling the Code</span></span>  
 <span data-ttu-id="4dea2-115">El ejemplo anterior está diseñado para su uso con Windows Forms y requiere <xref:System.Windows.Forms.PaintEventArgs> `e`, que es un parámetro de la <xref:System.Windows.Forms.Control.Paint> controlador de eventos.</span><span class="sxs-lookup"><span data-stu-id="4dea2-115">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span> <span data-ttu-id="4dea2-116">No olvide reemplazar `Apple.gif` con un nombre de archivo de imagen y la ruta de acceso que son válidos en el sistema.</span><span class="sxs-lookup"><span data-stu-id="4dea2-116">Make sure to replace `Apple.gif` with an image file name and path that are valid on your system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4dea2-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="4dea2-117">See also</span></span>
- [<span data-ttu-id="4dea2-118">Imágenes, mapas de bits y metarchivos</span><span class="sxs-lookup"><span data-stu-id="4dea2-118">Images, Bitmaps, and Metafiles</span></span>](images-bitmaps-and-metafiles.md)
- [<span data-ttu-id="4dea2-119">Trabajar con imágenes, mapas de bits, iconos y metarchivos</span><span class="sxs-lookup"><span data-stu-id="4dea2-119">Working with Images, Bitmaps, Icons, and Metafiles</span></span>](working-with-images-bitmaps-icons-and-metafiles.md)
