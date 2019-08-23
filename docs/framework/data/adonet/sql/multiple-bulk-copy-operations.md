---
title: Varias operaciones de copia masiva
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 5ad12f94-7459-4a93-a421-4160d1a90715
ms.openlocfilehash: 8ee0fdbfc167c819942d8282aca56b7c5168fd87
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69946861"
---
# <a name="multiple-bulk-copy-operations"></a><span data-ttu-id="fb7a1-102">Varias operaciones de copia masiva</span><span class="sxs-lookup"><span data-stu-id="fb7a1-102">Multiple Bulk Copy Operations</span></span>
<span data-ttu-id="fb7a1-103">Se pueden realizar varias operaciones de copia masiva con una única instancia de una clase <xref:System.Data.SqlClient.SqlBulkCopy>.</span><span class="sxs-lookup"><span data-stu-id="fb7a1-103">You can perform multiple bulk copy operations using a single instance of a <xref:System.Data.SqlClient.SqlBulkCopy> class.</span></span> <span data-ttu-id="fb7a1-104">Si los parámetros de la operación cambian entre copias (por ejemplo, el nombre de la tabla de destino), debe actualizarlos antes de las llamadas subsiguientes a cualquiera de los métodos **WriteToServer** , como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="fb7a1-104">If the operation parameters change between copies (for example, the name of the destination table), you must update them prior to any subsequent calls to any of the **WriteToServer** methods, as demonstrated in the following example.</span></span> <span data-ttu-id="fb7a1-105">A menos que se cambien explícitamente, todos los valores de propiedades permanecen igual que estaban en la operación anterior de copia masiva de una determinada instancia.</span><span class="sxs-lookup"><span data-stu-id="fb7a1-105">Unless explicitly changed, all property values remain the same as they were on the previous bulk copy operation for a given instance.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="fb7a1-106">Realizar varias operaciones de copia masiva con la misma instancia de <xref:System.Data.SqlClient.SqlBulkCopy> resulta generalmente más eficiente que utilizar una instancia distinta para cada operación.</span><span class="sxs-lookup"><span data-stu-id="fb7a1-106">Performing multiple bulk copy operations using the same instance of <xref:System.Data.SqlClient.SqlBulkCopy> is usually more efficient than using a separate instance for each operation.</span></span>  
  
 <span data-ttu-id="fb7a1-107">Si realiza varias operaciones de copia masiva con el mismo objeto <xref:System.Data.SqlClient.SqlBulkCopy>, no existen restricciones en cuanto a si la información de origen o destino es igual o diferente en cada operación.</span><span class="sxs-lookup"><span data-stu-id="fb7a1-107">If you perform several bulk copy operations using the same <xref:System.Data.SqlClient.SqlBulkCopy> object, there are no restrictions on whether source or target information is equal or different in each operation.</span></span> <span data-ttu-id="fb7a1-108">No obstante, debe asegurarse de que la información de asociación de columnas esté establecida correctamente cada vez que escriba en el servidor.</span><span class="sxs-lookup"><span data-stu-id="fb7a1-108">However, you must ensure that column association information is properly set each time you write to the server.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="fb7a1-109">Este ejemplo no se ejecutará a menos que haya creado las tablas de trabajo como se describe en el ejemplo de configuración de la [copia masiva](../../../../../docs/framework/data/adonet/sql/bulk-copy-example-setup.md).</span><span class="sxs-lookup"><span data-stu-id="fb7a1-109">This sample will not run unless you have created the work tables as described in [Bulk Copy Example Setup](../../../../../docs/framework/data/adonet/sql/bulk-copy-example-setup.md).</span></span> <span data-ttu-id="fb7a1-110">Este código se proporciona para mostrar la sintaxis para usar únicamente **SqlBulkCopy** .</span><span class="sxs-lookup"><span data-stu-id="fb7a1-110">This code is provided to demonstrate the syntax for using **SqlBulkCopy** only.</span></span> <span data-ttu-id="fb7a1-111">Si las tablas de origen y de destino están incluidas en la misma instancia de SQL Server, lo más rápido y sencillo es usar una instrucción `INSERT … SELECT` de Transact-SQL para copiar los datos.</span><span class="sxs-lookup"><span data-stu-id="fb7a1-111">If the source and destination tables are located in the same SQL Server instance, it is easier and faster to use a Transact-SQL `INSERT … SELECT` statement to copy the data.</span></span>  
  
 [!code-csharp[DataWorks SqlBulkCopy.ColumnMappingOrdersDetails#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlBulkCopy.ColumnMappingOrdersDetails/CS/source.cs#1)]
 [!code-vb[DataWorks SqlBulkCopy.ColumnMappingOrdersDetails#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlBulkCopy.ColumnMappingOrdersDetails/VB/source.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="fb7a1-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="fb7a1-112">See also</span></span>

- [<span data-ttu-id="fb7a1-113">Operaciones de copia masiva en SQL Server</span><span class="sxs-lookup"><span data-stu-id="fb7a1-113">Bulk Copy Operations in SQL Server</span></span>](../../../../../docs/framework/data/adonet/sql/bulk-copy-operations-in-sql-server.md)
- [<span data-ttu-id="fb7a1-114">Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet</span><span class="sxs-lookup"><span data-stu-id="fb7a1-114">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
