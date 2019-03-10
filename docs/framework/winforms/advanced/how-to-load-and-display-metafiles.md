---
title: Filtrar Cargar y mostrar metarchivos
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- examples [Windows Forms], metafiles
- metafiles [Windows Forms], displaying
ms.assetid: 60af1714-f148-4d85-a739-0557965ffa73
ms.openlocfilehash: 121f285a95d0169db79bdc302d80dba03b3b40c2
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2019
ms.locfileid: "57720048"
---
# <a name="how-to-load-and-display-metafiles"></a><span data-ttu-id="4e946-102">Procedimiento Cargar y mostrar metarchivos</span><span class="sxs-lookup"><span data-stu-id="4e946-102">How to: Load and Display Metafiles</span></span>
<span data-ttu-id="4e946-103">El <xref:System.Drawing.Imaging.Metafile> (clase), que hereda de la <xref:System.Drawing.Image> de clases, que proporciona métodos para registrar, mostrar y examinar imágenes vectoriales.</span><span class="sxs-lookup"><span data-stu-id="4e946-103">The <xref:System.Drawing.Imaging.Metafile> class, which inherits from the <xref:System.Drawing.Image> class, provides methods for recording, displaying, and examining vector images.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4e946-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="4e946-104">Example</span></span>  
 <span data-ttu-id="4e946-105">Para mostrar una imagen vectorial (metarchivo) en la pantalla, necesita un <xref:System.Drawing.Imaging.Metafile> objeto y un <xref:System.Drawing.Graphics> objeto.</span><span class="sxs-lookup"><span data-stu-id="4e946-105">To display a vector image (metafile) on the screen, you need a <xref:System.Drawing.Imaging.Metafile> object and a <xref:System.Drawing.Graphics> object.</span></span> <span data-ttu-id="4e946-106">Pasar el nombre de un archivo (o una secuencia) a un <xref:System.Drawing.Imaging.Metafile> constructor.</span><span class="sxs-lookup"><span data-stu-id="4e946-106">Pass the name of a file (or a stream) to a <xref:System.Drawing.Imaging.Metafile> constructor.</span></span> <span data-ttu-id="4e946-107">Después de haber creado un <xref:System.Drawing.Imaging.Metafile> de objetos, pasar ese <xref:System.Drawing.Imaging.Metafile> de objeto para el <xref:System.Drawing.Graphics.DrawImage%2A> método de un <xref:System.Drawing.Graphics> objeto.</span><span class="sxs-lookup"><span data-stu-id="4e946-107">After you have created a <xref:System.Drawing.Imaging.Metafile> object, pass that <xref:System.Drawing.Imaging.Metafile> object to the <xref:System.Drawing.Graphics.DrawImage%2A> method of a <xref:System.Drawing.Graphics> object.</span></span>  
  
 <span data-ttu-id="4e946-108">El ejemplo se crea un <xref:System.Drawing.Imaging.Metafile> objeto desde un archivo EMF (metarchivo mejorado) y, a continuación, dibuja la imagen con la esquina superior izquierda en (60, 10).</span><span class="sxs-lookup"><span data-stu-id="4e946-108">The example creates a <xref:System.Drawing.Imaging.Metafile> object from an EMF (enhanced metafile) file and then draws the image with its upper-left corner at (60, 10).</span></span>  
  
 <span data-ttu-id="4e946-109">La siguiente ilustración muestra el metarchivo dibujado en la ubicación especificada.</span><span class="sxs-lookup"><span data-stu-id="4e946-109">The following illustration shows the metafile drawn at the specified location.</span></span>  
  
 <span data-ttu-id="4e946-110">![Posición de la imagen](./media/imageposition2.png "imageposition2")</span><span class="sxs-lookup"><span data-stu-id="4e946-110">![Image Position](./media/imageposition2.png "imageposition2")</span></span>  
  
 [!code-csharp[System.Drawing.WorkingWithImages#41](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#41)]
 [!code-vb[System.Drawing.WorkingWithImages#41](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#41)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="4e946-111">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="4e946-111">Compiling the Code</span></span>  
 <span data-ttu-id="4e946-112">El ejemplo anterior está diseñado para su uso con Windows Forms y requiere <xref:System.Windows.Forms.PaintEventArgs> `e`, que es un parámetro del controlador de eventos <xref:System.Windows.Forms.Control.Paint>.</span><span class="sxs-lookup"><span data-stu-id="4e946-112">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4e946-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="4e946-113">See also</span></span>
- [<span data-ttu-id="4e946-114">Trabajar con imágenes, mapas de bits, iconos y metarchivos</span><span class="sxs-lookup"><span data-stu-id="4e946-114">Working with Images, Bitmaps, Icons, and Metafiles</span></span>](working-with-images-bitmaps-icons-and-metafiles.md)
