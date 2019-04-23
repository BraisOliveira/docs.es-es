---
title: 'Ejemplos de sintaxis de expresiones de consulta: Restricción (LINQ to DataSet)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 1daf42c2-c9f4-4cda-b291-7641b9c6d3fe
ms.openlocfilehash: 0c711a2d9edbc3b462048272dd7dd138fd934a89
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59160581"
---
# <a name="query-expression-syntax-examples-restriction-linq-to-dataset"></a><span data-ttu-id="b8e3b-102">Ejemplos de sintaxis de expresiones de consulta: Restricción (LINQ to DataSet)</span><span class="sxs-lookup"><span data-stu-id="b8e3b-102">Query Expression Syntax Examples: Restriction (LINQ to DataSet)</span></span>
<span data-ttu-id="b8e3b-103">Los ejemplos de este tema muestran cómo utilizar el método <xref:System.Linq.Enumerable.Where%2A> para consultar <xref:System.Data.DataSet> utilizando sintaxis de expresión de consultas.</span><span class="sxs-lookup"><span data-stu-id="b8e3b-103">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.Where%2A> method to query a <xref:System.Data.DataSet> using the query expression syntax.</span></span>  
  
 <span data-ttu-id="b8e3b-104">El `FillDataSet` método usado en estos ejemplos se especifica en [cargar datos en un conjunto de datos](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md).</span><span class="sxs-lookup"><span data-stu-id="b8e3b-104">The `FillDataSet` method used in these examples is specified in [Loading Data Into a DataSet](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md).</span></span>  
  
 <span data-ttu-id="b8e3b-105">Los ejemplos de este tema utilizan las tablas Contact, Address, Product, SalesOrderHeader y SalesOrderDetail en la base de datos de ejemplo de AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="b8e3b-105">The examples in this topic use the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="b8e3b-106">Los ejemplos de este tema usan los siguientes `using` / `Imports` instrucciones:</span><span class="sxs-lookup"><span data-stu-id="b8e3b-106">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
[!code-csharp[DP LINQ to DataSetExamples#ImportsUsing](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#importsusing)]        
  
 <span data-ttu-id="b8e3b-107">Para obtener más información, vea [Cómo: Crear un proyecto de LINQ to DataSet en Visual Studio](../../../../docs/framework/data/adonet/how-to-create-a-linq-to-dataset-project-in-vs.md).</span><span class="sxs-lookup"><span data-stu-id="b8e3b-107">For more information, see [How to: Create a LINQ to DataSet Project In Visual Studio](../../../../docs/framework/data/adonet/how-to-create-a-linq-to-dataset-project-in-vs.md).</span></span>  
  
## <a name="where"></a><span data-ttu-id="b8e3b-108">Where</span><span class="sxs-lookup"><span data-stu-id="b8e3b-108">Where</span></span>  
  
### <a name="example"></a><span data-ttu-id="b8e3b-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="b8e3b-109">Example</span></span>  
 <span data-ttu-id="b8e3b-110">Este ejemplo devuelve todos los pedidos en línea.</span><span class="sxs-lookup"><span data-stu-id="b8e3b-110">This example returns all online orders.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#Where1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#where1)]  
 [!code-vb[DP LINQ to DataSet Examples#Where1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#where1)]     
  
### <a name="example"></a><span data-ttu-id="b8e3b-111">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="b8e3b-111">Example</span></span>  
 <span data-ttu-id="b8e3b-112">Este ejemplo devuelve los pedidos en los que la cantidad de pedido es superior a 2 e inferior a 6.</span><span class="sxs-lookup"><span data-stu-id="b8e3b-112">This example returns the orders where the order quantity is greater than 2 and less than 6.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#Where2](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#where2)]  
 [!code-vb[DP LINQ to DataSet Examples#Where2](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#where2)]     
  
### <a name="example"></a><span data-ttu-id="b8e3b-113">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="b8e3b-113">Example</span></span>  
 <span data-ttu-id="b8e3b-114">Este ejemplo devuelve todos los productos de color rojo.</span><span class="sxs-lookup"><span data-stu-id="b8e3b-114">This example returns all red colored products.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#Where3](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#where3)]  
 [!code-vb[DP LINQ to DataSet Examples#Where3](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#where3)]     
  
### <a name="example"></a><span data-ttu-id="b8e3b-115">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="b8e3b-115">Example</span></span>  
 <span data-ttu-id="b8e3b-116">En este ejemplo se utiliza el método <xref:System.Linq.Enumerable.Where%2A> para buscar pedidos efectuados con posterioridad al 1 de diciembre de 2002 y, a continuación, se utiliza el método <xref:System.Data.DataRow.GetChildRows%2A> para obtener los detalles de cada pedido.</span><span class="sxs-lookup"><span data-stu-id="b8e3b-116">This example uses the <xref:System.Linq.Enumerable.Where%2A> method to find orders that were made after December 1, 2002 and then uses the <xref:System.Data.DataRow.GetChildRows%2A> method to get the details for each order.</span></span>  
  
 [!code-csharp[DP LINQ to DataSetExamples#WhereDrillDown](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#wheredrilldown)]       
 [!code-vb[DP LINQ to DataSet Examples#WhereDrillDown](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#wheredrilldown)]  
  
## <a name="see-also"></a><span data-ttu-id="b8e3b-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="b8e3b-117">See also</span></span>

- [<span data-ttu-id="b8e3b-118">Carga de datos en un conjunto de datos</span><span class="sxs-lookup"><span data-stu-id="b8e3b-118">Loading Data Into a DataSet</span></span>](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md)
- [<span data-ttu-id="b8e3b-119">Ejemplos de LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="b8e3b-119">LINQ to DataSet Examples</span></span>](../../../../docs/framework/data/adonet/linq-to-dataset-examples.md)
- <span data-ttu-id="b8e3b-120">[Standard Query Operators Overview (C#)](../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md) (Información general sobre operadores de consulta estándar (C#))</span><span class="sxs-lookup"><span data-stu-id="b8e3b-120">[Standard Query Operators Overview (C#)](../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md)</span></span>
- [<span data-ttu-id="b8e3b-121">Información general sobre operadores de consulta estándar (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b8e3b-121">Standard Query Operators Overview (Visual Basic)</span></span>](../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)
