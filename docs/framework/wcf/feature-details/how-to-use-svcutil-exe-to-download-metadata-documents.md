---
title: Procedimiento para usar Svcutil.exe para descargar documentos de metadatos
ms.date: 03/30/2017
ms.assetid: 15524274-3167-4627-b722-d6cedb9fa8c6
ms.openlocfilehash: 25840247e59b9dd61cadaa2ee94713240d135f88
ms.sourcegitcommit: 005980b14629dfc193ff6cdc040800bc75e0a5a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/14/2019
ms.locfileid: "70991611"
---
# <a name="how-to-use-svcutilexe-to-download-metadata-documents"></a>Procedimiento para usar Svcutil.exe para descargar documentos de metadatos
Puede utilizar Svcutil.exe para descargar metadatos de los servicios en ejecución y para guardar los metadatos en archivos locales. En el caso de los esquemas de dirección URL HTTP y HTTPS, SvcUtil. exe intenta recuperar metadatos mediante WS-MetadataExchange y la [detección de servicios Web XML](https://go.microsoft.com/fwlink/?LinkId=94950). Para todos los otros esquemas de URL, Svcutil.exe utiliza sólo WS-MetadataExchange.  
  
 De forma predeterminada, Svcutil.exe utiliza los enlaces definidos en la clase <xref:System.ServiceModel.Description.MetadataExchangeBindings>. Para configurar el enlace utilizado para WS-MetadataExchange, debe definir un extremo de cliente en el archivo de configuración para Svcutil.exe (svcutil.exe.config) que utiliza el contrato `IMetadataExchange` y que tiene el mismo nombre que el esquema del Identificador uniforme de recursos (URI) de la dirección del extremo de metadatos.  
  
> [!CAUTION]
> Al ejecutar SvcUtil. exe para obtener los metadatos de un servicio que expone dos contratos de servicio diferentes, cada uno de los cuales contiene una operación con el mismo nombre, SvcUtil. exe muestra un error que indica "no se pueden obtener metadatos de...". Por ejemplo, si tiene un servicio que expone un contrato de servicio `ICarService` denominado que tiene una operación `Get(Car c)` y el mismo servicio expone un contrato de servicio denominado `IBookService` que tiene una operación `Get(Book b)`. Para solucionar este problema, realice una de las operaciones siguientes:
>
> - Cambie el nombre de una de las operaciones.
> - Establezca el <xref:System.ServiceModel.OperationContractAttribute.Name%2A> en un nombre distinto.
> - Establezca el espacio de nombres de una de las operaciones en un espacio de nombres distinto mediante la propiedad <xref:System.ServiceModel.ServiceContractAttribute.Namespace%2A>.
  
## <a name="to-download-metadata-using-svcutilexe"></a>Para descargar metadatos mediante Svcutil.exe  
  
1. Busque la herramienta Svcutil.exe en la ubicación siguiente:  
  
     C:\Archivos de programa\Microsoft SDKs\Windows\v1.0.\bin  
  
2. En el símbolo del sistema, inicie la herramienta mediante el formato siguiente.  
  
    ```console
    svcutil.exe /t:metadata  <url>* | <epr>  
    ```  
  
     Debe especificar la opción `/t:metadata` para descargar los metadatos. De lo contrario, se generan el código de cliente y la configuración.  
  
3. El argumento`url`< > especifica la dirección URL a un extremo de servicio que proporciona metadatos o a un documento de metadatos hospedado en línea. El argumento`epr`< > especifica la ruta de acceso a un archivo XML que contiene un WS `EndpointAddress` -Addressing para un punto de conexión de servicio que admite WS-MetadataExchange.  
  
 Para obtener más opciones sobre el uso de esta herramienta para la descarga de metadatos, vea [herramienta de utilidad de metadatos de ServiceModel (SvcUtil. exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md).  
  
## <a name="example"></a>Ejemplo  
 El comando siguiente descarga los documentos de metadatos de un servicio en ejecución.  
  
```console
svcutil /t:metadata http://service/metadataEndpoint  
```  
  
## <a name="see-also"></a>Vea también

- [Herramienta de utilidad de metadatos de ServiceModel (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)
