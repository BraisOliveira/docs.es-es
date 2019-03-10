---
title: Procedimiento Enumerar los codificadores instalados
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- image codecs [Windows Forms], listing
- image encoders [Windows Forms], listing
ms.assetid: 49e8e4e9-7a67-42d9-86bf-08821cdc282e
ms.openlocfilehash: 492930b7d8a47db478c8fa0f282cb5f491e144ac
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2019
ms.locfileid: "57708462"
---
# <a name="how-to-list-installed-encoders"></a><span data-ttu-id="5658e-102">Procedimiento Enumerar los codificadores instalados</span><span class="sxs-lookup"><span data-stu-id="5658e-102">How to: List Installed Encoders</span></span>
<span data-ttu-id="5658e-103">Es posible que desee enumerar los codificadores de imagen disponibles en un equipo, para determinar si la aplicación puede guardar en un formato de archivo de imagen determinado.</span><span class="sxs-lookup"><span data-stu-id="5658e-103">You may want to list the image encoders available on a computer, to determine whether your application can save to a particular image file format.</span></span> <span data-ttu-id="5658e-104">El <xref:System.Drawing.Imaging.ImageCodecInfo> clase proporciona el <xref:System.Drawing.Imaging.ImageCodecInfo.GetImageEncoders%2A> métodos estáticos para que pueda determinar los codificadores de imagen que están disponibles.</span><span class="sxs-lookup"><span data-stu-id="5658e-104">The <xref:System.Drawing.Imaging.ImageCodecInfo> class provides the <xref:System.Drawing.Imaging.ImageCodecInfo.GetImageEncoders%2A> static methods so that you can determine which image encoders are available.</span></span> <span data-ttu-id="5658e-105"><xref:System.Drawing.Imaging.ImageCodecInfo.GetImageEncoders%2A> Devuelve una matriz de <xref:System.Drawing.Imaging.ImageCodecInfo> objetos.</span><span class="sxs-lookup"><span data-stu-id="5658e-105"><xref:System.Drawing.Imaging.ImageCodecInfo.GetImageEncoders%2A> returns an array of <xref:System.Drawing.Imaging.ImageCodecInfo> objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5658e-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="5658e-106">Example</span></span>  
 <span data-ttu-id="5658e-107">El ejemplo de código siguiente genera la lista de los codificadores instalados y sus valores de propiedad.</span><span class="sxs-lookup"><span data-stu-id="5658e-107">The following code example outputs the list of installed encoders and their property values.</span></span>  
  
 [!code-csharp[UsingImageEncodersDecoders#1](~/samples/snippets/csharp/VS_Snippets_Winforms/UsingImageEncodersDecoders/CS/Form1.cs#1)]
 [!code-vb[UsingImageEncodersDecoders#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/UsingImageEncodersDecoders/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="5658e-108">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="5658e-108">Compiling the Code</span></span>  
 <span data-ttu-id="5658e-109">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="5658e-109">This example requires:</span></span>  
  
-   <span data-ttu-id="5658e-110">Una aplicación de Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="5658e-110">A Windows Forms application.</span></span>  
  
-   <span data-ttu-id="5658e-111">Un <xref:System.Windows.Forms.PaintEventArgs>, que es un parámetro de <xref:System.Windows.Forms.PaintEventHandler>.</span><span class="sxs-lookup"><span data-stu-id="5658e-111">A <xref:System.Windows.Forms.PaintEventArgs>, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5658e-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="5658e-112">See also</span></span>
- [<span data-ttu-id="5658e-113">Cómo: Enumerar los descodificadores instalados</span><span class="sxs-lookup"><span data-stu-id="5658e-113">How to: List Installed Decoders</span></span>](how-to-list-installed-decoders.md)
- [<span data-ttu-id="5658e-114">Usar codificadores y descodificadores de imagen en la interfaz GDI+ administrada</span><span class="sxs-lookup"><span data-stu-id="5658e-114">Using Image Encoders and Decoders in Managed GDI+</span></span>](using-image-encoders-and-decoders-in-managed-gdi.md)
