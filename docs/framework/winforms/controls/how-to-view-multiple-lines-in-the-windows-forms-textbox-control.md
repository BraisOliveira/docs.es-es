---
title: Procedimiento Ver múltiples líneas en el Control TextBox de Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- newline
- end of line
- ScrollBars property [Windows Forms], in TextBox control
- CRLF
- MultiLine property in TextBox control
- line-feed
- TextBox control [Windows Forms], viewing multiple lines
- carriage return
ms.assetid: 43173201-0b74-4067-a472-605029ca5f35
ms.openlocfilehash: d80a0262455b9b5e0e8535d88eb6292ab60e3ea8
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2019
ms.locfileid: "57716015"
---
# <a name="how-to-view-multiple-lines-in-the-windows-forms-textbox-control"></a><span data-ttu-id="e4ef7-102">Procedimiento Ver múltiples líneas en el Control TextBox de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="e4ef7-102">How to: View Multiple Lines in the Windows Forms TextBox Control</span></span>
<span data-ttu-id="e4ef7-103">De forma predeterminada, los formularios de Windows <xref:System.Windows.Forms.TextBox> control muestra una sola línea de texto y no muestra barras de desplazamiento.</span><span class="sxs-lookup"><span data-stu-id="e4ef7-103">By default, the Windows Forms <xref:System.Windows.Forms.TextBox> control displays a single line of text and does not display scroll bars.</span></span> <span data-ttu-id="e4ef7-104">Si el texto es mayor que el espacio disponible, sólo una parte del texto es visible.</span><span class="sxs-lookup"><span data-stu-id="e4ef7-104">If the text is longer than the available space, only part of the text is visible.</span></span> <span data-ttu-id="e4ef7-105">Puede cambiar este comportamiento predeterminado estableciendo la <xref:System.Windows.Forms.TextBox.Multiline%2A>, <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A>, y <xref:System.Windows.Forms.TextBox.ScrollBars%2A> propiedades en los valores adecuados.</span><span class="sxs-lookup"><span data-stu-id="e4ef7-105">You can change this default behavior by setting the <xref:System.Windows.Forms.TextBox.Multiline%2A>, <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A>, and <xref:System.Windows.Forms.TextBox.ScrollBars%2A> properties to appropriate values.</span></span>  
  
### <a name="to-display-a-carriage-return-in-the-textbox-control"></a><span data-ttu-id="e4ef7-106">Para mostrar un retorno de carro en el control TextBox</span><span class="sxs-lookup"><span data-stu-id="e4ef7-106">To display a carriage return in the TextBox control</span></span>  
  
-   <span data-ttu-id="e4ef7-107">Para mostrar un retorno de carro en una de varias líneas <xref:System.Windows.Forms.TextBox>, utilice el <xref:System.Environment.NewLine%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="e4ef7-107">To display a carriage return in a multi-line <xref:System.Windows.Forms.TextBox>, use the <xref:System.Environment.NewLine%2A> property.</span></span>  
  
     <span data-ttu-id="e4ef7-108">Tenga en cuenta que la interpretación de los caracteres de escape (\\) es específico del idioma.</span><span class="sxs-lookup"><span data-stu-id="e4ef7-108">Be aware that the interpretation of escape characters (\\) is language-specific.</span></span> <span data-ttu-id="e4ef7-109">Visual Basic usa `Chr$(13) & Chr$(10)` para la combinación de caracteres de retorno de carro y de transporte.</span><span class="sxs-lookup"><span data-stu-id="e4ef7-109">Visual Basic uses `Chr$(13) & Chr$(10)` for the carriage return and linefeed character combination.</span></span>  
  
### <a name="to-view-multiple-lines-in-the-textbox-control"></a><span data-ttu-id="e4ef7-110">Para ver varias líneas en el control TextBox</span><span class="sxs-lookup"><span data-stu-id="e4ef7-110">To view multiple lines in the TextBox control</span></span>  
  
1.  <span data-ttu-id="e4ef7-111">Establezca la propiedad <xref:System.Windows.Forms.TextBox.Multiline%2A> en `true`.</span><span class="sxs-lookup"><span data-stu-id="e4ef7-111">Set the <xref:System.Windows.Forms.TextBox.Multiline%2A> property to `true`.</span></span> <span data-ttu-id="e4ef7-112">Si <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> es `true` (valor predeterminado), a continuación, el texto en el control se mostrará como uno o varios párrafos; en caso contrario, aparecerá como una lista, en el que algunas líneas pueden quedar cortadas en el borde del control.</span><span class="sxs-lookup"><span data-stu-id="e4ef7-112">If <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> is `true` (the default), then the text in the control will appear as one or more paragraphs; otherwise it will appear as a list, in which some lines may be clipped at the edge of the control.</span></span>  
  
