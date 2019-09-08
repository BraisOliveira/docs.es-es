---
title: SqlDependency en una aplicación ASP.NET
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: ff226ce3-f6b5-47a1-8d22-dc78b67e07f5
ms.openlocfilehash: f3e28adc2cf7c24cee9ee344eb78404f01b79793
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70780721"
---
# <a name="sqldependency-in-an-aspnet-application"></a><span data-ttu-id="12ffa-102">SqlDependency en una aplicación ASP.NET</span><span class="sxs-lookup"><span data-stu-id="12ffa-102">SqlDependency in an ASP.NET Application</span></span>
<span data-ttu-id="12ffa-103">En el ejemplo de esta sección se muestra cómo utilizar <xref:System.Data.SqlClient.SqlDependency> de forma indirecta aprovechando el objeto <xref:System.Web.Caching.SqlCacheDependency> de ASP:NET.</span><span class="sxs-lookup"><span data-stu-id="12ffa-103">The example in this section shows how to use <xref:System.Data.SqlClient.SqlDependency> indirectly by leveraging the ASP.NET <xref:System.Web.Caching.SqlCacheDependency> object.</span></span> <span data-ttu-id="12ffa-104">El objeto <xref:System.Web.Caching.SqlCacheDependency> utiliza <xref:System.Data.SqlClient.SqlDependency> para escuchar notificaciones y de actualizar correctamente la caché.</span><span class="sxs-lookup"><span data-stu-id="12ffa-104">The <xref:System.Web.Caching.SqlCacheDependency> object uses a <xref:System.Data.SqlClient.SqlDependency> to listen for notifications and correctly update the cache.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="12ffa-105">En el código de ejemplo se supone que ha habilitado las notificaciones de consulta ejecutando los scripts en [habilitando las notificaciones de consulta](enabling-query-notifications.md).</span><span class="sxs-lookup"><span data-stu-id="12ffa-105">The sample code assumes that you have enabled query notifications by executing the scripts in [Enabling Query Notifications](enabling-query-notifications.md).</span></span>  
  
## <a name="about-the-sample-application"></a><span data-ttu-id="12ffa-106">Acerca de la aplicación de ejemplo</span><span class="sxs-lookup"><span data-stu-id="12ffa-106">About the Sample Application</span></span>  
 <span data-ttu-id="12ffa-107">La aplicación de ejemplo utiliza una única página web de ASP.net para mostrar información de productos de la base de <xref:System.Web.UI.WebControls.GridView> datos de SQL Server AdventureWorks en un control.</span><span class="sxs-lookup"><span data-stu-id="12ffa-107">The sample application uses a single ASP.NET Web page to display product information from the **AdventureWorks** SQL Server database in a <xref:System.Web.UI.WebControls.GridView> control.</span></span> <span data-ttu-id="12ffa-108">Cuando se carga la página, el código escribe la hora actual en un control <xref:System.Web.UI.WebControls.Label>.</span><span class="sxs-lookup"><span data-stu-id="12ffa-108">When the page loads, the code writes the current time to a <xref:System.Web.UI.WebControls.Label> control.</span></span> <span data-ttu-id="12ffa-109">A continuación, se define un objeto <xref:System.Web.Caching.SqlCacheDependency> y se establecen las propiedades del objeto <xref:System.Web.Caching.Cache> para almacenar los datos de la caché durante tres minutos como máximo.</span><span class="sxs-lookup"><span data-stu-id="12ffa-109">It then defines a <xref:System.Web.Caching.SqlCacheDependency> object and sets properties on the <xref:System.Web.Caching.Cache> object to store the cache data for up to three minutes.</span></span> <span data-ttu-id="12ffa-110">Entonces el código se conecta a la base de datos y recupera los datos.</span><span class="sxs-lookup"><span data-stu-id="12ffa-110">The code then connects to the database and retrieves the data.</span></span> <span data-ttu-id="12ffa-111">Cuando la página está cargada y la aplicación se está ejecutando, ASP.NET recuperará datos de la caché, lo cual podrá comprobar si observa que la hora de la página no cambia.</span><span class="sxs-lookup"><span data-stu-id="12ffa-111">When the page is loaded and the application is running ASP.NET will retrieve data from the cache, which you can verify by noting that the time on the page does not change.</span></span> <span data-ttu-id="12ffa-112">Si los datos que se supervisan cambian, ASP.NET invalida la caché y vuelve a llenar el control `GridView` con datos nuevos, actualizando la hora que se muestra en el control `Label`.</span><span class="sxs-lookup"><span data-stu-id="12ffa-112">If the data being monitored changes, ASP.NET invalidates the cache and repopulate the `GridView` control with fresh data, updating the time displayed in the `Label` control.</span></span>  
  
## <a name="creating-the-sample-application"></a><span data-ttu-id="12ffa-113">Crear la aplicación de ejemplo</span><span class="sxs-lookup"><span data-stu-id="12ffa-113">Creating the Sample Application</span></span>  
 <span data-ttu-id="12ffa-114">Para crear y ejecutar la aplicación de ejemplo, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="12ffa-114">Follow these steps to create and run the sample application:</span></span>  
  
1. <span data-ttu-id="12ffa-115">Cree un nuevo sitio web ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="12ffa-115">Create a new ASP.NET Web site.</span></span>  
  
2. <span data-ttu-id="12ffa-116">Agregue un control <xref:System.Web.UI.WebControls.Label> y <xref:System.Web.UI.WebControls.GridView> a la página Default.aspx.</span><span class="sxs-lookup"><span data-stu-id="12ffa-116">Add a <xref:System.Web.UI.WebControls.Label> and a <xref:System.Web.UI.WebControls.GridView> control to the Default.aspx page.</span></span>  
  
