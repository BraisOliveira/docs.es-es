---
title: Filtrar para convertir una imagen BMP en una imagen PNG
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- BMP images [Windows Forms], converting to PNG
- image formats [Windows Forms], converting between
ms.assetid: 9d4a692d-73ac-4ce3-9e05-9ec321e8fbd6
ms.openlocfilehash: 3072c07781a8e8e57b64b48e5b4c304c2a0a0efb
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59217021"
---
# <a name="how-to-convert-a-bmp-image-to-a-png-image"></a><span data-ttu-id="b6313-102">Filtrar para convertir una imagen BMP en una imagen PNG</span><span class="sxs-lookup"><span data-stu-id="b6313-102">How to: Convert a BMP image to a PNG image</span></span>
<span data-ttu-id="b6313-103">A menudo, deseará convertir de un formato a otro.</span><span class="sxs-lookup"><span data-stu-id="b6313-103">Oftentimes, you will want to convert from one image file format to another.</span></span> <span data-ttu-id="b6313-104">Puede hacer esta conversión fácilmente llamando al método <xref:System.Drawing.Image.Save%2A> de la clase <xref:System.Drawing.Image> y especificando <xref:System.Drawing.Imaging.ImageFormat> para el formato de archivo de imagen deseado.</span><span class="sxs-lookup"><span data-stu-id="b6313-104">You can do this conversion easily by calling the <xref:System.Drawing.Image.Save%2A> method of the <xref:System.Drawing.Image> class and specifying the <xref:System.Drawing.Imaging.ImageFormat> for the desired image file format.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b6313-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="b6313-105">Example</span></span>  
 <span data-ttu-id="b6313-106">En el ejemplo siguiente, se carga una imagen BMP de un tipo y se guarda la imagen en formato PNG.</span><span class="sxs-lookup"><span data-stu-id="b6313-106">The following example loads a BMP image from a type, and saves the image in the PNG format.</span></span>  
  
 [!code-csharp[UsingImageEncodersDecoders#4](~/samples/snippets/csharp/VS_Snippets_Winforms/UsingImageEncodersDecoders/CS/Form1.cs#4)]
 [!code-vb[UsingImageEncodersDecoders#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/UsingImageEncodersDecoders/VB/Form1.vb#4)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="b6313-107">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="b6313-107">Compiling the Code</span></span>  
 <span data-ttu-id="b6313-108">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="b6313-108">This example requires:</span></span>  
  
-   <span data-ttu-id="b6313-109">Una aplicación de Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="b6313-109">A Windows Forms application.</span></span>  
  
-   <span data-ttu-id="b6313-110">Una referencia al espacio de nombres `System.Drawing.Imaging`.</span><span class="sxs-lookup"><span data-stu-id="b6313-110">A reference to the `System.Drawing.Imaging` namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b6313-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="b6313-111">See also</span></span>

- [<span data-ttu-id="b6313-112">Filtrar para enumerar los codificadores instalados</span><span class="sxs-lookup"><span data-stu-id="b6313-112">How to: List Installed Encoders</span></span>](how-to-list-installed-encoders.md)
- [<span data-ttu-id="b6313-113">Usar codificadores y descodificadores de imagen en la interfaz GDI+ administrada</span><span class="sxs-lookup"><span data-stu-id="b6313-113">Using Image Encoders and Decoders in Managed GDI+</span></span>](using-image-encoders-and-decoders-in-managed-gdi.md)
- [<span data-ttu-id="b6313-114">Tipos de mapas de bits</span><span class="sxs-lookup"><span data-stu-id="b6313-114">Types of Bitmaps</span></span>](types-of-bitmaps.md)
