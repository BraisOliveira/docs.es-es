---
title: Procedimiento para ejecutar directamente consultas SQL
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e491b9bf-741a-4296-9f51-76c25ddf6a82
ms.openlocfilehash: 04353361f8356b1d2b2aa3b930bb9b5ab88b9c0b
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/14/2019
ms.locfileid: "65583688"
---
# <a name="how-to-directly-execute-sql-queries"></a><span data-ttu-id="3f949-102">Procedimiento para ejecutar directamente consultas SQL</span><span class="sxs-lookup"><span data-stu-id="3f949-102">How to: Directly Execute SQL Queries</span></span>
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="3f949-103">convierte las consultas que se escriben en consultas SQL parametrizadas (en formato de texto) y las envía al servidor SQL Server para su procesamiento.</span><span class="sxs-lookup"><span data-stu-id="3f949-103">translates the queries you write into parameterized SQL queries (in text form) and sends them to the SQL server for processing.</span></span>  
  
 <span data-ttu-id="3f949-104">SQL no puede ejecutar todos los métodos que podrían estar localmente disponibles para una aplicación.</span><span class="sxs-lookup"><span data-stu-id="3f949-104">SQL cannot execute the variety of methods that might be locally available to your application.</span></span> [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="3f949-105">intenta convertir estos métodos locales en operaciones y funciones equivalentes que estén disponibles en el entorno de SQL.</span><span class="sxs-lookup"><span data-stu-id="3f949-105">tries to convert these local methods to equivalent operations and functions that are available inside the SQL environment.</span></span> <span data-ttu-id="3f949-106">La mayoría de los métodos y operadores en los tipos integrados de .NET Framework tienen equivalentes directos en comandos SQL.</span><span class="sxs-lookup"><span data-stu-id="3f949-106">Most methods and operators on .NET Framework built-in types have direct translations to SQL commands.</span></span> <span data-ttu-id="3f949-107">Algunos se pueden generar a partir de las funciones que están disponibles.</span><span class="sxs-lookup"><span data-stu-id="3f949-107">Some can be produced from the functions that are available.</span></span> <span data-ttu-id="3f949-108">Aquellos que no se pueden generar, inician excepciones en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="3f949-108">Those that cannot be produced generate run-time exceptions.</span></span> <span data-ttu-id="3f949-109">Para obtener más información, consulte [asignación de tipos de CLR de SQL](../../../../../../docs/framework/data/adonet/sql/linq/sql-clr-type-mapping.md).</span><span class="sxs-lookup"><span data-stu-id="3f949-109">For more information, see [SQL-CLR Type Mapping](../../../../../../docs/framework/data/adonet/sql/linq/sql-clr-type-mapping.md).</span></span>  
  
 <span data-ttu-id="3f949-110">Cuando una consulta [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] no es suficiente para una tarea especializada, puede utilizar el método <xref:System.Data.Linq.DataContext.ExecuteQuery%2A> para ejecutar una consulta SQL y después convertir el resultado de la consulta directamente en objetos.</span><span class="sxs-lookup"><span data-stu-id="3f949-110">In cases where a [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] query is insufficient for a specialized task, you can use the <xref:System.Data.Linq.DataContext.ExecuteQuery%2A> method to execute a SQL query, and then convert the result of your query directly into objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3f949-111">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="3f949-111">Example</span></span>  
 <span data-ttu-id="3f949-112">En el ejemplo siguiente, supongamos que los datos de la clase `Customer` ocupan dos tablas (customer1 y customer2).</span><span class="sxs-lookup"><span data-stu-id="3f949-112">In the following example, assume that the data for the `Customer` class is spread over two tables (customer1 and customer2).</span></span> <span data-ttu-id="3f949-113">La consulta devuelve una secuencia de objetos `Customer`.</span><span class="sxs-lookup"><span data-stu-id="3f949-113">The query returns a sequence of `Customer` objects.</span></span>  
  
 [!code-csharp[DLinqQuerying#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQuerying/cs/Program.cs#4)]
 [!code-vb[DLinqQuerying#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQuerying/vb/Module1.vb#4)]  
  
 <span data-ttu-id="3f949-114">Siempre que los nombres de columna en los resultados tabulares coincidan con las propiedades de columna de la clase de entidad, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] crea objetos a partir de cualquier consulta SQL.</span><span class="sxs-lookup"><span data-stu-id="3f949-114">As long as the column names in the tabular results match column properties of your entity class, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] creates your objects out of any SQL query.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3f949-115">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="3f949-115">Example</span></span>  
 <span data-ttu-id="3f949-116">El método <xref:System.Data.Linq.DataContext.ExecuteQuery%2A> también permite el uso de parámetros.</span><span class="sxs-lookup"><span data-stu-id="3f949-116">The <xref:System.Data.Linq.DataContext.ExecuteQuery%2A> method also allows for parameters.</span></span> <span data-ttu-id="3f949-117">Utilice código como el siguiente para ejecutar una consulta parametrizada.</span><span class="sxs-lookup"><span data-stu-id="3f949-117">Use code such as the following to execute a parameterized query.</span></span>  
  
 [!code-csharp[DLinqQuerying#5](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQuerying/cs/Program.cs#5)]
 [!code-vb[DLinqQuerying#5](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQuerying/vb/Module1.vb#5)]  
  
 <span data-ttu-id="3f949-118">Los parámetros se expresan en el texto de la consulta con la misma notación con llaves que `Console.WriteLine()` y `String.Format()`.</span><span class="sxs-lookup"><span data-stu-id="3f949-118">The parameters are expressed in the query text by using the same curly notation used by `Console.WriteLine()` and `String.Format()`.</span></span> <span data-ttu-id="3f949-119">De hecho, `String.Format()` realmente se llama en la cadena de consulta proporcionada, sustituyendo los parámetros entre llaves con genera los nombres de parámetro como @p0, @p1 ..., @p(n).</span><span class="sxs-lookup"><span data-stu-id="3f949-119">In fact, `String.Format()` is actually called on the query string you provide, substituting the curly braced parameters with generated parameter names such as @p0, @p1 …, @p(n).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3f949-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="3f949-120">See also</span></span>

- [<span data-ttu-id="3f949-121">Información general</span><span class="sxs-lookup"><span data-stu-id="3f949-121">Background Information</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/background-information.md)
- [<span data-ttu-id="3f949-122">Consulta de la base de datos</span><span class="sxs-lookup"><span data-stu-id="3f949-122">Querying the Database</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/querying-the-database.md)
