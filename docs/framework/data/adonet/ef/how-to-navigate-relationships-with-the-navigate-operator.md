---
title: Filtrar para navegar por las relaciones con el operador Navigate
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 79996d2d-9b03-4a9d-82cc-7c5e7c2ad93d
ms.openlocfilehash: e5b7ba8ab6dc0d144ea57598c38ba8d1bbd5dc1e
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59085290"
---
# <a name="how-to-navigate-relationships-with-the-navigate-operator"></a><span data-ttu-id="3efb4-102">Filtrar para navegar por las relaciones con el operador Navigate</span><span class="sxs-lookup"><span data-stu-id="3efb4-102">How to: Navigate Relationships with the Navigate Operator</span></span>
<span data-ttu-id="3efb4-103">En este tema se muestra cómo ejecutar un comando contra un modelo conceptual usando un objeto <xref:System.Data.EntityClient.EntityCommand>, y cómo recuperar los resultados de <xref:System.Data.Metadata.Edm.RefType> usando un <xref:System.Data.EntityClient.EntityDataReader>.</span><span class="sxs-lookup"><span data-stu-id="3efb4-103">This topic shows how to execute a command against a conceptual model by using an <xref:System.Data.EntityClient.EntityCommand> object, and how to retrieve the <xref:System.Data.Metadata.Edm.RefType> results by using an <xref:System.Data.EntityClient.EntityDataReader>.</span></span>  
  
### <a name="to-run-the-code-in-this-example"></a><span data-ttu-id="3efb4-104">Para ejecutar el código de este ejemplo</span><span class="sxs-lookup"><span data-stu-id="3efb4-104">To run the code in this example</span></span>  
  
1.  <span data-ttu-id="3efb4-105">Agregar el [modelo AdventureWorks Sales](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks) al proyecto y configurar el proyecto para usar el [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3efb4-105">Add the [AdventureWorks Sales Model](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks) to your project and configure your project to use the [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)].</span></span> <span data-ttu-id="3efb4-106">Para obtener más información, vea [Cómo: Utilice el Asistente para Entity Data Model](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738677(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="3efb4-106">For more information, see [How to: Use the Entity Data Model Wizard](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738677(v=vs.100)).</span></span>  
  
2.  <span data-ttu-id="3efb4-107">En la página de código de la aplicación, agregue las instrucciones `using` siguientes (`Imports` en Visual Basic):</span><span class="sxs-lookup"><span data-stu-id="3efb4-107">In the code page for your application, add the following `using` statements (`Imports` in Visual Basic):</span></span>  
  
     [!code-csharp[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#namespaces)]
     [!code-vb[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#namespaces)]  
  
## <a name="example"></a><span data-ttu-id="3efb4-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="3efb4-108">Example</span></span>  
 <span data-ttu-id="3efb4-109">El ejemplo siguiente muestra cómo navegar por las relaciones en [!INCLUDE[esql](../../../../../includes/esql-md.md)] utilizando el [NAVIGATE](../../../../../docs/framework/data/adonet/ef/language-reference/navigate-entity-sql.md) operador.</span><span class="sxs-lookup"><span data-stu-id="3efb4-109">The following example shows how to navigate relationships in [!INCLUDE[esql](../../../../../includes/esql-md.md)] by using the [NAVIGATE](../../../../../docs/framework/data/adonet/ef/language-reference/navigate-entity-sql.md) operator.</span></span> <span data-ttu-id="3efb4-110">El `Navigate` operador toma los siguientes parámetros: una instancia de una entidad, el tipo de relación, el extremo de la relación y el comienzo de la relación.</span><span class="sxs-lookup"><span data-stu-id="3efb4-110">The `Navigate` operator takes the following parameters: an instance of an entity, the relationship type, the end of the relationship, and the beginning of the relationship.</span></span> <span data-ttu-id="3efb4-111">Si lo desea, puede pasar solo una instancia de una entidad y el tipo de relación para el `Navigate` operador.</span><span class="sxs-lookup"><span data-stu-id="3efb4-111">Optionally, you can pass only an instance of an entity and the relationship type to the `Navigate` operator.</span></span>  
  
 [!code-csharp[DP EntityServices Concepts#NavigateWithNavOperatorWithEntityCommand](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#navigatewithnavoperatorwithentitycommand)]
 [!code-vb[DP EntityServices Concepts#NavigateWithNavOperatorWithEntityCommand](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#navigatewithnavoperatorwithentitycommand)]  
  
## <a name="see-also"></a><span data-ttu-id="3efb4-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="3efb4-112">See also</span></span>

- [<span data-ttu-id="3efb4-113">Proveedor de EntityClient para Entity Framework</span><span class="sxs-lookup"><span data-stu-id="3efb4-113">EntityClient Provider for the Entity Framework</span></span>](../../../../../docs/framework/data/adonet/ef/entityclient-provider-for-the-entity-framework.md)
- [<span data-ttu-id="3efb4-114">Lenguaje Entity SQL</span><span class="sxs-lookup"><span data-stu-id="3efb4-114">Entity SQL Language</span></span>](../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-language.md)
