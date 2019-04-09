---
title: Filtrar Usar un objeto ThicknessConverter
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- border thickness [WPF]
- ThicknessConverter objects [WPF]
ms.assetid: 52682194-d7fd-499c-8005-73fcc84e7b2c
ms.openlocfilehash: ebfb8642a01f6d602f4e5ffa58fde6a8ee0b4e1f
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59075956"
---
# <a name="how-to-use-a-thicknessconverter-object"></a><span data-ttu-id="8a360-102">Filtrar Usar un objeto ThicknessConverter</span><span class="sxs-lookup"><span data-stu-id="8a360-102">How to: Use a ThicknessConverter Object</span></span>
## <a name="example"></a><span data-ttu-id="8a360-103">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="8a360-103">Example</span></span>  
 <span data-ttu-id="8a360-104">En este ejemplo se muestra cómo crear una instancia de <xref:System.Windows.ThicknessConverter> y usarlo para cambiar el grosor del borde.</span><span class="sxs-lookup"><span data-stu-id="8a360-104">This example shows how to create an instance of <xref:System.Windows.ThicknessConverter> and use it to change the thickness of a border.</span></span>  
  
 <span data-ttu-id="8a360-105">El ejemplo define un método personalizado llamado `changeThickness`; en primer lugar, este método convierte el contenido de un <xref:System.Windows.Controls.ListBoxItem>, tal como se define en otro [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] archivo a una instancia de <xref:System.Windows.Thickness>y posteriormente convierte el contenido en un <xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="8a360-105">The example defines a custom method called `changeThickness`; this method first converts the contents of a <xref:System.Windows.Controls.ListBoxItem>, as defined in a separate [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] file, to an instance of <xref:System.Windows.Thickness>, and later converts the content into a <xref:System.String>.</span></span> <span data-ttu-id="8a360-106">Este método pasa el <xref:System.Windows.Controls.ListBoxItem> a un <xref:System.Windows.ThicknessConverter> objeto, que convierte el <xref:System.Windows.Controls.ContentControl.Content%2A> de un <xref:System.Windows.Controls.ListBoxItem> a una instancia de <xref:System.Windows.Thickness>.</span><span class="sxs-lookup"><span data-stu-id="8a360-106">This method passes the <xref:System.Windows.Controls.ListBoxItem> to a <xref:System.Windows.ThicknessConverter> object, which converts the <xref:System.Windows.Controls.ContentControl.Content%2A> of a <xref:System.Windows.Controls.ListBoxItem> to an instance of <xref:System.Windows.Thickness>.</span></span> <span data-ttu-id="8a360-107">Este valor, a continuación, se pasa como el valor de la <xref:System.Windows.Controls.Border.BorderThickness%2A> propiedad de la <xref:System.Windows.Controls.Border>.</span><span class="sxs-lookup"><span data-stu-id="8a360-107">This value is then passed back as the value of the <xref:System.Windows.Controls.Border.BorderThickness%2A> property of the <xref:System.Windows.Controls.Border>.</span></span>  
  
 <span data-ttu-id="8a360-108">En este ejemplo no se ejecuta.</span><span class="sxs-lookup"><span data-stu-id="8a360-108">This example does not run.</span></span>  
  
 [!code-csharp[ThicknessConverter#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ThicknessConverter/CSharp/Window1.xaml.cs#1)]
 [!code-vb[ThicknessConverter#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ThicknessConverter/VisualBasic/Window1.xaml.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="8a360-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="8a360-109">See also</span></span>

- <xref:System.Windows.Thickness>
- <xref:System.Windows.ThicknessConverter>
- <xref:System.Windows.Controls.Border>
- [<span data-ttu-id="8a360-110">Filtrar Cambiar la propiedad Margin</span><span class="sxs-lookup"><span data-stu-id="8a360-110">How to: Change the Margin Property</span></span>](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms750561(v=vs.90))
- [<span data-ttu-id="8a360-111">Filtrar Convertir un elemento ListBoxItem en un nuevo tipo de datos</span><span class="sxs-lookup"><span data-stu-id="8a360-111">How to: Convert a ListBoxItem to a new Data Type</span></span>](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms749147(v=vs.90))
- [<span data-ttu-id="8a360-112">Información general sobre elementos Panel</span><span class="sxs-lookup"><span data-stu-id="8a360-112">Panels Overview</span></span>](../controls/panels-overview.md)
