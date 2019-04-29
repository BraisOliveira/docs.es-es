---
title: Procedimiento Enlazar a los resultados de una consulta LINQ
ms.date: 03/30/2017
helpviewer_keywords:
- running a LINQ query [WPF], bind to results
- binding to LINQ query results [WPF]
ms.assetid: ff2844d9-17ed-4ea6-aab1-5111af0bc684
ms.openlocfilehash: 5464ee9c59a7c99a83774a7535b9b3c422c1d2e1
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61644423"
---
# <a name="how-to-bind-to-the-results-of-a-linq-query"></a><span data-ttu-id="ae939-102">Procedimiento Enlazar a los resultados de una consulta LINQ</span><span class="sxs-lookup"><span data-stu-id="ae939-102">How to: Bind to the Results of a LINQ Query</span></span>
<span data-ttu-id="ae939-103">En este ejemplo se muestra cómo ejecutar una consulta LINQ y, a continuación, enlazar a los resultados.</span><span class="sxs-lookup"><span data-stu-id="ae939-103">This example demonstrates how to run a LINQ query and then bind to the results.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ae939-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ae939-104">Example</span></span>  
 <span data-ttu-id="ae939-105">El ejemplo siguiente crea dos cuadros de lista.</span><span class="sxs-lookup"><span data-stu-id="ae939-105">The following example creates two list boxes.</span></span> <span data-ttu-id="ae939-106">El primer cuadro de lista contiene tres elementos de lista.</span><span class="sxs-lookup"><span data-stu-id="ae939-106">The first list box contains three list items.</span></span>  
  
 [!code-xaml[LinqExample#UI](~/samples/snippets/csharp/VS_Snippets_Wpf/LinqExample/CSharp/Window1.xaml#ui)]  
  
 <span data-ttu-id="ae939-107">Seleccionar un elemento en el primer cuadro de lista, invoca el controlador de eventos siguiente.</span><span class="sxs-lookup"><span data-stu-id="ae939-107">Selecting an item from the first list box invokes the following event handler.</span></span> <span data-ttu-id="ae939-108">En este ejemplo, `Tasks` es una colección de `Task` objetos.</span><span class="sxs-lookup"><span data-stu-id="ae939-108">In this example, `Tasks` is a collection of `Task` objects.</span></span> <span data-ttu-id="ae939-109">El `Task` clase tiene una propiedad denominada `Priority`.</span><span class="sxs-lookup"><span data-stu-id="ae939-109">The `Task` class has a property named `Priority`.</span></span> <span data-ttu-id="ae939-110">Este controlador de eventos ejecuta una consulta LINQ que devuelve la colección de `Task` objetos que tienen el valor de prioridad seleccionada y, a continuación, se establece como el <xref:System.Windows.FrameworkElement.DataContext%2A>:</span><span class="sxs-lookup"><span data-stu-id="ae939-110">This event handler runs a LINQ query that returns the collection of `Task` objects that have the selected priority value, and then sets that as the <xref:System.Windows.FrameworkElement.DataContext%2A>:</span></span>  
  
 [!code-csharp[LinqExample#Using](~/samples/snippets/csharp/VS_Snippets_Wpf/LinqExample/CSharp/Window1.xaml.cs#using)]  
[!code-csharp[LinqExample#Tasks](~/samples/snippets/csharp/VS_Snippets_Wpf/LinqExample/CSharp/Window1.xaml.cs#tasks)]  
[!code-csharp[LinqExample#Handler](~/samples/snippets/csharp/VS_Snippets_Wpf/LinqExample/CSharp/Window1.xaml.cs#handler)]  
  
 <span data-ttu-id="ae939-111">El segundo cuadro de lista se enlaza a esa colección porque su <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> valor se establece en `{Binding}`.</span><span class="sxs-lookup"><span data-stu-id="ae939-111">The second list box binds to that collection because its <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> value is set to `{Binding}`.</span></span> <span data-ttu-id="ae939-112">Como resultado, muestra la colección devuelta (según la `myTaskTemplate` <xref:System.Windows.DataTemplate>).</span><span class="sxs-lookup"><span data-stu-id="ae939-112">As a result, it displays the returned collection (based on the `myTaskTemplate`<xref:System.Windows.DataTemplate>).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae939-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="ae939-113">See also</span></span>

- [<span data-ttu-id="ae939-114">Hacer que los datos estén disponibles para el enlace en XAML</span><span class="sxs-lookup"><span data-stu-id="ae939-114">Make Data Available for Binding in XAML</span></span>](how-to-make-data-available-for-binding-in-xaml.md)
- [<span data-ttu-id="ae939-115">Enlazar a una colección y mostrar información basada en la selección</span><span class="sxs-lookup"><span data-stu-id="ae939-115">Bind to a Collection and Display Information Based on Selection</span></span>](how-to-bind-to-a-collection-and-display-information-based-on-selection.md)
- [<span data-ttu-id="ae939-116">Novedades de WPF versión 4.5</span><span class="sxs-lookup"><span data-stu-id="ae939-116">What's New in WPF Version 4.5</span></span>](../getting-started/whats-new.md)
- [<span data-ttu-id="ae939-117">Información general sobre el enlace de datos</span><span class="sxs-lookup"><span data-stu-id="ae939-117">Data Binding Overview</span></span>](data-binding-overview.md)
- [<span data-ttu-id="ae939-118">Temas "Cómo..."</span><span class="sxs-lookup"><span data-stu-id="ae939-118">How-to Topics</span></span>](data-binding-how-to-topics.md)
