---
title: <netHttpsBinding>
ms.date: 03/30/2017
ms.assetid: ff122116-6042-4792-9f21-275b4f97a105
ms.openlocfilehash: 25bda2985e665fc792a256b5ae97e29ab91a9ddb
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/07/2019
ms.locfileid: "73738877"
---
# <a name="nethttpsbinding"></a>\<Nethttpbinding >
Representa un enlace que un servicio de Windows Communication Foundation (WCF) puede usar para configurar y exponer extremos que pueden comunicarse a través de HTTPS. Cuando se usa con un contrato dúplex, se usará WebSockets; si no, se usará HTTPS.  
  
[ **\<configuration>** ](../configuration-element.md)\
&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;\<[**enlaces**](bindings.md) >\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<nethttpbinding >**  

## <a name="syntax"></a>Sintaxis  
  
```xml  
<netHttpsBinding>
  <binding allowCookies="Boolean"
           bypassProxyOnLocal="Boolean"
           closeTimeout="TimeSpan"
           hostNameComparisonMode="StrongWildCard/Exact/WeakWildcard"
           maxBufferPoolSize="Integer"
           maxBufferSize="Integer"
           maxReceivedMessageSize="Integer"
           messageEncoding="Binary/Text/Mtom"
           name="string"
           openTimeout="TimeSpan"
           proxyAddress="URI"
           receiveTimeout="TimeSpan"
           sendTimeout="TimeSpan"
           textEncoding="UnicodeFffeTextEncoding/Utf16TextEncoding/Utf8TextEncoding"
           transferMode="Buffered/Streamed/StreamedRequest/StreamedResponse"
           useDefaultWebProxy="Boolean">
    <security mode="None/Transport/Message/TransportWithMessageCredential/TransportCredentialOnly">
      <transport clientCredentialType="None/Basic/Digest/Ntlm/Windows/Certificate"
                 proxyCredentialType="None/Basic/Digest/Ntlm/Windows"
                 realm="string" />
      <message algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
               clientCredentialType="UserName/Certificate" />
    </security>
    <readerQuotas maxArrayLength="Integer"
                  maxBytesPerRead="Integer"
                  maxDepth="Integer"
                  maxNameTableCharCount="Integer"
                  maxStringContentLength="Integer" />
  </binding>
</netHttpsBinding>
```  
  
## <a name="type"></a>Type  
 `Type`  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|Descripción|  
