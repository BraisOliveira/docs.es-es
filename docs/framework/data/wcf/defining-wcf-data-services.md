---
title: Definir Servicios de datos de WCF
ms.date: 03/30/2017
helpviewer_keywords:
- WCF Data Services, configuring
ms.assetid: 05006ff3-02dc-410e-831e-54ec3e7e24ef
ms.openlocfilehash: ac75f5fd91f68d9403dc7b42325bf8970f0c6794
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61765653"
---
# <a name="defining-wcf-data-services"></a><span data-ttu-id="813dd-102">Definir Servicios de datos de WCF</span><span class="sxs-lookup"><span data-stu-id="813dd-102">Defining WCF Data Services</span></span>

<span data-ttu-id="813dd-103">En esta sección se describe cómo crear y configurar WCF Data Services para exponer datos como un [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] fuentes de distribución.</span><span class="sxs-lookup"><span data-stu-id="813dd-103">This section describes how to create and configure WCF Data Services to expose data as an [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] feed.</span></span> <span data-ttu-id="813dd-104">Para obtener más información acerca de los pasos básicos necesarios para crear un servicio de datos, vea [exponer los datos como un servicio](../../../../docs/framework/data/wcf/exposing-your-data-as-a-service-wcf-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="813dd-104">For more information about the basic steps required to create a data service, see [Exposing Your Data as a Service](../../../../docs/framework/data/wcf/exposing-your-data-as-a-service-wcf-data-services.md).</span></span>

## <a name="in-this-section"></a><span data-ttu-id="813dd-105">En esta sección</span><span class="sxs-lookup"><span data-stu-id="813dd-105">In This Section</span></span>

 [<span data-ttu-id="813dd-106">Configuración del servicio de datos</span><span class="sxs-lookup"><span data-stu-id="813dd-106">Configuring the Data Service</span></span>](../../../../docs/framework/data/wcf/configuring-the-data-service-wcf-data-services.md)

 <span data-ttu-id="813dd-107">Describe las opciones de configuración del servicio de datos proporcionadas por WCF Data Services.</span><span class="sxs-lookup"><span data-stu-id="813dd-107">Describes the data service configuration options provided by WCF Data Services.</span></span>

 [<span data-ttu-id="813dd-108">Proveedores de Data Services</span><span class="sxs-lookup"><span data-stu-id="813dd-108">Data Services Providers</span></span>](../../../../docs/framework/data/wcf/data-services-providers-wcf-data-services.md)

 <span data-ttu-id="813dd-109">Describe los modelos de proveedor para exponer datos como un servicio de datos.</span><span class="sxs-lookup"><span data-stu-id="813dd-109">Describes the provider models for exposing data as a data service.</span></span>

 [<span data-ttu-id="813dd-110">Operaciones de servicio</span><span class="sxs-lookup"><span data-stu-id="813dd-110">Service Operations</span></span>](../../../../docs/framework/data/wcf/service-operations-wcf-data-services.md)

 <span data-ttu-id="813dd-111">Describe cómo definir operaciones de servicio que exponen métodos en el servidor.</span><span class="sxs-lookup"><span data-stu-id="813dd-111">Describes how to define service operations that expose methods on the server.</span></span>

 [<span data-ttu-id="813dd-112">Personalización de fuentes</span><span class="sxs-lookup"><span data-stu-id="813dd-112">Feed Customization</span></span>](../../../../docs/framework/data/wcf/feed-customization-wcf-data-services.md)

 <span data-ttu-id="813dd-113">Describe cómo crear una asignación entre las entidades del modelo de datos definidas por el proveedor del servicio de datos y los elementos de la fuente de distribución de datos.</span><span class="sxs-lookup"><span data-stu-id="813dd-113">Describes how to create a mapping between entities in the data model defined by the data service provider and elements in the data feed.</span></span>

 [<span data-ttu-id="813dd-114">Interceptores</span><span class="sxs-lookup"><span data-stu-id="813dd-114">Interceptors</span></span>](../../../../docs/framework/data/wcf/interceptors-wcf-data-services.md)

 <span data-ttu-id="813dd-115">Describe cómo definir métodos de interceptor para ejecutar lógica de negocios personalizada en solicitudes al servicio de datos.</span><span class="sxs-lookup"><span data-stu-id="813dd-115">Describes how to define interceptor methods to perform custom business logic on requests to the data service.</span></span>

 [<span data-ttu-id="813dd-116">Desarrollo e implementación de WCF Data Services</span><span class="sxs-lookup"><span data-stu-id="813dd-116">Developing and Deploying WCF Data Services</span></span>](../../../../docs/framework/data/wcf/developing-and-deploying-wcf-data-services.md)

 <span data-ttu-id="813dd-117">Describe cómo desarrollar e implementar un servicio de datos con Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="813dd-117">Describes how to develop and deploy a data service by using Visual Studio.</span></span>

 [<span data-ttu-id="813dd-118">Protección de WCF Data Services</span><span class="sxs-lookup"><span data-stu-id="813dd-118">Securing WCF Data Services</span></span>](../../../../docs/framework/data/wcf/securing-wcf-data-services.md)

 <span data-ttu-id="813dd-119">Describe la autenticación y la autorización del servicio de datos y otras consideraciones de seguridad.</span><span class="sxs-lookup"><span data-stu-id="813dd-119">Describes authentication and authorization for the data service and other security considerations.</span></span>

 [<span data-ttu-id="813dd-120">Hospedaje del servicio de datos</span><span class="sxs-lookup"><span data-stu-id="813dd-120">Hosting the Data Service</span></span>](../../../../docs/framework/data/wcf/hosting-the-data-service-wcf-data-services.md)

 <span data-ttu-id="813dd-121">Describe cómo seleccionar un host para un servicio de datos.</span><span class="sxs-lookup"><span data-stu-id="813dd-121">Describes how to select a host for your data service.</span></span>

 [<span data-ttu-id="813dd-122">Control de versiones del servicio de datos</span><span class="sxs-lookup"><span data-stu-id="813dd-122">Data Service Versioning</span></span>](../../../../docs/framework/data/wcf/data-service-versioning-wcf-data-services.md)

 <span data-ttu-id="813dd-123">Describe cómo trabajar con distintas versiones de OData.</span><span class="sxs-lookup"><span data-stu-id="813dd-123">Describes how to work with different versions of the OData.</span></span>

 [<span data-ttu-id="813dd-124">Detalles de implementación del protocolo WCF Data Services</span><span class="sxs-lookup"><span data-stu-id="813dd-124">WCF Data Services Protocol Implementation Details</span></span>](../../../../docs/framework/data/wcf/wcf-data-services-protocol-implementation-details.md)

 <span data-ttu-id="813dd-125">Describe las funcionalidades opcionales del Protocolo OData que no están implementadas actualmente por WCF Data Services.</span><span class="sxs-lookup"><span data-stu-id="813dd-125">Describes optional functionalities of the OData protocol that are not currently implemented by WCF Data Services.</span></span>

## <a name="see-also"></a><span data-ttu-id="813dd-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="813dd-126">See also</span></span>

- [<span data-ttu-id="813dd-127">Biblioteca cliente de Servicios de datos de WCF</span><span class="sxs-lookup"><span data-stu-id="813dd-127">WCF Data Services Client Library</span></span>](../../../../docs/framework/data/wcf/wcf-data-services-client-library.md)
- [<span data-ttu-id="813dd-128">Acceso a recursos de servicios de datos</span><span class="sxs-lookup"><span data-stu-id="813dd-128">Accessing Data Service Resources</span></span>](../../../../docs/framework/data/wcf/accessing-data-service-resources-wcf-data-services.md)
- [<span data-ttu-id="813dd-129">Introducción</span><span class="sxs-lookup"><span data-stu-id="813dd-129">Getting Started</span></span>](../../../../docs/framework/data/wcf/getting-started-with-wcf-data-services.md)
