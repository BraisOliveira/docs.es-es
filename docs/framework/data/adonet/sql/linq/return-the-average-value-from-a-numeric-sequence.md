---
title: Devolver el valor medio de una secuencia numérica
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: ee3b8673-a2e7-4b2d-9b5c-4972ff9e665d
ms.openlocfilehash: 8d6f5f76787c1110e91b245a3dd2425450b4db7e
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70781394"
---
# <a name="return-the-average-value-from-a-numeric-sequence"></a><span data-ttu-id="95b2e-102">Devolver el valor medio de una secuencia numérica</span><span class="sxs-lookup"><span data-stu-id="95b2e-102">Return the Average Value From a Numeric Sequence</span></span>
<span data-ttu-id="95b2e-103">El operador <xref:System.Linq.Enumerable.Average%2A> calcula el promedio de una secuencia de valores numéricos.</span><span class="sxs-lookup"><span data-stu-id="95b2e-103">The <xref:System.Linq.Enumerable.Average%2A> operator computes the average of a sequence of numeric values.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="95b2e-104">La conversión de [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] de valores enteros en `Average` se calcula como un entero, no como double.</span><span class="sxs-lookup"><span data-stu-id="95b2e-104">The [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] translation of `Average` of integer values is computed as an integer, not as a double.</span></span>  
  
## <a name="example"></a><span data-ttu-id="95b2e-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="95b2e-105">Example</span></span>  
 <span data-ttu-id="95b2e-106">En el ejemplo siguiente se devuelve el promedio de los valores `Freight` de la tabla `Orders`.</span><span class="sxs-lookup"><span data-stu-id="95b2e-106">The following example returns the average of `Freight` values in the `Orders` table.</span></span>  
  
 <span data-ttu-id="95b2e-107">Los resultados de la base de datos de ejemplo Northwind serían `78.2442`.</span><span class="sxs-lookup"><span data-stu-id="95b2e-107">Results from the sample Northwind database would be `78.2442`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#1)]
 [!code-vb[DLinqQueryExamples#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#1)]  
  
## <a name="example"></a><span data-ttu-id="95b2e-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="95b2e-108">Example</span></span>  
 <span data-ttu-id="95b2e-109">En el ejemplo siguiente se devuelve el promedio de precio unitario de todos los `Products` de la tabla `Products`.</span><span class="sxs-lookup"><span data-stu-id="95b2e-109">The following example returns the average of the unit price of all `Products` in the `Products` table.</span></span>  
  
 <span data-ttu-id="95b2e-110">Los resultados de la base de datos de ejemplo Northwind serían `28.8663`.</span><span class="sxs-lookup"><span data-stu-id="95b2e-110">Results from the sample Northwind database would be `28.8663`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#2)]
 [!code-vb[DLinqQueryExamples#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#2)]  
  
## <a name="example"></a><span data-ttu-id="95b2e-111">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="95b2e-111">Example</span></span>  
 <span data-ttu-id="95b2e-112">En el ejemplo siguiente se utiliza al operador `Average` para buscar `Products` cuyo precio unitario es más alto que el precio unitario promedio de la categoría a la que pertenece.</span><span class="sxs-lookup"><span data-stu-id="95b2e-112">The following example uses the `Average` operator to find those `Products` whose unit price is higher than the average unit price of the category it belongs to.</span></span> <span data-ttu-id="95b2e-113">A continuación, el ejemplo muestra los resultados en grupos.</span><span class="sxs-lookup"><span data-stu-id="95b2e-113">The example then displays the results in groups.</span></span>  
  
 <span data-ttu-id="95b2e-114">Observe que este ejemplo requiere el uso de la palabra clave `var` en C#, porque el tipo de valor devuelto es anónimo.</span><span class="sxs-lookup"><span data-stu-id="95b2e-114">Note that this example requires the use of the `var` keyword in C#, because the return type is anonymous.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#3)]
 [!code-vb[DLinqQueryExamples#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#3)]  
  
 <span data-ttu-id="95b2e-115">Si ejecuta esta consulta en la base de datos de ejemplo Northwind, los resultados deberían parecerse a los siguientes:</span><span class="sxs-lookup"><span data-stu-id="95b2e-115">If you run this query against the Northwind sample database, the results should resemble of the following:</span></span>  
  
 `1`  
  
 `Côte de Blaye`  
  
 `Ipoh Coffee`  
  
 `2`  
  
 `Grandma's Boysenberry Spread`  
  
 `Northwoods Cranberry Sauce`  
  
 `Sirop d'érable`  
  
 `Vegie-spread`  
  
 `3`  
  
 `Sir Rodney's Marmalade`  
  
 `Gumbär Gummibärchen`  
  
 `Schoggi Schokolade`  
  
 `Tarte au sucre`  
  
 `4`  
  
 `Queso Manchego La Pastora`  
  
 `Mascarpone Fabioli`  
  
 `Raclette Courdavault`  
  
 `Camembert Pierrot`  
  
 `Gudbrandsdalsost`  
  
 `Mozzarella di Giovanni`  
  
 `5`  
  
 `Gustaf's Knäckebröd`  
  
 `Gnocchi di nonna Alice`  
  
 `Wimmers gute Semmelknödel`  
  
 `6`  
  
 `Mishi Kobe Niku`  
  
 `Thüringer Rostbratwurst`  
  
 `7`  
  
 `Rössle Sauerkraut`  
  
 `Manjimup Dried Apples`  
  
 `8`  
  
 `Ikura`  
  
 `Carnarvon Tigers`  
  
 `Nord-Ost Matjeshering`  
  
 `Gravad lax`  
  
## <a name="see-also"></a><span data-ttu-id="95b2e-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="95b2e-116">See also</span></span>

- [<span data-ttu-id="95b2e-117">Consultas de agregado</span><span class="sxs-lookup"><span data-stu-id="95b2e-117">Aggregate Queries</span></span>](aggregate-queries.md)
