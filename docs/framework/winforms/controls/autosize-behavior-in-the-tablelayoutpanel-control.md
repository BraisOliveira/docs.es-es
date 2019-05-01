---
title: Comportamiento de AutoSize en el control TableLayoutPanel
ms.date: 03/30/2017
helpviewer_keywords:
- AutoSize property [Windows Forms], tableLayoutPanel control
- controls [Windows Forms], sizing
- localizing forms
- layout [Windows Forms], AutoSize
- sizing [Windows Forms], automatic
- TableLayoutPanel control [Windows Forms], AutoSize behavior
- automatic sizing
- AutoSizeMode property
ms.assetid: 9233e0c3-2fa6-405e-8701-959479b1250e
ms.openlocfilehash: 466edeee5f45ec72ef265ef4855049c7852641b0
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61954354"
---
# <a name="autosize-behavior-in-the-tablelayoutpanel-control"></a><span data-ttu-id="8826a-102">Comportamiento de AutoSize en el control TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="8826a-102">AutoSize Behavior in the TableLayoutPanel Control</span></span>
## <a name="distinct-autosize-behaviors"></a><span data-ttu-id="8826a-103">Distintos comportamientos de AutoSize</span><span class="sxs-lookup"><span data-stu-id="8826a-103">Distinct AutoSize Behaviors</span></span>  
 <span data-ttu-id="8826a-104">El <xref:System.Windows.Forms.TableLayoutPanel> control admite el comportamiento de ajuste de tamaño automático de las maneras siguientes:</span><span class="sxs-lookup"><span data-stu-id="8826a-104">The <xref:System.Windows.Forms.TableLayoutPanel> control supports automatic sizing behavior in the following ways:</span></span>  
  
- <span data-ttu-id="8826a-105">A través de la <xref:System.Windows.Forms.Control.AutoSize%2A> propiedad;</span><span class="sxs-lookup"><span data-stu-id="8826a-105">Through the <xref:System.Windows.Forms.Control.AutoSize%2A> property;</span></span>  
  
- <span data-ttu-id="8826a-106">A través de la <xref:System.Windows.Forms.TableLayoutStyle.SizeType%2A> propiedad en el <xref:System.Windows.Forms.TableLayoutPanel> estilos de fila y columna del control.</span><span class="sxs-lookup"><span data-stu-id="8826a-106">Through the <xref:System.Windows.Forms.TableLayoutStyle.SizeType%2A> property on the <xref:System.Windows.Forms.TableLayoutPanel> control’s column and row styles.</span></span>  
  
### <a name="the-autosize-property-with-row-and-column-styles"></a><span data-ttu-id="8826a-107">La propiedad AutoSize con estilos de columna y fila</span><span class="sxs-lookup"><span data-stu-id="8826a-107">The AutoSize Property with Row and Column Styles</span></span>  
 <span data-ttu-id="8826a-108">En la tabla siguiente se describe la interacción entre el <xref:System.Windows.Forms.Control.AutoSize%2A> propiedad y el <xref:System.Windows.Forms.TableLayoutPanel> estilos de fila y columna del control.</span><span class="sxs-lookup"><span data-stu-id="8826a-108">The following table describes the interaction between the <xref:System.Windows.Forms.Control.AutoSize%2A> property and the <xref:System.Windows.Forms.TableLayoutPanel> control’s column and row styles.</span></span>  
  
