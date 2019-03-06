---
title: Procedimiento Definir un lápiz
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- pens [WPF], defining
- creating [WPF], pens
ms.assetid: 7a4f2900-cdf9-49de-84e0-ba5d0ded4d33
ms.openlocfilehash: 1d69a40604dbf2f7a73c17279ae946faeb6c634a
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2019
ms.locfileid: "57365794"
---
# <a name="how-to-define-a-pen"></a><span data-ttu-id="5bc4a-102">Filtrar Definir un lápiz</span><span class="sxs-lookup"><span data-stu-id="5bc4a-102">How to: Define a Pen</span></span>
<span data-ttu-id="5bc4a-103">En este ejemplo se muestra cómo utilizar un <xref:System.Windows.Media.Pen> para esquematizar una forma.</span><span class="sxs-lookup"><span data-stu-id="5bc4a-103">This example shows how use a <xref:System.Windows.Media.Pen> to outline a shape.</span></span> <span data-ttu-id="5bc4a-104">Para crear una sencilla <xref:System.Windows.Media.Pen>, sólo necesita especificar su <xref:System.Windows.Media.Pen.Thickness%2A> y <xref:System.Windows.Media.Pen.Brush%2A>.</span><span class="sxs-lookup"><span data-stu-id="5bc4a-104">To create a simple <xref:System.Windows.Media.Pen>, you need only specify its <xref:System.Windows.Media.Pen.Thickness%2A> and <xref:System.Windows.Media.Pen.Brush%2A>.</span></span> <span data-ttu-id="5bc4a-105">Puede crear lápiz más complejo especificando un <xref:System.Windows.Media.Pen.DashStyle%2A>, <xref:System.Windows.Media.Pen.DashCap%2A>, <xref:System.Windows.Media.Pen.LineJoin%2A>, <xref:System.Windows.Media.Pen.StartLineCap%2A>, y <xref:System.Windows.Media.Pen.EndLineCap%2A>.</span><span class="sxs-lookup"><span data-stu-id="5bc4a-105">You can create more complex pen's by specifying a <xref:System.Windows.Media.Pen.DashStyle%2A>, <xref:System.Windows.Media.Pen.DashCap%2A>, <xref:System.Windows.Media.Pen.LineJoin%2A>, <xref:System.Windows.Media.Pen.StartLineCap%2A>, and <xref:System.Windows.Media.Pen.EndLineCap%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5bc4a-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="5bc4a-106">Example</span></span>  
 <span data-ttu-id="5bc4a-107">En el ejemplo siguiente se usa un <xref:System.Windows.Media.Pen> describir una forma definida por un <xref:System.Windows.Media.GeometryDrawing>.</span><span class="sxs-lookup"><span data-stu-id="5bc4a-107">The following example uses a <xref:System.Windows.Media.Pen> to outline a shape defined by a <xref:System.Windows.Media.GeometryDrawing>.</span></span>  
  
 [!code-csharp[PenExamples_snip#PenExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/PenExamples_snip/CSharp/PenExample.cs#penexamplewholepage)]
 [!code-vb[PenExamples_snip#PenExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PenExamples_snip/VisualBasic/PenExample.vb#penexamplewholepage)]  
  
 <span data-ttu-id="5bc4a-108">![Esquema producido por un lápiz](./media/graphicsmm-simple-pen.jpg "graphicsmm_simple_pen")</span><span class="sxs-lookup"><span data-stu-id="5bc4a-108">![Outlines produces by a Pen](./media/graphicsmm-simple-pen.jpg "graphicsmm_simple_pen")</span></span>  
<span data-ttu-id="5bc4a-109">GeometryDrawing</span><span class="sxs-lookup"><span data-stu-id="5bc4a-109">A GeometryDrawing</span></span>
