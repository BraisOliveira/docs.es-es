---
title: Filtrar Dibujar con pinceles opacos y semitransparentes
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- semi-transparent shapes [Windows Forms], drawing
- transparency [Windows Forms], semi-transparent shapes
- alpha blending [Windows Forms], brush
- brushes [Windows Forms], using semi-transparent
ms.assetid: a4f6f6b8-3bc8-440a-84af-d62ef0f8ff40
ms.openlocfilehash: ebb2f1008d267c4b5dcf36a7a4aae749fe73bb59
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2019
ms.locfileid: "57716886"
---
# <a name="how-to-draw-with-opaque-and-semitransparent-brushes"></a><span data-ttu-id="445fc-102">Procedimiento Dibujar con pinceles opacos y semitransparentes</span><span class="sxs-lookup"><span data-stu-id="445fc-102">How to: Draw with Opaque and Semitransparent Brushes</span></span>
<span data-ttu-id="445fc-103">Cuando se rellena una forma, se debe pasar un objeto <xref:System.Drawing.Brush> en uno de los métodos de relleno de la clase <xref:System.Drawing.Graphics>.</span><span class="sxs-lookup"><span data-stu-id="445fc-103">When you fill a shape, you must pass a <xref:System.Drawing.Brush> object to one of the fill methods of the <xref:System.Drawing.Graphics> class.</span></span> <span data-ttu-id="445fc-104">El único parámetro del constructor <xref:System.Drawing.SolidBrush.%23ctor%2A> es un objeto <xref:System.Drawing.Color>.</span><span class="sxs-lookup"><span data-stu-id="445fc-104">The one parameter of the <xref:System.Drawing.SolidBrush.%23ctor%2A> constructor is a <xref:System.Drawing.Color> object.</span></span> <span data-ttu-id="445fc-105">Para rellenar una forma opaca, establezca el componente alfa del color en 255.</span><span class="sxs-lookup"><span data-stu-id="445fc-105">To fill an opaque shape, set the alpha component of the color to 255.</span></span> <span data-ttu-id="445fc-106">Para rellenar una forma semitransparente, establezca el componente alfa en cualquier valor entre 1 y 254.</span><span class="sxs-lookup"><span data-stu-id="445fc-106">To fill a semitransparent shape, set the alpha component to any value from 1 through 254.</span></span>  
  
 <span data-ttu-id="445fc-107">Cuando se rellena una forma semitransparente, el color de la forma se mezcla con los colores del fondo.</span><span class="sxs-lookup"><span data-stu-id="445fc-107">When you fill a semitransparent shape, the color of the shape is blended with the colors of the background.</span></span> <span data-ttu-id="445fc-108">El componente alfa especifica cómo se mezclan los colores de la forma y del fondo; los valores alfa cercanos a 0 dan más importancia a los colores de fondo y los cercanos a 255 dan más importancia al color de la forma.</span><span class="sxs-lookup"><span data-stu-id="445fc-108">The alpha component specifies how the shape and background colors are mixed; alpha values near 0 place more weight on the background colors, and alpha values near 255 place more weight on the shape color.</span></span>  
  
## <a name="example"></a><span data-ttu-id="445fc-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="445fc-109">Example</span></span>  
 <span data-ttu-id="445fc-110">En el ejemplo siguiente se dibuja un mapa de bits y después se rellenan tres elipses que se superponen al mapa de bits.</span><span class="sxs-lookup"><span data-stu-id="445fc-110">The following example draws a bitmap and then fills three ellipses that overlap the bitmap.</span></span> <span data-ttu-id="445fc-111">La primera elipse usa un componente alfa de 255, por lo que es opaca.</span><span class="sxs-lookup"><span data-stu-id="445fc-111">The first ellipse uses an alpha component of 255, so it is opaque.</span></span> <span data-ttu-id="445fc-112">La segunda y tercera elipses usan un componente alfa de 128, por lo que son semitransparentes; puede ver la imagen de fondo a través de las elipses.</span><span class="sxs-lookup"><span data-stu-id="445fc-112">The second and third ellipses use an alpha component of 128, so they are semitransparent; you can see the background image through the ellipses.</span></span> <span data-ttu-id="445fc-113">La instrucción que establece la propiedad <xref:System.Drawing.Graphics.CompositingQuality%2A> hace que la mezcla de la tercera elipse se realice conjuntamente con la corrección gamma.</span><span class="sxs-lookup"><span data-stu-id="445fc-113">The call that sets the <xref:System.Drawing.Graphics.CompositingQuality%2A> property causes the blending for the third ellipse to be done in conjunction with gamma correction.</span></span>  
  
 <span data-ttu-id="445fc-114">En la siguiente ilustración se muestra el resultado del código siguiente.</span><span class="sxs-lookup"><span data-stu-id="445fc-114">The following illustration shows the output of the following code.</span></span>  
  
 <span data-ttu-id="445fc-115">![Opacas y semitransparentes](./media/compqualellipse.png "compqualellipse")</span><span class="sxs-lookup"><span data-stu-id="445fc-115">![Opaque and Semitransparent](./media/compqualellipse.png "compqualellipse")</span></span>  
  
 [!code-csharp[System.Drawing.AlphaBlending#31](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlphaBlending/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.AlphaBlending#31](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlphaBlending/VB/Class1.vb#31)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="445fc-116">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="445fc-116">Compiling the Code</span></span>  
 <span data-ttu-id="445fc-117">El ejemplo anterior está diseñado para su uso con Windows Forms y requiere <xref:System.Windows.Forms.PaintEventArgs>`e`, que es un parámetro de <xref:System.Windows.Forms.PaintEventHandler>.</span><span class="sxs-lookup"><span data-stu-id="445fc-117">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs>`e`, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="445fc-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="445fc-118">See also</span></span>
- [<span data-ttu-id="445fc-119">Gráficos y dibujos en Windows Forms</span><span class="sxs-lookup"><span data-stu-id="445fc-119">Graphics and Drawing in Windows Forms</span></span>](graphics-and-drawing-in-windows-forms.md)
- [<span data-ttu-id="445fc-120">Líneas y rellenos con combinación alfa</span><span class="sxs-lookup"><span data-stu-id="445fc-120">Alpha Blending Lines and Fills</span></span>](alpha-blending-lines-and-fills.md)
- [<span data-ttu-id="445fc-121">Cómo: Proporcionar un fondo transparente a un Control</span><span class="sxs-lookup"><span data-stu-id="445fc-121">How to: Give Your Control a Transparent Background</span></span>](../controls/how-to-give-your-control-a-transparent-background.md)
- [<span data-ttu-id="445fc-122">Cómo: Dibujar líneas opacas y semitransparentes</span><span class="sxs-lookup"><span data-stu-id="445fc-122">How to: Draw Opaque and Semitransparent Lines</span></span>](how-to-draw-opaque-and-semitransparent-lines.md)
