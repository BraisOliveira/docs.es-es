---
title: INTERSECT (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 93c6fe33-f341-4b52-911e-adf503891951
ms.openlocfilehash: 85b0abb03161b2df0cfc4ddf6cafc92fb7de9d95
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61780385"
---
# <a name="intersect-entity-sql"></a><span data-ttu-id="69b33-102">INTERSECT (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="69b33-102">INTERSECT (Entity SQL)</span></span>
<span data-ttu-id="69b33-103">Devuelve una colección de los valores distintos que devuelven las expresiones de consulta situadas a los lados izquierdo y derecho del operando INTERSECT.</span><span class="sxs-lookup"><span data-stu-id="69b33-103">Returns a collection of any distinct values that are returned by both the query expressions on the left and right sides of the INTERSECT operand.</span></span> <span data-ttu-id="69b33-104">Todas las expresiones deben ser del mismo tipo que `expression`o de un tipo base común o derivado.</span><span class="sxs-lookup"><span data-stu-id="69b33-104">All expressions must be of the same type or of a common base or derived type as `expression`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="69b33-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="69b33-105">Syntax</span></span>  
  
```  
expression INTERSECT expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="69b33-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="69b33-106">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="69b33-107">Cualquier expresión de consulta válida que devuelva una colección para comparar con la colección que devuelve otra expresión de consulta.</span><span class="sxs-lookup"><span data-stu-id="69b33-107">Any valid query expression that returns a collection to compare with the collection returned from another query expression.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="69b33-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="69b33-108">Return Value</span></span>  
 <span data-ttu-id="69b33-109">Colección del mismo tipo que `expression`o de un tipo base común o derivado.</span><span class="sxs-lookup"><span data-stu-id="69b33-109">A collection of the same type or of a common base or derived type as `expression`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="69b33-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="69b33-110">Remarks</span></span>  
 <span data-ttu-id="69b33-111">INTERSECT es uno de los operadores de conjuntos de [!INCLUDE[esql](../../../../../../includes/esql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="69b33-111">INTERSECT is one of the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators.</span></span> <span data-ttu-id="69b33-112">Todos los operadores de conjuntos de [!INCLUDE[esql](../../../../../../includes/esql-md.md)] se evalúan de izquierda a derecha.</span><span class="sxs-lookup"><span data-stu-id="69b33-112">All [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators are evaluated from left to right.</span></span> <span data-ttu-id="69b33-113">Para obtener información de prioridad para la [!INCLUDE[esql](../../../../../../includes/esql-md.md)] operadores de conjuntos, vea [EXCEPT](../../../../../../docs/framework/data/adonet/ef/language-reference/except-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="69b33-113">For precedence information for the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators, see [EXCEPT](../../../../../../docs/framework/data/adonet/ef/language-reference/except-entity-sql.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="69b33-114">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="69b33-114">Example</span></span>  
 <span data-ttu-id="69b33-115">La siguiente consulta de Entity SQL usa el operador INTERSECT para devolver una colección de los valores distintos que devuelven las expresiones de consulta situadas a los lados izquierdo y derecho del operando INTERSECT.</span><span class="sxs-lookup"><span data-stu-id="69b33-115">The following Entity SQL query uses the INTERSECT operator to return a collection of any distinct values that are returned by both the query expressions on the left and right sides of the INTERSECT operand.</span></span> <span data-ttu-id="69b33-116">La consulta se basa en el modelo AdventureWorks Sales.</span><span class="sxs-lookup"><span data-stu-id="69b33-116">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="69b33-117">Para compilar y ejecutar esta consulta, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="69b33-117">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="69b33-118">Siga el procedimiento de [Cómo: Ejecutar una consulta que devuelve resultados StructuralType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="69b33-118">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="69b33-119">Pase la consulta siguiente como argumento al método `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="69b33-119">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#INTERSECT](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#intersect)]  
  
## <a name="see-also"></a><span data-ttu-id="69b33-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="69b33-120">See also</span></span>

- [<span data-ttu-id="69b33-121">Referencia de Entity SQL</span><span class="sxs-lookup"><span data-stu-id="69b33-121">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
