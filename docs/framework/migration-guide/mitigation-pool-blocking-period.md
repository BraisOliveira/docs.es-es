---
title: 'Mitigación: período de bloqueo del grupo'
ms.date: 03/30/2017
ms.assetid: 92d2de20-79be-4df1-b182-144143a8866a
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 01bd548bbafda34202705dda3dda148aae941e2b
ms.sourcegitcommit: 26f4a7697c32978f6a328c89dc4ea87034065989
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/28/2019
ms.locfileid: "66251100"
---
# <a name="mitigation-pool-blocking-period"></a><span data-ttu-id="941ff-102">Mitigación: período de bloqueo del grupo</span><span class="sxs-lookup"><span data-stu-id="941ff-102">Mitigation: Pool Blocking Period</span></span>
<span data-ttu-id="941ff-103">El período de bloqueo del grupo de conexiones se quito de las conexiones a bases de datos SQL de Azure.</span><span class="sxs-lookup"><span data-stu-id="941ff-103">The connection pool blocking period has been removed for connections to Azure SQL databases.</span></span>  
  
## <a name="additional-description"></a><span data-ttu-id="941ff-104">Descripción adicional</span><span class="sxs-lookup"><span data-stu-id="941ff-104">Additional description</span></span>  
 <span data-ttu-id="941ff-105">En .NET Framework 4.6.1 y versiones anteriores, cuando una aplicación encuentra un error de conexión transitorio al conectarse a una base de datos, no es posible reintentar rápidamente la conexión, porque el grupo de conexiones almacena el error en la caché y vuelve a generarlo entre 5 segundos y 1 minuto. Para obtener más información, consulte [Agrupaciones de conexiones de SQL Server (ADO.NET)](../../../docs/framework/data/adonet/sql-server-connection-pooling.md).</span><span class="sxs-lookup"><span data-stu-id="941ff-105">In the .NET Framework 4.6.1 and earlier versions, when an app encounters a transient connection failure when connecting to a database, the connection attempt cannot be retried quickly, because the connection pool caches the error and re-throws it for 5 seconds to 1 min. For more information, see [SQL Server Connection Pooling (ADO.NET)](../../../docs/framework/data/adonet/sql-server-connection-pooling.md).</span></span> <span data-ttu-id="941ff-106">Este comportamiento causa problemas en las conexiones a bases de datos SQL de Azure, las que habitualmente presentan errores transitorios de los que se recuperan dentro de unos pocos segundos.</span><span class="sxs-lookup"><span data-stu-id="941ff-106">This behavior is problematic for connections to Azure SQL databases, which often fail with transient errors that are typically recovered from within a few seconds.</span></span> <span data-ttu-id="941ff-107">La característica de bloqueo del grupo de conexiones significa que la aplicación no se puede conectar a la base de datos durante un período prolongado, incluso si la base de datos está disponible.</span><span class="sxs-lookup"><span data-stu-id="941ff-107">The connection pool blocking feature means that the app cannot connect to the database for an extensive period, even though the database is available.</span></span> <span data-ttu-id="941ff-108">Este comportamiento es problemático especialmente para las aplicaciones web que se conectan a las bases de datos SQL de Azure y que necesitan presentarse dentro de unos segundos.</span><span class="sxs-lookup"><span data-stu-id="941ff-108">This behavior is particularly problematic for web apps that connect to Azure SQL databases and that need to render within a few seconds.</span></span>  
  
 <span data-ttu-id="941ff-109">A partir de .NET Framework 4.6.2, para las solicitudes de apertura de conexión a bases de datos SQL de Azure conocidas (\*.database.windows.net, \*.database.chinacloudapi.cn, \*.database.usgovcloudapi.net, \*.database.cloudapi.de), los errores de apertura de conexión no se almacenan en la caché.</span><span class="sxs-lookup"><span data-stu-id="941ff-109">Starting with the .NET Framework 4.6.2, for connection open requests to known Azure SQL databases (\*.database.windows.net, \*.database.chinacloudapi.cn, \*.database.usgovcloudapi.net, \*.database.cloudapi.de), connection open errors are not cached.</span></span> <span data-ttu-id="941ff-110">Para todos los otros intentos de conexión, se sigue aplicando el período de bloqueo del grupo de conexiones.</span><span class="sxs-lookup"><span data-stu-id="941ff-110">For all other connection attempts, the connection pool blocking period continues to be enforced.</span></span>  
  
## <a name="impact"></a><span data-ttu-id="941ff-111">Impacto</span><span class="sxs-lookup"><span data-stu-id="941ff-111">Impact</span></span>  
 <span data-ttu-id="941ff-112">Este cambio permite que el intento de abrir una conexión a las bases de datos SQL de Azure se reintente de inmediato, lo que mejora el rendimiento de las aplicaciones habilitadas para la nube.</span><span class="sxs-lookup"><span data-stu-id="941ff-112">This change allows the connection open attempt to be retried immediately for Azure SQL databases, thereby improving the performance of cloud-enabled apps.</span></span>  
  
## <a name="mitigation"></a><span data-ttu-id="941ff-113">Mitigación</span><span class="sxs-lookup"><span data-stu-id="941ff-113">Mitigation</span></span>  
 <span data-ttu-id="941ff-114">En el caso de las aplicaciones a las que este cambio afecta negativamente, puede configurar el período de bloqueo del grupo de conexiones si establece la nueva propiedad <xref:System.Data.SqlClient.SqlConnectionStringBuilder.PoolBlockingPeriod%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="941ff-114">For apps that are adversely affected by this change, the connection pool blocking period can be configured by setting the new <xref:System.Data.SqlClient.SqlConnectionStringBuilder.PoolBlockingPeriod%2A?displayProperty=nameWithType> property.</span></span>  <span data-ttu-id="941ff-115">El valor de la propiedad es un miembro de la enumeración <xref:System.Data.SqlClient.PoolBlockingPeriod?displayProperty=nameWithType> que puede tener cualquiera de los tres valores:</span><span class="sxs-lookup"><span data-stu-id="941ff-115">The value of the property is a member of the <xref:System.Data.SqlClient.PoolBlockingPeriod?displayProperty=nameWithType> enumeration that can take either of three values:</span></span>  
  
- <xref:System.Data.SqlClient.PoolBlockingPeriod.AlwaysBlock?displayProperty=nameWithType>
  
- <xref:System.Data.SqlClient.PoolBlockingPeriod.Auto?displayProperty=nameWithType>
  
- <xref:System.Data.SqlClient.PoolBlockingPeriod.NeverBlock?displayProperty=nameWithType>
  
 <span data-ttu-id="941ff-116">El comportamiento anterior se puede restaurar al establecer la propiedad <xref:System.Data.SqlClient.SqlConnectionStringBuilder.PoolBlockingPeriod%2A> en <xref:System.Data.SqlClient.PoolBlockingPeriod.AlwaysBlock?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="941ff-116">The previous behavior can be restored by setting the <xref:System.Data.SqlClient.SqlConnectionStringBuilder.PoolBlockingPeriod%2A> property to <xref:System.Data.SqlClient.PoolBlockingPeriod.AlwaysBlock?displayProperty=nameWithType>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="941ff-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="941ff-117">See also</span></span>

- [<span data-ttu-id="941ff-118">Cambios en el runtime</span><span class="sxs-lookup"><span data-stu-id="941ff-118">Runtime Changes</span></span>](../../../docs/framework/migration-guide/runtime-changes-in-the-net-framework-4-6-2.md)
