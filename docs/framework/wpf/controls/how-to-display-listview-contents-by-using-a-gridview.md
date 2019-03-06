---
title: Procedimiento Mostrar el contenido de ListView mediante un control GridView
ms.date: 03/30/2017
helpviewer_keywords:
- ListView controls [WPF], displaying contents with GridView
- GridView [WPF], displaying ListView contents
ms.assetid: 5bc1e767-ab46-4f14-bd41-3d5d39e1d000
ms.openlocfilehash: 9a4bcc8b613637521ee91a11b0bdac8f77f90a03
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2019
ms.locfileid: "57354406"
---
# <a name="how-to-display-listview-contents-by-using-a-gridview"></a><span data-ttu-id="3adc3-102">Filtrar Mostrar el contenido de ListView mediante un control GridView</span><span class="sxs-lookup"><span data-stu-id="3adc3-102">How to: Display ListView Contents by Using a GridView</span></span>
<span data-ttu-id="3adc3-103">En este ejemplo se muestra cómo definir un <xref:System.Windows.Controls.GridView> modo de vista para un <xref:System.Windows.Controls.ListView> control.</span><span class="sxs-lookup"><span data-stu-id="3adc3-103">This example shows how to define a <xref:System.Windows.Controls.GridView> view mode for a <xref:System.Windows.Controls.ListView> control.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3adc3-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="3adc3-104">Example</span></span>  
 <span data-ttu-id="3adc3-105">Puede definir el modo de vista de un <xref:System.Windows.Controls.GridView> especificando <xref:System.Windows.Controls.GridViewColumn> objetos.</span><span class="sxs-lookup"><span data-stu-id="3adc3-105">You can define the view mode of a <xref:System.Windows.Controls.GridView> by specifying <xref:System.Windows.Controls.GridViewColumn> objects.</span></span> <span data-ttu-id="3adc3-106">El ejemplo siguiente muestra cómo definir <xref:System.Windows.Controls.GridViewColumn> objetos que se enlazan al contenido de datos que se ha especificado para el <xref:System.Windows.Controls.ListView> control.</span><span class="sxs-lookup"><span data-stu-id="3adc3-106">The following example shows how to define <xref:System.Windows.Controls.GridViewColumn> objects that bind to the data content that is specified for the <xref:System.Windows.Controls.ListView> control.</span></span> <span data-ttu-id="3adc3-107">Esto <xref:System.Windows.Controls.GridView> ejemplo especifica tres <xref:System.Windows.Controls.GridViewColumn> objetos que se asignan a la `FirstName`, `LastName`, y `EmployeeNumber` campos de la `EmployeeInfoDataSource` que se establece como el <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> de la <xref:System.Windows.Controls.ListView> control.</span><span class="sxs-lookup"><span data-stu-id="3adc3-107">This <xref:System.Windows.Controls.GridView> example specifies three <xref:System.Windows.Controls.GridViewColumn> objects that map to the `FirstName`, `LastName`, and `EmployeeNumber` fields of the `EmployeeInfoDataSource` that is set as the <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> of the <xref:System.Windows.Controls.ListView> control.</span></span>  
  
 [!code-xaml[ListViewCode#ListViewEmployee](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewCode/CSharp/Window1.xaml#listviewemployee)]  
  
 <span data-ttu-id="3adc3-108">La siguiente ilustración muestra cómo aparece en este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="3adc3-108">The following illustration shows how this example appears.</span></span>  
  
 <span data-ttu-id="3adc3-109">![ListView con salida de GridView](./media/listviewgridview.JPG "ListViewGridView")</span><span class="sxs-lookup"><span data-stu-id="3adc3-109">![ListView with GridView output](./media/listviewgridview.JPG "ListViewGridView")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3adc3-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="3adc3-110">See also</span></span>
- <xref:System.Windows.Controls.ListView>
- <xref:System.Windows.Controls.GridView>
- [<span data-ttu-id="3adc3-111">Información general sobre ListView</span><span class="sxs-lookup"><span data-stu-id="3adc3-111">ListView Overview</span></span>](listview-overview.md)
- [<span data-ttu-id="3adc3-112">Información general sobre GridView</span><span class="sxs-lookup"><span data-stu-id="3adc3-112">GridView Overview</span></span>](gridview-overview.md)
- [<span data-ttu-id="3adc3-113">Temas "Cómo..."</span><span class="sxs-lookup"><span data-stu-id="3adc3-113">How-to Topics</span></span>](listview-how-to-topics.md)
