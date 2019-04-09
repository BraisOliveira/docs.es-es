---
title: EXCEPT (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 69cc23e5-3f8f-4b49-b20e-2f84ff11c80d
ms.openlocfilehash: 32c8c418056231e98696eb8f4e9cb372d6c5740c
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59089463"
---
# <a name="except-entity-sql"></a><span data-ttu-id="1ca35-102">EXCEPT (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="1ca35-102">EXCEPT (Entity SQL)</span></span>
<span data-ttu-id="1ca35-103">Devuelve una colección de los valores distintos de la expresión de consulta situada a la izquierda del operando EXCEPT, que tampoco se devuelven en la expresión de consulta situada a la derecha del operando EXCEPT.</span><span class="sxs-lookup"><span data-stu-id="1ca35-103">Returns a collection of any distinct values from the query expression to the left of the EXCEPT operand that are not also returned from the query expression to the right of the EXCEPT operand.</span></span> <span data-ttu-id="1ca35-104">Todas las expresiones deben ser del mismo tipo que `expression`o de un tipo base común o derivado.</span><span class="sxs-lookup"><span data-stu-id="1ca35-104">All expressions must be of the same type or of a common base or derived type as `expression`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1ca35-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1ca35-105">Syntax</span></span>  
  
```  
expression EXCEPT expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="1ca35-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="1ca35-106">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="1ca35-107">Cualquier expresión de consulta válida que devuelva una colección para comparar con la colección que devuelve otra expresión de consulta.</span><span class="sxs-lookup"><span data-stu-id="1ca35-107">Any valid query expression that returns a collection to compare with the collection returned from another query expression.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1ca35-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="1ca35-108">Return Value</span></span>  
 <span data-ttu-id="1ca35-109">Colección del mismo tipo que `expression`o de un tipo base común o derivado.</span><span class="sxs-lookup"><span data-stu-id="1ca35-109">A collection of the same type or of a common base or derived type as `expression`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1ca35-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="1ca35-110">Remarks</span></span>  
 <span data-ttu-id="1ca35-111">EXCEPT es uno de los operadores de conjuntos de [!INCLUDE[esql](../../../../../../includes/esql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1ca35-111">EXCEPT is one of the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators.</span></span> <span data-ttu-id="1ca35-112">Todos los operadores de conjuntos de [!INCLUDE[esql](../../../../../../includes/esql-md.md)] se evalúan de izquierda a derecha.</span><span class="sxs-lookup"><span data-stu-id="1ca35-112">All [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators are evaluated from left to right.</span></span> <span data-ttu-id="1ca35-113">En la tabla siguiente se muestra la prioridad de los operadores de conjuntos de [!INCLUDE[esql](../../../../../../includes/esql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1ca35-113">The following table shows the precedence of the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators.</span></span>  
  
|<span data-ttu-id="1ca35-114">Precedencia</span><span class="sxs-lookup"><span data-stu-id="1ca35-114">Precedence</span></span>|<span data-ttu-id="1ca35-115">Operadores</span><span class="sxs-lookup"><span data-stu-id="1ca35-115">Operators</span></span>|  
|----------------|---------------|  
|<span data-ttu-id="1ca35-116">Máxima</span><span class="sxs-lookup"><span data-stu-id="1ca35-116">Highest</span></span>|<span data-ttu-id="1ca35-117">INTERSECT</span><span class="sxs-lookup"><span data-stu-id="1ca35-117">INTERSECT</span></span>|  
||<span data-ttu-id="1ca35-118">UNION</span><span class="sxs-lookup"><span data-stu-id="1ca35-118">UNION</span></span><br /><br /> <span data-ttu-id="1ca35-119">UNION ALL</span><span class="sxs-lookup"><span data-stu-id="1ca35-119">UNION ALL</span></span>|  
||<span data-ttu-id="1ca35-120">EXCEPT</span><span class="sxs-lookup"><span data-stu-id="1ca35-120">EXCEPT</span></span>|  
|<span data-ttu-id="1ca35-121">Mínima</span><span class="sxs-lookup"><span data-stu-id="1ca35-121">Lowest</span></span>|<span data-ttu-id="1ca35-122">EXISTS</span><span class="sxs-lookup"><span data-stu-id="1ca35-122">EXISTS</span></span><br /><br /> <span data-ttu-id="1ca35-123">OVERLAPS</span><span class="sxs-lookup"><span data-stu-id="1ca35-123">OVERLAPS</span></span><br /><br /> <span data-ttu-id="1ca35-124">FLATTEN</span><span class="sxs-lookup"><span data-stu-id="1ca35-124">FLATTEN</span></span><br /><br /> <span data-ttu-id="1ca35-125">SET</span><span class="sxs-lookup"><span data-stu-id="1ca35-125">SET</span></span>|  
  
## <a name="example"></a><span data-ttu-id="1ca35-126">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="1ca35-126">Example</span></span>  
 <span data-ttu-id="1ca35-127">La siguiente consulta de Entity SQL usa el operador EXCEPT para devolver una colección de valores distintos de dos expresiones de consulta.</span><span class="sxs-lookup"><span data-stu-id="1ca35-127">The following Entity SQL query uses the EXCEPT operator to return a collection of any distinct values from two query expressions.</span></span> <span data-ttu-id="1ca35-128">La consulta se basa en el modelo AdventureWorks Sales.</span><span class="sxs-lookup"><span data-stu-id="1ca35-128">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="1ca35-129">Para compilar y ejecutar esta consulta, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="1ca35-129">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="1ca35-130">Siga el procedimiento de [Cómo: Ejecutar una consulta que devuelve resultados StructuralType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="1ca35-130">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2.  <span data-ttu-id="1ca35-131">Pase la consulta siguiente como argumento al método `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="1ca35-131">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#EXCEPT](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#except)]  
  
## <a name="see-also"></a><span data-ttu-id="1ca35-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="1ca35-132">See also</span></span>

- [<span data-ttu-id="1ca35-133">Referencia de Entity SQL</span><span class="sxs-lookup"><span data-stu-id="1ca35-133">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
