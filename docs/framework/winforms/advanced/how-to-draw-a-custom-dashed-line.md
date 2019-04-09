---
title: Filtrar para dibujar una línea discontinua personalizada
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- lines [Windows Forms], custom
- lines [Windows Forms], drawing
- lines [Windows Forms], dashed
ms.assetid: cd0ed96a-cce4-47b9-b58a-3bae2e3d1bee
ms.openlocfilehash: 8dc1ad41cf8067bea5b811ca126ad29f5a600f69
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59109192"
---
# <a name="how-to-draw-a-custom-dashed-line"></a><span data-ttu-id="d0463-102">Filtrar para dibujar una línea discontinua personalizada</span><span class="sxs-lookup"><span data-stu-id="d0463-102">How to: Draw a Custom Dashed Line</span></span>
[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] <span data-ttu-id="d0463-103">proporciona varios estilos de guión que aparecen en la <xref:System.Drawing.Drawing2D.DashStyle> enumeración.</span><span class="sxs-lookup"><span data-stu-id="d0463-103">provides several dash styles that are listed in the <xref:System.Drawing.Drawing2D.DashStyle> enumeration.</span></span> <span data-ttu-id="d0463-104">Si los estilos de guión estándar no satisface sus necesidades, puede crear un modelo de guión personalizado.</span><span class="sxs-lookup"><span data-stu-id="d0463-104">If those standard dash styles do not suit your needs, you can create a custom dash pattern.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d0463-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d0463-105">Example</span></span>  
 <span data-ttu-id="d0463-106">Para dibujar una línea discontinua personalizada, ponga la longitud de los guiones y espacios en una matriz y asigne la matriz como el valor de la <xref:System.Drawing.Pen.DashPattern%2A> propiedad de un <xref:System.Drawing.Pen> objeto.</span><span class="sxs-lookup"><span data-stu-id="d0463-106">To draw a custom dashed line, put the lengths of the dashes and spaces in an array and assign the array as the value of the <xref:System.Drawing.Pen.DashPattern%2A> property of a <xref:System.Drawing.Pen> object.</span></span> <span data-ttu-id="d0463-107">En el ejemplo siguiente se dibuja una línea discontinua personalizada basada en la matriz `{5, 2, 15, 4}`.</span><span class="sxs-lookup"><span data-stu-id="d0463-107">The following example draws a custom dashed line based on the array `{5, 2, 15, 4}`.</span></span> <span data-ttu-id="d0463-108">Si se multiplican los elementos de la matriz por el ancho del lápiz de 5, obtendrá `{25, 10, 75, 20}`.</span><span class="sxs-lookup"><span data-stu-id="d0463-108">If you multiply the elements of the array by the pen width of 5, you get `{25, 10, 75, 20}`.</span></span> <span data-ttu-id="d0463-109">Los guiones mostrados alternan en la longitud de entre 25 y 75 y los espacios de alternan en la longitud de entre 10 y 20.</span><span class="sxs-lookup"><span data-stu-id="d0463-109">The displayed dashes alternate in length between 25 and 75, and the spaces alternate in length between 10 and 20.</span></span>  
  
 <span data-ttu-id="d0463-110">La siguiente ilustración muestra la línea discontinua resultante.</span><span class="sxs-lookup"><span data-stu-id="d0463-110">The following illustration shows the resulting dashed line.</span></span> <span data-ttu-id="d0463-111">Tenga en cuenta que el guión final debe ser menor que 25 unidades para que la línea puede terminar en (405, 5).</span><span class="sxs-lookup"><span data-stu-id="d0463-111">Note that the final dash has to be shorter than 25 units so that the line can end at (405, 5).</span></span>  
  
 <span data-ttu-id="d0463-112">![Ilustración que muestra una línea discontinua. ](./media/how-to-draw-a-custom-dashed-line/dashed-line-illustration.gif "pens6")</span><span class="sxs-lookup"><span data-stu-id="d0463-112">![Illustration that shows a dashed line.](./media/how-to-draw-a-custom-dashed-line/dashed-line-illustration.gif "pens6")</span></span>  
  
 [!code-csharp[System.Drawing.UsingAPen#51](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#51)]
 [!code-vb[System.Drawing.UsingAPen#51](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#51)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="d0463-113">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="d0463-113">Compiling the Code</span></span>  
 <span data-ttu-id="d0463-114">Crear un formulario de Windows y controlar el formato <xref:System.Windows.Forms.Control.Paint> eventos.</span><span class="sxs-lookup"><span data-stu-id="d0463-114">Create a Windows Form and handle the form's <xref:System.Windows.Forms.Control.Paint> event.</span></span> <span data-ttu-id="d0463-115">Pegue el código anterior en el <xref:System.Windows.Forms.Control.Paint> controlador de eventos.</span><span class="sxs-lookup"><span data-stu-id="d0463-115">Paste the preceding code into the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d0463-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="d0463-116">See also</span></span>

- [<span data-ttu-id="d0463-117">Utilizar lápiz para dibujar líneas y formas</span><span class="sxs-lookup"><span data-stu-id="d0463-117">Using a Pen to Draw Lines and Shapes</span></span>](using-a-pen-to-draw-lines-and-shapes.md)
