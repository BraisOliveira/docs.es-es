---
title: Filtrar Convertir datos enlazados
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- converting [WPF], bound data
- data binding [WPF], converting bound data
- binding data [WPF], converting bound data
ms.assetid: b00aaa19-c6df-4c3b-a9fd-88a0b488df2b
ms.openlocfilehash: 40699bec1c6cd775f7f8495b7a49eda15fb2ed83
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59093805"
---
# <a name="how-to-convert-bound-data"></a><span data-ttu-id="6dd87-102">Filtrar Convertir datos enlazados</span><span class="sxs-lookup"><span data-stu-id="6dd87-102">How to: Convert Bound Data</span></span>
<span data-ttu-id="6dd87-103">En este ejemplo se muestra cómo aplicar la conversión a datos que se utilizan en enlaces.</span><span class="sxs-lookup"><span data-stu-id="6dd87-103">This example shows how to apply conversion to data that is used in bindings.</span></span>  
  
 <span data-ttu-id="6dd87-104">Para convertir datos durante el enlace, debe crear una clase que implementa el <xref:System.Windows.Data.IValueConverter> interfaz, que incluye el <xref:System.Windows.Data.IValueConverter.Convert%2A> y <xref:System.Windows.Data.IValueConverter.ConvertBack%2A> métodos.</span><span class="sxs-lookup"><span data-stu-id="6dd87-104">To convert data during binding, you must create a class that implements the <xref:System.Windows.Data.IValueConverter> interface, which includes the <xref:System.Windows.Data.IValueConverter.Convert%2A> and <xref:System.Windows.Data.IValueConverter.ConvertBack%2A> methods.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6dd87-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="6dd87-105">Example</span></span>  
 <span data-ttu-id="6dd87-106">El ejemplo siguiente muestra la implementación de un convertidor de fecha que convierte el valor de fecha pasado de manera que solo se muestra el año, mes y día.</span><span class="sxs-lookup"><span data-stu-id="6dd87-106">The following example shows the implementation of a date converter that converts the date value passed in so that it only shows the year, the month, and the day.</span></span> <span data-ttu-id="6dd87-107">Al implementar el <xref:System.Windows.Data.IValueConverter> interfaz, es una buena práctica para decorar la implementación con un <xref:System.Windows.Data.ValueConversionAttribute> atributo para indicar al desarrollo de herramientas de los tipos de datos implicados en la conversión, como en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="6dd87-107">When implementing the <xref:System.Windows.Data.IValueConverter> interface, it is a good practice to decorate the implementation with a <xref:System.Windows.Data.ValueConversionAttribute> attribute to indicate to development tools the data types involved in the conversion, as in the following example:</span></span>  
  
 [!code-csharp[DataBindingLab#18](~/samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/DateConverter.cs#18)]
 [!code-vb[DataBindingLab#18](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DataBindingLab/VisualBasic/DateConverter.vb#18)]  
  
 <span data-ttu-id="6dd87-108">Una vez haya creado un convertidor, puede agregarlo como un recurso en su [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] archivo.</span><span class="sxs-lookup"><span data-stu-id="6dd87-108">Once you have created a converter, you can add it as a resource in your [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] file.</span></span> <span data-ttu-id="6dd87-109">En el ejemplo siguiente, *src* se asigna al espacio de nombres en el que *DateConverter* está definido.</span><span class="sxs-lookup"><span data-stu-id="6dd87-109">In the following example, *src* maps to the namespace in which *DateConverter* is defined.</span></span>  
  
 [!code-xaml[DataBindingLab#15](~/samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/DataBindingLabApp.xaml#15)]  
  
 <span data-ttu-id="6dd87-110">Por último, puede utilizar el convertidor en el enlace mediante la sintaxis siguiente.</span><span class="sxs-lookup"><span data-stu-id="6dd87-110">Finally, you can use the converter in your binding using the following syntax.</span></span> <span data-ttu-id="6dd87-111">En el ejemplo siguiente, el contenido de texto el <xref:System.Windows.Controls.TextBlock> está enlazado a *StartDate*, que es una propiedad de origen de datos externo.</span><span class="sxs-lookup"><span data-stu-id="6dd87-111">In the following example, the text content of the <xref:System.Windows.Controls.TextBlock> is bound to *StartDate*, which is a property of an external data source.</span></span>  
  
 [!code-xaml[DataBindingLab#17](~/samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/DataBindingLabApp.xaml#17)]  
  
 <span data-ttu-id="6dd87-112">Los recursos de estilo que se hace referencia en el ejemplo anterior se definen en una sección de recursos que no se muestra en este tema.</span><span class="sxs-lookup"><span data-stu-id="6dd87-112">The style resources referenced in the above example are defined in a resource section not shown in this topic.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6dd87-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="6dd87-113">See also</span></span>

- [<span data-ttu-id="6dd87-114">Implementar la validación de enlaces</span><span class="sxs-lookup"><span data-stu-id="6dd87-114">Implement Binding Validation</span></span>](how-to-implement-binding-validation.md)
- [<span data-ttu-id="6dd87-115">Información general sobre el enlace de datos</span><span class="sxs-lookup"><span data-stu-id="6dd87-115">Data Binding Overview</span></span>](data-binding-overview.md)
- [<span data-ttu-id="6dd87-116">Temas "Cómo..."</span><span class="sxs-lookup"><span data-stu-id="6dd87-116">How-to Topics</span></span>](data-binding-how-to-topics.md)
