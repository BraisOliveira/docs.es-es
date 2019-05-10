---
title: Procedimiento para usar Utilizar una clase de representación de controles
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- professional appearance [Windows Forms], rendering Windows Forms controls
- visual themes [Windows Forms], applying to Windows Forms controls
- visual styles [Windows Forms], rendering Windows Forms controls
ms.assetid: c0125e34-cd74-4c35-818c-3e40f462b0a3
ms.openlocfilehash: a0f450ff5f169026007002a0d2907ee35e79b29d
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64630551"
---
# <a name="how-to-use-a-control-rendering-class"></a><span data-ttu-id="6417a-102">Procedimiento para usar Utilizar una clase de representación de controles</span><span class="sxs-lookup"><span data-stu-id="6417a-102">How to: Use a Control Rendering Class</span></span>
<span data-ttu-id="6417a-103">Este ejemplo muestra cómo usar el <xref:System.Windows.Forms.ComboBoxRenderer> clase para representar la flecha de lista desplegable de una combinación de control de cuadro.</span><span class="sxs-lookup"><span data-stu-id="6417a-103">This example demonstrates how to use the <xref:System.Windows.Forms.ComboBoxRenderer> class to render the drop-down arrow of a combo box control.</span></span> <span data-ttu-id="6417a-104">El ejemplo consta de los <xref:System.Windows.Forms.Control.OnPaint%2A> método de un control personalizado simple.</span><span class="sxs-lookup"><span data-stu-id="6417a-104">The example consists of the <xref:System.Windows.Forms.Control.OnPaint%2A> method of a simple custom control.</span></span> <span data-ttu-id="6417a-105">El <xref:System.Windows.Forms.ComboBoxRenderer.IsSupported%2A?displayProperty=nameWithType> propiedad se utiliza para determinar si los estilos visuales están habilitados en el área de cliente de windows de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="6417a-105">The <xref:System.Windows.Forms.ComboBoxRenderer.IsSupported%2A?displayProperty=nameWithType> property is used to determine whether visual styles are enabled in the client area of application windows.</span></span> <span data-ttu-id="6417a-106">Si los estilos visuales están activos, el <xref:System.Windows.Forms.ComboBoxRenderer.DrawDropDownButton%2A?displayProperty=nameWithType> método representará la flecha de lista desplegable con estilos visuales; de lo contrario, el <xref:System.Windows.Forms.ControlPaint.DrawComboButton%2A?displayProperty=nameWithType> método representará la flecha desplegable en el estilo clásico de Windows.</span><span class="sxs-lookup"><span data-stu-id="6417a-106">If visual styles are active, then the <xref:System.Windows.Forms.ComboBoxRenderer.DrawDropDownButton%2A?displayProperty=nameWithType> method will render the drop-down arrow with visual styles; otherwise, the <xref:System.Windows.Forms.ControlPaint.DrawComboButton%2A?displayProperty=nameWithType> method will render the drop-down arrow in the classic Windows style.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6417a-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="6417a-107">Example</span></span>  
 [!code-cpp[System.Windows.Forms_ControlRenderer#10](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms_ControlRenderer/cpp/form1.cpp#10)]
 [!code-csharp[System.Windows.Forms_ControlRenderer#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms_ControlRenderer/CS/form1.cs#10)]
 [!code-vb[System.Windows.Forms_ControlRenderer#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms_ControlRenderer/VB/form1.vb#10)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="6417a-108">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="6417a-108">Compiling the Code</span></span>  
 <span data-ttu-id="6417a-109">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="6417a-109">This example requires:</span></span>  
  
- <span data-ttu-id="6417a-110">Un control personalizado derivado de la <xref:System.Windows.Forms.Control> clase.</span><span class="sxs-lookup"><span data-stu-id="6417a-110">A custom control derived from the <xref:System.Windows.Forms.Control> class.</span></span>  
  
- <span data-ttu-id="6417a-111">Un <xref:System.Windows.Forms.Form> que hospeda el control personalizado.</span><span class="sxs-lookup"><span data-stu-id="6417a-111">A <xref:System.Windows.Forms.Form> that hosts the custom control.</span></span>  
  
- <span data-ttu-id="6417a-112">Las referencias a la <xref:System?displayProperty=nameWithType>, <xref:System.Drawing?displayProperty=nameWithType>, <xref:System.Windows.Forms?displayProperty=nameWithType>, y <xref:System.Windows.Forms.VisualStyles?displayProperty=nameWithType> espacios de nombres.</span><span class="sxs-lookup"><span data-stu-id="6417a-112">References to the <xref:System?displayProperty=nameWithType>, <xref:System.Drawing?displayProperty=nameWithType>, <xref:System.Windows.Forms?displayProperty=nameWithType>, and <xref:System.Windows.Forms.VisualStyles?displayProperty=nameWithType> namespaces.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6417a-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="6417a-113">See also</span></span>

- [<span data-ttu-id="6417a-114">Representar controles con estilos visuales</span><span class="sxs-lookup"><span data-stu-id="6417a-114">Rendering Controls with Visual Styles</span></span>](rendering-controls-with-visual-styles.md)
