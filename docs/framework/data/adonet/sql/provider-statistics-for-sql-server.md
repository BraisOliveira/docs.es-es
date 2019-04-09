---
title: Estadísticas de proveedor de SQL Server
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 429c9d09-92ac-46ec-829a-fbff0a9575a2
ms.openlocfilehash: b2b63719149c21eba493b3d8f2fc65309515bb0f
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59149102"
---
# <a name="provider-statistics-for-sql-server"></a><span data-ttu-id="ecc8f-102">Estadísticas de proveedor de SQL Server</span><span class="sxs-lookup"><span data-stu-id="ecc8f-102">Provider Statistics for SQL Server</span></span>
<span data-ttu-id="ecc8f-103">Desde .NET Framework versión 2.0, el proveedor de datos .NET Framework para servidor SQL Server admite estadísticas en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="ecc8f-103">Starting with the .NET Framework version 2.0, the .NET Framework Data Provider for SQL Server supports run-time statistics.</span></span> <span data-ttu-id="ecc8f-104">Para habilitar las estadísticas, establezca la propiedad <xref:System.Data.SqlClient.SqlConnection.StatisticsEnabled%2A> del objeto <xref:System.Data.SqlClient.SqlConnection> en `True` después de que haya creado un objeto de conexión válido.</span><span class="sxs-lookup"><span data-stu-id="ecc8f-104">You must enable statistics by setting the <xref:System.Data.SqlClient.SqlConnection.StatisticsEnabled%2A> property of the <xref:System.Data.SqlClient.SqlConnection> object to `True` after you have a valid connection object created.</span></span> <span data-ttu-id="ecc8f-105">Una vez habilitadas las estadísticas, puede revisarlas como una "instantánea en el tiempo" si recupera una referencia <xref:System.Collections.IDictionary> mediante el método <xref:System.Data.SqlClient.SqlConnection.RetrieveStatistics%2A> del objeto <xref:System.Data.SqlClient.SqlConnection>.</span><span class="sxs-lookup"><span data-stu-id="ecc8f-105">After statistics are enabled, you can review them as a "snapshot in time" by retrieving an <xref:System.Collections.IDictionary> reference via the <xref:System.Data.SqlClient.SqlConnection.RetrieveStatistics%2A> method of the <xref:System.Data.SqlClient.SqlConnection> object.</span></span> <span data-ttu-id="ecc8f-106">La enumeración tiene lugar a través de la lista como un conjunto de entradas de diccionario de pares de nombre y valor.</span><span class="sxs-lookup"><span data-stu-id="ecc8f-106">You enumerate through the list as a set of name/value pair dictionary entries.</span></span> <span data-ttu-id="ecc8f-107">Estos pares de nombre y valor están sin ordenar.</span><span class="sxs-lookup"><span data-stu-id="ecc8f-107">These name/value pairs are unordered.</span></span> <span data-ttu-id="ecc8f-108">En cualquier momento, puede llamar al método <xref:System.Data.SqlClient.SqlConnection.ResetStatistics%2A> del objeto <xref:System.Data.SqlClient.SqlConnection> para restablecer los contadores.</span><span class="sxs-lookup"><span data-stu-id="ecc8f-108">At any time, you can call the <xref:System.Data.SqlClient.SqlConnection.ResetStatistics%2A> method of the <xref:System.Data.SqlClient.SqlConnection> object to reset the counters.</span></span> <span data-ttu-id="ecc8f-109">Si la recopilación de estadísticas no se ha habilitado, no se genera una excepción.</span><span class="sxs-lookup"><span data-stu-id="ecc8f-109">If statistic gathering has not been enabled, an exception is not generated.</span></span> <span data-ttu-id="ecc8f-110">Además, si se llama a <xref:System.Data.SqlClient.SqlConnection.RetrieveStatistics%2A> sin haber llamado primero a <xref:System.Data.SqlClient.SqlConnection.StatisticsEnabled%2A>, los valores recuperados son los valores iniciales de cada entrada.</span><span class="sxs-lookup"><span data-stu-id="ecc8f-110">In addition, if <xref:System.Data.SqlClient.SqlConnection.RetrieveStatistics%2A> is called without <xref:System.Data.SqlClient.SqlConnection.StatisticsEnabled%2A> having been called first, the values retrieved are the initial values for each entry.</span></span> <span data-ttu-id="ecc8f-111">Si habilita las estadísticas, ejecuta la aplicación durante un rato y, a continuación, deshabilita las estadísticas, los valores recuperados reflejarán los valores recopilados hasta el momento en que se deshabilitaron las estadísticas.</span><span class="sxs-lookup"><span data-stu-id="ecc8f-111">If you enable statistics, run your application for a while, and then disable statistics, the values retrieved will reflect the values collected up to the point where statistics were disabled.</span></span> <span data-ttu-id="ecc8f-112">Todos los valores estadísticos recuperados son por cada conexión.</span><span class="sxs-lookup"><span data-stu-id="ecc8f-112">All statistical values gathered are on a per-connection basis.</span></span>  
  
