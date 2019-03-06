---
title: Filtrar Invalidar el método OnRender de un objeto Panel
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
f1_keywords:
- overriding OnRender method
- Panel control, overriding OnRender method
- OnRender method
- controls, Panel, overriding OnRender method
helpviewer_keywords:
- overriding OnRender method of Panel control [WPF]
- OnRender method [WPF], overriding
- Panel control [WPF], overriding OnRender method
ms.assetid: 57397834-a085-4e36-90ab-416fad98f341
ms.openlocfilehash: cefeee320e10a9e9de0d38894d4d865ca2e639ec
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2019
ms.locfileid: "57368965"
---
# <a name="how-to-override-the-panel-onrender-method"></a><span data-ttu-id="e0d5d-102">Filtrar Invalidar el método OnRender de un objeto Panel</span><span class="sxs-lookup"><span data-stu-id="e0d5d-102">How to: Override the Panel OnRender Method</span></span>
<span data-ttu-id="e0d5d-103">En este ejemplo se muestra cómo invalidar el <xref:System.Windows.Controls.Panel.OnRender%2A> método <xref:System.Windows.Controls.Panel> con el fin de agregar efectos gráficos personalizados a un elemento de diseño.</span><span class="sxs-lookup"><span data-stu-id="e0d5d-103">This example shows how to override the <xref:System.Windows.Controls.Panel.OnRender%2A> method of <xref:System.Windows.Controls.Panel> in order to add custom graphical effects to a layout element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e0d5d-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e0d5d-104">Example</span></span>  
 <span data-ttu-id="e0d5d-105">Use el <xref:System.Windows.Controls.Panel.OnRender%2A> método para agregar efectos gráficos a un elemento panel representado.</span><span class="sxs-lookup"><span data-stu-id="e0d5d-105">Use the <xref:System.Windows.Controls.Panel.OnRender%2A> method in order to add graphical effects to a rendered panel element.</span></span> <span data-ttu-id="e0d5d-106">Por ejemplo, puede usar este método para agregar un borde personalizado o efectos en segundo plano.</span><span class="sxs-lookup"><span data-stu-id="e0d5d-106">For example, you can use this method to add custom border or background effects.</span></span> <span data-ttu-id="e0d5d-107">Un <xref:System.Windows.Media.DrawingContext> objeto se pasa como argumento, que proporciona métodos para dibujar formas, texto, imágenes o vídeos.</span><span class="sxs-lookup"><span data-stu-id="e0d5d-107">A <xref:System.Windows.Media.DrawingContext> object is passed as an argument, which provides methods for drawing shapes, text, images, or videos.</span></span> <span data-ttu-id="e0d5d-108">Como resultado, este método es útil para la personalización de un objeto de panel.</span><span class="sxs-lookup"><span data-stu-id="e0d5d-108">As a result, this method is useful for customization of a panel object.</span></span>  
  
 [!code-csharp[LightWeightCustomPanel#1](~/samples/snippets/csharp/VS_Snippets_Wpf/LightWeightCustomPanel/CSharp/OffsetPanel.cs#1)]
 [!code-vb[LightWeightCustomPanel#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/LightWeightCustomPanel/visualbasic/offsetpanel.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="e0d5d-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="e0d5d-109">See also</span></span>
- <xref:System.Windows.Controls.Panel>
- [<span data-ttu-id="e0d5d-110">Información general sobre elementos Panel</span><span class="sxs-lookup"><span data-stu-id="e0d5d-110">Panels Overview</span></span>](panels-overview.md)
- [<span data-ttu-id="e0d5d-111">Ejemplo de Panel Radial personalizado</span><span class="sxs-lookup"><span data-stu-id="e0d5d-111">Custom Radial Panel Sample</span></span>](https://go.microsoft.com/fwlink/?LinkID=159982)
- [<span data-ttu-id="e0d5d-112">Temas "Cómo..."</span><span class="sxs-lookup"><span data-stu-id="e0d5d-112">How-to Topics</span></span>](panel-how-to-topics.md)
