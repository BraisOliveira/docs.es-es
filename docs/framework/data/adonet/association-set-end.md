---
title: extremo del conjunto de asociaciones
ms.date: 03/30/2017
ms.assetid: fe4bf1d3-047a-4a37-98c5-a66e70811346
ms.openlocfilehash: 7b6c646592c1878ea30396d98b4976dc8fa0be12
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61769595"
---
# <a name="association-set-end"></a><span data-ttu-id="cf58f-102">extremo del conjunto de asociaciones</span><span class="sxs-lookup"><span data-stu-id="cf58f-102">association set end</span></span>
<span data-ttu-id="cf58f-103">Un *final del conjunto de asociaciones* identifica el [tipo de entidad](../../../../docs/framework/data/adonet/entity-type.md) y [conjunto de entidades](../../../../docs/framework/data/adonet/entity-set.md) al final de un [conjunto de asociaciones](../../../../docs/framework/data/adonet/association-set.md).</span><span class="sxs-lookup"><span data-stu-id="cf58f-103">An *association set end* identifies the [entity type](../../../../docs/framework/data/adonet/entity-type.md) and the [entity set](../../../../docs/framework/data/adonet/entity-set.md) at the end of an [association set](../../../../docs/framework/data/adonet/association-set.md).</span></span> <span data-ttu-id="cf58f-104">Los extremos de conjuntos de asociaciones se definen como parte de un conjunto de asociaciones, que debe tener exactamente dos extremos.</span><span class="sxs-lookup"><span data-stu-id="cf58f-104">Association set ends are defined as part of an association set; an association set must have exactly two association set ends.</span></span>  
  
 <span data-ttu-id="cf58f-105">Una definición de extremo de conjunto de asociaciones contiene la información siguiente:</span><span class="sxs-lookup"><span data-stu-id="cf58f-105">An association set end definition contains the following information:</span></span>  
  
- <span data-ttu-id="cf58f-106">Uno de los tipos de entidad implicados en el conjunto de asociaciones.</span><span class="sxs-lookup"><span data-stu-id="cf58f-106">One of the entity types involved in the association set.</span></span> <span data-ttu-id="cf58f-107">(Necesario)</span><span class="sxs-lookup"><span data-stu-id="cf58f-107">(Required)</span></span>  
  
- <span data-ttu-id="cf58f-108">El conjunto de entidades para el tipo de entidad implicado en el conjunto de asociaciones.</span><span class="sxs-lookup"><span data-stu-id="cf58f-108">The entity set for the entity type involved in the association set.</span></span> <span data-ttu-id="cf58f-109">(Necesario)</span><span class="sxs-lookup"><span data-stu-id="cf58f-109">(Required)</span></span>  
  
## <a name="example"></a><span data-ttu-id="cf58f-110">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="cf58f-110">Example</span></span>  
 <span data-ttu-id="cf58f-111">El diagrama siguiente muestra un modelo conceptual con dos asociaciones: `WrittenBy` y `PublishedBy`.</span><span class="sxs-lookup"><span data-stu-id="cf58f-111">The diagram below shows a conceptual model with two associations: `WrittenBy` and `PublishedBy`.</span></span>  
  
 ![Modelo de ejemplo con tres tipos de entidad](./media/association-set-end/example-model-three-entity-types.gif)  
  
 <span data-ttu-id="cf58f-113">El diagrama siguiente muestra un conjunto de asociaciones (`PublishedBy` y dos conjuntos de entidades (`Books` y `Publishers`) basados en el modelo conceptual mostrado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="cf58f-113">The following diagram shows an association set (`PublishedBy`) and two entity sets (`Books` and `Publishers`) based on the conceptual model shown above.</span></span> <span data-ttu-id="cf58f-114">Los extremos del conjunto de asociaciones son los conjuntos de entidades `Books` y `Publishers`.</span><span class="sxs-lookup"><span data-stu-id="cf58f-114">The association set ends are the `Books` and `Publishers` entity sets.</span></span> <span data-ttu-id="cf58f-115">BI en el `Books` conjunto de entidades representa una instancia de la `Book` tipo de entidad en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="cf58f-115">Bi in the `Books` entity set represents an instance of the `Book` entity type at run time.</span></span> <span data-ttu-id="cf58f-116">De forma similar, Pj representa un `Publisher` de instancia en el `Publishers` conjunto de entidades.</span><span class="sxs-lookup"><span data-stu-id="cf58f-116">Similarly, Pj represents a `Publisher` instance in the `Publishers` entity set.</span></span> <span data-ttu-id="cf58f-117">BiPj representa una instancia de la `PublishedBy` asociación en el `PublishedBy` conjunto de asociaciones.</span><span class="sxs-lookup"><span data-stu-id="cf58f-117">BiPj represents an instance of the `PublishedBy` association in the `PublishedBy` association set.</span></span>  
  
 ![Captura de pantalla que muestra un ejemplo de conjuntos.](./media/association-set-end/sets-example-association.gif)  
  
 <span data-ttu-id="cf58f-119">El [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) usa un DSL denominado lenguaje de definición de esquemas conceptuales ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) para definir los modelos conceptuales.</span><span class="sxs-lookup"><span data-stu-id="cf58f-119">The [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) uses a DSL called conceptual schema definition language ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) to define conceptual models.</span></span> <span data-ttu-id="cf58f-120">El siguiente CSDL define un contenedor de entidad con un conjunto de asociaciones para cada asociación en el diagrama anterior.</span><span class="sxs-lookup"><span data-stu-id="cf58f-120">The following CSDL defines an entity container with one association set for each association in the diagram above.</span></span> <span data-ttu-id="cf58f-121">Observe que los extremos del conjunto de asociaciones se definen como parte de cada definición del conjunto de asociaciones.</span><span class="sxs-lookup"><span data-stu-id="cf58f-121">Note that association set ends are defined as part of each association set definition.</span></span>  
  
 [!code-xml[EDM_Example_Model#EntityContainerExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#entitycontainerexample)]  
  
## <a name="see-also"></a><span data-ttu-id="cf58f-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="cf58f-122">See also</span></span>

- [<span data-ttu-id="cf58f-123">Conceptos clave de Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="cf58f-123">Entity Data Model Key Concepts</span></span>](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)
- [<span data-ttu-id="cf58f-124">Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="cf58f-124">Entity Data Model</span></span>](../../../../docs/framework/data/adonet/entity-data-model.md)
