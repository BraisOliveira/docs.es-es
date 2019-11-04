---
title: 'Cómo: Ordenar datos en una vista'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data binding [WPF], sorting data in views
- data binding [WPF], grouping data in views
- grouping data in views [WPF]
- views [WPF], sorting data
- views [WPF], grouping data
- sorting data in views [WPF]
ms.assetid: f4c43578-01b7-4774-a953-acb95a13b94a
ms.openlocfilehash: 14314ed019f9194a657787bd767ae68615e94ac7
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2019
ms.locfileid: "73454830"
---
# <a name="how-to-sort-data-in-a-view"></a><span data-ttu-id="d00ca-102">Cómo: Ordenar datos en una vista</span><span class="sxs-lookup"><span data-stu-id="d00ca-102">How to: Sort Data in a View</span></span>
<span data-ttu-id="d00ca-103">En este ejemplo se describe cómo ordenar los datos en una vista.</span><span class="sxs-lookup"><span data-stu-id="d00ca-103">This example describes how to sort data in a view.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d00ca-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d00ca-104">Example</span></span>  
 <span data-ttu-id="d00ca-105">En el ejemplo siguiente se crea un <xref:System.Windows.Controls.ListBox> simple y un <xref:System.Windows.Controls.Button>:</span><span class="sxs-lookup"><span data-stu-id="d00ca-105">The following example creates a simple <xref:System.Windows.Controls.ListBox> and a <xref:System.Windows.Controls.Button>:</span></span>  
  
 [!code-xaml[ListBoxSort_snip#HowTo](~/samples/snippets/csharp/VS_Snippets_Wpf/ListBoxSort_snip/CSharp/Window1.xaml#howto)]  
  
 <span data-ttu-id="d00ca-106">El controlador de eventos <xref:System.Windows.Controls.Primitives.ButtonBase.Click> del botón contiene la lógica para ordenar los elementos del <xref:System.Windows.Controls.ListBox> en orden descendente.</span><span class="sxs-lookup"><span data-stu-id="d00ca-106">The <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event handler of the button contains logic to sort the items in the <xref:System.Windows.Controls.ListBox> in the descending order.</span></span> <span data-ttu-id="d00ca-107">Puede hacerlo porque agregar elementos a un <xref:System.Windows.Controls.ListBox> de esta manera los agrega al <xref:System.Windows.Controls.ItemCollection> de la <xref:System.Windows.Controls.ListBox>y <xref:System.Windows.Controls.ItemCollection> deriva de la clase <xref:System.Windows.Data.CollectionView>.</span><span class="sxs-lookup"><span data-stu-id="d00ca-107">You can do this because adding items to a <xref:System.Windows.Controls.ListBox> this way adds them to the <xref:System.Windows.Controls.ItemCollection> of the <xref:System.Windows.Controls.ListBox>, and <xref:System.Windows.Controls.ItemCollection> derives from the <xref:System.Windows.Data.CollectionView> class.</span></span> <span data-ttu-id="d00ca-108">Si va a enlazar el <xref:System.Windows.Controls.ListBox> a una colección mediante la propiedad <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>, puede usar la misma técnica para ordenar.</span><span class="sxs-lookup"><span data-stu-id="d00ca-108">If you are binding your <xref:System.Windows.Controls.ListBox> to a collection using the <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> property, you can use the same technique to sort.</span></span>  
  
 [!code-csharp[ListBoxSort_snip#HowToCode](~/samples/snippets/csharp/VS_Snippets_Wpf/ListBoxSort_snip/CSharp/Window1.xaml.cs#howtocode)]
 [!code-vb[ListBoxSort_snip#HowToCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ListBoxSort_snip/visualbasic/window1.xaml.vb#howtocode)]  
  
 <span data-ttu-id="d00ca-109">Siempre que tenga una referencia al objeto de vista, puede usar la misma técnica para ordenar el contenido de otras vistas de colección.</span><span class="sxs-lookup"><span data-stu-id="d00ca-109">As long as you have a reference to the view object, you can use the same technique to sort the content of other collection views.</span></span> <span data-ttu-id="d00ca-110">Para obtener un ejemplo de cómo obtener una vista, vea [obtener la vista predeterminada de una recolección de datos](how-to-get-the-default-view-of-a-data-collection.md).</span><span class="sxs-lookup"><span data-stu-id="d00ca-110">For an example of how to obtain a view, see [Get the Default View of a Data Collection](how-to-get-the-default-view-of-a-data-collection.md).</span></span> <span data-ttu-id="d00ca-111">Para ver otro ejemplo, vea [ordenar una columna de GridView cuando se hace clic en un encabezado](../controls/how-to-sort-a-gridview-column-when-a-header-is-clicked.md).</span><span class="sxs-lookup"><span data-stu-id="d00ca-111">For another example, see [Sort a GridView Column When a Header Is Clicked](../controls/how-to-sort-a-gridview-column-when-a-header-is-clicked.md).</span></span> <span data-ttu-id="d00ca-112">Para obtener más información sobre las vistas, vea enlazar a colecciones en [información general](../../../desktop-wpf/data/data-binding-overview.md)sobre el enlace de datos.</span><span class="sxs-lookup"><span data-stu-id="d00ca-112">For more information about views, see Binding to Collections in [Data Binding Overview](../../../desktop-wpf/data/data-binding-overview.md).</span></span>  
  
 <span data-ttu-id="d00ca-113">Para obtener un ejemplo de cómo aplicar la lógica de ordenación en [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], vea [ordenar y agrupar datos mediante una vista en XAML](how-to-sort-and-group-data-using-a-view-in-xaml.md).</span><span class="sxs-lookup"><span data-stu-id="d00ca-113">For an example of how to apply sorting logic in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], see [Sort and Group Data Using a View in XAML](how-to-sort-and-group-data-using-a-view-in-xaml.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d00ca-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="d00ca-114">See also</span></span>

- <xref:System.Windows.Data.ListCollectionView.CustomSort%2A>
- [<span data-ttu-id="d00ca-115">Ordenar una columna de GridView cuando se hace clic en un encabezado</span><span class="sxs-lookup"><span data-stu-id="d00ca-115">Sort a GridView Column When a Header Is Clicked</span></span>](../controls/how-to-sort-a-gridview-column-when-a-header-is-clicked.md)
- [<span data-ttu-id="d00ca-116">Información general sobre el enlace de datos</span><span class="sxs-lookup"><span data-stu-id="d00ca-116">Data Binding Overview</span></span>](../../../desktop-wpf/data/data-binding-overview.md)
- [<span data-ttu-id="d00ca-117">Filtrar datos en una vista</span><span class="sxs-lookup"><span data-stu-id="d00ca-117">Filter Data in a View</span></span>](how-to-filter-data-in-a-view.md)
- [<span data-ttu-id="d00ca-118">Temas "Cómo..."</span><span class="sxs-lookup"><span data-stu-id="d00ca-118">How-to Topics</span></span>](data-binding-how-to-topics.md)