|<span data-ttu-id="8826a-109">Ajuste automático de tamaño</span><span class="sxs-lookup"><span data-stu-id="8826a-109">AutoSize setting</span></span>|<span data-ttu-id="8826a-110">Interacción de estilo</span><span class="sxs-lookup"><span data-stu-id="8826a-110">Style interaction</span></span>|  
|----------------------|-----------------------|  
|`false`|<span data-ttu-id="8826a-111">El <xref:System.Windows.Forms.TableLayoutPanel> control avanza de izquierda a derecha y asigna espacio para la columna o fila o en el orden siguiente.</span><span class="sxs-lookup"><span data-stu-id="8826a-111">The <xref:System.Windows.Forms.TableLayoutPanel> control proceeds from left to right, and allocates space for the column or row or in the following order.</span></span><br /><br /> <span data-ttu-id="8826a-112">1.  Si el <xref:System.Windows.Forms.TableLayoutStyle.SizeType%2A> propiedad está establecida en <xref:System.Windows.Forms.SizeType.Absolute>, el número de píxeles especificada por <xref:System.Windows.Forms.ColumnStyle.Width%2A> o <xref:System.Windows.Forms.RowStyle.Height%2A> está asignada.</span><span class="sxs-lookup"><span data-stu-id="8826a-112">1.  If the <xref:System.Windows.Forms.TableLayoutStyle.SizeType%2A> property is set to <xref:System.Windows.Forms.SizeType.Absolute>, the number of pixels specified by <xref:System.Windows.Forms.ColumnStyle.Width%2A> or <xref:System.Windows.Forms.RowStyle.Height%2A> is allocated.</span></span><br /><span data-ttu-id="8826a-113">2.  Si el <xref:System.Windows.Forms.TableLayoutStyle.SizeType%2A> propiedad está establecida en <xref:System.Windows.Forms.SizeType.AutoSize>, el número de píxeles devuelto por el control secundario <xref:System.Windows.Forms.Control.GetPreferredSize%2A> se asigna el método.</span><span class="sxs-lookup"><span data-stu-id="8826a-113">2.  If the <xref:System.Windows.Forms.TableLayoutStyle.SizeType%2A> property is set to <xref:System.Windows.Forms.SizeType.AutoSize>, the number of pixels returned by the child control’s <xref:System.Windows.Forms.Control.GetPreferredSize%2A> method is allocated.</span></span><br /><span data-ttu-id="8826a-114">3.  Después de un espacio para todas las <xref:System.Windows.Forms.SizeType.Absolute> y <xref:System.Windows.Forms.SizeType.AutoSize> está asignado el columnas o filas, columnas o filas con <xref:System.Windows.Forms.TableLayoutStyle.SizeType%2A> establecido en <xref:System.Windows.Forms.SizeType.Percent> se usan para asignar proporcionalmente el espacio libre restante</span><span class="sxs-lookup"><span data-stu-id="8826a-114">3.  After space for all <xref:System.Windows.Forms.SizeType.Absolute> and <xref:System.Windows.Forms.SizeType.AutoSize> columns or rows is allocated, any columns or rows with <xref:System.Windows.Forms.TableLayoutStyle.SizeType%2A> set to <xref:System.Windows.Forms.SizeType.Percent> are used to proportionally allocate the remaining free space</span></span>|  
|`true`|<span data-ttu-id="8826a-115">Similar a la interacción anterior, con la excepción que <xref:System.Windows.Forms.SizeType.Percent> columnas o filas adquieren un aspecto de ajuste de tamaño automático.</span><span class="sxs-lookup"><span data-stu-id="8826a-115">Similar to the previous interaction, with the exception that <xref:System.Windows.Forms.SizeType.Percent> columns or rows acquire an automatic sizing aspect.</span></span><br /><br /> <span data-ttu-id="8826a-116">El <xref:System.Windows.Forms.TableLayoutPanel> control expande la columna o fila para crear espacio disponible, por lo que ninguna columna o fila con <xref:System.Windows.Forms.SizeType.Percent> estilo recorta su contenido.</span><span class="sxs-lookup"><span data-stu-id="8826a-116">The <xref:System.Windows.Forms.TableLayoutPanel> control expands the column or row to create adequate free space, so that no column or row with <xref:System.Windows.Forms.SizeType.Percent> styling clips its contents.</span></span> <span data-ttu-id="8826a-117">El <xref:System.Windows.Forms.TableLayoutPanel> control asigna el nuevo espacio proporcionalmente conforme a la <xref:System.Windows.Forms.ColumnStyle.Width%2A> o <xref:System.Windows.Forms.RowStyle.Height%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="8826a-117">The <xref:System.Windows.Forms.TableLayoutPanel> control allocates the new space proportionally according to the <xref:System.Windows.Forms.ColumnStyle.Width%2A> or <xref:System.Windows.Forms.RowStyle.Height%2A> property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="8826a-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="8826a-118">See also</span></span>

- <xref:System.Windows.Forms.TableLayoutPanel>
- [<span data-ttu-id="8826a-119">Información general sobre el control TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="8826a-119">TableLayoutPanel Control Overview</span></span>](tablelayoutpanel-control-overview.md)