## <a name="statistical-values-available"></a><span data-ttu-id="ecc8f-113">Valores estadísticos disponibles</span><span class="sxs-lookup"><span data-stu-id="ecc8f-113">Statistical Values Available</span></span>  
 <span data-ttu-id="ecc8f-114">Actualmente, hay 18 elementos diferentes disponibles con el proveedor de Microsoft SQL Server.</span><span class="sxs-lookup"><span data-stu-id="ecc8f-114">Currently there are 18 different items available from the Microsoft SQL Server provider.</span></span> <span data-ttu-id="ecc8f-115">El número de elementos disponibles que puede obtenerse a través de la **recuento** propiedad de la <xref:System.Collections.IDictionary> referencia devuelto por la interfaz <xref:System.Data.SqlClient.SqlConnection.RetrieveStatistics%2A>.</span><span class="sxs-lookup"><span data-stu-id="ecc8f-115">The number of items available can be accessed via the **Count** property of the <xref:System.Collections.IDictionary> interface reference returned by <xref:System.Data.SqlClient.SqlConnection.RetrieveStatistics%2A>.</span></span> <span data-ttu-id="ecc8f-116">Todos los contadores para estadísticas de proveedor utilizan common language runtime <xref:System.Int64> tipo (**largo** en C# y Visual Basic), que es el ancho de 64 bits.</span><span class="sxs-lookup"><span data-stu-id="ecc8f-116">All of the counters for provider statistics use the common language runtime <xref:System.Int64> type (**long** in C# and Visual Basic), which is 64 bits wide.</span></span> <span data-ttu-id="ecc8f-117">El valor máximo de la **int64** tipo de datos, como se define en el **int64. MaxValue** campo, es ((2^63)-1)).</span><span class="sxs-lookup"><span data-stu-id="ecc8f-117">The maximum value of the **int64** data type, as defined by the **int64.MaxValue** field, is ((2^63)-1)).</span></span> <span data-ttu-id="ecc8f-118">Cuando los valores de los contadores alcanzan este valor máximo, ya no se deben considerar precisos.</span><span class="sxs-lookup"><span data-stu-id="ecc8f-118">When the values for the counters reach this maximum value, they should no longer be considered accurate.</span></span> <span data-ttu-id="ecc8f-119">Esto significa que **int64. MaxValue**-1((2^63)-2) es realmente el valor válido para cualquier estadística.</span><span class="sxs-lookup"><span data-stu-id="ecc8f-119">This means that **int64.MaxValue**-1((2^63)-2) is effectively the greatest valid value for any statistic.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ecc8f-120">Para devolver estadísticas de proveedor se emplea un diccionario, dado que el número, los nombres y el orden de las estadísticas devueltas podrían cambiar en el futuro.</span><span class="sxs-lookup"><span data-stu-id="ecc8f-120">A dictionary is used for returning provider statistics because the number, names and order of the returned statistics may change in the future.</span></span> <span data-ttu-id="ecc8f-121">Las aplicaciones no deben depender de que se encuentre un valor específico en el diccionario, sino que, por el contrario, deben comprobar si el valor está ahí y bifurcarse en consecuencia.</span><span class="sxs-lookup"><span data-stu-id="ecc8f-121">Applications should not rely on a specific value being found in the dictionary, but should instead check whether the value is there and branch accordingly.</span></span>  
  
 <span data-ttu-id="ecc8f-122">En la siguiente tabla se describen los valores estadísticos actuales disponibles.</span><span class="sxs-lookup"><span data-stu-id="ecc8f-122">The following table describes the current statistical values available.</span></span> <span data-ttu-id="ecc8f-123">Tenga en cuenta que los nombres de claves de los valores individuales no se localizan en las versiones regionales de Microsoft .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="ecc8f-123">Note that the key names for the individual values are not localized across regional versions of the Microsoft .NET Framework.</span></span>  
  
|<span data-ttu-id="ecc8f-124">Nombre de clave</span><span class="sxs-lookup"><span data-stu-id="ecc8f-124">Key Name</span></span>|<span data-ttu-id="ecc8f-125">Descripción</span><span class="sxs-lookup"><span data-stu-id="ecc8f-125">Description</span></span>|  
|--------------|-----------------|  
|`BuffersReceived`|<span data-ttu-id="ecc8f-126">Devuelve el número de paquetes de flujo de datos en tabla (TDS) recibidos por el proveedor de SQL Server una vez que se ha iniciado la aplicación con el proveedor y se han habilitado las estadísticas.</span><span class="sxs-lookup"><span data-stu-id="ecc8f-126">Returns the number of tabular data stream (TDS) packets received by the provider from SQL Server after the application has started using the provider and has enabled statistics.</span></span>|  
|`BuffersSent`|<span data-ttu-id="ecc8f-127">Devuelve el número de paquetes TDS enviados a SQL Server por el proveedor una vez que se han habilitado las estadísticas.</span><span class="sxs-lookup"><span data-stu-id="ecc8f-127">Returns the number of TDS packets sent to SQL Server by the provider after statistics have been enabled.</span></span> <span data-ttu-id="ecc8f-128">Los comandos grandes pueden necesitar varios búferes.</span><span class="sxs-lookup"><span data-stu-id="ecc8f-128">Large commands can require multiple buffers.</span></span> <span data-ttu-id="ecc8f-129">Por ejemplo, si se envía un comando largo al servidor y necesita seis paquetes, `ServerRoundtrips` aumenta en uno y `BuffersSent` aumenta en seis.</span><span class="sxs-lookup"><span data-stu-id="ecc8f-129">For example, if a large command is sent to the server and it requires six packets, `ServerRoundtrips` is incremented by one and `BuffersSent` is incremented by six.</span></span>|  
|`BytesReceived`|<span data-ttu-id="ecc8f-130">Devuelve el número de bytes de datos de los paquetes TDS recibidos por el proveedor de SQL Server una vez que se ha iniciado la aplicación con el proveedor y se han habilitado las estadísticas.</span><span class="sxs-lookup"><span data-stu-id="ecc8f-130">Returns the number of bytes of data in the TDS packets received by the provider from SQL Server once the application has started using the provider and has enabled statistics.</span></span>|  
|`BytesSent`|<span data-ttu-id="ecc8f-131">Devuelve el número de bytes de datos enviados a SQL Server en paquetes TDS una vez que se ha iniciado la aplicación con el proveedor y se han habilitado las estadísticas.</span><span class="sxs-lookup"><span data-stu-id="ecc8f-131">Returns the number of bytes of data sent to SQL Server in TDS packets after the application has started using the provider and has enabled statistics.</span></span>|  
|`ConnectionTime`|<span data-ttu-id="ecc8f-132">El periodo de tiempo (en milisegundos) durante el cual la conexión ha estado abierta tras haber habilitado las estadísticas (el tiempo total de conexión si las estadísticas se han habilitado antes de abrir la conexión).</span><span class="sxs-lookup"><span data-stu-id="ecc8f-132">The amount of time (in milliseconds) that the connection has been opened after statistics have been enabled (total connection time if statistics were enabled before opening the connection).</span></span>|  
|`CursorOpens`|<span data-ttu-id="ecc8f-133">Devuelve el número de veces que se ha abierto un cursor a través de la conexión una vez que se ha iniciado la aplicación con el proveedor y se han habilitado las estadísticas.</span><span class="sxs-lookup"><span data-stu-id="ecc8f-133">Returns the number of times a cursor was open through the connection once the application has started using the provider and has enabled statistics.</span></span><br /><br /> <span data-ttu-id="ecc8f-134">Tenga en cuenta que los resultados de solo lectura y solo avance que devuelven las instrucciones SELECT no se consideran cursores y, por tanto, no afectan a este contador.</span><span class="sxs-lookup"><span data-stu-id="ecc8f-134">Note that read-only/forward-only results returned by SELECT statements are not considered cursors and thus do not affect this counter.</span></span>|  
|`ExecutionTime`|<span data-ttu-id="ecc8f-135">Devuelve el periodo de tiempo acumulado (en milisegundos) que ha invertido el proveedor en el procesamiento una vez que se han habilitado las estadísticas, lo que incluye el tiempo dedicado a esperar una respuesta del servidor, así como el tiempo dedicado a ejecutar código en el propio servidor.</span><span class="sxs-lookup"><span data-stu-id="ecc8f-135">Returns the cumulative amount of time (in milliseconds) that the provider has spent processing once statistics have been enabled, including the time spent waiting for replies from the server as well as the time spent executing code in the provider itself.</span></span><br /><br /> <span data-ttu-id="ecc8f-136">Las clases que incluyen código de tiempo son:</span><span class="sxs-lookup"><span data-stu-id="ecc8f-136">The classes that include timing code are:</span></span><br /><br /> <span data-ttu-id="ecc8f-137">SqlConnection</span><span class="sxs-lookup"><span data-stu-id="ecc8f-137">SqlConnection</span></span><br /><br /> <span data-ttu-id="ecc8f-138">SqlCommand</span><span class="sxs-lookup"><span data-stu-id="ecc8f-138">SqlCommand</span></span><br /><br /> <span data-ttu-id="ecc8f-139">SqlDataReader</span><span class="sxs-lookup"><span data-stu-id="ecc8f-139">SqlDataReader</span></span><br /><br /> <span data-ttu-id="ecc8f-140">SqlDataAdapter</span><span class="sxs-lookup"><span data-stu-id="ecc8f-140">SqlDataAdapter</span></span><br /><br /> <span data-ttu-id="ecc8f-141">SqlTransaction</span><span class="sxs-lookup"><span data-stu-id="ecc8f-141">SqlTransaction</span></span><br /><br /> <span data-ttu-id="ecc8f-142">SqlCommandBuilder</span><span class="sxs-lookup"><span data-stu-id="ecc8f-142">SqlCommandBuilder</span></span><br /><br /> <span data-ttu-id="ecc8f-143">Para mantener los miembros críticos para el rendimiento lo más pequeños posible, no se calcula el tiempo de los siguientes miembros:</span><span class="sxs-lookup"><span data-stu-id="ecc8f-143">To keep performance-critical members as small as possible, the following members are not timed:</span></span><br /><br /> <span data-ttu-id="ecc8f-144">SqlDataReader</span><span class="sxs-lookup"><span data-stu-id="ecc8f-144">SqlDataReader</span></span><br /><br /> <span data-ttu-id="ecc8f-145">este[] operador (todas las sobrecargas)</span><span class="sxs-lookup"><span data-stu-id="ecc8f-145">this[] operator (all overloads)</span></span><br /><br /> <span data-ttu-id="ecc8f-146">GetBoolean</span><span class="sxs-lookup"><span data-stu-id="ecc8f-146">GetBoolean</span></span><br /><br /> <span data-ttu-id="ecc8f-147">GetChar</span><span class="sxs-lookup"><span data-stu-id="ecc8f-147">GetChar</span></span><br /><br /> <span data-ttu-id="ecc8f-148">GetDateTime</span><span class="sxs-lookup"><span data-stu-id="ecc8f-148">GetDateTime</span></span><br /><br /> <span data-ttu-id="ecc8f-149">GetDecimal</span><span class="sxs-lookup"><span data-stu-id="ecc8f-149">GetDecimal</span></span><br /><br /> <span data-ttu-id="ecc8f-150">GetDouble</span><span class="sxs-lookup"><span data-stu-id="ecc8f-150">GetDouble</span></span><br /><br /> <span data-ttu-id="ecc8f-151">GetFloat</span><span class="sxs-lookup"><span data-stu-id="ecc8f-151">GetFloat</span></span><br /><br /> <span data-ttu-id="ecc8f-152">GetGuid</span><span class="sxs-lookup"><span data-stu-id="ecc8f-152">GetGuid</span></span><br /><br /> <span data-ttu-id="ecc8f-153">GetInt16</span><span class="sxs-lookup"><span data-stu-id="ecc8f-153">GetInt16</span></span><br /><br /> <span data-ttu-id="ecc8f-154">GetInt32</span><span class="sxs-lookup"><span data-stu-id="ecc8f-154">GetInt32</span></span><br /><br /> <span data-ttu-id="ecc8f-155">GetInt64</span><span class="sxs-lookup"><span data-stu-id="ecc8f-155">GetInt64</span></span><br /><br /> <span data-ttu-id="ecc8f-156">GetName</span><span class="sxs-lookup"><span data-stu-id="ecc8f-156">GetName</span></span><br /><br /> <span data-ttu-id="ecc8f-157">GetOrdinal</span><span class="sxs-lookup"><span data-stu-id="ecc8f-157">GetOrdinal</span></span><br /><br /> <span data-ttu-id="ecc8f-158">GetSqlBinary</span><span class="sxs-lookup"><span data-stu-id="ecc8f-158">GetSqlBinary</span></span><br /><br /> <span data-ttu-id="ecc8f-159">GetSqlBoolean </span><span class="sxs-lookup"><span data-stu-id="ecc8f-159">GetSqlBoolean</span></span><br /><br /> <span data-ttu-id="ecc8f-160">GetSqlByte</span><span class="sxs-lookup"><span data-stu-id="ecc8f-160">GetSqlByte</span></span><br /><br /> <span data-ttu-id="ecc8f-161">GetSqlDateTime</span><span class="sxs-lookup"><span data-stu-id="ecc8f-161">GetSqlDateTime</span></span><br /><br /> <span data-ttu-id="ecc8f-162">GetSqlDecimal</span><span class="sxs-lookup"><span data-stu-id="ecc8f-162">GetSqlDecimal</span></span><br /><br /> <span data-ttu-id="ecc8f-163">GetSqlDouble</span><span class="sxs-lookup"><span data-stu-id="ecc8f-163">GetSqlDouble</span></span><br /><br /> <span data-ttu-id="ecc8f-164">GetSqlGuid</span><span class="sxs-lookup"><span data-stu-id="ecc8f-164">GetSqlGuid</span></span><br /><br /> <span data-ttu-id="ecc8f-165">GetSqlInt16</span><span class="sxs-lookup"><span data-stu-id="ecc8f-165">GetSqlInt16</span></span><br /><br /> <span data-ttu-id="ecc8f-166">GetSqlInt32</span><span class="sxs-lookup"><span data-stu-id="ecc8f-166">GetSqlInt32</span></span><br /><br /> <span data-ttu-id="ecc8f-167">GetSqlInt64</span><span class="sxs-lookup"><span data-stu-id="ecc8f-167">GetSqlInt64</span></span><br /><br /> <span data-ttu-id="ecc8f-168">GetSqlMoney </span><span class="sxs-lookup"><span data-stu-id="ecc8f-168">GetSqlMoney</span></span><br /><br /> <span data-ttu-id="ecc8f-169">GetSqlSingle </span><span class="sxs-lookup"><span data-stu-id="ecc8f-169">GetSqlSingle</span></span><br /><br /> <span data-ttu-id="ecc8f-170">GetSqlString </span><span class="sxs-lookup"><span data-stu-id="ecc8f-170">GetSqlString</span></span><br /><br /> <span data-ttu-id="ecc8f-171">GetString</span><span class="sxs-lookup"><span data-stu-id="ecc8f-171">GetString</span></span><br /><br /> <span data-ttu-id="ecc8f-172">IsDBNull</span><span class="sxs-lookup"><span data-stu-id="ecc8f-172">IsDBNull</span></span>|  
|`IduCount`|<span data-ttu-id="ecc8f-173">Devuelve el número total de instrucciones INSERT, DELETE y UPDATE ejecutadas a través de la conexión una vez que se ha iniciado la aplicación con el proveedor y se han habilitado las estadísticas.</span><span class="sxs-lookup"><span data-stu-id="ecc8f-173">Returns the total number of INSERT, DELETE, and UPDATE statements executed through the connection once the application has started using the provider and has enabled statistics.</span></span>|  
|`IduRows`|<span data-ttu-id="ecc8f-174">Devuelve el número total de filas afectadas por las instrucciones INSERT, DELETE y UPDATE ejecutadas a través de la conexión una vez que se ha iniciado la aplicación con el proveedor y se han habilitado las estadísticas.</span><span class="sxs-lookup"><span data-stu-id="ecc8f-174">Returns the total number of rows affected by INSERT, DELETE, and UPDATE statements executed through the connection once the application has started using the provider and has enabled statistics.</span></span>|  
|`NetworkServerTime`|<span data-ttu-id="ecc8f-175">Devuelve el periodo de tiempo acumulado (en milisegundos) que el proveedor ha dedicado a esperar una respuesta del servidor una vez que se ha iniciado la aplicación con el proveedor y se han habilitado las estadísticas.</span><span class="sxs-lookup"><span data-stu-id="ecc8f-175">Returns the cumulative amount of time (in milliseconds) that the provider spent waiting for replies from the server once the application has started using the provider and has enabled statistics.</span></span>|  
|`PreparedExecs`|<span data-ttu-id="ecc8f-176">Devuelve el número de comandos preparados ejecutados a través de la conexión una vez que se ha iniciado la aplicación con el proveedor y se han habilitado las estadísticas.</span><span class="sxs-lookup"><span data-stu-id="ecc8f-176">Returns the number of prepared commands executed through the connection once the application has started using the provider and has enabled statistics.</span></span>|  
|`Prepares`|<span data-ttu-id="ecc8f-177">Devuelve el número de instrucciones preparadas a través de la conexión una vez que se ha iniciado la aplicación con el proveedor y se han habilitado las estadísticas.</span><span class="sxs-lookup"><span data-stu-id="ecc8f-177">Returns the number of statements prepared through the connection once the application has started using the provider and has enabled statistics.</span></span>|  
|`SelectCount`|<span data-ttu-id="ecc8f-178">Devuelve el número de instrucciones SELECT ejecutadas a través de la conexión una vez que se ha iniciado la aplicación con el proveedor y se han habilitado las estadísticas.</span><span class="sxs-lookup"><span data-stu-id="ecc8f-178">Returns the number of SELECT statements executed through the connection once the application has started using the provider and has enabled statistics.</span></span> <span data-ttu-id="ecc8f-179">Esto incluye las instrucciones FETCH, para recuperar filas a partir de cursores, y el número de instrucciones SELECT que se actualizan cuando se llega al final de un <xref:System.Data.SqlClient.SqlDataReader>.</span><span class="sxs-lookup"><span data-stu-id="ecc8f-179">This includes FETCH statements to retrieve rows from cursors, and the count for SELECT statements is updated when the end of a <xref:System.Data.SqlClient.SqlDataReader> is reached.</span></span>|  
|`SelectRows`|<span data-ttu-id="ecc8f-180">Devuelve el número de filas seleccionadas una vez que se ha iniciado la aplicación con el proveedor y se han habilitado las estadísticas.</span><span class="sxs-lookup"><span data-stu-id="ecc8f-180">Returns the number of rows selected once the application has started using the provider and has enabled statistics.</span></span> <span data-ttu-id="ecc8f-181">Este contador refleja todas las filas que generan las instrucciones SQL, incluso las que no ha consumido realmente la persona que llama.</span><span class="sxs-lookup"><span data-stu-id="ecc8f-181">This counter reflects all the rows generated by SQL statements, even those that were not actually consumed by the caller.</span></span> <span data-ttu-id="ecc8f-182">Por ejemplo, cerrar un lector de datos antes de leer todo el conjunto de resultados no afectará al recuento.</span><span class="sxs-lookup"><span data-stu-id="ecc8f-182">For example, closing a data reader before reading the entire result set would not affect the count.</span></span> <span data-ttu-id="ecc8f-183">Aquí se incluyen las filas recuperadas con cursores a través de instrucciones FETCH.</span><span class="sxs-lookup"><span data-stu-id="ecc8f-183">This includes the rows retrieved from cursors through FETCH statements.</span></span>|  
|`ServerRoundtrips`|<span data-ttu-id="ecc8f-184">Devuelve el número de veces que la conexión ha enviado comandos al servidor y ha obtenido una respuesta una vez que se ha iniciado la aplicación con el proveedor y se han habilitado las estadísticas.</span><span class="sxs-lookup"><span data-stu-id="ecc8f-184">Returns the number of times the connection sent commands to the server and got a reply back once the application has started using the provider and has enabled statistics.</span></span>|  
|`SumResultSets`|<span data-ttu-id="ecc8f-185">Devuelve el número de conjuntos de resultados que se han utilizado una vez que se ha iniciado la aplicación con el proveedor y se han habilitado las estadísticas.</span><span class="sxs-lookup"><span data-stu-id="ecc8f-185">Returns the number of result sets that have been used once the application has started using the provider and has enabled statistics.</span></span> <span data-ttu-id="ecc8f-186">Por ejemplo, esto incluiría cualquier conjunto de resultados devuelto al cliente.</span><span class="sxs-lookup"><span data-stu-id="ecc8f-186">For example this would include any result set returned to the client.</span></span> <span data-ttu-id="ecc8f-187">En el caso de cursores, cada operación FETCH y BLOCK-FETCH se considera un conjunto de resultados independiente.</span><span class="sxs-lookup"><span data-stu-id="ecc8f-187">For cursors, each fetch or block-fetch operation is considered an independent result set.</span></span>|  
|`Transactions`|<span data-ttu-id="ecc8f-188">Devuelve el número de transacciones de usuario iniciadas una vez que se ha iniciado la aplicación con el proveedor y se han habilitado las estadísticas. Esto incluye las transacciones deshechas.</span><span class="sxs-lookup"><span data-stu-id="ecc8f-188">Returns the number of user transactions started once the application has started using the provider and has enabled statistics, including rollbacks.</span></span> <span data-ttu-id="ecc8f-189">Si una conexión se ejecuta con la confirmación automática activada, cada comando se considera una transacción.</span><span class="sxs-lookup"><span data-stu-id="ecc8f-189">If a connection is running with auto commit on, each command is considered a transaction.</span></span><br /><br /> <span data-ttu-id="ecc8f-190">Este contador aumenta el recuento de transacciones tan pronto se ejecuta una transacción BEGIN TRAN, con independencia de si la transacción se confirma o revierte en un momento posterior.</span><span class="sxs-lookup"><span data-stu-id="ecc8f-190">This counter increments the transaction count as soon as a BEGIN TRAN statement is executed, regardless of whether the transaction is committed or rolled back later.</span></span>|  
|`UnpreparedExecs`|<span data-ttu-id="ecc8f-191">Devuelve el número de instrucciones no preparadas ejecutadas a través de la conexión una vez que se ha iniciado la aplicación con el proveedor y se han habilitado las estadísticas.</span><span class="sxs-lookup"><span data-stu-id="ecc8f-191">Returns the number of unprepared statements executed through the connection once the application has started using the provider and has enabled statistics.</span></span>|  
  
### <a name="retrieving-a-value"></a><span data-ttu-id="ecc8f-192">Recuperación de un valor</span><span class="sxs-lookup"><span data-stu-id="ecc8f-192">Retrieving a Value</span></span>  
 <span data-ttu-id="ecc8f-193">La siguiente aplicación de consola muestra cómo habilitar las estadísticas en una conexión, recuperar cuatro valores estadísticos individuales y escribirlos en la ventana de la consola.</span><span class="sxs-lookup"><span data-stu-id="ecc8f-193">The following console application shows how to enable statistics on a connection, retrieve four individual statistic values, and write them out to the console window.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ecc8f-194">En el ejemplo siguiente se usa el ejemplo **AdventureWorks** incluido con SQL Server de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="ecc8f-194">The following example uses the sample **AdventureWorks** database included with SQL Server.</span></span> <span data-ttu-id="ecc8f-195">La cadena de conexión proporcionada en el código de ejemplo asume que la base de datos está instalada y disponible en el equipo local.</span><span class="sxs-lookup"><span data-stu-id="ecc8f-195">The connection string provided in the sample code assumes the database is installed and available on the local computer.</span></span> <span data-ttu-id="ecc8f-196">Modifique la cadena de conexión según sea necesario para su entorno.</span><span class="sxs-lookup"><span data-stu-id="ecc8f-196">Modify the connection string as necessary for your environment.</span></span>  
  
```vb  
Option Strict On  
  
Imports System  
Imports System.Collections  
Imports System.Data  
Imports System.Data.SqlClient  
  
Module Module1  
  
  Sub Main()  
    Dim connectionString As String = GetConnectionString()  
  
    Using awConnection As New SqlConnection(connectionString)  
      ' StatisticsEnabled is False by default.  
      ' It must be set to True to start the   
      ' statistic collection process.  
      awConnection.StatisticsEnabled = True  
  
      Dim productSQL As String = "SELECT * FROM Production.Product"  
      Dim productAdapter As _  
          New SqlDataAdapter(productSQL, awConnection)  
  
      Dim awDataSet As New DataSet()  
  
      awConnection.Open()  
  
      productAdapter.Fill(awDataSet, "ProductTable")  
  
      ' Retrieve the current statistics as  
      ' a collection of values at this point  
      ' and time.  
      Dim currentStatistics As IDictionary = _  
          awConnection.RetrieveStatistics()  
  
      Console.WriteLine("Total Counters: " & _  
          currentStatistics.Count.ToString())  
      Console.WriteLine()  
  
      ' Retrieve a few individual values  
      ' related to the previous command.  
      Dim bytesReceived As Long = _  
          CLng(currentStatistics.Item("BytesReceived"))  
      Dim bytesSent As Long = _  
          CLng(currentStatistics.Item("BytesSent"))  
      Dim selectCount As Long = _  
          CLng(currentStatistics.Item("SelectCount"))  
      Dim selectRows As Long = _  
          CLng(currentStatistics.Item("SelectRows"))  
  
      Console.WriteLine("BytesReceived: " & bytesReceived.ToString())  
      Console.WriteLine("BytesSent: " & bytesSent.ToString())  
      Console.WriteLine("SelectCount: " & selectCount.ToString())  
      Console.WriteLine("SelectRows: " & selectRows.ToString())  
  
      Console.WriteLine()  
      Console.WriteLine("Press any key to continue")  
      Console.ReadLine()  
    End Using  
  
  End Sub  
  
  Function GetConnectionString() As String  
    ' To avoid storing the connection string in your code,  
    ' you can retrive it from a configuration file.  
    Return "Data Source=localhost;Integrated Security=SSPI;" & _  
      "Initial Catalog=AdventureWorks"  
  End Function  
End Module  
```  
  
```csharp  
using System;  
using System.Collections;  
using System.Collections.Generic;  
using System.Data;  
using System.Data.SqlClient;  
  
namespace CS_Stats_Console_GetValue  
{  
  class Program  
  {  
    static void Main(string[] args)  
    {  
      string connectionString = GetConnectionString();  
  
      using (SqlConnection awConnection =   
        new SqlConnection(connectionString))  
      {  
        // StatisticsEnabled is False by default.  
        // It must be set to True to start the   
        // statistic collection process.  
        awConnection.StatisticsEnabled = true;  
  
        string productSQL = "SELECT * FROM Production.Product";  
        SqlDataAdapter productAdapter =   
          new SqlDataAdapter(productSQL, awConnection);  
  
        DataSet awDataSet = new DataSet();  
  
        awConnection.Open();  
  
        productAdapter.Fill(awDataSet, "ProductTable");  
        // Retrieve the current statistics as  
        // a collection of values at this point  
        // and time.  
        IDictionary currentStatistics =  
          awConnection.RetrieveStatistics();  
  
        Console.WriteLine("Total Counters: " +  
          currentStatistics.Count.ToString());  
        Console.WriteLine();  
  
        // Retrieve a few individual values  
        // related to the previous command.  
        long bytesReceived =  
            (long) currentStatistics["BytesReceived"];  
        long bytesSent =  
            (long) currentStatistics["BytesSent"];  
        long selectCount =  
            (long) currentStatistics["SelectCount"];  
        long selectRows =  
            (long) currentStatistics["SelectRows"];  
  
        Console.WriteLine("BytesReceived: " +  
            bytesReceived.ToString());  
        Console.WriteLine("BytesSent: " +  
            bytesSent.ToString());  
        Console.WriteLine("SelectCount: " +  
            selectCount.ToString());  
        Console.WriteLine("SelectRows: " +  
            selectRows.ToString());  
  
        Console.WriteLine();  
        Console.WriteLine("Press any key to continue");  
        Console.ReadLine();  
      }  
  
    }  
    private static string GetConnectionString()  
    {  
      // To avoid storing the connection string in your code,  
      // you can retrive it from a configuration file.  
      return "Data Source=localhost;Integrated Security=SSPI;" +   
        "Initial Catalog=AdventureWorks";  
    }  
  }  
}  
```  
  
### <a name="retrieving-all-values"></a><span data-ttu-id="ecc8f-197">Recuperación de todos los valores</span><span class="sxs-lookup"><span data-stu-id="ecc8f-197">Retrieving All Values</span></span>  
 <span data-ttu-id="ecc8f-198">La siguiente aplicación de consola muestra cómo habilitar las estadísticas en una conexión, recuperar todos los valores estadísticos disponibles y escribirlos en la ventana de la consola.</span><span class="sxs-lookup"><span data-stu-id="ecc8f-198">The following console application shows how to enable statistics on a connection, retrieve all available statistic values using the enumerator, and write them to the console window.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ecc8f-199">En el ejemplo siguiente se usa el ejemplo **AdventureWorks** incluido con SQL Server de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="ecc8f-199">The following example uses the sample **AdventureWorks** database included with SQL Server.</span></span> <span data-ttu-id="ecc8f-200">La cadena de conexión proporcionada en el código de ejemplo asume que la base de datos está instalada y disponible en el equipo local.</span><span class="sxs-lookup"><span data-stu-id="ecc8f-200">The connection string provided in the sample code assumes the database is installed and available on the local computer.</span></span> <span data-ttu-id="ecc8f-201">Modifique la cadena de conexión según sea necesario para su entorno.</span><span class="sxs-lookup"><span data-stu-id="ecc8f-201">Modify the connection string as necessary for your environment.</span></span>  
  
```vb  
Option Strict On  
  
Imports System  
Imports System.Collections  
Imports System.Data  
Imports System.Data.SqlClient  
  
Module Module1  
  Sub Main()  
    Dim connectionString As String = GetConnectionString()  
  
    Using awConnection As New SqlConnection(connectionString)  
      ' StatisticsEnabled is False by default.  
      ' It must be set to True to start the   
      ' statistic collection process.  
      awConnection.StatisticsEnabled = True  
  
      Dim productSQL As String = "SELECT * FROM Production.Product"  
      Dim productAdapter As _  
          New SqlDataAdapter(productSQL, awConnection)  
  
      Dim awDataSet As New DataSet()  
  
      awConnection.Open()  
  
      productAdapter.Fill(awDataSet, "ProductTable")  
  
      ' Retrieve the current statistics as  
      ' a collection of values at this point  
      ' and time.  
      Dim currentStatistics As IDictionary = _  
          awConnection.RetrieveStatistics()  
  
      Console.WriteLine("Total Counters: " & _  
          currentStatistics.Count.ToString())  
      Console.WriteLine()  
  
      Console.WriteLine("Key Name and Value")  
  
      ' Note the entries are unsorted.  
      For Each entry As DictionaryEntry In currentStatistics  
        Console.WriteLine(entry.Key.ToString() & _  
            ": " & entry.Value.ToString())  
      Next  
  
      Console.WriteLine()  
      Console.WriteLine("Press any key to continue")  
      Console.ReadLine()  
    End Using  
  
  End Sub  
  
  Function GetConnectionString() As String  
    ' To avoid storing the connection string in your code,  
    ' you can retrive it from a configuration file.  
    Return "Data Source=localhost;Integrated Security=SSPI;" & _  
      "Initial Catalog=AdventureWorks"  
  End Function  
End Module  
```  
  
```csharp  
using System;  
using System.Collections;  
using System.Collections.Generic;  
using System.Text;  
using System.Data;  
using System.Data.SqlClient;  
  
namespace CS_Stats_Console_GetAll  
{  
  class Program  
  {  
    static void Main(string[] args)  
    {  
      string connectionString = GetConnectionString();  
  
      using (SqlConnection awConnection =   
        new SqlConnection(connectionString))  
      {  
        // StatisticsEnabled is False by default.  
        // It must be set to True to start the   
        // statistic collection process.  
        awConnection.StatisticsEnabled = true;  
  
        string productSQL = "SELECT * FROM Production.Product";  
        SqlDataAdapter productAdapter =  
            new SqlDataAdapter(productSQL, awConnection);  
  
        DataSet awDataSet = new DataSet();  
  
        awConnection.Open();  
  
        productAdapter.Fill(awDataSet, "ProductTable");  
  
        // Retrieve the current statistics as  
        // a collection of values at this point  
        // and time.  
        IDictionary currentStatistics =  
            awConnection.RetrieveStatistics();  
  
        Console.WriteLine("Total Counters: " +  
            currentStatistics.Count.ToString());  
        Console.WriteLine();  
  
        Console.WriteLine("Key Name and Value");  
  
        // Note the entries are unsorted.  
        foreach (DictionaryEntry entry in currentStatistics)  
        {  
          Console.WriteLine(entry.Key.ToString() +  
              ": " + entry.Value.ToString());  
        }  
  
        Console.WriteLine();  
        Console.WriteLine("Press any key to continue");  
        Console.ReadLine();  
      }  
  
    }  
    private static string GetConnectionString()  
    {  
      // To avoid storing the connection string in your code,  
      // you can retrive it from a configuration file.  
      return "Data Source=localhost;Integrated Security=SSPI;" +   
        "Initial Catalog=AdventureWorks";  
    }  
  }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="ecc8f-202">Vea también</span><span class="sxs-lookup"><span data-stu-id="ecc8f-202">See also</span></span>

- [<span data-ttu-id="ecc8f-203">SQL Server y ADO.NET</span><span class="sxs-lookup"><span data-stu-id="ecc8f-203">SQL Server and ADO.NET</span></span>](../../../../../docs/framework/data/adonet/sql/index.md)
- [<span data-ttu-id="ecc8f-204">Proveedores administrados de ADO.NET y centro de desarrolladores de DataSet</span><span class="sxs-lookup"><span data-stu-id="ecc8f-204">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
