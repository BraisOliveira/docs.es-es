---
title: Sistema de tipos (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 818a505b-a196-41dd-aaac-2ccd5f7a2f1a
ms.openlocfilehash: d86c97834b9cc6698da8664ff2a09ceda7cc0043
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64641228"
---
# <a name="type-system-entity-sql"></a><span data-ttu-id="408a5-102">Sistema de tipos (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="408a5-102">Type System (Entity SQL)</span></span>
[!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="408a5-103">admite varios tipos:</span><span class="sxs-lookup"><span data-stu-id="408a5-103">supports a number of types:</span></span>  
  
- <span data-ttu-id="408a5-104">Tipos primitivos (simples), como `Int32` y `String.`.</span><span class="sxs-lookup"><span data-stu-id="408a5-104">Primitive (simple) types such as `Int32` and `String.`</span></span>  
  
- <span data-ttu-id="408a5-105">Tipos nominales que se definen en el esquema, como <xref:System.Data.Metadata.Edm.EntityType>, <xref:System.Data.Metadata.Edm.ComplexType> y <xref:System.Data.Metadata.Edm.RelationshipType>.</span><span class="sxs-lookup"><span data-stu-id="408a5-105">Nominal types that are defined in the schema, such as <xref:System.Data.Metadata.Edm.EntityType>, <xref:System.Data.Metadata.Edm.ComplexType>, and <xref:System.Data.Metadata.Edm.RelationshipType>.</span></span>  
  
- <span data-ttu-id="408a5-106">Tipos anónimos que no se definen explícitamente en el esquema: <xref:System.Data.Metadata.Edm.CollectionType>, <xref:System.Data.Metadata.Edm.RowType> y <xref:System.Data.Metadata.Edm.RefType>.</span><span class="sxs-lookup"><span data-stu-id="408a5-106">Anonymous types that are not defined in the schema explicitly: <xref:System.Data.Metadata.Edm.CollectionType>, <xref:System.Data.Metadata.Edm.RowType>, and <xref:System.Data.Metadata.Edm.RefType>.</span></span>  
  
 <span data-ttu-id="408a5-107">Esta sección describen los tipos anónimos que no se definen explícitamente en el esquema pero que son compatibles con Entity SQL.</span><span class="sxs-lookup"><span data-stu-id="408a5-107">This section discusses the anonymous types that are not defined in the schema explicitly but are supported by Entity SQL.</span></span> <span data-ttu-id="408a5-108">Para obtener información sobre los tipos nominales y primitivos, vea [tipos de modelos conceptuales (CSDL)](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec#conceptual-model-types-csdl).</span><span class="sxs-lookup"><span data-stu-id="408a5-108">For information on primitive and nominal types, see [Conceptual Model Types (CSDL)](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec#conceptual-model-types-csdl).</span></span>  
  
## <a name="rows"></a><span data-ttu-id="408a5-109">Filas</span><span class="sxs-lookup"><span data-stu-id="408a5-109">Rows</span></span>  
 <span data-ttu-id="408a5-110">La estructura de una fila depende de la secuencia de miembros con nombre y con tipo de que consta la misma.</span><span class="sxs-lookup"><span data-stu-id="408a5-110">The structure of a row depends on the sequence of typed and named members that the row consists of.</span></span> <span data-ttu-id="408a5-111">Un tipo de fila no tiene ninguna identidad y no se puede heredar.</span><span class="sxs-lookup"><span data-stu-id="408a5-111">A row type has no identity and cannot be inherited from.</span></span> <span data-ttu-id="408a5-112">Las instancias del mismo tipo de fila son equivalentes si los miembros son respectivamente equivalentes.</span><span class="sxs-lookup"><span data-stu-id="408a5-112">Instances of the same row type are equivalent if the members are respectively equivalent.</span></span> <span data-ttu-id="408a5-113">Las filas no tienen ningún otro comportamiento más allá de su equivalencia estructural y no tienen ningún equivalente en Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="408a5-113">Rows have no behavior beyond their structural equivalence and have no equivalent in the common language runtime.</span></span> <span data-ttu-id="408a5-114">Las consultas pueden producir estructuras que contienen filas o colecciones de filas.</span><span class="sxs-lookup"><span data-stu-id="408a5-114">Queries can result in structures that contain rows or collections of rows.</span></span> <span data-ttu-id="408a5-115">El enlace de API entre las consultas de [!INCLUDE[esql](../../../../../../includes/esql-md.md)] y el lenguaje del host define el modo en que las filas se materializan en la consulta que generó el resultado.</span><span class="sxs-lookup"><span data-stu-id="408a5-115">The API binding between the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] queries and the host language defines how rows are realized in the query that produced the result.</span></span> <span data-ttu-id="408a5-116">Para obtener información sobre cómo construir una instancia de fila, vea [construir tipos](../../../../../../docs/framework/data/adonet/ef/language-reference/constructing-types-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="408a5-116">For information on how to construct a row instance, see [Constructing Types](../../../../../../docs/framework/data/adonet/ef/language-reference/constructing-types-entity-sql.md).</span></span>  
  
## <a name="collections"></a><span data-ttu-id="408a5-117">Colecciones</span><span class="sxs-lookup"><span data-stu-id="408a5-117">Collections</span></span>  
 <span data-ttu-id="408a5-118">Los tipos de colección representan cero o más instancias de otros objetos.</span><span class="sxs-lookup"><span data-stu-id="408a5-118">Collection types represent zero or more instances of other objects.</span></span> <span data-ttu-id="408a5-119">Para obtener información sobre cómo construir una colección, vea [construir tipos](../../../../../../docs/framework/data/adonet/ef/language-reference/constructing-types-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="408a5-119">For information on how to construct collection, see [Constructing Types](../../../../../../docs/framework/data/adonet/ef/language-reference/constructing-types-entity-sql.md).</span></span>  
  
## <a name="references"></a><span data-ttu-id="408a5-120">Referencias</span><span class="sxs-lookup"><span data-stu-id="408a5-120">References</span></span>  
 <span data-ttu-id="408a5-121">Una referencia es un puntero lógico a una entidad concreta en un conjunto de entidades específico.</span><span class="sxs-lookup"><span data-stu-id="408a5-121">A reference is a logical pointer to a specific entity in a specific entity set.</span></span>  
  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="408a5-122">admite los operadores siguientes para construir, anular la construcción y navegar a través de referencias.</span><span class="sxs-lookup"><span data-stu-id="408a5-122">supports the following operators to construct, deconstruct, and navigate through references:</span></span>  
  
- [<span data-ttu-id="408a5-123">REF</span><span class="sxs-lookup"><span data-stu-id="408a5-123">REF</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/ref-entity-sql.md)  
  
- [<span data-ttu-id="408a5-124">CREATEREF</span><span class="sxs-lookup"><span data-stu-id="408a5-124">CREATEREF</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/createref-entity-sql.md)  
  
- [<span data-ttu-id="408a5-125">KEY</span><span class="sxs-lookup"><span data-stu-id="408a5-125">KEY</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/key-entity-sql.md)  
  
- [<span data-ttu-id="408a5-126">DEREF</span><span class="sxs-lookup"><span data-stu-id="408a5-126">DEREF</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/deref-entity-sql.md)  
  
 <span data-ttu-id="408a5-127">Puede navegar por una referencia utilizando el operador de acceso a miembros (`.`) (punto).</span><span class="sxs-lookup"><span data-stu-id="408a5-127">You can navigate through a reference by using the member access (dot) operator(`.`).</span></span> <span data-ttu-id="408a5-128">El fragmento de código siguiente extrae la propiedad Id (de Order) navegando por la propiedad r (referencia).</span><span class="sxs-lookup"><span data-stu-id="408a5-128">The following snippet extracts the Id property (of Order) by navigating through the r (reference) property.</span></span>  
  
```  
select o2.r.Id   
from (select ref(o) as r from LOB.Orders as o) as o2   
```  
  
 <span data-ttu-id="408a5-129">Si el valor de referencia es NULL o si el destino de la referencia no existe, el resultado es NULL.</span><span class="sxs-lookup"><span data-stu-id="408a5-129">If the reference value is null, or if the target of the reference does not exist, the result is null.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="408a5-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="408a5-130">See also</span></span>

- [<span data-ttu-id="408a5-131">Información general sobre Entity SQL</span><span class="sxs-lookup"><span data-stu-id="408a5-131">Entity SQL Overview</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)
- [<span data-ttu-id="408a5-132">Referencia de Entity SQL</span><span class="sxs-lookup"><span data-stu-id="408a5-132">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
- [<span data-ttu-id="408a5-133">CAST</span><span class="sxs-lookup"><span data-stu-id="408a5-133">CAST</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/cast-entity-sql.md)
- [<span data-ttu-id="408a5-134">Especificaciones CSDL, SSDL MSL</span><span class="sxs-lookup"><span data-stu-id="408a5-134">CSDL, SSDL, and MSL Specifications</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/csdl-ssdl-and-msl-specifications.md)
