---
title: Operaciones de copia masiva en SQL Server
ms.date: 03/30/2017
ms.assetid: 83a7a0d2-8018-4354-97b9-0b1d99f8342b
ms.openlocfilehash: ae97bcdd6776d573cf9e523133c2c00a42c273bb
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70782526"
---
# <a name="bulk-copy-operations-in-sql-server"></a><span data-ttu-id="f14f9-102">Operaciones de copia masiva en SQL Server</span><span class="sxs-lookup"><span data-stu-id="f14f9-102">Bulk Copy Operations in SQL Server</span></span>
<span data-ttu-id="f14f9-103">Microsoft SQL Server incluye una conocida utilidad de línea de comandos denominada **BCP** para la copia masiva rápida de archivos grandes en tablas o vistas en bases de datos de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="f14f9-103">Microsoft SQL Server includes a popular command-line utility named **bcp** for quickly bulk copying large files into tables or views in SQL Server databases.</span></span> <span data-ttu-id="f14f9-104">La clase <xref:System.Data.SqlClient.SqlBulkCopy> permite escribir soluciones de código administrado que ofrecen una funcionalidad similar.</span><span class="sxs-lookup"><span data-stu-id="f14f9-104">The <xref:System.Data.SqlClient.SqlBulkCopy> class allows you to write managed code solutions that provide similar functionality.</span></span> <span data-ttu-id="f14f9-105">Aunque existen otras formas de cargar datos en una tabla SQL Server (por ejemplo, mediante instrucciones INSERT), <xref:System.Data.SqlClient.SqlBulkCopy> tiene la ventaja sobre las demás de un rendimiento significativo.</span><span class="sxs-lookup"><span data-stu-id="f14f9-105">There are other ways to load data into a SQL Server table (INSERT statements, for example) but <xref:System.Data.SqlClient.SqlBulkCopy> offers a significant performance advantage over them.</span></span>  
  
 <span data-ttu-id="f14f9-106">La clase <xref:System.Data.SqlClient.SqlBulkCopy> sólo se puede utilizar para escribir datos en tablas SQL Server.</span><span class="sxs-lookup"><span data-stu-id="f14f9-106">The <xref:System.Data.SqlClient.SqlBulkCopy> class can be used to write data only to SQL Server tables.</span></span> <span data-ttu-id="f14f9-107">Sin embargo, el origen de datos no está limitado a SQL Server; se puede utilizar cualquier origen de datos siempre y cuando pueda cargarse en una instancia <xref:System.Data.DataTable> o leerse con una instancia <xref:System.Data.IDataReader>.</span><span class="sxs-lookup"><span data-stu-id="f14f9-107">But the data source is not limited to SQL Server; any data source can be used, as long as the data can be loaded to a <xref:System.Data.DataTable> instance or read with a <xref:System.Data.IDataReader> instance.</span></span>  
  
 <span data-ttu-id="f14f9-108">El uso de la clase <xref:System.Data.SqlClient.SqlBulkCopy> le permite realizar:</span><span class="sxs-lookup"><span data-stu-id="f14f9-108">Using the <xref:System.Data.SqlClient.SqlBulkCopy> class, you can perform:</span></span>  
  
- <span data-ttu-id="f14f9-109">una única operación de copia masiva</span><span class="sxs-lookup"><span data-stu-id="f14f9-109">A single bulk copy operation</span></span>  
  
- <span data-ttu-id="f14f9-110">varias operaciones de copia masiva</span><span class="sxs-lookup"><span data-stu-id="f14f9-110">Multiple bulk copy operations</span></span>  
  
