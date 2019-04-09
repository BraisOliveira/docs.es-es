---
title: THEN (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 54222642-23c6-4f61-9861-67caca53ac5f
ms.openlocfilehash: d5f9f2b8c9d7397cbcd91fa52a95544fc66e4dce
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59184602"
---
# <a name="then-entity-sql"></a><span data-ttu-id="38989-102">THEN (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="38989-102">THEN (Entity SQL)</span></span>
<span data-ttu-id="38989-103">El resultado de una cláusula WHEN cuando se evalúa como `true`.</span><span class="sxs-lookup"><span data-stu-id="38989-103">The result of a WHEN clause when it evaluates to `true`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="38989-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="38989-104">Syntax</span></span>  
  
```  
WHEN when_expression THEN then_expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="38989-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="38989-105">Arguments</span></span>  
 `when_expression`  
 <span data-ttu-id="38989-106">Cualquier expresión Boolean válida.</span><span class="sxs-lookup"><span data-stu-id="38989-106">Any valid Boolean expression.</span></span>  
  
 `then_expression`  
 <span data-ttu-id="38989-107">Expresión de consulta válida que devuelve una colección.</span><span class="sxs-lookup"><span data-stu-id="38989-107">Any valid query expression that returns a collection.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="38989-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="38989-108">Remarks</span></span>  
 <span data-ttu-id="38989-109">Si `when_expression` se evalúa como el valor `true`, el resultado es la `then-expression`correspondiente.</span><span class="sxs-lookup"><span data-stu-id="38989-109">If `when_expression` evaluates to the value `true`, the result is the corresponding `then-expression`.</span></span> <span data-ttu-id="38989-110">Si no se cumple ninguna de las condiciones WHEN, se evalúa `else-expression` .</span><span class="sxs-lookup"><span data-stu-id="38989-110">If none of the WHEN conditions are satisfied, the `else-expression` is evaluated.</span></span> <span data-ttu-id="38989-111">Sin embargo, si no hay ninguna `else-expression`, el resultado es Null.</span><span class="sxs-lookup"><span data-stu-id="38989-111">However, if there is no `else-expression`, the result is null.</span></span>  
  
 <span data-ttu-id="38989-112">Para obtener un ejemplo, vea [caso](../../../../../../docs/framework/data/adonet/ef/language-reference/case-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="38989-112">For an example, see [CASE](../../../../../../docs/framework/data/adonet/ef/language-reference/case-entity-sql.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="38989-113">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="38989-113">Example</span></span>  
 <span data-ttu-id="38989-114">La siguiente consulta de Entity SQL usa la expresión CASE para evaluar un conjunto de expresiones `Boolean` .</span><span class="sxs-lookup"><span data-stu-id="38989-114">The following Entity SQL query uses the CASE expression to evaluate a set of `Boolean` expressions.</span></span> <span data-ttu-id="38989-115">La consulta se basa en el modelo AdventureWorks Sales.</span><span class="sxs-lookup"><span data-stu-id="38989-115">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="38989-116">Para compilar y ejecutar esta consulta, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="38989-116">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="38989-117">Siga el procedimiento de [Cómo: Ejecutar una consulta que devuelve resultados PrimitiveType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md).</span><span class="sxs-lookup"><span data-stu-id="38989-117">Follow the procedure in [How to: Execute a Query that Returns PrimitiveType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md).</span></span>  
  
2.  <span data-ttu-id="38989-118">Pase la consulta siguiente como argumento al método `ExecutePrimitiveTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="38989-118">Pass the following query as an argument to the `ExecutePrimitiveTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#CASE_WHEN_THEN_ELSE](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#case_when_then_else)]  
  
## <a name="see-also"></a><span data-ttu-id="38989-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="38989-119">See also</span></span>

- [<span data-ttu-id="38989-120">CASE</span><span class="sxs-lookup"><span data-stu-id="38989-120">CASE</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/case-entity-sql.md)
- [<span data-ttu-id="38989-121">Referencia de Entity SQL</span><span class="sxs-lookup"><span data-stu-id="38989-121">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
