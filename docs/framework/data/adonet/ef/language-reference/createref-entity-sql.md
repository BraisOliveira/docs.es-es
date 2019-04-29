---
title: CREATEREF (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 489828cf-a335-4449-9360-b0d92eec5481
ms.openlocfilehash: 6ae4712fb280418ad8cf17cd68a7bbcd9cf3b8a9
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61785286"
---
# <a name="createref-entity-sql"></a><span data-ttu-id="e2113-102">CREATEREF (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="e2113-102">CREATEREF (Entity SQL)</span></span>
<span data-ttu-id="e2113-103">Crea referencias a una entidad en un elemento entityset.</span><span class="sxs-lookup"><span data-stu-id="e2113-103">Fabricates references to an entity in an entityset.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e2113-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e2113-104">Syntax</span></span>  
  
```  
CreateRef(entityset_identifier, row_typed_expression)  
```  
  
## <a name="arguments"></a><span data-ttu-id="e2113-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="e2113-105">Arguments</span></span>  
 `entityset_identifier`  
 <span data-ttu-id="e2113-106">Identificador de entityset, no un literal de cadena.</span><span class="sxs-lookup"><span data-stu-id="e2113-106">The entityset identifier, not a string literal.</span></span>  
  
 `row_typed_expression`  
 <span data-ttu-id="e2113-107">Expresión escrita por fila que corresponde a las propiedades de clave del tipo de entidad.</span><span class="sxs-lookup"><span data-stu-id="e2113-107">A row-typed expression that corresponds to the key properties of the entity type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e2113-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e2113-108">Remarks</span></span>  
 <span data-ttu-id="e2113-109">`row_typed_expression` debe ser estructuralmente equivalentes al tipo de clave de la entidad.</span><span class="sxs-lookup"><span data-stu-id="e2113-109">`row_typed_expression` must be structurally equivalent to the key type for the entity.</span></span> <span data-ttu-id="e2113-110">Es decir, debe tener el mismo número y los mismos tipos de campos en el mismo orden que las claves de entidad.</span><span class="sxs-lookup"><span data-stu-id="e2113-110">That is, it must have the same number and types of fields in the same order as the entity keys.</span></span>  
  
 <span data-ttu-id="e2113-111">En el ejemplo siguiente, Orders y BadOrders son ambos elementos entityset de tipo Order y se supone que Id es la propiedad de clave única de Order.</span><span class="sxs-lookup"><span data-stu-id="e2113-111">In the example below, Orders and BadOrders are both entitysets of type Order, and Id is assumed to be the single key property of Order.</span></span> <span data-ttu-id="e2113-112">El ejemplo muestra cómo se puede generar una referencia a una entidad en BadOrders.</span><span class="sxs-lookup"><span data-stu-id="e2113-112">The example illustrates how we may produce a reference to an entity in BadOrders.</span></span> <span data-ttu-id="e2113-113">Observe que la referencia puede estar pendiente.</span><span class="sxs-lookup"><span data-stu-id="e2113-113">Note that the reference may be dangling.</span></span>  <span data-ttu-id="e2113-114">Es decir, la referencia puede no identificar realmente una entidad concreta.</span><span class="sxs-lookup"><span data-stu-id="e2113-114">That is, the reference may not actually identify a specific entity.</span></span> <span data-ttu-id="e2113-115">En esos casos, una operación `DEREF` en esa referencia devuelve un valor NULL.</span><span class="sxs-lookup"><span data-stu-id="e2113-115">In those cases, a `DEREF` operation on that reference returns a null.</span></span>  
  
```  
select CreateRef(LOB.BadOrders, row(o.Id))   
from LOB.Orders as o   
```  
  
## <a name="example"></a><span data-ttu-id="e2113-116">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e2113-116">Example</span></span>  
 <span data-ttu-id="e2113-117">La consulta de Entity SQL siguiente utiliza el operador CREATEREF para crear las referencias a una entidad en un conjunto de entidades.</span><span class="sxs-lookup"><span data-stu-id="e2113-117">The following Entity SQL query uses the CREATEREF operator to fabricate references to an entity in an entity set.</span></span> <span data-ttu-id="e2113-118">La consulta se basa en el modelo AdventureWorks Sales.</span><span class="sxs-lookup"><span data-stu-id="e2113-118">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="e2113-119">Para compilar y ejecutar esta consulta, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="e2113-119">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="e2113-120">Siga el procedimiento de [Cómo: Ejecutar una consulta que devuelve resultados StructuralType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="e2113-120">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="e2113-121">Pase la consulta siguiente como argumento al método `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="e2113-121">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#CREATEREF](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#createref)]  
  
## <a name="see-also"></a><span data-ttu-id="e2113-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="e2113-122">See also</span></span>

- [<span data-ttu-id="e2113-123">Referencia de Entity SQL</span><span class="sxs-lookup"><span data-stu-id="e2113-123">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
- [<span data-ttu-id="e2113-124">DEREF</span><span class="sxs-lookup"><span data-stu-id="e2113-124">DEREF</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/deref-entity-sql.md)
- [<span data-ttu-id="e2113-125">KEY</span><span class="sxs-lookup"><span data-stu-id="e2113-125">KEY</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/key-entity-sql.md)
- [<span data-ttu-id="e2113-126">REF</span><span class="sxs-lookup"><span data-stu-id="e2113-126">REF</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/ref-entity-sql.md)
