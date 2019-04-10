---
title: IN (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 51662950-ee01-4857-b7b9-311dd8515966
ms.openlocfilehash: d88f79dbfcd27f0ca0d1e26815d7d2bbee731bcf
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/09/2019
ms.locfileid: "59331278"
---
# <a name="in-entity-sql"></a><span data-ttu-id="eca2e-102">IN (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="eca2e-102">IN (Entity SQL)</span></span>
<span data-ttu-id="eca2e-103">Determina si un valor determinado coincide con algún valor de una colección.</span><span class="sxs-lookup"><span data-stu-id="eca2e-103">Determines whether a value matches any value in a collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eca2e-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="eca2e-104">Syntax</span></span>  
  
```  
value [ NOT ] IN expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="eca2e-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="eca2e-105">Arguments</span></span>  
 `value`  
 <span data-ttu-id="eca2e-106">Expresión válida que devuelve el valor que hay que buscar.</span><span class="sxs-lookup"><span data-stu-id="eca2e-106">Any valid expression that returns the value to match.</span></span>  
  
 <span data-ttu-id="eca2e-107">[ NOT ]</span><span class="sxs-lookup"><span data-stu-id="eca2e-107">[ NOT ]</span></span>  
 <span data-ttu-id="eca2e-108">Especifica que el resultado `Boolean` de IN se niega.</span><span class="sxs-lookup"><span data-stu-id="eca2e-108">Specifies that the `Boolean` result of IN be negated.</span></span>  
  
 `expression`  
 <span data-ttu-id="eca2e-109">Expresión válida que devuelve la colección en la que hay que buscar una coincidencia.</span><span class="sxs-lookup"><span data-stu-id="eca2e-109">Any valid expression that returns the collection to test for a match.</span></span> <span data-ttu-id="eca2e-110">Todas las expresiones deben ser del mismo tipo que `value`o de un tipo base común o derivado.</span><span class="sxs-lookup"><span data-stu-id="eca2e-110">All expressions must be of the same type or of a common base or derived type as `value`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="eca2e-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="eca2e-111">Return Value</span></span>  
 `true` <span data-ttu-id="eca2e-112">Si el valor se encuentra en la colección; null si el valor es null o la colección es null; en caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="eca2e-112">if the value is found in the collection; null if the value is null or the collection is null; otherwise, `false`.</span></span> <span data-ttu-id="eca2e-113">El uso de NOT IN niega el resultado de IN.</span><span class="sxs-lookup"><span data-stu-id="eca2e-113">Using NOT IN negates the results of IN.</span></span>  
  
## <a name="example"></a><span data-ttu-id="eca2e-114">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="eca2e-114">Example</span></span>  
 <span data-ttu-id="eca2e-115">La siguiente consulta de Entity SQL usa el operador IN para determinar si un valor coincide con algún valor de una colección.</span><span class="sxs-lookup"><span data-stu-id="eca2e-115">The following Entity SQL query uses the IN operator to determine whether a value matches any value in a collection.</span></span> <span data-ttu-id="eca2e-116">La consulta se basa en el modelo AdventureWorks Sales.</span><span class="sxs-lookup"><span data-stu-id="eca2e-116">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="eca2e-117">Para compilar y ejecutar esta consulta, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="eca2e-117">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="eca2e-118">Siga el procedimiento de [Cómo: Ejecutar una consulta que devuelve resultados StructuralType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="eca2e-118">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="eca2e-119">Pase la consulta siguiente como argumento al método `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="eca2e-119">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#IN](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#in)]  
  
## <a name="see-also"></a><span data-ttu-id="eca2e-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="eca2e-120">See also</span></span>

- [<span data-ttu-id="eca2e-121">Referencia de Entity SQL</span><span class="sxs-lookup"><span data-stu-id="eca2e-121">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
