---
title: Filtrar Habilitar el recorte de texto
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- text [WPF], trimming
- documents [WPF], trimmng text
- trimmng text [WPF]
ms.assetid: dd8c9191-d2be-45fd-9fb4-3c75b65578c5
ms.openlocfilehash: 367e1f46524d8135d8269a2e2159dfe7c2468c45
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2019
ms.locfileid: "57354471"
---
# <a name="how-to-enable-text-trimming"></a><span data-ttu-id="e06f3-102">Procedimiento Habilitar el recorte de texto</span><span class="sxs-lookup"><span data-stu-id="e06f3-102">How to: Enable Text Trimming</span></span>
<span data-ttu-id="e06f3-103">Este ejemplo muestra el uso y los efectos de los valores disponibles en el <xref:System.Windows.TextTrimming> enumeración.</span><span class="sxs-lookup"><span data-stu-id="e06f3-103">This example demonstrates the usage and effects of the values available in the <xref:System.Windows.TextTrimming> enumeration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e06f3-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e06f3-104">Example</span></span>  
 <span data-ttu-id="e06f3-105">En el ejemplo siguiente se define un <xref:System.Windows.Controls.TextBlock> elemento con el <xref:System.Windows.Controls.TextBlock.TextTrimming%2A> conjunto de atributos.</span><span class="sxs-lookup"><span data-stu-id="e06f3-105">The following example defines a <xref:System.Windows.Controls.TextBlock> element with the <xref:System.Windows.Controls.TextBlock.TextTrimming%2A> attribute set.</span></span>  
  
 [!code-xaml[TextTrimmingSnippets#_TextTrimmingXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/TextTrimmingSnippets/CSharp/Window1.xaml#_texttrimmingxaml)]  
  
## <a name="example"></a><span data-ttu-id="e06f3-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e06f3-106">Example</span></span>  
 <span data-ttu-id="e06f3-107">Establecer la correspondiente <xref:System.Windows.TextTrimming> propiedad en el código se muestra a continuación.</span><span class="sxs-lookup"><span data-stu-id="e06f3-107">Setting the corresponding <xref:System.Windows.TextTrimming> property in code is demonstrated below.</span></span>  
  
 [!code-csharp[TextTrimmingSnippets#_TextTrimmingSetTextTrimming](~/samples/snippets/csharp/VS_Snippets_Wpf/TextTrimmingSnippets/CSharp/Window1.xaml.cs#_texttrimmingsettexttrimming)]
 [!code-vb[TextTrimmingSnippets#_TextTrimmingSetTextTrimming](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextTrimmingSnippets/VisualBasic/Window1.xaml.vb#_texttrimmingsettexttrimming)]  
  
 <span data-ttu-id="e06f3-108">Hay actualmente tres opciones para el texto de recorte: **CharacterEllipsis**, **WordEllipsis**, y **ninguno**.</span><span class="sxs-lookup"><span data-stu-id="e06f3-108">There are currently three options for trimming text: **CharacterEllipsis**, **WordEllipsis**, and **None**.</span></span>  
  
 <span data-ttu-id="e06f3-109">Cuando <xref:System.Windows.Controls.TextBlock.TextTrimming%2A> está establecido en **CharacterEllipsis**, texto se recorta y continúa con puntos suspensivos en el carácter más próximo al borde de recorte.</span><span class="sxs-lookup"><span data-stu-id="e06f3-109">When <xref:System.Windows.Controls.TextBlock.TextTrimming%2A> is set to **CharacterEllipsis**, text is trimmed and continued with an ellipsis at the character closest to the trimming edge.</span></span>  <span data-ttu-id="e06f3-110">Este valor suele recortar el texto para que se ajuste más al límite de recorte, pero puede dar lugar al recorte parcial de palabras.</span><span class="sxs-lookup"><span data-stu-id="e06f3-110">This setting tends to trim text to fit more closely to the trimming boundary, but may result in words being partially trimmed.</span></span>  <span data-ttu-id="e06f3-111">En la siguiente ilustración se muestra el efecto de esta configuración en un <xref:System.Windows.Controls.TextBlock> similar al definido anteriormente.</span><span class="sxs-lookup"><span data-stu-id="e06f3-111">The following figure shows the effect of this setting on a <xref:System.Windows.Controls.TextBlock> similar to the one defined above.</span></span>  
  
 <span data-ttu-id="e06f3-112">![Ejemplo: TextTrimming.CharacterEllipsis](./media/texttrimming-character.png "TextTrimming_Character")</span><span class="sxs-lookup"><span data-stu-id="e06f3-112">![Example: TextTrimming.CharacterEllipsis](./media/texttrimming-character.png "TextTrimming_Character")</span></span>  
  
 <span data-ttu-id="e06f3-113">Cuando <xref:System.Windows.Controls.TextBlock.TextTrimming%2A> está establecido en **WordEllipsis**, texto se recorta y continúa con puntos suspensivos al final de la primera palabra completa más próxima al borde de recorte.</span><span class="sxs-lookup"><span data-stu-id="e06f3-113">When <xref:System.Windows.Controls.TextBlock.TextTrimming%2A> is set to **WordEllipsis**, text is trimmed and continued with an ellipsis at the end of the first full word closest to the trimming edge.</span></span>  <span data-ttu-id="e06f3-114">Este valor no mostrará palabras parcialmente recortadas, pero no suele recortar el texto tan cerca del borde de recorte como la **CharacterEllipsis** configuración.</span><span class="sxs-lookup"><span data-stu-id="e06f3-114">This setting will not show partially trimmed words, but tends not to trim text as closely to the trimming edge as the **CharacterEllipsis** setting.</span></span>  <span data-ttu-id="e06f3-115">En la siguiente ilustración se muestra el efecto de esta configuración en el <xref:System.Windows.Controls.TextBlock> definido anteriormente.</span><span class="sxs-lookup"><span data-stu-id="e06f3-115">The following figure shows the effect of this setting on the <xref:System.Windows.Controls.TextBlock> defined above.</span></span>  
  
 <span data-ttu-id="e06f3-116">![Ejemplo: TextTrimming.WordEllipsis](./media/texttrimming-word.png "TextTrimming_Word")</span><span class="sxs-lookup"><span data-stu-id="e06f3-116">![Example: TextTrimming.WordEllipsis](./media/texttrimming-word.png "TextTrimming_Word")</span></span>  
  
 <span data-ttu-id="e06f3-117">Cuando <xref:System.Windows.Controls.TextBlock.TextTrimming%2A> está establecido en **ninguno**, no se realiza ningún recorte de texto.</span><span class="sxs-lookup"><span data-stu-id="e06f3-117">When <xref:System.Windows.Controls.TextBlock.TextTrimming%2A> is set to **None**, no text trimming is performed.</span></span>  <span data-ttu-id="e06f3-118">En este caso, el texto se recorta simplemente en el límite del contenedor de texto primario.</span><span class="sxs-lookup"><span data-stu-id="e06f3-118">In this case, text is simply cropped to the boundary of the parent text container.</span></span>  <span data-ttu-id="e06f3-119">En la siguiente ilustración se muestra el efecto de esta configuración en un <xref:System.Windows.Controls.TextBlock> similar al definido anteriormente.</span><span class="sxs-lookup"><span data-stu-id="e06f3-119">The following figure shows the effect of this setting on a <xref:System.Windows.Controls.TextBlock> similar to the one defined above.</span></span>  
  
 <span data-ttu-id="e06f3-120">![Ejemplo: TextTrimming.None](./media/texttrimming-none.png "TextTrimming_None")</span><span class="sxs-lookup"><span data-stu-id="e06f3-120">![Example: TextTrimming.None](./media/texttrimming-none.png "TextTrimming_None")</span></span>
