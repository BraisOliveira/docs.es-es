---
title: Qué puede hacer con LINQ to SQL
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 061d98b2-baa7-4336-8ad2-c14de8134d91
ms.openlocfilehash: efb7b86c3add99e596e6798c8267c09689899d56
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59231583"
---
# <a name="what-you-can-do-with-linq-to-sql"></a><span data-ttu-id="afa66-102">Qué puede hacer con LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="afa66-102">What You Can Do With LINQ to SQL</span></span>
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="afa66-103">admite toda la funcionalidad clave que puede esperar un programador de SQL.</span><span class="sxs-lookup"><span data-stu-id="afa66-103">supports all the key capabilities you would expect as a SQL developer.</span></span> <span data-ttu-id="afa66-104">Puede consultar, insertar, actualizar y eliminar información en las tablas.</span><span class="sxs-lookup"><span data-stu-id="afa66-104">You can query for information, and insert, update, and delete information from tables.</span></span>  
  
## <a name="selecting"></a><span data-ttu-id="afa66-105">Selección</span><span class="sxs-lookup"><span data-stu-id="afa66-105">Selecting</span></span>  
 <span data-ttu-id="afa66-106">Para la selección (*proyección*), basta con que escriba una consulta [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)] en su propio lenguaje de programación y, después, la ejecute para recuperar los resultados.</span><span class="sxs-lookup"><span data-stu-id="afa66-106">Selecting (*projection*) is achieved by just writing a [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)] query in your own programming language, and then executing that query to retrieve the results.</span></span> [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="afa66-107">traduce automáticamente todas las operaciones necesarias a las operaciones SQL correspondientes con la que ya está familiarizado.</span><span class="sxs-lookup"><span data-stu-id="afa66-107">itself translates all the necessary operations into the necessary SQL operations that you are familiar with.</span></span> <span data-ttu-id="afa66-108">Para obtener más información, consulta [LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/index.md).</span><span class="sxs-lookup"><span data-stu-id="afa66-108">For more information, see [LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/index.md).</span></span>  
  
 <span data-ttu-id="afa66-109">En el ejemplo siguiente se recuperan los nombres de las compañías de los clientes de Londres y se muestran en la ventana de la consola.</span><span class="sxs-lookup"><span data-stu-id="afa66-109">In the following example, the company names of customers from London are retrieved and displayed in the console window.</span></span>  
  
 [!code-csharp[DLinqGettingStarted#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqGettingStarted/cs/Program.cs#1)]
 [!code-vb[DLinqGettingStarted#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqGettingStarted/vb/Module1.vb#1)]  
  
## <a name="inserting"></a><span data-ttu-id="afa66-110">Inserción</span><span class="sxs-lookup"><span data-stu-id="afa66-110">Inserting</span></span>  
 <span data-ttu-id="afa66-111">Para realizar una operación `Insert`de SQL, basta con que agregue objetos al modelo de objetos que ha creado y llame a <xref:System.Data.Linq.DataContext.SubmitChanges%2A> en <xref:System.Data.Linq.DataContext>.</span><span class="sxs-lookup"><span data-stu-id="afa66-111">To execute a SQL `Insert`, just add objects to the object model you have created, and call <xref:System.Data.Linq.DataContext.SubmitChanges%2A> on the <xref:System.Data.Linq.DataContext>.</span></span>  
  
 <span data-ttu-id="afa66-112">En el ejemplo siguiente se agrega un nuevo cliente, e información sobre el cliente, a la tabla `Customers` utilizando el método <xref:System.Data.Linq.Table%601.InsertOnSubmit%2A>.</span><span class="sxs-lookup"><span data-stu-id="afa66-112">In the following example, a new customer and information about the customer is added to the `Customers` table by using <xref:System.Data.Linq.Table%601.InsertOnSubmit%2A>.</span></span>  
  
 [!code-csharp[DLinqGettingStarted#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqGettingStarted/cs/Program.cs#2)]
 [!code-vb[DLinqGettingStarted#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqGettingStarted/vb/Module1.vb#2)]  
  
## <a name="updating"></a><span data-ttu-id="afa66-113">Updating</span><span class="sxs-lookup"><span data-stu-id="afa66-113">Updating</span></span>  
 <span data-ttu-id="afa66-114">Para realizar una operación `Update` en una entrada de base de datos, primero recupere el elemento y modifíquelo directamente en el modelo de objetos.</span><span class="sxs-lookup"><span data-stu-id="afa66-114">To `Update` a database entry, first retrieve the item and edit it directly in the object model.</span></span> <span data-ttu-id="afa66-115">Después de haber modificado el objeto, llame a <xref:System.Data.Linq.DataContext.SubmitChanges%2A> en <xref:System.Data.Linq.DataContext> para actualizar la base de datos.</span><span class="sxs-lookup"><span data-stu-id="afa66-115">After you have modified the object, call <xref:System.Data.Linq.DataContext.SubmitChanges%2A> on the <xref:System.Data.Linq.DataContext> to update the database.</span></span>  
  
 <span data-ttu-id="afa66-116">En el ejemplo siguiente se recuperan todos los clientes que son de Londres.</span><span class="sxs-lookup"><span data-stu-id="afa66-116">In the following example, all customers who are from London are retrieved.</span></span> <span data-ttu-id="afa66-117">A continuación, el nombre de la ciudad se cambia de "London" a "London - Metro".</span><span class="sxs-lookup"><span data-stu-id="afa66-117">Then the name of the city is changed from "London" to "London - Metro".</span></span> <span data-ttu-id="afa66-118">Finalmente, se llama a <xref:System.Data.Linq.DataContext.SubmitChanges%2A> para enviar los cambios a la base de datos.</span><span class="sxs-lookup"><span data-stu-id="afa66-118">Finally, <xref:System.Data.Linq.DataContext.SubmitChanges%2A> is called to send the changes to the database.</span></span>  
  
 [!code-csharp[DLinqGettingStarted#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqGettingStarted/cs/Program.cs#3)]
 [!code-vb[DLinqGettingStarted#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqGettingStarted/vb/Module1.vb#3)]  
  
## <a name="deleting"></a><span data-ttu-id="afa66-119">Eliminando</span><span class="sxs-lookup"><span data-stu-id="afa66-119">Deleting</span></span>  
 <span data-ttu-id="afa66-120">Para realizar una operación `Delete` en un elemento, quite el elemento de la colección a la que pertenece y, a continuación, llame al método <xref:System.Data.Linq.DataContext.SubmitChanges%2A> en <xref:System.Data.Linq.DataContext> para confirmar el cambio.</span><span class="sxs-lookup"><span data-stu-id="afa66-120">To `Delete` an item, remove the item from the collection to which it belongs, and then call <xref:System.Data.Linq.DataContext.SubmitChanges%2A> on the <xref:System.Data.Linq.DataContext> to commit the change.</span></span>  
  
> [!NOTE]
>  [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="afa66-121">no reconoce las operaciones de eliminación en cascada.</span><span class="sxs-lookup"><span data-stu-id="afa66-121">does not recognize cascade-delete operations.</span></span> <span data-ttu-id="afa66-122">Si desea eliminar una fila en una tabla que tiene restricciones, vea [Cómo: Eliminar filas de la base de datos](../../../../../../docs/framework/data/adonet/sql/linq/how-to-delete-rows-from-the-database.md).</span><span class="sxs-lookup"><span data-stu-id="afa66-122">If you want to delete a row in a table that has constraints against it, see [How to: Delete Rows From the Database](../../../../../../docs/framework/data/adonet/sql/linq/how-to-delete-rows-from-the-database.md).</span></span>  
  
 <span data-ttu-id="afa66-123">En el ejemplo siguiente, se recupera el cliente cuyo `CustomerID` es `98128` de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="afa66-123">In the following example, the customer who has `CustomerID` of `98128` is retrieved from the database.</span></span> <span data-ttu-id="afa66-124">A continuación, después de confirmar que se recuperó la fila del cliente, se llama a <xref:System.Data.Linq.Table%601.DeleteOnSubmit%2A> para quitar ese objeto de la colección.</span><span class="sxs-lookup"><span data-stu-id="afa66-124">Then, after confirming that the customer row was retrieved, <xref:System.Data.Linq.Table%601.DeleteOnSubmit%2A> is called to remove that object from the collection.</span></span> <span data-ttu-id="afa66-125">Finalmente, se llama a <xref:System.Data.Linq.DataContext.SubmitChanges%2A> para transmitir la eliminación a la base de datos.</span><span class="sxs-lookup"><span data-stu-id="afa66-125">Finally, <xref:System.Data.Linq.DataContext.SubmitChanges%2A> is called to forward the deletion to the database.</span></span>  
  
 [!code-csharp[DLinqGettingStarted#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqGettingStarted/cs/Program.cs#4)]
 [!code-vb[DLinqGettingStarted#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqGettingStarted/vb/Module1.vb#4)]  
  
## <a name="see-also"></a><span data-ttu-id="afa66-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="afa66-126">See also</span></span>

- [<span data-ttu-id="afa66-127">Guía de programación</span><span class="sxs-lookup"><span data-stu-id="afa66-127">Programming Guide</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/programming-guide.md)
- [<span data-ttu-id="afa66-128">Modelo de objetos de LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="afa66-128">The LINQ to SQL Object Model</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)
- [<span data-ttu-id="afa66-129">Introducción</span><span class="sxs-lookup"><span data-stu-id="afa66-129">Getting Started</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/getting-started.md)