3. <span data-ttu-id="12ffa-117">Abra el módulo de clase de la página y agregue las siguientes directivas:</span><span class="sxs-lookup"><span data-stu-id="12ffa-117">Open the page's class module and add the following directives:</span></span>  
  
    ```vb  
    Option Strict On  
    Option Explicit On  
  
    Imports System.Data.SqlClient  
    ```  
  
    ```csharp  
    using System.Data.SqlClient;  
    using System.Web.Caching;  
    ```  
  
4. <span data-ttu-id="12ffa-118">Agregue el siguiente código al evento `Page_Load` de la página:</span><span class="sxs-lookup"><span data-stu-id="12ffa-118">Add the following code in the page's `Page_Load` event:</span></span>  
  
     [!code-csharp[DataWorks SqlDependency.AspNet#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlDependency.AspNet/CS/Default.aspx.cs#1)]
     [!code-vb[DataWorks SqlDependency.AspNet#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlDependency.AspNet/VB/Default.aspx.vb#1)]  
  
5. <span data-ttu-id="12ffa-119">Agregue dos métodos del asistente: `GetConnectionString` y `GetSQL`.</span><span class="sxs-lookup"><span data-stu-id="12ffa-119">Add two helper methods, `GetConnectionString` and `GetSQL`.</span></span> <span data-ttu-id="12ffa-120">La cadena de conexión definida utiliza seguridad integrada.</span><span class="sxs-lookup"><span data-stu-id="12ffa-120">The connection string defined uses integrated security.</span></span> <span data-ttu-id="12ffa-121">Tendrá que comprobar que la cuenta que está usando tiene los permisos de base de datos necesarios y que la base de datos de ejemplo, **AdventureWorks**, tiene habilitadas las notificaciones.</span><span class="sxs-lookup"><span data-stu-id="12ffa-121">You will need to verify that the account you are using has the necessary database permissions and that the sample database, **AdventureWorks**, has notifications enabled.</span></span>
  
     [!code-csharp[DataWorks SqlDependency.AspNet#2](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlDependency.AspNet/CS/Default.aspx.cs#2)]
     [!code-vb[DataWorks SqlDependency.AspNet#2](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlDependency.AspNet/VB/Default.aspx.vb#2)]  
  
### <a name="testing-the-application"></a><span data-ttu-id="12ffa-122">Probar la aplicación</span><span class="sxs-lookup"><span data-stu-id="12ffa-122">Testing the Application</span></span>  
 <span data-ttu-id="12ffa-123">La aplicación almacena en caché los datos mostrados en el formulario web y los actualiza cada tres minutos si no hay ninguna actividad</span><span class="sxs-lookup"><span data-stu-id="12ffa-123">The application caches the data displayed on the Web form and refreshes it every three minutes if there is no activity.</span></span> <span data-ttu-id="12ffa-124">Si se produce un cambio en la base de datos, la caché se actualiza inmediatamente.</span><span class="sxs-lookup"><span data-stu-id="12ffa-124">If a change occurs to the database, the cache is refreshed immediately.</span></span> <span data-ttu-id="12ffa-125">Ejecute la aplicación desde Visual Studio, que carga la página en el explorador.</span><span class="sxs-lookup"><span data-stu-id="12ffa-125">Run the application from Visual Studio, which loads the page into the browser.</span></span> <span data-ttu-id="12ffa-126">La hora de actualización de la caché que se muestra indica la hora de la última actualización.</span><span class="sxs-lookup"><span data-stu-id="12ffa-126">The cache refresh time displayed indicates when the cache was last refreshed.</span></span> <span data-ttu-id="12ffa-127">Espere tres minutos y, a continuación, actualice la página, lo que dará lugar a un evento postback de datos.</span><span class="sxs-lookup"><span data-stu-id="12ffa-127">Wait three minutes, and then refresh the page, causing a postback event to occur.</span></span> <span data-ttu-id="12ffa-128">Observe que la hora que se muestra en la página ha cambiado.</span><span class="sxs-lookup"><span data-stu-id="12ffa-128">Note that the time displayed on the page has changed.</span></span> <span data-ttu-id="12ffa-129">Si actualiza la página sin esperar los tres minutos, la hora mostrada será la misma.</span><span class="sxs-lookup"><span data-stu-id="12ffa-129">If you refresh the page in less than three minutes, the time displayed on the page will remain the same.</span></span>  
  
 <span data-ttu-id="12ffa-130">A continuación, actualice los datos de la base de datos mediante un comando UPDATE deTransact-SQL y actualice la página.</span><span class="sxs-lookup"><span data-stu-id="12ffa-130">Now update the data in the database, using a Transact-SQL UPDATE command and refresh the page.</span></span> <span data-ttu-id="12ffa-131">La hora que se muestra indica ahora que la caché se ha actualizado con los datos nuevos de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="12ffa-131">The time displayed now indicates that the cache was refreshed with the new data from the database.</span></span> <span data-ttu-id="12ffa-132">Tenga en cuenta que, aunque la caché está actualizada, la hora que se muestra en la página no cambia hasta que se produce un evento postback de datos.</span><span class="sxs-lookup"><span data-stu-id="12ffa-132">Note that although the cache is updated, the time displayed on the page does not change until a postback event occurs.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="12ffa-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="12ffa-133">See also</span></span>

- [<span data-ttu-id="12ffa-134">Notificaciones de consulta en SQL Server</span><span class="sxs-lookup"><span data-stu-id="12ffa-134">Query Notifications in SQL Server</span></span>](query-notifications-in-sql-server.md)
- [<span data-ttu-id="12ffa-135">Información general sobre ADO.NET</span><span class="sxs-lookup"><span data-stu-id="12ffa-135">ADO.NET Overview</span></span>](../ado-net-overview.md)