2.  <span data-ttu-id="e4ef7-113">Establezca la propiedad <xref:System.Windows.Forms.TextBox.ScrollBars%2A> en un valor apropiado.</span><span class="sxs-lookup"><span data-stu-id="e4ef7-113">Set the <xref:System.Windows.Forms.TextBox.ScrollBars%2A> property to an appropriate value.</span></span>  
  
    |<span data-ttu-id="e4ef7-114">Valor</span><span class="sxs-lookup"><span data-stu-id="e4ef7-114">Value</span></span>|<span data-ttu-id="e4ef7-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="e4ef7-115">Description</span></span>|  
    |-----------|-----------------|  
    |<xref:System.Windows.Forms.ScrollBars.None>|<span data-ttu-id="e4ef7-116">Use este valor si el texto estará en un párrafo que casi siempre se adapta el control.</span><span class="sxs-lookup"><span data-stu-id="e4ef7-116">Use this value if the text will be a paragraph that almost always fits the control.</span></span> <span data-ttu-id="e4ef7-117">El usuario puede utilizar el puntero del mouse para moverse por el control si el texto es demasiado largo para mostrarse a la vez.</span><span class="sxs-lookup"><span data-stu-id="e4ef7-117">The user can use the mouse pointer to move around inside the control if the text is too long to display all at once.</span></span>|  
    |<xref:System.Windows.Forms.ScrollBars.Horizontal>|<span data-ttu-id="e4ef7-118">Use este valor si desea mostrar una lista de líneas, algunos de los cuales pueden ser mayor que el ancho de la <xref:System.Windows.Forms.TextBox> control.</span><span class="sxs-lookup"><span data-stu-id="e4ef7-118">Use this value if you want to display a list of lines, some of which may be longer than the width of the <xref:System.Windows.Forms.TextBox> control.</span></span>|  
    |<xref:System.Windows.Forms.ScrollBars.Both>|<span data-ttu-id="e4ef7-119">Use este valor si la lista puede ser mayor que el alto del control.</span><span class="sxs-lookup"><span data-stu-id="e4ef7-119">Use this value if the list may be longer than the height of the control.</span></span>|  
  
3.  <span data-ttu-id="e4ef7-120">Establezca la propiedad <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> en un valor apropiado.</span><span class="sxs-lookup"><span data-stu-id="e4ef7-120">Set the <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> property to an appropriate value.</span></span>  
  
    |<span data-ttu-id="e4ef7-121">Valor</span><span class="sxs-lookup"><span data-stu-id="e4ef7-121">Value</span></span>|<span data-ttu-id="e4ef7-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="e4ef7-122">Description</span></span>|  
    |-----------|-----------------|  
    |`false`|<span data-ttu-id="e4ef7-123">Texto del control no se ajustarán automáticamente, por lo que se desplazará a la derecha hasta que se alcanza un salto de línea.</span><span class="sxs-lookup"><span data-stu-id="e4ef7-123">Text in the control will not automatically be wrapped, so it will scroll to the right until a line break is reached.</span></span> <span data-ttu-id="e4ef7-124">Use este valor si eligió <xref:System.Windows.Forms.ScrollBars.Horizontal> las barras de desplazamiento o <xref:System.Windows.Forms.ScrollBars.Both>, más arriba.</span><span class="sxs-lookup"><span data-stu-id="e4ef7-124">Use this value if you chose <xref:System.Windows.Forms.ScrollBars.Horizontal> scroll bars or <xref:System.Windows.Forms.ScrollBars.Both>, above.</span></span>|  
    |<span data-ttu-id="e4ef7-125">`true` (valor predeterminado)</span><span class="sxs-lookup"><span data-stu-id="e4ef7-125">`true` (default)</span></span>|<span data-ttu-id="e4ef7-126">No aparecerá la barra de desplazamiento horizontal.</span><span class="sxs-lookup"><span data-stu-id="e4ef7-126">The horizontal scrollbar will not appear.</span></span> <span data-ttu-id="e4ef7-127">Use este valor si eligió <xref:System.Windows.Forms.ScrollBars.Vertical> las barras de desplazamiento o <xref:System.Windows.Forms.ScrollBars.None>, anteriormente, para mostrar uno o varios párrafos.</span><span class="sxs-lookup"><span data-stu-id="e4ef7-127">Use this value if you chose <xref:System.Windows.Forms.ScrollBars.Vertical> scroll bars or <xref:System.Windows.Forms.ScrollBars.None>, above, to display one or more paragraphs.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e4ef7-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="e4ef7-128">See also</span></span>
- <xref:System.Windows.Forms.TextBox>
- [<span data-ttu-id="e4ef7-129">Información general sobre el control TextBox</span><span class="sxs-lookup"><span data-stu-id="e4ef7-129">TextBox Control Overview</span></span>](textbox-control-overview-windows-forms.md)
- [<span data-ttu-id="e4ef7-130">Cómo: Controlar el punto de inserción en un Control TextBox de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="e4ef7-130">How to: Control the Insertion Point in a Windows Forms TextBox Control</span></span>](how-to-control-the-insertion-point-in-a-windows-forms-textbox-control.md)
- [<span data-ttu-id="e4ef7-131">Cómo: Crear un cuadro de texto de contraseña con el Control TextBox de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="e4ef7-131">How to: Create a Password Text Box with the Windows Forms TextBox Control</span></span>](how-to-create-a-password-text-box-with-the-windows-forms-textbox-control.md)
- [<span data-ttu-id="e4ef7-132">Cómo: Crear un cuadro de texto de solo lectura</span><span class="sxs-lookup"><span data-stu-id="e4ef7-132">How to: Create a Read-Only Text Box</span></span>](how-to-create-a-read-only-text-box-windows-forms.md)
- [<span data-ttu-id="e4ef7-133">Cómo: Insertar comillas en una cadena</span><span class="sxs-lookup"><span data-stu-id="e4ef7-133">How to: Put Quotation Marks in a String</span></span>](how-to-put-quotation-marks-in-a-string-windows-forms.md)
- [<span data-ttu-id="e4ef7-134">Cómo: Seleccionar texto en el Control TextBox de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="e4ef7-134">How to: Select Text in the Windows Forms TextBox Control</span></span>](how-to-select-text-in-the-windows-forms-textbox-control.md)
- [<span data-ttu-id="e4ef7-135">Control TextBox</span><span class="sxs-lookup"><span data-stu-id="e4ef7-135">TextBox Control</span></span>](textbox-control-windows-forms.md)
