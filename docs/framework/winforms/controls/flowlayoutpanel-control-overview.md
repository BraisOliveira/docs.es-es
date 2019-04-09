---
title: Información general sobre el control FlowLayoutPanel
ms.date: 03/30/2017
f1_keywords:
- FlowLayoutPanel
helpviewer_keywords:
- forms [Windows Forms], dynamic layout
- layout [Windows Forms], dynamic
- Windows Forms, dynamic layout
- FlowLayoutPanel control [Windows Forms], about FlowLayoutPanel control
ms.assetid: 3883e024-f5a0-456d-9c27-b4dfa1cc9045
ms.openlocfilehash: 260146cd901fe2b80a73c01060ccd55958cd169e
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59203046"
---
# <a name="flowlayoutpanel-control-overview"></a><span data-ttu-id="845e4-102">Información general sobre el control FlowLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="845e4-102">FlowLayoutPanel Control Overview</span></span>
<span data-ttu-id="845e4-103">El control <xref:System.Windows.Forms.FlowLayoutPanel> organiza su contenido en una dirección de flujo horizontal o vertical.</span><span class="sxs-lookup"><span data-stu-id="845e4-103">The <xref:System.Windows.Forms.FlowLayoutPanel> control arranges its contents in a horizontal or vertical flow direction.</span></span> <span data-ttu-id="845e4-104">Puede ajustar el contenido del control de una fila a la siguiente, o de una columna a la siguiente.</span><span class="sxs-lookup"><span data-stu-id="845e4-104">You can wrap the control's contents from one row to the next, or from one column to the next.</span></span> <span data-ttu-id="845e4-105">También puede recortar el contenido en lugar de ajustarlo.</span><span class="sxs-lookup"><span data-stu-id="845e4-105">Alternately, you can clip instead of wrap its contents.</span></span>  
  
 <span data-ttu-id="845e4-106">Puede especificar la dirección de flujo estableciendo el valor de la propiedad <xref:System.Windows.Forms.FlowLayoutPanel.FlowDirection%2A>.</span><span class="sxs-lookup"><span data-stu-id="845e4-106">You can specify the flow direction by setting the value of the <xref:System.Windows.Forms.FlowLayoutPanel.FlowDirection%2A> property.</span></span> <span data-ttu-id="845e4-107">El control <xref:System.Windows.Forms.FlowLayoutPanel> invierte correctamente su dirección de flujo en diseños de derecha a izquierda (RTL).</span><span class="sxs-lookup"><span data-stu-id="845e4-107">The <xref:System.Windows.Forms.FlowLayoutPanel> control correctly reverses its flow direction in Right-to-Left (RTL) layouts.</span></span> <span data-ttu-id="845e4-108">También puede especificar si el contenido del control <xref:System.Windows.Forms.FlowLayoutPanel> se ajustará o se recortará estableciendo el valor de la propiedad <xref:System.Windows.Forms.FlowLayoutPanel.WrapContents%2A>.</span><span class="sxs-lookup"><span data-stu-id="845e4-108">You can also specify whether the <xref:System.Windows.Forms.FlowLayoutPanel> control's contents are wrapped or clipped by setting the value of the <xref:System.Windows.Forms.FlowLayoutPanel.WrapContents%2A> property.</span></span>  
  
 <span data-ttu-id="845e4-109">El control <xref:System.Windows.Forms.FlowLayoutPanel> ajusta automáticamente su tamaño al contenido cuando la propiedad <xref:System.Windows.Forms.Control.AutoSize%2A> se establece en `true`.</span><span class="sxs-lookup"><span data-stu-id="845e4-109">The <xref:System.Windows.Forms.FlowLayoutPanel> control automatically sizes to its contents when you set the <xref:System.Windows.Forms.Control.AutoSize%2A> property to `true`.</span></span> <span data-ttu-id="845e4-110">También proporciona un **FlowBreak** propiedad a sus controles secundarios.</span><span class="sxs-lookup"><span data-stu-id="845e4-110">It also provides a **FlowBreak** property to its child controls.</span></span> <span data-ttu-id="845e4-111">Al establecer el valor de la propiedad FlowBreak en `true` , el control <xref:System.Windows.Forms.FlowLayoutPanel> deja de distribuir los controles en la dirección del flujo actual y ajusta a la siguiente fila o columna.</span><span class="sxs-lookup"><span data-stu-id="845e4-111">Setting the value of the FlowBreak property to `true` causes the <xref:System.Windows.Forms.FlowLayoutPanel> control to stop laying out controls in the current flow direction and wrap to the next row or column.</span></span>  
  
 <span data-ttu-id="845e4-112">Cualquier control de Windows Forms puede ser un control secundario del control <xref:System.Windows.Forms.FlowLayoutPanel>, incluidas otras instancias de <xref:System.Windows.Forms.FlowLayoutPanel>.</span><span class="sxs-lookup"><span data-stu-id="845e4-112">Any Windows Forms control can be a child of the <xref:System.Windows.Forms.FlowLayoutPanel> control, including other instances of <xref:System.Windows.Forms.FlowLayoutPanel>.</span></span> <span data-ttu-id="845e4-113">Con esta funcionalidad, puede construir diseños sofisticados que se adapten a las dimensiones del formulario en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="845e4-113">With this capability, you can construct sophisticated layouts that adapt to your form's dimensions at run time.</span></span>  
  
 <span data-ttu-id="845e4-114">Consulte también [Tutorial: Organizar controles en formularios de Windows Forms mediante FlowLayoutPanel](walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md).</span><span class="sxs-lookup"><span data-stu-id="845e4-114">Also see [Walkthrough: Arranging Controls on Windows Forms Using a FlowLayoutPanel](walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="845e4-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="845e4-115">See also</span></span>

- <xref:System.Windows.Forms.FlowLayoutPanel.FlowDirection%2A>
- <xref:System.Windows.Forms.TableLayoutPanel>
- [<span data-ttu-id="845e4-116">Control FlowLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="845e4-116">FlowLayoutPanel Control</span></span>](flowlayoutpanel-control-windows-forms.md)
