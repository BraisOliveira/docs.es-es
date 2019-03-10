---
title: Procedimiento Crear texto de tamaño Variable en un Control ComboBox
ms.date: 03/30/2017
dev_langs:
- vb
helpviewer_keywords:
- text [Windows Forms], drawing in combo boxes
- examples [Windows Forms], ComboBox control
- combo boxes [Windows Forms], drawing text
- ComboBox control [Windows Forms], examples [C#]
- ComboBox control [Windows Forms], drawing custom text
ms.assetid: ce39b9ea-e626-49fe-bd5a-f567f6d157df
ms.openlocfilehash: b55a6b66416aa79427035abdfbc19d1b0e21d94e
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2019
ms.locfileid: "57707799"
---
# <a name="how-to-create-variable-sized-text-in-a-combobox-control"></a><span data-ttu-id="6dd36-102">Filtrar Crear texto de tamaño Variable en un Control ComboBox</span><span class="sxs-lookup"><span data-stu-id="6dd36-102">How to: Create Variable Sized Text in a ComboBox Control</span></span>
<span data-ttu-id="6dd36-103">En este ejemplo muestra el dibujo personalizado de texto en un <xref:System.Windows.Forms.ComboBox> control.</span><span class="sxs-lookup"><span data-stu-id="6dd36-103">This example demonstrates custom drawing of text in a <xref:System.Windows.Forms.ComboBox> control.</span></span> <span data-ttu-id="6dd36-104">Cuando un elemento cumple determinados criterios, se dibuja en una fuente mayor y activa el rojo.</span><span class="sxs-lookup"><span data-stu-id="6dd36-104">When an item meets a certain criteria, it is drawn in a larger font and turned red.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6dd36-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="6dd36-105">Example</span></span>  
  
```vb  
Private Sub ComboBox1_MeasureItem(ByVal sender As Object, ByVal e As _  
System.Windows.Forms.MeasureItemEventArgs) Handles ComboBox1.MeasureItem  
    Dim bFont As New Font("Arial", 8, FontStyle.Bold)  
    Dim lFont As New Font("Arial", 12, FontStyle.Bold)  
    Dim siText As SizeF  
  
    If ComboBox1.Items().Item(e.Index) = "Two" Then  
        siText = e.Graphics.MeasureString(ComboBox1.Items().Item(e.Index), _  
lFont)  
    Else  
        siText = e.Graphics.MeasureString(ComboBox1.Items().Item(e.Index), bFont)  
    End If  
  
    e.ItemHeight = siText.Height  
    e.ItemWidth = siText.Width  
End Sub  
  
Private Sub ComboBox1_DrawItem(ByVal sender As Object, ByVal e As _  
System.Windows.Forms.DrawItemEventArgs) Handles ComboBox1.DrawItem  
    Dim g As Graphics = e.Graphics  
    Dim bFont As New Font("Arial", 8, FontStyle.Bold)  
    Dim lFont As New Font("Arial", 12, FontStyle.Bold)  
  
    If ComboBox1.Items().Item(e.Index) = "Two" Then  
        g.DrawString(ComboBox1.Items.Item(e.Index), lfont, Brushes.Red, _  
e.Bounds.X, e.Bounds.Y)  
    Else  
        g.DrawString(ComboBox1.Items.Item(e.Index), bFont, Brushes.Black, e.Bounds.X, e.Bounds.Y)  
    End If  
End Sub  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="6dd36-106">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="6dd36-106">Compiling the Code</span></span>  
 <span data-ttu-id="6dd36-107">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="6dd36-107">This example requires:</span></span>  
  
-   <span data-ttu-id="6dd36-108">Un formulario de Windows.</span><span class="sxs-lookup"><span data-stu-id="6dd36-108">A Windows form.</span></span>  
  
-   <span data-ttu-id="6dd36-109">Un <xref:System.Windows.Forms.ComboBox> control denominado `ListBox1` con tres elementos en el <xref:System.Windows.Forms.ComboBox.Items%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="6dd36-109">A <xref:System.Windows.Forms.ComboBox> control named `ListBox1` with three items in the <xref:System.Windows.Forms.ComboBox.Items%2A> property.</span></span> <span data-ttu-id="6dd36-110">En este ejemplo, los tres elementos se denominan `"One", Two", and Three"`.</span><span class="sxs-lookup"><span data-stu-id="6dd36-110">In this example, the three items are named `"One", Two", and Three"`.</span></span> <span data-ttu-id="6dd36-111">El <xref:System.Windows.Forms.ComboBox.DrawMode%2A> propiedad de `ComboBox1` debe establecerse en <xref:System.Windows.Forms.DrawMode.OwnerDrawVariable>.</span><span class="sxs-lookup"><span data-stu-id="6dd36-111">The <xref:System.Windows.Forms.ComboBox.DrawMode%2A> property of `ComboBox1` must be set to <xref:System.Windows.Forms.DrawMode.OwnerDrawVariable>.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="6dd36-112">Esta técnica también es aplicable a la <xref:System.Windows.Forms.ListBox> control, puede sustituir un <xref:System.Windows.Forms.ListBox> para el <xref:System.Windows.Forms.ComboBox>.</span><span class="sxs-lookup"><span data-stu-id="6dd36-112">This technique is also applicable to the <xref:System.Windows.Forms.ListBox> control — you can substitute a <xref:System.Windows.Forms.ListBox> for the <xref:System.Windows.Forms.ComboBox>.</span></span>  
  
-   <span data-ttu-id="6dd36-113">Referencias a los espacios de nombres <xref:System.Windows.Forms?displayProperty=nameWithType> y <xref:System.Drawing?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="6dd36-113">References to the <xref:System.Windows.Forms?displayProperty=nameWithType> and <xref:System.Drawing?displayProperty=nameWithType> namespaces.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6dd36-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="6dd36-114">See also</span></span>
- <xref:System.Windows.Forms.ComboBox.DrawItem>
- <xref:System.Windows.Forms.DrawItemEventArgs>
- <xref:System.Windows.Forms.ComboBox.MeasureItem>
- [<span data-ttu-id="6dd36-115">Controles compatibles con dibujos propietarios integrados</span><span class="sxs-lookup"><span data-stu-id="6dd36-115">Controls with Built-In Owner-Drawing Support</span></span>](controls-with-built-in-owner-drawing-support.md)
- [<span data-ttu-id="6dd36-116">ListBox (control)</span><span class="sxs-lookup"><span data-stu-id="6dd36-116">ListBox Control</span></span>](listbox-control-windows-forms.md)
- [<span data-ttu-id="6dd36-117">ComboBox (control)</span><span class="sxs-lookup"><span data-stu-id="6dd36-117">ComboBox Control</span></span>](combobox-control-windows-forms.md)