|---------------|-----------------|  
|`allowCookies`|Valor de tipo booleano que indica si el cliente acepta las cookies y las propaga en solicitudes futuras. De manera predeterminada, es `false`.<br /><br /> Puede utilizar esta propiedad al interactuar con los servicios Web ASMX que utilizan cookies. De esta manera, puede estar seguro de que las cookies devueltas del servidor se copian automáticamente en todas las solicitudes de cliente futuras para ese servicio.|  
|`bypassProxyOnLocal`|Valor de tipo booleano que indica si se omitirá el servidor proxy para las direcciones locales. De manera predeterminada, es `false`.<br /><br /> Un recurso de Internet es local si tiene una dirección local. Una dirección local es aquella que se encuentra en el mismo equipo, en la LAN local o en la intranet y se identifica, sintácticamente, por la falta de un punto (.) como en los URI "http://webserver/" y "http://localhost/".<br /><br /> Al establecer este atributo se determina si los extremos configurados con BasicHttpBinding utilizan el servidor proxy al obtener acceso a los recursos locales. Si este atributo es `true`, las solicitudes que se realicen en recursos locales de Internet no usarán el servidor proxy. Utilice el nombre de host (en lugar del host local) si desea que los clientes pasen por un proxy al hablar con los servicios del mismo equipo cuando este atributo está establecido como `true`.<br /><br /> Cuando este atributo es `false`, todas las solicitudes de Internet se realizan a través del servidor proxy.|  
|`closeTimeout`|Un valor <xref:System.TimeSpan> que especifica el intervalo de tiempo del que dispone una operación de cierre para completarse. Este valor debe ser mayor o igual que <xref:System.TimeSpan.Zero>. El valor predeterminado es 00:01:00.|  
|`hostNameComparisonMode`|Especifica el modo de comparación de nombres de host HTTP usado para analizar los URI. Este atributo es del tipo <xref:System.ServiceModel.HostNameComparisonMode>, que indica si se va a utilizar el nombre del host para llegar al servicio cuando coincida en el URI. El valor predeterminado es <xref:System.ServiceModel.HostNameComparisonMode.StrongWildcard>, que omite el nombre del host en la coincidencia.|  
|`maxBufferPoolSize`|Un valor entero que especifica la cantidad de memoria máxima que se asigna para el uso realizado por el administrador de los búferes que reciben los mensajes del canal. El valor predeterminado es 524288 (0x80000) bytes.<br /><br /> El administrador de búfer reduce el coste de utilizar los búferes con un grupo de búferes. Es necesario que los búferes procesen los mensajes del servicio cuando salen del canal. Si no hay memoria suficiente en el grupo de búferes para procesar la carga de mensajes, el administrador de búfer debe asignar memoria adicional del montón CLR, que aumenta la carga de recolección de elementos no utilizados. La amplia asignación del montón de elementos no utilizados de CLR es una indicación de que el tamaño del grupo de búferes es demasiado pequeño y de que el rendimiento podría mejorar con una asignación mayor aumentando el límite especificado por este atributo.|  
|`maxBufferSize`|Un valor entero que especifica el tamaño máximo, en bytes, de un búfer que almacena los mensajes mientras se procesan para un extremo configurado con este enlace. El valor predeterminado es 65.536 bytes.|  
|`maxReceivedMessageSize`|Un entero positivo que define el tamaño máximo del mensaje, en bytes, incluidos los encabezados, para un mensaje que se puede recibir en un canal configurado con este enlace. El remitente recibe un error SOAP cuando el mensaje es demasiado grande para el receptor. El destinatario quita el mensaje y crea una entrada del evento en el registro de seguimiento. El valor predeterminado es 65.536 bytes.|  
|`messageEncoding`|Define el codificador utilizado para codificar el mensaje SOAP. Los valores válidos son los siguientes:<br /><br /> -Text: usar un codificador de mensajes de texto.<br />-MTOM: usar un codificador del mecanismo de la organización de transmisión de mensajes 1,0 (MTOM).<br /><br /> El valor predeterminado es Text. Este atributo es del tipo <xref:System.ServiceModel.WSMessageEncoding>.|  
|`name`|Cadena que contiene el nombre de configuración del enlace. Este valor debe ser único porque se usa como identificación del enlace. Cada enlace tiene los atributos `name` y `namespace` que, juntos, lo identifican de forma exclusiva en los metadatos del servicio. Además, este nombre es único entre los enlaces del mismo tipo. A partir de [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], no es necesario que los enlaces y los comportamientos tengan nombre. Para obtener más información sobre la configuración predeterminada y los enlaces y comportamientos sin nombre, vea [configuración simplificada](../../../wcf/simplified-configuration.md) y [configuración simplificada para servicios WCF](../../../wcf/samples/simplified-configuration-for-wcf-services.md).|  
|`namespace`|Especifica el espacio de nombres XML del enlace. El valor predeterminado es "http://tempuri.org/Bindings". Cada enlace tiene los atributos `name` y `namespace` que, juntos, lo identifican de forma exclusiva en los metadatos del servicio.|  
|`openTimeout`|Valor de la estructura <xref:System.TimeSpan> que especifica el intervalo de tiempo del que dispone una operación de apertura para completarse. Este valor debe ser mayor o igual que <xref:System.TimeSpan.Zero>. El valor predeterminado es 00:01:00.|  
|`proxyAddress`|Un URI que contiene la dirección del proxy HTTP. Si `useSystemWebProxy` se establece como `true`, esta configuración debe ser `null`. De manera predeterminada, es `null`.|  
|`receiveTimeout`|Un valor <xref:System.TimeSpan> que especifica el intervalo de tiempo del que dispone una operación de recepción para completarse. Este valor debe ser mayor o igual que <xref:System.TimeSpan.Zero>. El valor predeterminado es 00:10:00.|  
|`sendTimeout`|Un valor <xref:System.TimeSpan> que especifica el intervalo de tiempo del que dispone una operación de envío para completarse. Este valor debe ser mayor o igual que <xref:System.TimeSpan.Zero>. El valor predeterminado es 00:01:00.|  
|`textEncoding`|Establece el codificador del juego de caracteres que se va a usar para emitir los mensajes en el enlace. Los valores válidos son los siguientes:<br /><br /> -BigEndianUnicode: codificación Unicode BigEndian.<br />-Unicode: codificación de 16 bits.<br />-UTF8: codificación de 8 bits<br /><br /> El valor predeterminado es UTF8. Este atributo es del tipo <xref:System.Text.Encoding>.|  
|`transferMode`|Un valor <xref:System.ServiceModel.TransferMode> válido que especifica si los mensajes se almacenan en búfer, se transmiten o si son una solicitud o una respuesta.|  
|`useDefaultWebProxy`|Valor de tipo booleano que especifica si se debería utilizar el proxy HTTP configurado automáticamente del sistema, si está disponible. De manera predeterminada, es `true`.|  
|||  
  
