---
title: Procedimiento para crear un formulario Windows Forms con forma
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- forms [Windows Forms], rounded
- Windows Forms, custom shapes
- Windows Forms, shaped
- shaped forms
- forms [Windows Forms], changing the shape of
- forms [Windows Forms], circular
- forms [Windows Forms], nonrectangular
- Windows Forms, nonrectangular shape
- Windows Forms, rounded
- Windows Forms, circular
- forms [Windows Forms], custom shapes
ms.assetid: 6e6041e0-8e67-4487-b1e9-e410dbd1ef6c
ms.openlocfilehash: 3c90e6d5d2613239e513f8ec30d67b58084cba5e
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64643495"
---
# <a name="how-to-create-a-shaped-windows-form"></a><span data-ttu-id="98138-102">Procedimiento para crear un formulario Windows Forms con forma</span><span class="sxs-lookup"><span data-stu-id="98138-102">How to: Create a Shaped Windows Form</span></span>
<span data-ttu-id="98138-103">En este ejemplo da forma elíptica que cambia el tamaño con el formulario a un formulario.</span><span class="sxs-lookup"><span data-stu-id="98138-103">This example gives a form an elliptical shape that resizes with the form.</span></span>  
  
## <a name="example"></a><span data-ttu-id="98138-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="98138-104">Example</span></span>  
 [!code-cpp[System.Drawing.ConceptualHowTos#10](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/cpp/form1.cpp#10)]
 [!code-csharp[System.Drawing.ConceptualHowTos#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/CS/form1.cs#10)]
 [!code-vb[System.Drawing.ConceptualHowTos#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/VB/form1.vb#10)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="98138-105">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="98138-105">Compiling the Code</span></span>  
 <span data-ttu-id="98138-106">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="98138-106">This example requires:</span></span>  
  
- <span data-ttu-id="98138-107">Referencias a los espacios de nombres <xref:System.Windows.Forms> y <xref:System.Drawing>.</span><span class="sxs-lookup"><span data-stu-id="98138-107">References to the <xref:System.Windows.Forms> and <xref:System.Drawing> namespaces.</span></span>  
  
 <span data-ttu-id="98138-108">Este ejemplo se invalida el <xref:System.Windows.Forms.Control.OnPaint%2A> método para cambiar la forma del formulario.</span><span class="sxs-lookup"><span data-stu-id="98138-108">This example overrides the <xref:System.Windows.Forms.Control.OnPaint%2A> method to change the shape of the form.</span></span> <span data-ttu-id="98138-109">Para usar este código, copie la declaración del método, así como el código de dibujo dentro del método.</span><span class="sxs-lookup"><span data-stu-id="98138-109">To use this code, copy the method declaration as well as the drawing code inside the method.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="98138-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="98138-110">See also</span></span>

- <xref:System.Windows.Forms.Control.OnPaint%2A>
- <xref:System.Drawing.Region>
- <xref:System.Drawing>
- <xref:System.Drawing.Drawing2D.GraphicsPath.AddEllipse%2A>
- <xref:System.Windows.Forms.Control.Region%2A>
- [<span data-ttu-id="98138-111">Introducción a la programación de gráficos</span><span class="sxs-lookup"><span data-stu-id="98138-111">Getting Started with Graphics Programming</span></span>](getting-started-with-graphics-programming.md)
