---
title: Detalles de implementación del protocolo WCF Data Services
ms.date: 03/30/2017
ms.assetid: 712d689b-fada-4cbb-bcdb-d65a3ef83b4c
ms.openlocfilehash: 1cd4204d9e1626ac45bccf3954fdaf1c156af7f8
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70779656"
---
# <a name="wcf-data-services-protocol-implementation-details"></a>Detalles de implementación del protocolo WCF Data Services
## <a name="odata-protocol-implementation-details"></a>Detalles de implementación del protocolo OData  
 [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] requiere que un servicio de datos que implementa el protocolo proporcione un cierto conjunto mínimo de funcionalidades. Estas funcionalidades se describen en los documentos del protocolo en términos de "debe" y "debe". Otra funcionalidad opcional se describe en términos de "mayo". Este tema aborda estas funcionalidades opcionales que en estos momentos no implementa [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]. Para obtener más información, consulte la [documentación del protocolo OData](https://go.microsoft.com/fwlink/?LinkID=184554).  
  
### <a name="support-for-the-format-query-option"></a>Compatibilidad con la opción de consulta $format  
 El protocolo [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] admite fuentes Notación de objetos JavaScript (JSON) y Atom, y [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] proporciona la opción de consulta del sistema `$format` para permitir a un cliente solicitar el formato de la fuente de respuesta. Esta opción de consulta del sistema, si el servicio de datos la admite, debe invalidar el valor del encabezado Accept de la solicitud. [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] admite devolver fuentes tanto JSON como Atom. Sin embargo, la implementación predeterminada no admite la opción de consulta `$format` y usa solo el valor del encabezado Accept para determinar el formato de la respuesta. Hay casos en los que el servicio de datos quizás necesite admitir la opción de consulta `$format`, como cuando los clientes no pueden establecer el encabezado Accept. Para admitir estos escenarios, debe extender su servicio de datos para administrar esta opción en el URI. Puede Agregar esta funcionalidad al servicio de datos descargando el [JSONP y la compatibilidad con el formato controlado por la dirección URL de ADO.NET Data Services](https://go.microsoft.com/fwlink/?LinkId=208228) proyecto de ejemplo en el sitio web de la galería de código de MSDN y agregándolo a su proyecto de servicio de datos. Este ejemplo quita la opción de consulta `$format` y cambia el encabezado Accept a `application/json`. Al incluir el proyecto de ejemplo y agregar `JSONPSupportBehaviorAttribute` a la clase del servicio de datos permite al servicio administrar la opción de consulta `$format``$format=json`. Se requiere mayor personalización de este proyecto de ejemplo para administrar también `$format=atom` u otros formatos personalizados.  
  
## <a name="wcf-data-services-behaviors"></a>Comportamientos de WCF Data Services  
 El protocolo [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] no define explícitamente los siguientes comportamientos de [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]:  
  
### <a name="default-sorting-behavior"></a>Comportamiento de ordenación predeterminado  
 Cuando una solicitud de consulta que se envía al servicio de datos incluye una opción de consulta del sistema `$top` o `$skip` y no incluye la opción de consulta del sistema `$orderby`, las propiedades clave ordenan la fuente devuelta en sentido ascendente. Esto es porque se necesita la ordenación para asegurar la correcta paginación de los resultados. Para ello, el servicio de datos agrega una expresión de ordenación a la consulta. Este comportamiento también se produce cuando la paginación controlada por servidor está habilitada en el servicio de datos. Para obtener más información, vea [configurar el servicio de datos](configuring-the-data-service-wcf-data-services.md). Para controlar el orden de la fuente devuelta, debe incluir `$orderby` en el URI de la consulta.  
  
## <a name="see-also"></a>Vea también

- [Definir Servicios de datos de WCF](defining-wcf-data-services.md)
- [Biblioteca cliente de Servicios de datos de WCF](wcf-data-services-client-library.md)
