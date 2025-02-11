---
title: Procedimiento Ejecutar consultas de servicio de datos (WCF Data Services)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- querying the data service [WCF Data Services]
- WCF Data Services, querying
- WCF Data Services, accessing data
ms.assetid: 62997821-e0c6-4c4d-9fb7-1273fb5e5d18
ms.openlocfilehash: 984bba9f31ddaee68c6997ba6da09a511e42b4ce
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70780064"
---
# <a name="how-to-execute-data-service-queries-wcf-data-services"></a>Procedimiento Ejecutar consultas de servicio de datos (WCF Data Services)
[!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] le permite consultar un servicio datos desde una aplicación cliente basada en .NET Framework usando las clases generadas del servicio de datos del cliente. Puede ejecutar las consultas usando uno de estos métodos:  
  
- Ejecutar una consulta LINQ en la instancia con nombre de <xref:System.Data.Services.Client.DataServiceQuery%601> que se obtiene desde la instancia de <xref:System.Data.Services.Client.DataServiceContext> generada por la herramienta `Add Data Service Reference`.  
  
- Implícitamente, enumerando en la instancia con nombre de <xref:System.Data.Services.Client.DataServiceQuery%601> que se obtiene desde la instancia de <xref:System.Data.Services.Client.DataServiceContext> generada por la herramienta `Add Data Service Reference`.  
  
- Explícitamente, llamando al método <xref:System.Data.Services.Client.DataServiceContext.Execute%2A> de <xref:System.Data.Services.Client.DataServiceQuery%601> o al método <xref:System.Data.Services.Client.DataServiceQuery%601.BeginExecute%2A> para la ejecución asincrónica.  
  
 Para obtener más información, consulte [consultar el servicio de datos](querying-the-data-service-wcf-data-services.md).  
  
 En el ejemplo de este tema se usa el servicio de datos de ejemplo Northwind y las clases del servicio de datos de cliente generadas automáticamente. Este servicio y las clases de datos de cliente se crean al completar la guía de [Inicio rápido de WCF Data Services](quickstart-wcf-data-services.md).  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra cómo definir y ejecutar en el servicio de datos de Northwind una consulta LINQ que devuelve todas las entidades `Customers`.  
  
 [!code-csharp[Astoria Northwind Client#GetAllCustomersLinq](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#getallcustomerslinq)]
 [!code-vb[Astoria Northwind Client#GetAllCustomersLinq](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#getallcustomerslinq)]  
  
## <a name="example"></a>Ejemplo  
 En el siguiente ejemplo se muestra cómo usar el contexto que genera la herramienta `Add Data Service Reference` para ejecutar implícitamente en el servicio de datos de Northwind una consulta que devuelve todas las entidades `Customers`. El contexto determina automáticamente el URI del conjunto de entidades `Customers` solicitado. La consulta se ejecuta implícitamente cuando se produce la enumeración.  
  
 [!code-csharp[Astoria Northwind Client#GetAllCustomers](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#getallcustomers)]
 [!code-vb[Astoria Northwind Client#GetAllCustomers](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#getallcustomers)]  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra cómo usar <xref:System.Data.Services.Client.DataServiceContext> para ejecutar explícitamente en el servicio de datos de Northwind una consulta que devuelve todas las entidades `Customers`.  
  
 [!code-csharp[Astoria Northwind Client#GetAllCustomersExplicit](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#getallcustomersexplicit)]
 [!code-vb[Astoria Northwind Client#GetAllCustomersExplicit](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#getallcustomersexplicit)]  
  
## <a name="see-also"></a>Vea también

- [Cómo: Agregar opciones de consulta a una consulta de servicio de datos](how-to-add-query-options-to-a-data-service-query-wcf-data-services.md)
