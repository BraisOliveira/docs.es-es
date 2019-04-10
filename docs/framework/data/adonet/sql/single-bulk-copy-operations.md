---
title: Operaciones de copia masiva únicas
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 5e7ff0be-3f23-4996-a92c-bd54d65c3836
ms.openlocfilehash: b2783779965505d09f73c7203770c19ccaa78d26
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/09/2019
ms.locfileid: "59323374"
---
# <a name="single-bulk-copy-operations"></a><span data-ttu-id="e2414-102">Operaciones de copia masiva únicas</span><span class="sxs-lookup"><span data-stu-id="e2414-102">Single Bulk Copy Operations</span></span>
<span data-ttu-id="e2414-103">La manera más sencilla de realizar una operación de copia masiva de SQL Server es ejecutar una sola operación con respecto a una base de datos.</span><span class="sxs-lookup"><span data-stu-id="e2414-103">The simplest approach to performing a SQL Server bulk copy operation is to perform a single operation against a database.</span></span> <span data-ttu-id="e2414-104">De forma predeterminada, las operaciones de copia masiva se realizan como una operación aislada: la operación de copia tiene lugar sin transacción, sin la oportunidad de revertirla.</span><span class="sxs-lookup"><span data-stu-id="e2414-104">By default, a bulk copy operation is performed as an isolated operation: the copy operation occurs in a non-transacted way, with no opportunity for rolling it back.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e2414-105">Si necesita revertir la copia masiva total o parcialmente cuando se produce un error, puede utilizar una transacción administrada por <xref:System.Data.SqlClient.SqlBulkCopy> o realizar la operación de copia masiva en una transacción existente.</span><span class="sxs-lookup"><span data-stu-id="e2414-105">If you need to roll back all or part of the bulk copy when an error occurs, you can either use a <xref:System.Data.SqlClient.SqlBulkCopy>-managed transaction, or perform the bulk copy operation within an existing transaction.</span></span> <span data-ttu-id="e2414-106">**SqlBulkCopy** también funcionará con <xref:System.Transactions> si la conexión está inscrita (implícita o explícitamente) en un **System.Transactions** transacciones.</span><span class="sxs-lookup"><span data-stu-id="e2414-106">**SqlBulkCopy** will also work with <xref:System.Transactions> if the connection is enlisted (implicitly or explicitly) into a **System.Transactions** transaction.</span></span>  
>   
>  <span data-ttu-id="e2414-107">Para obtener más información, consulte [transacciones y operaciones de copia masiva](../../../../../docs/framework/data/adonet/sql/transaction-and-bulk-copy-operations.md).</span><span class="sxs-lookup"><span data-stu-id="e2414-107">For more information, see [Transaction and Bulk Copy Operations](../../../../../docs/framework/data/adonet/sql/transaction-and-bulk-copy-operations.md).</span></span>  
  
 <span data-ttu-id="e2414-108">Los pasos generales para realizar una operación de copia masiva son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="e2414-108">The general steps for performing a bulk copy operation are as follows:</span></span>  
  
1. <span data-ttu-id="e2414-109">conéctese al servidor de origen y obtenga los datos que se van a copiar.</span><span class="sxs-lookup"><span data-stu-id="e2414-109">Connect to the source server and obtain the data to be copied.</span></span> <span data-ttu-id="e2414-110">Los datos también pueden proceder de otros orígenes, si se pueden recuperar de un objeto <xref:System.Data.IDataReader> o <xref:System.Data.DataTable>.</span><span class="sxs-lookup"><span data-stu-id="e2414-110">Data can also come from other sources, if it can be retrieved from an <xref:System.Data.IDataReader> or <xref:System.Data.DataTable> object.</span></span>  
  
2. <span data-ttu-id="e2414-111">Conectarse al servidor de destino (a menos que desee **SqlBulkCopy** para establecer una conexión automáticamente).</span><span class="sxs-lookup"><span data-stu-id="e2414-111">Connect to the destination server (unless you want **SqlBulkCopy** to establish a connection for you).</span></span>  
  
