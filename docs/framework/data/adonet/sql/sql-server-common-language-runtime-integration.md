---
title: Integración con Common Language Runtime de SQL Server
ms.date: 03/30/2017
ms.assetid: c7a324c4-160d-44c2-b593-641af06eca61
ms.openlocfilehash: d87f2b89583747b80ef103f419bd9bd2e3b1e0da
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59089840"
---
# <a name="sql-server-common-language-runtime-integration"></a><span data-ttu-id="ae59b-102">Integración con Common Language Runtime de SQL Server</span><span class="sxs-lookup"><span data-stu-id="ae59b-102">SQL Server Common Language Runtime Integration</span></span>
<span data-ttu-id="ae59b-103">SQL Server 2005 introdujo la integración del componente Common Language Runtime (CLR) de .NET Framework para Microsoft Windows.</span><span class="sxs-lookup"><span data-stu-id="ae59b-103">SQL Server 2005 introduced the integration of the common language runtime (CLR) component of the .NET Framework for Microsoft Windows.</span></span> <span data-ttu-id="ae59b-104">Esto significa que ahora se pueden escribir procedimientos almacenados, desencadenadores, tipos definidos por el usuario, funciones definidas por el usuario, agregados definidos por el usuario y funciones con valores de tabla de transmisión por secuencias mediante cualquier lenguaje de .NET Framework, como Microsoft Visual Basic .NET y Microsoft Visual C#.</span><span class="sxs-lookup"><span data-stu-id="ae59b-104">This means that you can write stored procedures, triggers, user-defined types, user-defined functions, user-defined aggregates, and streaming table-valued functions, using any .NET Framework language, including Microsoft Visual Basic .NET and Microsoft Visual C#.</span></span> <span data-ttu-id="ae59b-105">El espacio de nombres <xref:Microsoft.SqlServer.Server> contiene un conjunto de nuevas interfaces de programación de aplicaciones (API) que permiten que el código administrado interactúe con el entorno de Microsoft SQL Server.</span><span class="sxs-lookup"><span data-stu-id="ae59b-105">The <xref:Microsoft.SqlServer.Server> namespace contains a set of new application programming interfaces (APIs) so that managed code can interact with the Microsoft SQL Server environment.</span></span>  
  
 <span data-ttu-id="ae59b-106">En esta sección se describen las características y comportamientos que son específicos de la integración Common Language Runtime (CLR) de SQL Server, así como las extensiones específicas en proceso de SQL Server a ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="ae59b-106">This section describes features and behaviors that are specific to SQL Server common language runtime (CLR) integration and the SQL Server in-process specific extensions to ADO.NET.</span></span>  
  
 <span data-ttu-id="ae59b-107">El objetivo de esta sección es proporcionar suficiente información para iniciarse en la programación con la integración CLR de SQL Server; no pretende tratar el tema en toda su extensión.</span><span class="sxs-lookup"><span data-stu-id="ae59b-107">This section is meant to provide only enough information to get started programming with SQL Server CLR integration, and is not meant to be comprehensive.</span></span> <span data-ttu-id="ae59b-108">Para obtener información más detallada, busque la versión de SQL Server que utiliza en los Libros en pantalla de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="ae59b-108">For more detailed information, see the version of SQL Server Books Online for the version of SQL Server you are using.</span></span>  
  
 **<span data-ttu-id="ae59b-109">Libros en pantalla de SQL Server</span><span class="sxs-lookup"><span data-stu-id="ae59b-109">SQL Server Books Online</span></span>**  
  
