---
title: Filtrar Crear y usar un objeto GridLengthConverter
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Grid control [WPF], creating [WPF], GridLengthConverter objects
ms.assetid: 5ab75911-e36a-4825-80e4-081c57e8e182
ms.openlocfilehash: 498d2b9c531f391f4cbeb1478469a99d381deec7
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59206790"
---
# <a name="how-to-create-and-use-a-gridlengthconverter-object"></a><span data-ttu-id="ebd1e-102">Filtrar Crear y usar un objeto GridLengthConverter</span><span class="sxs-lookup"><span data-stu-id="ebd1e-102">How to: Create and Use a GridLengthConverter Object</span></span>
## <a name="example"></a><span data-ttu-id="ebd1e-103">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ebd1e-103">Example</span></span>  
 <span data-ttu-id="ebd1e-104">El ejemplo siguiente muestra cómo crear y usar una instancia de <xref:System.Windows.GridLengthConverter>.</span><span class="sxs-lookup"><span data-stu-id="ebd1e-104">The following example shows how to create and use an instance of <xref:System.Windows.GridLengthConverter>.</span></span> <span data-ttu-id="ebd1e-105">El ejemplo define un método personalizado llamado `changeCol`, que pasan el <xref:System.Windows.Controls.ListBoxItem> a un <xref:System.Windows.GridLengthConverter> que convierte el <xref:System.Windows.Controls.ContentControl.Content%2A> de un <xref:System.Windows.Controls.ListBoxItem> a una instancia de <xref:System.Windows.GridLength>.</span><span class="sxs-lookup"><span data-stu-id="ebd1e-105">The example defines a custom method called `changeCol`, which passes the <xref:System.Windows.Controls.ListBoxItem> to a <xref:System.Windows.GridLengthConverter> that converts the <xref:System.Windows.Controls.ContentControl.Content%2A> of a <xref:System.Windows.Controls.ListBoxItem> to an instance of <xref:System.Windows.GridLength>.</span></span> <span data-ttu-id="ebd1e-106">El valor convertido, a continuación, se pasa como el valor de la <xref:System.Windows.Controls.ColumnDefinition.Width%2A> propiedad de la <xref:System.Windows.Controls.ColumnDefinition> elemento.</span><span class="sxs-lookup"><span data-stu-id="ebd1e-106">The converted value is then passed back as the value of the <xref:System.Windows.Controls.ColumnDefinition.Width%2A> property of the <xref:System.Windows.Controls.ColumnDefinition> element.</span></span>  
  
 <span data-ttu-id="ebd1e-107">El ejemplo también define un segundo método personalizado, denominado `changeColVal`.</span><span class="sxs-lookup"><span data-stu-id="ebd1e-107">The example also defines a second custom method, called `changeColVal`.</span></span> <span data-ttu-id="ebd1e-108">Convierte este método personalizado la <xref:System.Windows.Controls.Primitives.RangeBase.Value%2A> de un <xref:System.Windows.Controls.Slider> a un <xref:System.String> y, a continuación, pasa ese valor a la <xref:System.Windows.Controls.ColumnDefinition> como el <xref:System.Windows.Controls.ColumnDefinition.Width%2A> del elemento.</span><span class="sxs-lookup"><span data-stu-id="ebd1e-108">This custom method converts the <xref:System.Windows.Controls.Primitives.RangeBase.Value%2A> of a <xref:System.Windows.Controls.Slider> to a <xref:System.String> and then passes that value back to the <xref:System.Windows.Controls.ColumnDefinition> as the <xref:System.Windows.Controls.ColumnDefinition.Width%2A> of the element.</span></span>  
  
 <span data-ttu-id="ebd1e-109">Tenga en cuenta que otro [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] archivo define el contenido de un <xref:System.Windows.Controls.ListBoxItem>.</span><span class="sxs-lookup"><span data-stu-id="ebd1e-109">Note that a separate [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] file defines the contents of a <xref:System.Windows.Controls.ListBoxItem>.</span></span>  
  
 [!code-csharp[gridlengthConverterGrid#1](~/samples/snippets/csharp/VS_Snippets_Wpf/gridlengthConverterGrid/CSharp/Window1.xaml.cs#1)]
 [!code-vb[gridlengthConverterGrid#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/gridlengthConverterGrid/VisualBasic/Window1.xaml.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="ebd1e-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="ebd1e-110">See also</span></span>

- <xref:System.Windows.GridLengthConverter>
- <xref:System.Windows.GridLength>