### <a name="child-elements"></a>Elementos secundarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<La >](security-of-nethttpbinding.md)|Define la configuración de seguridad del enlace. Este elemento es del tipo <xref:System.ServiceModel.Configuration.BasicHttpsSecurityElement>. |  
|[\<readerQuotas >](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))|Define las restricciones en la complejidad de los mensajes SOAP que pueden ser procesados por los puntos de conexión configurados con este enlace. Este elemento es del tipo <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.|  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<enlaces >](bindings.md)|Este elemento contiene una colección de enlaces estándar y personalizados.|  
  
## <a name="remarks"></a>Comentarios  
 NetHttpBinding usa HTTPS como transporte para enviar mensajes. Cuando se usa con un contrato dúplex, se usará WebSockets.  Cuando se usa con un contrato de solicitud-respuesta, NetHttpsBinding se comportará como un BasicHttpsBinding con un codificador binario.  
  
 La seguridad está desactivada de forma predeterminada, pero se puede Agregar estableciendo el atributo de modo del elemento secundario [\<security >](security-of-basichttpbinding.md) en un valor distinto de `None`. De forma predeterminada, usa una codificación de mensajes "Text" y codificación de texto UTF-8.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra el uso de la clase <xref:System.ServiceModel.NetHttpBinding> que proporciona comunicación HTTPS e interoperabilidad máxima a los servicios Web de primera y segunda generación. El enlace se especifica en los archivos de configuración para el cliente y servicio. El tipo de enlace se especifica en el atributo `binding` del elemento `<endpoint>`. Si desea configurar el enlace básico y cambiar algunos de sus valores, es necesario definir una configuración de enlace. El extremo debe hacer referencia a la configuración de enlace por nombre utilizando el atributo `bindingConfiguration` del elemento `<endpoint>`, como se muestra en el siguiente código de configuración para el servicio.  
  
```xml  
<system.serviceModel>
  <services>
    <service type="Microsoft.ServiceModel.Samples.CalculatorService"
             behaviorConfiguration="CalculatorServiceBehavior">
      <endpoint address=""
                binding="netHttpsBinding"
                bindingConfiguration="Binding1"
                contract="Microsoft.ServiceModel.Samples.ICalculator" />
    </service>
  </services>
  <bindings>
    <netHttpsBinding>
      <binding name="Binding1"
               hostNameComparisonMode="StrongWildcard"
               receiveTimeout="00:10:00"
               sendTimeout="00:10:00"
               openTimeout="00:10:00"
               closeTimeout="00:10:00"
               maxReceivedMessageSize="65536"
               maxBufferSize="65536"
               maxBufferPoolSize="524288"
               transferMode="Buffered"
               messageEncoding="Binary"
               textEncoding="utf-8"
               bypassProxyOnLocal="false"
               useDefaultWebProxy="true">
        <security mode="None" />
      </binding>
    </netHttpsBinding>
  </bindings>
</system.serviceModel>
```  
  
## <a name="example"></a>Ejemplo  
 A partir de [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], no es necesario que los enlaces y los comportamientos tengan nombre. La funcionalidad del ejemplo anterior se puede llevar a cabo quitando bindingConfiguration de la dirección del punto de conexión y el nombre del enlace.  
  
```xml  
<system.serviceModel>
  <services>
    <service type="Microsoft.ServiceModel.Samples.CalculatorService"
             behaviorConfiguration="CalculatorServiceBehavior">
      <endpoint address=""
                binding="netHttpsBinding"
                contract="Microsoft.ServiceModel.Samples.ICalculator" />
    </service>
  </services>
  <bindings>
    <netHttpsBinding>
      <binding hostNameComparisonMode="StrongWildcard"
               receiveTimeout="00:10:00"
               sendTimeout="00:10:00"
               openTimeout="00:10:00"
               closeTimeout="00:10:00"
               maxReceivedMessageSize="65536"
               maxBufferSize="65536"
               maxBufferPoolSize="524288"
               transferMode="Buffered"
               messageEncoding="Binary"
               textEncoding="utf-8"
               bypassProxyOnLocal="false"
               useDefaultWebProxy="true">
        <security mode="None" />
      </binding>
    </netHttpsBinding>
  </bindings>
</system.serviceModel>
```  
  
 Para obtener más información sobre la configuración predeterminada y los enlaces y comportamientos sin nombre, vea [configuración simplificada](../../../wcf/simplified-configuration.md) y [configuración simplificada para servicios WCF](../../../wcf/samples/simplified-configuration-for-wcf-services.md).  
  
## <a name="see-also"></a>Vea también

- <xref:System.ServiceModel.Channels.Binding>
- <xref:System.ServiceModel.Channels.BindingElement>
- <xref:System.ServiceModel.BasicHttpBinding>
- <xref:System.ServiceModel.Configuration.BasicHttpBindingElement>
- [Enlaces](../../../wcf/bindings.md)
- [Configuración de enlaces proporcionados por el sistema](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [Utilización de enlaces para configurar servicios y clientes](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<> de enlace](bindings.md)