1.  [<span data-ttu-id="ae59b-110">Conceptos de programación de la integración con Common Language Runtime (CLR)</span><span class="sxs-lookup"><span data-stu-id="ae59b-110">Common Language Runtime (CLR) Integration Programming Concepts</span></span>](https://go.microsoft.com/fwlink/?LinkId=115240)  
  
## <a name="in-this-section"></a><span data-ttu-id="ae59b-111">En esta sección</span><span class="sxs-lookup"><span data-stu-id="ae59b-111">In This Section</span></span>  
 [<span data-ttu-id="ae59b-112">Introducción a la integración con CLR de SQL Server</span><span class="sxs-lookup"><span data-stu-id="ae59b-112">Introduction to SQL Server CLR Integration</span></span>](../../../../../docs/framework/data/adonet/sql/introduction-to-sql-server-clr-integration.md)  
 <span data-ttu-id="ae59b-113">Proporciona una introducción a la integración CLR de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="ae59b-113">Provides an introduction to SQL Server CLR integration.</span></span> <span data-ttu-id="ae59b-114">También proporciona vínculos a temas adicionales.</span><span class="sxs-lookup"><span data-stu-id="ae59b-114">Provides links to additional topics.</span></span>  
  
 [<span data-ttu-id="ae59b-115">Funciones definidas por el usuario de CLR</span><span class="sxs-lookup"><span data-stu-id="ae59b-115">CLR User-Defined Functions</span></span>](../../../../../docs/framework/data/adonet/sql/clr-user-defined-functions.md)  
 <span data-ttu-id="ae59b-116">Describe cómo implementar y utilizar los diferentes tipos de funciones CLR: con valores de tabla, escalares y funciones de agregado definidas por el usuario.</span><span class="sxs-lookup"><span data-stu-id="ae59b-116">Describes how to implement and use the various types of CLR functions: table-valued, scalar, and user-defined aggregate functions.</span></span>  
  
 [<span data-ttu-id="ae59b-117">Tipos CLR definidos por el usuario</span><span class="sxs-lookup"><span data-stu-id="ae59b-117">CLR User-Defined Types</span></span>](../../../../../docs/framework/data/adonet/sql/clr-user-defined-types.md)  
 <span data-ttu-id="ae59b-118">Describe cómo implementar y utilizar tipos definidos por el usuario CLR.</span><span class="sxs-lookup"><span data-stu-id="ae59b-118">Describes how to implement and use CLR user-defined types.</span></span> <span data-ttu-id="ae59b-119">También proporciona vínculos a temas adicionales.</span><span class="sxs-lookup"><span data-stu-id="ae59b-119">Provides links to additional topics.</span></span>  
  
 [<span data-ttu-id="ae59b-120">Procedimientos almacenados de CLR</span><span class="sxs-lookup"><span data-stu-id="ae59b-120">CLR Stored Procedures</span></span>](../../../../../docs/framework/data/adonet/sql/clr-stored-procedures.md)  
 <span data-ttu-id="ae59b-121">Describe cómo implementar y utilizar procedimientos almacenados CLR.</span><span class="sxs-lookup"><span data-stu-id="ae59b-121">Describes how to implement and use CLR stored procedures.</span></span> <span data-ttu-id="ae59b-122">También proporciona vínculos a temas adicionales.</span><span class="sxs-lookup"><span data-stu-id="ae59b-122">Provides links to additional topics.</span></span>  
  
 [<span data-ttu-id="ae59b-123">Desencadenadores de CLR</span><span class="sxs-lookup"><span data-stu-id="ae59b-123">CLR Triggers</span></span>](../../../../../docs/framework/data/adonet/sql/clr-triggers.md)  
 <span data-ttu-id="ae59b-124">Describe cómo implementar y utilizar desencadenadores CLR.</span><span class="sxs-lookup"><span data-stu-id="ae59b-124">Describes how to implement and use CLR triggers.</span></span> <span data-ttu-id="ae59b-125">También proporciona vínculos a temas adicionales.</span><span class="sxs-lookup"><span data-stu-id="ae59b-125">Provides links to additional topics.</span></span>  
  
 [<span data-ttu-id="ae59b-126">Conexión del contexto</span><span class="sxs-lookup"><span data-stu-id="ae59b-126">The Context Connection</span></span>](../../../../../docs/framework/data/adonet/sql/the-context-connection.md)  
 <span data-ttu-id="ae59b-127">Describe la conexión de contexto.</span><span class="sxs-lookup"><span data-stu-id="ae59b-127">Describes the context connection.</span></span>  
  
 [<span data-ttu-id="ae59b-128">Comportamiento específico en proceso de SQL Server en ADO.NET</span><span class="sxs-lookup"><span data-stu-id="ae59b-128">SQL Server In-Process-Specific Behavior of ADO.NET</span></span>](../../../../../docs/framework/data/adonet/sql/sql-server-in-process-specific-behavior-of-adonet.md)  
 <span data-ttu-id="ae59b-129">Describe las extensiones específicas en proceso de SQL Server a ADO.NET, y la conexión de contexto.</span><span class="sxs-lookup"><span data-stu-id="ae59b-129">Describes the SQL Server in-process specific extensions to ADO.NET, and the context connection.</span></span> <span data-ttu-id="ae59b-130">También proporciona vínculos a temas adicionales.</span><span class="sxs-lookup"><span data-stu-id="ae59b-130">Provides links to additional topics.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae59b-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="ae59b-131">See also</span></span>

- [<span data-ttu-id="ae59b-132">SQL Server y ADO.NET</span><span class="sxs-lookup"><span data-stu-id="ae59b-132">SQL Server and ADO.NET</span></span>](../../../../../docs/framework/data/adonet/sql/index.md)
- [<span data-ttu-id="ae59b-133">Proveedores administrados de ADO.NET y centro de desarrolladores de DataSet</span><span class="sxs-lookup"><span data-stu-id="ae59b-133">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
