---
title: 'Cómo: Enlazar a un origen de datos ADO.NET'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data binding [WPF], binding to ADO.NET data sources
- ADO.NET data sources [WPF], binding to
- binding [WPF], to ADO.NET data sources
ms.assetid: a70c6d7b-7b38-4fdf-b655-4804db7c8315
ms.openlocfilehash: 0b3d7147f45bee5e8abd95bdc51c5f5f695cf830
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2019
ms.locfileid: "73458409"
---
# <a name="how-to-bind-to-an-adonet-data-source"></a><span data-ttu-id="9e1db-102">Cómo: Enlazar a un origen de datos ADO.NET</span><span class="sxs-lookup"><span data-stu-id="9e1db-102">How to: Bind to an ADO.NET Data Source</span></span>

<span data-ttu-id="9e1db-103">En este ejemplo se muestra cómo enlazar un control de <xref:System.Windows.Controls.ListBox> de [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] a un `DataSet`de ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="9e1db-103">This example shows how to bind a [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] <xref:System.Windows.Controls.ListBox> control to an ADO.NET `DataSet`.</span></span>

## <a name="example"></a><span data-ttu-id="9e1db-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="9e1db-104">Example</span></span>

<span data-ttu-id="9e1db-105">En este ejemplo, se utiliza un objeto `OleDbConnection` para conectar al origen de datos, que es un archivo `Access MDB` especificado en la cadena de conexión.</span><span class="sxs-lookup"><span data-stu-id="9e1db-105">In this example, an `OleDbConnection` object is used to connect to the data source which is an `Access MDB` file that is specified in the connection string.</span></span> <span data-ttu-id="9e1db-106">Una vez establecida la conexión, se crea un objeto `OleDbDataAdapter`.</span><span class="sxs-lookup"><span data-stu-id="9e1db-106">After the connection is established, an `OleDbDataAdapter` object is created.</span></span> <span data-ttu-id="9e1db-107">El objeto `OleDbDataAdapter` ejecuta una instrucción SELECT Lenguaje de consulta estructurado (SQL) para recuperar el conjunto de registros de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="9e1db-107">The `OleDbDataAdapter` object executes a select Structured Query Language (SQL) statement to retrieve the recordset from the database.</span></span> <span data-ttu-id="9e1db-108">Los resultados del comando SQL se almacenan en un `DataTable` del `DataSet` llamando al método `Fill` del `OleDbDataAdapter`.</span><span class="sxs-lookup"><span data-stu-id="9e1db-108">The results from the SQL command are stored in a `DataTable` of the `DataSet` by calling the `Fill` method of the `OleDbDataAdapter`.</span></span> <span data-ttu-id="9e1db-109">El elemento `DataTable` de este ejemplo se denomina `BookTable`.</span><span class="sxs-lookup"><span data-stu-id="9e1db-109">The `DataTable` in this example is named `BookTable`.</span></span> <span data-ttu-id="9e1db-110">A continuación, en el ejemplo se establece la propiedad <xref:System.Windows.FrameworkElement.DataContext%2A> del <xref:System.Windows.Controls.ListBox> en el objeto `DataSet`.</span><span class="sxs-lookup"><span data-stu-id="9e1db-110">The example then sets the <xref:System.Windows.FrameworkElement.DataContext%2A> property of the <xref:System.Windows.Controls.ListBox> to the `DataSet` object.</span></span>

[!code-csharp[ADODataSet#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ADODataSet/CSharp/Window1.xaml.cs#1)]
[!code-vb[ADODataSet#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ADODataSet/VisualBasic/Window1.xaml.vb#1)]

<span data-ttu-id="9e1db-111">A continuación, podemos enlazar la propiedad <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> del <xref:System.Windows.Controls.ListBox> a `BookTable` del `DataSet`:</span><span class="sxs-lookup"><span data-stu-id="9e1db-111">We can then bind the <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> property of the <xref:System.Windows.Controls.ListBox> to `BookTable` of the `DataSet`:</span></span>

[!code-xaml[ADODataSet#2](~/samples/snippets/csharp/VS_Snippets_Wpf/ADODataSet/CSharp/Window1.xaml#2)]

<span data-ttu-id="9e1db-112">`BookItemTemplate` es el <xref:System.Windows.DataTemplate> que define cómo aparecen los datos:</span><span class="sxs-lookup"><span data-stu-id="9e1db-112">`BookItemTemplate` is the <xref:System.Windows.DataTemplate> that defines how the data appears:</span></span>

[!code-xaml[ADODataSet#3](~/samples/snippets/csharp/VS_Snippets_Wpf/ADODataSet/CSharp/Window1.xaml#3)]

<span data-ttu-id="9e1db-113">`IntColorConverter` convierte un valor `int` en un color.</span><span class="sxs-lookup"><span data-stu-id="9e1db-113">The `IntColorConverter` converts an `int` to a color.</span></span> <span data-ttu-id="9e1db-114">Con el uso de este convertidor, el color <xref:System.Windows.Controls.TextBlock.Background%2A> del tercer <xref:System.Windows.Controls.TextBlock> aparece en verde si el valor de `NumPages` es menor que 350 y rojo en caso contrario.</span><span class="sxs-lookup"><span data-stu-id="9e1db-114">With the use of this converter, the <xref:System.Windows.Controls.TextBlock.Background%2A> color of the third <xref:System.Windows.Controls.TextBlock> appears green if the value of `NumPages` is less than 350 and red otherwise.</span></span> <span data-ttu-id="9e1db-115">La implementación del convertidor no se muestra aquí.</span><span class="sxs-lookup"><span data-stu-id="9e1db-115">The implementation of the converter is not shown here.</span></span>

## <a name="see-also"></a><span data-ttu-id="9e1db-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="9e1db-116">See also</span></span>

- <xref:System.Windows.Data.BindingListCollectionView>
- [<span data-ttu-id="9e1db-117">Información general sobre el enlace de datos</span><span class="sxs-lookup"><span data-stu-id="9e1db-117">Data Binding Overview</span></span>](../../../desktop-wpf/data/data-binding-overview.md)
- [<span data-ttu-id="9e1db-118">Temas "Cómo..."</span><span class="sxs-lookup"><span data-stu-id="9e1db-118">How-to Topics</span></span>](data-binding-how-to-topics.md)
