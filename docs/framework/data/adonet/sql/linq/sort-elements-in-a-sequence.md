---
title: Ordenar los elementos de una secuencia
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d59b93a9-50c8-4770-a114-d902f6a0ea76
ms.openlocfilehash: 21fa2f9e1dc2f255fe94f2420ba90a809ab5b05e
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70792665"
---
# <a name="sort-elements-in-a-sequence"></a><span data-ttu-id="edbd2-102">Ordenar los elementos de una secuencia</span><span class="sxs-lookup"><span data-stu-id="edbd2-102">Sort Elements in a Sequence</span></span>
<span data-ttu-id="edbd2-103">Utilice el operador <xref:System.Linq.Enumerable.OrderBy%2A> para ordenar una secuencia según una o más claves.</span><span class="sxs-lookup"><span data-stu-id="edbd2-103">Use the <xref:System.Linq.Enumerable.OrderBy%2A> operator to sort a sequence according to one or more keys.</span></span>  
  
> [!NOTE]
> [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="edbd2-104">está diseñado para admitir la ordenación por tipos primitivos simples `string`, `int`como,, etc.</span><span class="sxs-lookup"><span data-stu-id="edbd2-104">is designed to support ordering by simple primitive types, such as `string`, `int`, and so on.</span></span> <span data-ttu-id="edbd2-105">No admite la ordenación de clases complejas con valores múltiples, como los tipos anónimos.</span><span class="sxs-lookup"><span data-stu-id="edbd2-105">It does not support ordering for complex multi-valued classes, such as anonymous types.</span></span> <span data-ttu-id="edbd2-106">Tampoco admite los tipos de datos `byte`.</span><span class="sxs-lookup"><span data-stu-id="edbd2-106">It also does not support `byte` datatypes.</span></span>  
  
## <a name="example"></a><span data-ttu-id="edbd2-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="edbd2-107">Example</span></span>  
 <span data-ttu-id="edbd2-108">En el ejemplo siguiente se ordena `Employees` por fecha de contratación.</span><span class="sxs-lookup"><span data-stu-id="edbd2-108">The following example sorts `Employees` by date of hire.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#20](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#20)]
 [!code-vb[DLinqQueryExamples#20](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#20)]  
  
## <a name="example"></a><span data-ttu-id="edbd2-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="edbd2-109">Example</span></span>  
 <span data-ttu-id="edbd2-110">En el ejemplo siguiente se utiliza `where` para ordenar los `Orders` distribuidos a `London` por flete.</span><span class="sxs-lookup"><span data-stu-id="edbd2-110">The following example uses `where` to sort `Orders` shipped to `London` by freight.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#21](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#21)]
 [!code-vb[DLinqQueryExamples#21](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#21)]  
  
## <a name="example"></a><span data-ttu-id="edbd2-111">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="edbd2-111">Example</span></span>  
 <span data-ttu-id="edbd2-112">En el ejemplo siguiente se ordenan los `Products` por precio unitario, de mayor a menor.</span><span class="sxs-lookup"><span data-stu-id="edbd2-112">The following example sorts `Products` by unit price from highest to lowest.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#22](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#22)]
 [!code-vb[DLinqQueryExamples#22](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#22)]  
  
## <a name="example"></a><span data-ttu-id="edbd2-113">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="edbd2-113">Example</span></span>  
 <span data-ttu-id="edbd2-114">En el ejemplo siguiente se utiliza una cláusula `OrderBy` compuesta para ordenar los `Customers` por ciudad y, después, por nombre de contacto.</span><span class="sxs-lookup"><span data-stu-id="edbd2-114">The following example uses a compound `OrderBy` to sort `Customers` by city and then by contact name.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#24](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#24)]
 [!code-vb[DLinqQueryExamples#24](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#24)]  
  
## <a name="example"></a><span data-ttu-id="edbd2-115">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="edbd2-115">Example</span></span>  
 <span data-ttu-id="edbd2-116">En el ejemplo siguiente se ordenan `ShipCountry`los pedidos de `EmployeeID 1` por y, a continuación, de mayor a menor.</span><span class="sxs-lookup"><span data-stu-id="edbd2-116">The following example sorts Orders from `EmployeeID 1` by `ShipCountry`, and then by highest to lowest freight.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#25](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#25)]
 [!code-vb[DLinqQueryExamples#25](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#25)]  
  
## <a name="example"></a><span data-ttu-id="edbd2-117">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="edbd2-117">Example</span></span>  
 <span data-ttu-id="edbd2-118">En el ejemplo siguiente se combinan los operadores <xref:System.Linq.Enumerable.OrderBy%2A>, <xref:System.Linq.Enumerable.Max%2A> y <xref:System.Linq.Enumerable.GroupBy%2A> para buscar los `Products` que tienen el precio unitario más alto en cada categoría y, después, se ordena el grupo por identificador de categoría.</span><span class="sxs-lookup"><span data-stu-id="edbd2-118">The following example combines <xref:System.Linq.Enumerable.OrderBy%2A>, <xref:System.Linq.Enumerable.Max%2A>, and <xref:System.Linq.Enumerable.GroupBy%2A> operators to find the `Products` that have the highest unit price in each category, and then sorts the group by category id.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#26](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#26)]
 [!code-vb[DLinqQueryExamples#26](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#26)]  
  
 <span data-ttu-id="edbd2-119">Si ejecuta la consulta anterior en la base de datos de ejemplo Northwind, los resultados se parecerán a los siguientes:</span><span class="sxs-lookup"><span data-stu-id="edbd2-119">If you run the previous query against the Northwind sample database, the results will resemble the following:</span></span>  
  
 `1`  
  
 `Côte de Blaye`  
  
 `2`  
  
 `Vegie-spread`  
  
 `3`  
  
 `Sir Rodney's Marmalade`  
  
 `4`  
  
 `Raclette Courdavault`  
  
 `5`  
  
 `Gnocchi di nonna Alice`  
  
 `6`  
  
 `Thüringer Rostbratwurst`  
  
 `7`  
  
 `Manjimup Dried Apples`  
  
 `8`  
  
 `Carnarvon Tigers`  
  
## <a name="see-also"></a><span data-ttu-id="edbd2-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="edbd2-120">See also</span></span>

- [<span data-ttu-id="edbd2-121">Ejemplos de consultas</span><span class="sxs-lookup"><span data-stu-id="edbd2-121">Query Examples</span></span>](query-examples.md)
- [<span data-ttu-id="edbd2-122">Descargar bases de datos de ejemplo</span><span class="sxs-lookup"><span data-stu-id="edbd2-122">Downloading Sample Databases</span></span>](downloading-sample-databases.md)
