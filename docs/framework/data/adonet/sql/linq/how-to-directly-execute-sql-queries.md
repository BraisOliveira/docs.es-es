---
title: Procedimiento para ejecutar directamente consultas SQL
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e491b9bf-741a-4296-9f51-76c25ddf6a82
ms.openlocfilehash: 6423959ed5036cc8ab2a88bb7273ef7aa95c8958
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59101541"
---
# <a name="how-to-directly-execute-sql-queries"></a><span data-ttu-id="54b47-102">Procedimiento para ejecutar directamente consultas SQL</span><span class="sxs-lookup"><span data-stu-id="54b47-102">How to: Directly Execute SQL Queries</span></span>
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="54b47-103">convierte las consultas que se escriben en consultas SQL parametrizadas (en formato de texto) y las envía al servidor SQL Server para su procesamiento.</span><span class="sxs-lookup"><span data-stu-id="54b47-103">translates the queries you write into parameterized SQL queries (in text form) and sends them to the SQL server for processing.</span></span>  
  
 <span data-ttu-id="54b47-104">SQL no puede ejecutar todos los métodos que podrían estar localmente disponibles para una aplicación.</span><span class="sxs-lookup"><span data-stu-id="54b47-104">SQL cannot execute the variety of methods that might be locally available to your application.</span></span> [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="54b47-105">intenta convertir estos métodos locales en operaciones y funciones equivalentes que estén disponibles en el entorno de SQL.</span><span class="sxs-lookup"><span data-stu-id="54b47-105">tries to convert these local methods to equivalent operations and functions that are available inside the SQL environment.</span></span> <span data-ttu-id="54b47-106">La mayoría de los métodos y operadores de los tipos integrados de [!INCLUDE[dnprdnshort](../../../../../../includes/dnprdnshort-md.md)] tienen comandos SQL que son equivalentes directos.</span><span class="sxs-lookup"><span data-stu-id="54b47-106">Most methods and operators on [!INCLUDE[dnprdnshort](../../../../../../includes/dnprdnshort-md.md)] built-in types have direct translations to SQL commands.</span></span> <span data-ttu-id="54b47-107">Algunos se pueden generar a partir de las funciones que están disponibles.</span><span class="sxs-lookup"><span data-stu-id="54b47-107">Some can be produced from the functions that are available.</span></span> <span data-ttu-id="54b47-108">Aquellos que no se pueden generar, inician excepciones en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="54b47-108">Those that cannot be produced generate run-time exceptions.</span></span> <span data-ttu-id="54b47-109">Para obtener más información, consulte [asignación de tipos de CLR de SQL](../../../../../../docs/framework/data/adonet/sql/linq/sql-clr-type-mapping.md).</span><span class="sxs-lookup"><span data-stu-id="54b47-109">For more information, see [SQL-CLR Type Mapping](../../../../../../docs/framework/data/adonet/sql/linq/sql-clr-type-mapping.md).</span></span>  
  
 <span data-ttu-id="54b47-110">Cuando una consulta [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] no es suficiente para una tarea especializada, puede utilizar el método <xref:System.Data.Linq.DataContext.ExecuteQuery%2A> para ejecutar una consulta SQL y después convertir el resultado de la consulta directamente en objetos.</span><span class="sxs-lookup"><span data-stu-id="54b47-110">In cases where a [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] query is insufficient for a specialized task, you can use the <xref:System.Data.Linq.DataContext.ExecuteQuery%2A> method to execute a SQL query, and then convert the result of your query directly into objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="54b47-111">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="54b47-111">Example</span></span>  
 <span data-ttu-id="54b47-112">En el ejemplo siguiente, supongamos que los datos de la clase `Customer` ocupan dos tablas (customer1 y customer2).</span><span class="sxs-lookup"><span data-stu-id="54b47-112">In the following example, assume that the data for the `Customer` class is spread over two tables (customer1 and customer2).</span></span> <span data-ttu-id="54b47-113">La consulta devuelve una secuencia de objetos `Customer`.</span><span class="sxs-lookup"><span data-stu-id="54b47-113">The query returns a sequence of `Customer` objects.</span></span>  
  
 [!code-csharp[DLinqQuerying#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQuerying/cs/Program.cs#4)]
 [!code-vb[DLinqQuerying#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQuerying/vb/Module1.vb#4)]  
  
 <span data-ttu-id="54b47-114">Siempre que los nombres de columna en los resultados tabulares coincidan con las propiedades de columna de la clase de entidad, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] crea objetos a partir de cualquier consulta SQL.</span><span class="sxs-lookup"><span data-stu-id="54b47-114">As long as the column names in the tabular results match column properties of your entity class, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] creates your objects out of any SQL query.</span></span>  
  
## <a name="example"></a><span data-ttu-id="54b47-115">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="54b47-115">Example</span></span>  
 <span data-ttu-id="54b47-116">El método <xref:System.Data.Linq.DataContext.ExecuteQuery%2A> también permite el uso de parámetros.</span><span class="sxs-lookup"><span data-stu-id="54b47-116">The <xref:System.Data.Linq.DataContext.ExecuteQuery%2A> method also allows for parameters.</span></span> <span data-ttu-id="54b47-117">Utilice código como el siguiente para ejecutar una consulta parametrizada.</span><span class="sxs-lookup"><span data-stu-id="54b47-117">Use code such as the following to execute a parameterized query.</span></span>  
  
 [!code-csharp[DLinqQuerying#5](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQuerying/cs/Program.cs#5)]
 [!code-vb[DLinqQuerying#5](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQuerying/vb/Module1.vb#5)]  
  
 <span data-ttu-id="54b47-118">Los parámetros se expresan en el texto de la consulta con la misma notación con llaves que `Console.WriteLine()` y `String.Format()`.</span><span class="sxs-lookup"><span data-stu-id="54b47-118">The parameters are expressed in the query text by using the same curly notation used by `Console.WriteLine()` and `String.Format()`.</span></span> <span data-ttu-id="54b47-119">De hecho, `String.Format()` realmente se llama en la cadena de consulta proporcionada, sustituyendo los parámetros entre llaves con genera los nombres de parámetro como @p0, @p1 ..., @p(n).</span><span class="sxs-lookup"><span data-stu-id="54b47-119">In fact, `String.Format()` is actually called on the query string you provide, substituting the curly braced parameters with generated parameter names such as @p0, @p1 …, @p(n).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="54b47-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="54b47-120">See also</span></span>

- [<span data-ttu-id="54b47-121">Información general</span><span class="sxs-lookup"><span data-stu-id="54b47-121">Background Information</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/background-information.md)
- [<span data-ttu-id="54b47-122">Consulta de la base de datos</span><span class="sxs-lookup"><span data-stu-id="54b47-122">Querying the Database</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/querying-the-database.md)
