---
title: Procedimiento Enlazar a los resultados de una consulta LINQ for XML, XDocument o XElement
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data binding [WPF], binding to XDocument
- data binding [WPF], binding to XElement
ms.assetid: 6a629a49-fe1c-465d-b76a-3dcbf4307b64
ms.openlocfilehash: 6c220bf7b06e6eaf4cf661c07a0a8c6c37ec333d
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2019
ms.locfileid: "57358267"
---
# <a name="how-to-bind-to-xdocument-xelement-or-linq-for-xml-query-results"></a><span data-ttu-id="1cf04-102">Filtrar Enlazar a los resultados de una consulta LINQ for XML, XDocument o XElement</span><span class="sxs-lookup"><span data-stu-id="1cf04-102">How to: Bind to XDocument, XElement, or LINQ for XML Query Results</span></span>
<span data-ttu-id="1cf04-103">En este ejemplo muestra cómo enlazar datos XML a un <xref:System.Windows.Controls.ItemsControl> mediante <xref:System.Xml.Linq.XDocument>.</span><span class="sxs-lookup"><span data-stu-id="1cf04-103">This example demonstrates how to bind XML data to an <xref:System.Windows.Controls.ItemsControl> using <xref:System.Xml.Linq.XDocument>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1cf04-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="1cf04-104">Example</span></span>  
 <span data-ttu-id="1cf04-105">El código XAML siguiente define un <xref:System.Windows.Controls.ItemsControl> e incluye una plantilla de datos para los datos de tipo `Planet` en el `http://planetsNS` espacio de nombres XML.</span><span class="sxs-lookup"><span data-stu-id="1cf04-105">The following XAML code defines an <xref:System.Windows.Controls.ItemsControl> and includes a data template for data of type `Planet` in the `http://planetsNS` XML namespace.</span></span> <span data-ttu-id="1cf04-106">Un tipo de datos XML que ocupa un espacio de nombres debe incluir el espacio de nombres entre llaves y, si aparece donde podría aparecer una extensión de marcado XAML, debe preceder al espacio de nombres con una secuencia de escape de llaves.</span><span class="sxs-lookup"><span data-stu-id="1cf04-106">An XML data type that occupies a namespace must include the namespace in braces, and if it appears where a XAML markup extension could appear, it must precede the namespace with a brace escape sequence.</span></span> <span data-ttu-id="1cf04-107">Este código enlaza a las propiedades dinámicas que corresponden a la <xref:System.Xml.Linq.XContainer.Element%2A> y <xref:System.Xml.Linq.XElement.Attribute%2A> métodos de la <xref:System.Xml.Linq.XElement> clase.</span><span class="sxs-lookup"><span data-stu-id="1cf04-107">This code binds to dynamic properties that correspond to the <xref:System.Xml.Linq.XContainer.Element%2A> and <xref:System.Xml.Linq.XElement.Attribute%2A> methods of the <xref:System.Xml.Linq.XElement> class.</span></span> <span data-ttu-id="1cf04-108">Las propiedades dinámicas permiten a XAML enlazar a las propiedades dinámicas que comparten los nombres de los métodos.</span><span class="sxs-lookup"><span data-stu-id="1cf04-108">Dynamic properties enable XAML to bind to dynamic properties that share the names of methods.</span></span> <span data-ttu-id="1cf04-109">Para más información, consulte [Propiedades dinámicas de LINQ to XML](/visualstudio/designers/linq-to-xml-dynamic-properties).</span><span class="sxs-lookup"><span data-stu-id="1cf04-109">To learn more, see [LINQ to XML Dynamic Properties](/visualstudio/designers/linq-to-xml-dynamic-properties).</span></span> <span data-ttu-id="1cf04-110">Tenga en cuenta cómo la declaración de espacio de nombres predeterminada para XML no se aplica a los nombres de atributo.</span><span class="sxs-lookup"><span data-stu-id="1cf04-110">Notice how the default namespace declaration for the XML does not apply to attribute names.</span></span>  
  
 [!code-xaml[XLinqExample#StackPanelResources](~/samples/snippets/csharp/VS_Snippets_Wpf/XLinqExample/CSharp/Window1.xaml#stackpanelresources)]  
[!code-xaml[XLinqExample#ItemsControl](~/samples/snippets/csharp/VS_Snippets_Wpf/XLinqExample/CSharp/Window1.xaml#itemscontrol)]  
  
 <span data-ttu-id="1cf04-111">Las siguientes llamadas de código de C# <xref:System.Xml.Linq.XDocument.Load%2A> y establece el contexto de datos del panel de pila en todos los subelementos del elemento denominado `SolarSystemPlanets` en el `http://planetsNS` espacio de nombres XML.</span><span class="sxs-lookup"><span data-stu-id="1cf04-111">The following C# code calls <xref:System.Xml.Linq.XDocument.Load%2A> and sets the stack panel data context to all subelements of the element named `SolarSystemPlanets` in the `http://planetsNS` XML namespace.</span></span>  
  
 [!code-csharp[XLinqExample#LoadDCFromFile](~/samples/snippets/csharp/VS_Snippets_Wpf/XLinqExample/CSharp/Window1.xaml.cs#loaddcfromfile)]
 [!code-vb[XLinqExample#LoadDCFromFile](~/samples/snippets/visualbasic/VS_Snippets_Wpf/XLinqExample/visualbasic/window1.xaml.vb#loaddcfromfile)]  
  
 <span data-ttu-id="1cf04-112">Datos XML pueden almacenarse como recurso XAML mediante <xref:System.Windows.Data.ObjectDataProvider>.</span><span class="sxs-lookup"><span data-stu-id="1cf04-112">XML data can be stored as a XAML resource using <xref:System.Windows.Data.ObjectDataProvider>.</span></span> <span data-ttu-id="1cf04-113">Para obtener un ejemplo completo, vea [código fuente de L2DBForm.xaml](/visualstudio/designers/l2dbform-xaml-source-code).</span><span class="sxs-lookup"><span data-stu-id="1cf04-113">For a complete example, see  [L2DBForm.xaml source code](/visualstudio/designers/l2dbform-xaml-source-code).</span></span> <span data-ttu-id="1cf04-114">En el ejemplo siguiente se muestra cómo el código puede establecer el contexto de datos en un recurso de objetos.</span><span class="sxs-lookup"><span data-stu-id="1cf04-114">The following sample shows how code can set the data context to an object resource.</span></span>  
  
 [!code-csharp[XLinqExample#LoadDCFromXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/XLinqExample/CSharp/Window1.xaml.cs#loaddcfromxaml)]
 [!code-vb[XLinqExample#LoadDCFromXAML](~/samples/snippets/visualbasic/VS_Snippets_Wpf/XLinqExample/visualbasic/window1.xaml.vb#loaddcfromxaml)]  
  
 <span data-ttu-id="1cf04-115">Las propiedades dinámicas que se asignan a <xref:System.Xml.Linq.XContainer.Element%2A> y <xref:System.Xml.Linq.XElement.Attribute%2A> proporcionan flexibilidad dentro de XAML.</span><span class="sxs-lookup"><span data-stu-id="1cf04-115">The dynamic properties that map to <xref:System.Xml.Linq.XContainer.Element%2A> and <xref:System.Xml.Linq.XElement.Attribute%2A> provide flexibility within XAML.</span></span> <span data-ttu-id="1cf04-116">El código también puede enlazar a los resultados de una consulta LINQ to XML.</span><span class="sxs-lookup"><span data-stu-id="1cf04-116">Your code can also bind to the results of a LINQ for XML query.</span></span> <span data-ttu-id="1cf04-117">Este ejemplo enlaza a los resultados de la consulta ordenados por un valor de elemento.</span><span class="sxs-lookup"><span data-stu-id="1cf04-117">This example binds to query results ordered by an element value.</span></span>  
  
 [!code-csharp[XLinqExample#BindToResults](~/samples/snippets/csharp/VS_Snippets_Wpf/XLinqExample/CSharp/Window1.xaml.cs#bindtoresults)]
 [!code-vb[XLinqExample#BindToResults](~/samples/snippets/visualbasic/VS_Snippets_Wpf/XLinqExample/visualbasic/window1.xaml.vb#bindtoresults)]  
  
## <a name="see-also"></a><span data-ttu-id="1cf04-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="1cf04-118">See also</span></span>
- [<span data-ttu-id="1cf04-119">Información general sobre orígenes de enlaces</span><span class="sxs-lookup"><span data-stu-id="1cf04-119">Binding Sources Overview</span></span>](binding-sources-overview.md)
- [<span data-ttu-id="1cf04-120">Información general de enlace de datos WPF con LINQ to XML</span><span class="sxs-lookup"><span data-stu-id="1cf04-120">WPF Data Binding with LINQ to XML Overview</span></span>](/visualstudio/designers/wpf-data-binding-with-linq-to-xml-overview)
- [<span data-ttu-id="1cf04-121">Ejemplo de enlace de datos WPF mediante LINQ to XML</span><span class="sxs-lookup"><span data-stu-id="1cf04-121">WPF Data Binding Using LINQ to XML Example</span></span>](/visualstudio/designers/wpf-data-binding-using-linq-to-xml-example)
- [<span data-ttu-id="1cf04-122">Propiedades dinámicas de LINQ to XML</span><span class="sxs-lookup"><span data-stu-id="1cf04-122">LINQ to XML Dynamic Properties</span></span>](/visualstudio/designers/linq-to-xml-dynamic-properties)
