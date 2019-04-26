---
title: Agrupar elementos de una secuencia
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 1d50c8b4-f550-4775-bbb6-eab6e874cb43
ms.openlocfilehash: 5d812ae9b5fd0a796588d3366b8546ef84c982c3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61877362"
---
# <a name="group-elements-in-a-sequence"></a><span data-ttu-id="c09e9-102">Agrupar elementos de una secuencia</span><span class="sxs-lookup"><span data-stu-id="c09e9-102">Group Elements in a Sequence</span></span>
<span data-ttu-id="c09e9-103">El operador <xref:System.Linq.Enumerable.GroupBy%2A> agrupa los elementos de una secuencia.</span><span class="sxs-lookup"><span data-stu-id="c09e9-103">The <xref:System.Linq.Enumerable.GroupBy%2A> operator groups the elements of a sequence.</span></span> <span data-ttu-id="c09e9-104">En los ejemplos siguientes se utiliza la base de datos Northwind.</span><span class="sxs-lookup"><span data-stu-id="c09e9-104">The following examples use the Northwind database.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c09e9-105">Los valores de columna nulos de las consultas <xref:System.Linq.Enumerable.GroupBy%2A> a veces pueden iniciar <xref:System.InvalidOperationException>.</span><span class="sxs-lookup"><span data-stu-id="c09e9-105">Null column values in <xref:System.Linq.Enumerable.GroupBy%2A> queries can sometimes throw an <xref:System.InvalidOperationException>.</span></span> <span data-ttu-id="c09e9-106">Para obtener más información, vea la sección "GroupBy InvalidOperationException" de [Troubleshooting](../../../../../../docs/framework/data/adonet/sql/linq/troubleshooting.md).</span><span class="sxs-lookup"><span data-stu-id="c09e9-106">For more information, see the "GroupBy InvalidOperationException" section of [Troubleshooting](../../../../../../docs/framework/data/adonet/sql/linq/troubleshooting.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="c09e9-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c09e9-107">Example</span></span>  
 <span data-ttu-id="c09e9-108">En el ejemplo siguiente se crea una partición de `Products` por `CategoryID`.</span><span class="sxs-lookup"><span data-stu-id="c09e9-108">The following example partitions `Products` by `CategoryID`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#27](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#27)]
 [!code-vb[DLinqQueryExamples#27](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#27)]  
  
## <a name="example"></a><span data-ttu-id="c09e9-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c09e9-109">Example</span></span>  
 <span data-ttu-id="c09e9-110">En el ejemplo siguiente se utiliza <xref:System.Linq.Enumerable.Max%2A> para buscar el precio unitario máximo para cada `CategoryID`.</span><span class="sxs-lookup"><span data-stu-id="c09e9-110">The following example uses <xref:System.Linq.Enumerable.Max%2A> to find the maximum unit price for each `CategoryID`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#28](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#28)]
 [!code-vb[DLinqQueryExamples#28](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#28)]  
  
## <a name="example"></a><span data-ttu-id="c09e9-111">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c09e9-111">Example</span></span>  
 <span data-ttu-id="c09e9-112">En el ejemplo siguiente se utiliza Average para buscar el `UnitPrice` promedio para cada `CategoryID`.</span><span class="sxs-lookup"><span data-stu-id="c09e9-112">The following example uses Average to find the average `UnitPrice` for each `CategoryID`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#29](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#29)]
 [!code-vb[DLinqQueryExamples#29](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#29)]  
  
## <a name="example"></a><span data-ttu-id="c09e9-113">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c09e9-113">Example</span></span>  
 <span data-ttu-id="c09e9-114">En el ejemplo siguiente se usa <xref:System.Linq.Queryable.Sum%2A> para buscar el `UnitPrice` total para cada `CategoryID`.</span><span class="sxs-lookup"><span data-stu-id="c09e9-114">The following example uses <xref:System.Linq.Queryable.Sum%2A> to find the total `UnitPrice` for each `CategoryID`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#30](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#30)]
 [!code-vb[DLinqQueryExamples#30](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#30)]  
  
## <a name="example"></a><span data-ttu-id="c09e9-115">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c09e9-115">Example</span></span>  
 <span data-ttu-id="c09e9-116">En el ejemplo siguiente se utiliza <xref:System.Linq.Queryable.Count%2A> para buscar el número de `Products` que ya no se fabrican en cada `CategoryID`.</span><span class="sxs-lookup"><span data-stu-id="c09e9-116">The following example uses <xref:System.Linq.Queryable.Count%2A> to find the number of discontinued `Products` in each `CategoryID`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#31](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#31)]
 [!code-vb[DLinqQueryExamples#31](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#31)]  
  
## <a name="example"></a><span data-ttu-id="c09e9-117">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c09e9-117">Example</span></span>  
 <span data-ttu-id="c09e9-118">En el ejemplo siguiente se utiliza una cláusula `where` posterior para buscar todas las categorías que tienen al menos 10 productos.</span><span class="sxs-lookup"><span data-stu-id="c09e9-118">The following example uses a following `where` clause to find all categories that have at least 10 products.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#32](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#32)]
 [!code-vb[DLinqQueryExamples#32](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#32)]  
  
## <a name="example"></a><span data-ttu-id="c09e9-119">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c09e9-119">Example</span></span>  
 <span data-ttu-id="c09e9-120">En el ejemplo siguiente se agrupan los productos por `CategoryID` y `SupplierID`.</span><span class="sxs-lookup"><span data-stu-id="c09e9-120">The following example groups products by `CategoryID` and `SupplierID`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#33](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#33)]
 [!code-vb[DLinqQueryExamples#33](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#33)]  
  
## <a name="example"></a><span data-ttu-id="c09e9-121">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c09e9-121">Example</span></span>  
 <span data-ttu-id="c09e9-122">En el ejemplo siguiente se devuelven dos secuencias de productos.</span><span class="sxs-lookup"><span data-stu-id="c09e9-122">The following example returns two sequences of products.</span></span> <span data-ttu-id="c09e9-123">La primera secuencia contiene los productos con precio unitario menor o igual que 10.</span><span class="sxs-lookup"><span data-stu-id="c09e9-123">The first sequence contains products with unit price less than or equal to 10.</span></span> <span data-ttu-id="c09e9-124">La segunda secuencia contiene los productos con precio unitario mayor que 10.</span><span class="sxs-lookup"><span data-stu-id="c09e9-124">The second sequence contains products with unit price greater than 10.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#34](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#34)]
 [!code-vb[DLinqQueryExamples#34](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#34)]  
  
## <a name="example"></a><span data-ttu-id="c09e9-125">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c09e9-125">Example</span></span>  
 <span data-ttu-id="c09e9-126">El operador <xref:System.Linq.Queryable.GroupBy%2A> solo acepta un argumento de clave única.</span><span class="sxs-lookup"><span data-stu-id="c09e9-126">The <xref:System.Linq.Queryable.GroupBy%2A> operator can take only a single key argument.</span></span> <span data-ttu-id="c09e9-127">Si necesita agrupar los elementos según más de una clave, debe crear un tipo anónimo, como en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="c09e9-127">If you need to group by more than one key, you must create an anonymous type, as in the following example:</span></span>  
  
 [!code-csharp[DLinqQueryExamples#35](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#35)]
 [!code-vb[DLinqQueryExamples#35](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#35)]  
  
## <a name="see-also"></a><span data-ttu-id="c09e9-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="c09e9-128">See also</span></span>

- [<span data-ttu-id="c09e9-129">Ejemplos de consultas</span><span class="sxs-lookup"><span data-stu-id="c09e9-129">Query Examples</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/query-examples.md)
- [<span data-ttu-id="c09e9-130">Descargar bases de datos de ejemplo</span><span class="sxs-lookup"><span data-stu-id="c09e9-130">Downloading Sample Databases</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md)
