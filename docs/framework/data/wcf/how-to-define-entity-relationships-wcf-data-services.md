---
title: Procedimiento Definir relaciones de entidad (WCF Data Services)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, changing data
ms.assetid: cc255524-1534-4fae-b83c-250933d5a72b
ms.openlocfilehash: 63714f97e691b2ba0177a36a599b62ca7681dcf6
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70790648"
---
# <a name="how-to-define-entity-relationships-wcf-data-services"></a>Procedimiento Definir relaciones de entidad (WCF Data Services)
Al agregar una nueva entidad en [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)], las relaciones entre la nueva entidad y las entidades relacionadas no se definen automáticamente. Puede crear y cambiar las relaciones entre las instancias de las entidades y hacer que la biblioteca de cliente refleje esos cambios en el servicio de datos. Para obtener más información, vea [actualizar el servicio de datos](updating-the-data-service-wcf-data-services.md).  
  
 En el ejemplo de este tema se usa el servicio de datos de ejemplo Northwind y las clases del servicio de datos de cliente generadas automáticamente. Este servicio y las clases de datos de cliente se crean al completar la guía de [Inicio rápido de WCF Data Services](quickstart-wcf-data-services.md).  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se crea una instancia de objeto nueva y, a continuación, se llama al método <xref:System.Data.Services.Client.DataServiceContext.AddRelatedObject%2A> de la clase <xref:System.Data.Services.Client.DataServiceContext> para crear el elemento en el contexto junto con el vínculo al pedido relacionado. Se envía un mensaje POST de HTTP al servicio de datos cuando se llama al método <xref:System.Data.Services.Client.DataServiceContext.SaveChanges%2A>.  
  
 [!code-csharp[Astoria Northwind Client#AddOrderDetailToOrderAuto](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#addorderdetailtoorderauto)]
 [!code-vb[Astoria Northwind Client#AddOrderDetailToOrderAuto](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#addorderdetailtoorderauto)]  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra cómo utilizar el método <xref:System.Data.Services.Client.DataServiceContext.AddObject%2A> para agregar un objeto `Order_Details` a un objeto `Orders` relacionado con una referencia a un objeto `Products` concreto. Los métodos <xref:System.Data.Services.Client.DataServiceContext.AddLink%2A> y <xref:System.Data.Services.Client.DataServiceContext.SetLink%2A> definen las relaciones. En este ejemplo, las propiedades de navegación del objeto `Order_Details` también se establecen explícitamente.  
  
 [!code-csharp[Astoria Northwind Client#AddOrderDetailToOrder](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#addorderdetailtoorder)]
 [!code-vb[Astoria Northwind Client#AddOrderDetailToOrder](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#addorderdetailtoorder)]  
  
## <a name="see-also"></a>Vea también

- [Biblioteca cliente de Servicios de datos de WCF](wcf-data-services-client-library.md)
- [Cómo: Agregar, modificar y eliminar entidades](how-to-add-modify-and-delete-entities-wcf-data-services.md)
