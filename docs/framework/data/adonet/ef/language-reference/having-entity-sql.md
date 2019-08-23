---
title: HAVING (Entity SQL)
ms.date: 03/30/2017
ms.assetid: b5d52d97-8372-4335-beac-2d0b79dc3707
ms.openlocfilehash: 76a63140668fb1f41cf9e6f901d9a43240a1d098
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69936082"
---
# <a name="having-entity-sql"></a><span data-ttu-id="471d4-102">HAVING (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="471d4-102">HAVING (Entity SQL)</span></span>
<span data-ttu-id="471d4-103">Especifica una condición de búsqueda para un grupo o agregado.</span><span class="sxs-lookup"><span data-stu-id="471d4-103">Specifies a search condition for a group or an aggregate.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="471d4-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="471d4-104">Syntax</span></span>  
  
```  
[ HAVING search_condition ]  
```  
  
## <a name="arguments"></a><span data-ttu-id="471d4-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="471d4-105">Arguments</span></span>  
 `search_condition`  
 <span data-ttu-id="471d4-106">Especifica la condición de búsqueda del grupo o del agregado que se debe cumplir.</span><span class="sxs-lookup"><span data-stu-id="471d4-106">Specifies the search condition for the group or the aggregate to meet.</span></span> <span data-ttu-id="471d4-107">Cuando se utiliza HAVING con GROUP BY ALL, la cláusula HAVING invalida ALL.</span><span class="sxs-lookup"><span data-stu-id="471d4-107">When HAVING is used with GROUP BY ALL, the HAVING clause overrides ALL.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="471d4-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="471d4-108">Remarks</span></span>  
 <span data-ttu-id="471d4-109">La cláusula HAVING se utiliza para especificar una condición de filtrado adicional en el resultado de una agrupación.</span><span class="sxs-lookup"><span data-stu-id="471d4-109">The HAVING clause is used to specify an additional filtering condition on the result of a grouping.</span></span> <span data-ttu-id="471d4-110">Si no se especifica una cláusula GROUP BY en la expresión de consulta, se supone un grupo de conjunto único implícito.</span><span class="sxs-lookup"><span data-stu-id="471d4-110">If no GROUP BY clause is specified in the query expression, an implicit single-set group is assumed.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="471d4-111">HAVING solo se puede usar con la instrucción [Select](../../../../../../docs/framework/data/adonet/ef/language-reference/select-entity-sql.md) .</span><span class="sxs-lookup"><span data-stu-id="471d4-111">HAVING can be used only with the [SELECT](../../../../../../docs/framework/data/adonet/ef/language-reference/select-entity-sql.md) statement.</span></span> <span data-ttu-id="471d4-112">Cuando no se usa [Group by](../../../../../../docs/framework/data/adonet/ef/language-reference/group-by-entity-sql.md) , having se comporta como una cláusula WHERE.</span><span class="sxs-lookup"><span data-stu-id="471d4-112">When [GROUP BY](../../../../../../docs/framework/data/adonet/ef/language-reference/group-by-entity-sql.md) is not used, HAVING behaves like a WHERE clause.</span></span>  
  
 <span data-ttu-id="471d4-113">La cláusula HAVING funciona como la cláusula WHERE salvo que se aplica después de la operación GROUP BY.</span><span class="sxs-lookup"><span data-stu-id="471d4-113">The HAVING clause works like the WHERE clause except that it is applied after the GROUP BY operation.</span></span> <span data-ttu-id="471d4-114">Esto significa que la cláusula HAVING solo puede hacer referencias a agrupar alias y agregados, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="471d4-114">This means that the HAVING clause can only make references to grouping aliases and aggregates, as illustrated in the following example.</span></span>  
  
```  
SELECT Name, SUM(o.Price * o.Quantity) AS Total FROM orderLines AS o GROUP BY o.Product AS Name  
HAVING SUM(o.Quantity) > 1  
```  
  
 <span data-ttu-id="471d4-115">Todo lo anterior hace que se restrinjan los grupos a solo aquellos que incluyen más de un producto.</span><span class="sxs-lookup"><span data-stu-id="471d4-115">The previous restricts the groups to only those that include more than one product.</span></span>  
  
## <a name="example"></a><span data-ttu-id="471d4-116">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="471d4-116">Example</span></span>  
 <span data-ttu-id="471d4-117">La consulta de Entity SQL siguiente utiliza los operadores HAVING y GROUP BY para especificar una condición de búsqueda para un grupo o un agregado.</span><span class="sxs-lookup"><span data-stu-id="471d4-117">The following Entity SQL query uses the HAVING and GROUP BY operators to specify a search condition for a group or an aggregate.</span></span> <span data-ttu-id="471d4-118">La consulta se basa en el modelo AdventureWorks Sales.</span><span class="sxs-lookup"><span data-stu-id="471d4-118">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="471d4-119">Para compilar y ejecutar esta consulta, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="471d4-119">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="471d4-120">Siga el procedimiento descrito [en cómo: Ejecuta una consulta que devuelve resultados](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md)PrimitiveType.</span><span class="sxs-lookup"><span data-stu-id="471d4-120">Follow the procedure in [How to: Execute a Query that Returns PrimitiveType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md).</span></span>  
  
2. <span data-ttu-id="471d4-121">Pase la consulta siguiente como argumento al método `ExecutePrimitiveTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="471d4-121">Pass the following query as an argument to the `ExecutePrimitiveTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#HAVING](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#having)]  
  
## <a name="see-also"></a><span data-ttu-id="471d4-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="471d4-122">See also</span></span>

- [<span data-ttu-id="471d4-123">Referencia de Entity SQL</span><span class="sxs-lookup"><span data-stu-id="471d4-123">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
- [<span data-ttu-id="471d4-124">Expresiones de consulta</span><span class="sxs-lookup"><span data-stu-id="471d4-124">Query Expressions</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/query-expressions-entity-sql.md)