3. <span data-ttu-id="e2414-112">Cree un objeto <xref:System.Data.SqlClient.SqlBulkCopy> y configure las propiedades necesarias.</span><span class="sxs-lookup"><span data-stu-id="e2414-112">Create a <xref:System.Data.SqlClient.SqlBulkCopy> object, setting any necessary properties.</span></span>  
  
4. <span data-ttu-id="e2414-113">Establecer el **DestinationTableName** propiedad para indicar la tabla de destino para la masiva de la operación de inserción.</span><span class="sxs-lookup"><span data-stu-id="e2414-113">Set the **DestinationTableName** property to indicate the target table for the bulk insert operation.</span></span>  
  
5. <span data-ttu-id="e2414-114">Llame a uno de los **WriteToServer** métodos.</span><span class="sxs-lookup"><span data-stu-id="e2414-114">Call one of the **WriteToServer** methods.</span></span>  
  
6. <span data-ttu-id="e2414-115">Opcionalmente, actualice las propiedades y llame **WriteToServer** nuevo según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="e2414-115">Optionally, update properties and call **WriteToServer** again as necessary.</span></span>  
  
7. <span data-ttu-id="e2414-116">Llame a <xref:System.Data.SqlClient.SqlBulkCopy.Close%2A>, o incluya las operaciones de copia masiva en una instrucción `Using`.</span><span class="sxs-lookup"><span data-stu-id="e2414-116">Call <xref:System.Data.SqlClient.SqlBulkCopy.Close%2A>, or wrap the bulk copy operations within a `Using` statement.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="e2414-117">Es recomendable que los tipos de datos de las columnas de origen y destino coincidan.</span><span class="sxs-lookup"><span data-stu-id="e2414-117">We recommend that the source and target column data types match.</span></span> <span data-ttu-id="e2414-118">Si no coinciden los tipos de datos, **SqlBulkCopy** intenta convertir cada valor de origen en el tipo de datos de destino, utilizando las reglas empleadas por <xref:System.Data.SqlClient.SqlParameter.Value%2A>.</span><span class="sxs-lookup"><span data-stu-id="e2414-118">If the data types do not match, **SqlBulkCopy** attempts to convert each source value to the target data type, using the rules employed by <xref:System.Data.SqlClient.SqlParameter.Value%2A>.</span></span> <span data-ttu-id="e2414-119">Las conversiones pueden afectar al rendimiento y también dar lugar a errores inesperados.</span><span class="sxs-lookup"><span data-stu-id="e2414-119">Conversions can affect performance, and also can result in unexpected errors.</span></span> <span data-ttu-id="e2414-120">Por ejemplo, un tipo de datos `Double` se puede convertir a un tipo de datos `Decimal` la mayoría de las veces, pero no siempre.</span><span class="sxs-lookup"><span data-stu-id="e2414-120">For example, a `Double` data type can be converted to a `Decimal` data type most of the time, but not always.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e2414-121">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e2414-121">Example</span></span>  
 <span data-ttu-id="e2414-122">En la siguiente aplicación de consola se demuestra cómo cargar datos mediante la clase <xref:System.Data.SqlClient.SqlBulkCopy>.</span><span class="sxs-lookup"><span data-stu-id="e2414-122">The following console application demonstrates how to load data using the <xref:System.Data.SqlClient.SqlBulkCopy> class.</span></span> <span data-ttu-id="e2414-123">En este ejemplo, un <xref:System.Data.SqlClient.SqlDataReader> se usa para copiar datos desde el **Production.Product** tabla en SQL Server **AdventureWorks** base de datos a una tabla similar en la misma base de datos.</span><span class="sxs-lookup"><span data-stu-id="e2414-123">In this example, a <xref:System.Data.SqlClient.SqlDataReader> is used to copy data from the **Production.Product** table in the SQL Server **AdventureWorks** database to a similar table in the same database.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="e2414-124">En este ejemplo no se ejecutará a menos que haya creado las tablas de trabajo como se describe en [configuración de ejemplo de copia masiva](../../../../../docs/framework/data/adonet/sql/bulk-copy-example-setup.md).</span><span class="sxs-lookup"><span data-stu-id="e2414-124">This sample will not run unless you have created the work tables as described in [Bulk Copy Example Setup](../../../../../docs/framework/data/adonet/sql/bulk-copy-example-setup.md).</span></span> <span data-ttu-id="e2414-125">Este código se proporciona para mostrar la sintaxis para usar **SqlBulkCopy** solo.</span><span class="sxs-lookup"><span data-stu-id="e2414-125">This code is provided to demonstrate the syntax for using **SqlBulkCopy** only.</span></span> <span data-ttu-id="e2414-126">Si las tablas de origen y de destino están incluidas en la misma instancia de SQL Server, lo más rápido y sencillo es usar una instrucción `INSERT … SELECT` de Transact-SQL para copiar los datos.</span><span class="sxs-lookup"><span data-stu-id="e2414-126">If the source and destination tables are located in the same SQL Server instance, it is easier and faster to use a Transact-SQL `INSERT … SELECT` statement to copy the data.</span></span>  
  
 [!code-csharp[DataWorks BulkCopy.Single#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks BulkCopy.Single/CS/source.cs#1)]
 [!code-vb[DataWorks BulkCopy.Single#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks BulkCopy.Single/VB/source.vb#1)]  
  
## <a name="performing-a-bulk-copy-operation-using-transact-sql-and-the-command-class"></a><span data-ttu-id="e2414-127">Realización de una operación de copia masiva mediante Transact-SQL y la clase Command</span><span class="sxs-lookup"><span data-stu-id="e2414-127">Performing a Bulk Copy Operation Using Transact-SQL and the Command Class</span></span>  
 <span data-ttu-id="e2414-128">En el siguiente ejemplo se ilustra cómo utilizar el método <xref:System.Data.SqlClient.SqlCommand.ExecuteNonQuery%2A> para ejecutar la instrucción BULK INSERT.</span><span class="sxs-lookup"><span data-stu-id="e2414-128">The following example illustrates how to use the <xref:System.Data.SqlClient.SqlCommand.ExecuteNonQuery%2A> method to execute the BULK INSERT statement.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e2414-129">La ruta de acceso al archivo del origen de los datos es relativa al servidor.</span><span class="sxs-lookup"><span data-stu-id="e2414-129">The file path for the data source is relative to the server.</span></span> <span data-ttu-id="e2414-130">El proceso de servidor debe tener acceso a ella para que la operación de copia masiva se realice correctamente.</span><span class="sxs-lookup"><span data-stu-id="e2414-130">The server process must have access to that path in order for the bulk copy operation to succeed.</span></span>  
  
```vb  
Using connection As SqlConnection = New SqlConnection(connectionString)  
Dim queryString As String = _  
    "BULK INSERT Northwind.dbo.[Order Details] FROM " & _  
    "'f:\mydata\data.tbl' WITH (FORMATFILE='f:\mydata\data.fmt' )"  
connection.Open()  
SqlCommand command = New SqlCommand(queryString, connection);  
  
command.ExecuteNonQuery()  
End Using  
```  
  
```csharp  
using (SqlConnection connection = New SqlConnection(connectionString))  
{  
string queryString =  "BULK INSERT Northwind.dbo.[Order Details] " +  
    "FROM 'f:\mydata\data.tbl' " +  
    "WITH ( FORMATFILE='f:\mydata\data.fmt' )";  
connection.Open();  
SqlCommand command = new SqlCommand(queryString, connection);  
  
command.ExecuteNonQuery();  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="e2414-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="e2414-131">See also</span></span>

- [<span data-ttu-id="e2414-132">Operaciones de copia masiva en SQL Server</span><span class="sxs-lookup"><span data-stu-id="e2414-132">Bulk Copy Operations in SQL Server</span></span>](../../../../../docs/framework/data/adonet/sql/bulk-copy-operations-in-sql-server.md)
- [<span data-ttu-id="e2414-133">Proveedores administrados de ADO.NET y centro de desarrolladores de DataSet</span><span class="sxs-lookup"><span data-stu-id="e2414-133">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