- <span data-ttu-id="f14f9-111">una operación de copia masiva en una transacción</span><span class="sxs-lookup"><span data-stu-id="f14f9-111">A bulk copy operation within a transaction</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f14f9-112">Cuando se usa .NET Framework versión 1,1 o anterior (que no admite la <xref:System.Data.SqlClient.SqlBulkCopy> clase), se puede ejecutar la instrucción SQL Server **Bulk Insert** de Transact-SQL mediante <xref:System.Data.SqlClient.SqlCommand> el objeto.</span><span class="sxs-lookup"><span data-stu-id="f14f9-112">When using .NET Framework version 1.1 or earlier (which does not support the <xref:System.Data.SqlClient.SqlBulkCopy> class), you can execute the SQL Server Transact-SQL **BULK INSERT** statement using the <xref:System.Data.SqlClient.SqlCommand> object.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="f14f9-113">En esta sección</span><span class="sxs-lookup"><span data-stu-id="f14f9-113">In This Section</span></span>  
 [<span data-ttu-id="f14f9-114">Configuración de ejemplos de copia masiva</span><span class="sxs-lookup"><span data-stu-id="f14f9-114">Bulk Copy Example Setup</span></span>](bulk-copy-example-setup.md)  
 <span data-ttu-id="f14f9-115">Describe las tablas usadas en los ejemplos de copia masiva y proporciona scripts SQL para crear las tablas de la base de datos AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="f14f9-115">Describes the tables used in the bulk copy examples and provides SQL scripts for creating the tables in the AdventureWorks database.</span></span>  
  
 [<span data-ttu-id="f14f9-116">Operaciones de copia masiva únicas</span><span class="sxs-lookup"><span data-stu-id="f14f9-116">Single Bulk Copy Operations</span></span>](single-bulk-copy-operations.md)  
 <span data-ttu-id="f14f9-117">Describe cómo realizar una sola copia masiva de datos en una instancia de SQL Server mediante la clase <xref:System.Data.SqlClient.SqlBulkCopy>, y cómo realizar la operación de copia masiva con las instrucciones Transact-SQL y la clase <xref:System.Data.SqlClient.SqlCommand>.</span><span class="sxs-lookup"><span data-stu-id="f14f9-117">Describes how to do a single bulk copy of data into an instance of SQL Server using the <xref:System.Data.SqlClient.SqlBulkCopy> class, and how to perform the bulk copy operation using Transact-SQL statements and the <xref:System.Data.SqlClient.SqlCommand> class.</span></span>  
  
 [<span data-ttu-id="f14f9-118">Varias operaciones de copia masiva</span><span class="sxs-lookup"><span data-stu-id="f14f9-118">Multiple Bulk Copy Operations</span></span>](multiple-bulk-copy-operations.md)  
 <span data-ttu-id="f14f9-119">Describe cómo realizar varias operaciones de copia masiva de datos en una instancia de SQL Server mediante la clase <xref:System.Data.SqlClient.SqlBulkCopy>.</span><span class="sxs-lookup"><span data-stu-id="f14f9-119">Describes how to do multiple bulk copy operations of data into an instance of SQL Server using the <xref:System.Data.SqlClient.SqlBulkCopy> class.</span></span>  
  
 [<span data-ttu-id="f14f9-120">Transacción y operaciones de copia masiva</span><span class="sxs-lookup"><span data-stu-id="f14f9-120">Transaction and Bulk Copy Operations</span></span>](transaction-and-bulk-copy-operations.md)  
 <span data-ttu-id="f14f9-121">Describe cómo realizar una operación de copia masiva en una transacción, lo que incluye cómo confirmar o revertir la transacción.</span><span class="sxs-lookup"><span data-stu-id="f14f9-121">Describes how to perform a bulk copy operation within a transaction, including how to commit or rollback the transaction.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f14f9-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="f14f9-122">See also</span></span>

- [<span data-ttu-id="f14f9-123">SQL Server y ADO.NET</span><span class="sxs-lookup"><span data-stu-id="f14f9-123">SQL Server and ADO.NET</span></span>](index.md)
- [<span data-ttu-id="f14f9-124">Información general sobre ADO.NET</span><span class="sxs-lookup"><span data-stu-id="f14f9-124">ADO.NET Overview</span></span>](../ado-net-overview.md)
