---
title: Filtrar para recuperar muchos objetos a la vez
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 18aff4d8-bde8-461b-9960-ccabb24e9d22
ms.openlocfilehash: dd53c2fd16a82ce0f69a33e0b7d7ffef7815b91b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59220531"
---
# <a name="how-to-retrieve-many-objects-at-once"></a><span data-ttu-id="34a25-102">Filtrar para recuperar muchos objetos a la vez</span><span class="sxs-lookup"><span data-stu-id="34a25-102">How to: Retrieve Many Objects At Once</span></span>
<span data-ttu-id="34a25-103">Puede recuperar muchos objetos en una consulta mediante <xref:System.Data.Linq.DataLoadOptions.LoadWith%2A>.</span><span class="sxs-lookup"><span data-stu-id="34a25-103">You can retrieve many objects in one query by using <xref:System.Data.Linq.DataLoadOptions.LoadWith%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="34a25-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="34a25-104">Example</span></span>  
 <span data-ttu-id="34a25-105">El código siguiente utiliza el método <xref:System.Data.Linq.DataLoadOptions.LoadWith%2A> para recuperar los objetos `Customer` y `Order`.</span><span class="sxs-lookup"><span data-stu-id="34a25-105">The following code uses the <xref:System.Data.Linq.DataLoadOptions.LoadWith%2A> method to retrieve both `Customer` and `Order` objects.</span></span>  
  
 [!code-csharp[DLinqQueryConcepts#9](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryConcepts/cs/Program.cs#9)]
 [!code-vb[DLinqQueryConcepts#9](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryConcepts/vb/Module1.vb#9)]  
  
## <a name="see-also"></a><span data-ttu-id="34a25-106">Vea también</span><span class="sxs-lookup"><span data-stu-id="34a25-106">See also</span></span>

- [<span data-ttu-id="34a25-107">Conceptos sobre consultas</span><span class="sxs-lookup"><span data-stu-id="34a25-107">Query Concepts</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/query-concepts.md)
