---
title: Procedimiento para crear un token de contexto de seguridad para una sesión segura
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 640676b6-c75a-4ff7-aea4-b1a1524d71b2
ms.openlocfilehash: e6c41ed32d63932bc1fac72bc6e727eb82806617
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69966081"
---
# <a name="how-to-create-a-security-context-token-for-a-secure-session"></a>Procedimiento para crear un token de contexto de seguridad para una sesión segura
Mediante el uso de un token de contexto de seguridad con estado (SCT) en una sesión segura, la sesión puede soportar que el servicio se recicle. Por ejemplo, cuando un SCT sin estado se utiliza en una sesión segura y se restablece Internet Information Services (IIS), a continuación, se pierden los datos de la sesión que están asociados al servicio. Estos datos de la sesión incluyen una caché de token de SCT. Así, la próxima vez que un cliente envíe un SCT sin estado al servicio, se devuelve un error, porque no se puede recuperar la clave que está asociada a SCT. Si, sin embargo, se utiliza un SCT con estado, la clave que está asociada a SCT se contiene dentro de SCT. Dado que la clave se contiene dentro de SCT y, por tanto, dentro del mensaje, el reciclaje del servicio no afecta a la sesión segura. De forma predeterminada, Windows Communication Foundation (WCF) usa SCT sin estado en una sesión segura. En este tema se detalla cómo utilizar SCT con estado en una sesión segura.  
  
> [!NOTE]
> Los SCT con estado no se puede utilizar en una sesión segura que implique un contrato que derive de <xref:System.ServiceModel.Channels.IDuplexChannel>.  
  
> [!NOTE]
> Para las aplicaciones que utilizan SCT con estado en una sesión segura, la identidad del subproceso para el servicio debe ser una cuenta de usuario que tenga un perfil de usuario asociado. Cuando el servicio se ejecuta bajo una cuenta que no tiene un perfil de usuario, como `Local Service`, se puede producir una excepción.  
  
> [!NOTE]
> Cuando se requiere la suplantación en Windows XP, utilice una sesión segura sin un SCT con estado. Cuando se utilizan SCT con estado con suplantación, se produce una <xref:System.InvalidOperationException>. Para obtener más información, vea [escenarios no admitidos](../../../../docs/framework/wcf/feature-details/unsupported-scenarios.md).  
  
### <a name="to-use-stateful-scts-in-a-secure-session"></a>Para utilizar SCT con estado en una sesión segura  
  
- Cree un enlace personalizado que especifique que una sesión segura que utiliza un SCT con estado protege los mensajes SOAP.  
  
    1. Defina un enlace personalizado, agregando una [ \<> customBinding](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) al archivo de configuración para el servicio.  
  
        ```xml  
        <customBinding>  
        ```  
  
    2. Agregue un [ \<enlace >](../../../../docs/framework/misc/binding.md) elemento secundario a la [ \<> customBinding](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md).  
  
         Especifique un nombre de enlace estableciendo el atributo `name` en un nombre único dentro del archivo de configuración.  
  
        ```xml  
        <binding name="StatefulSCTSecureSession">  
        ```  
  
    3. Especifique el modo de autenticación para los mensajes enviados hacia y desde este servicio agregando un [ \<](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) elemento [ \<](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)secundario de seguridad > al > customBinding.  
  
         Especifique que se utiliza una sesión segura estableciendo el atributo `authenticationMode` en `SecureConversation`. Especifique que se utilizan SCT con estado estableciendo el atributo `requireSecurityContextCancellation` en `false`.  
  
        ```xml  
        <security authenticationMode="SecureConversation"  
                  requireSecurityContextCancellation="false">  
        ```  
  
    4. Especifique cómo se autentica el cliente mientras se establece la sesión segura agregando un [ \<](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) [ \<elemento secundario secureConversationBootstrap >](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md) al > de seguridad.  
  
         Especifique cómo se autentica el cliente estableciendo el atributo `authenticationMode`.  
  
        ```xml  
        <secureConversationBootstrap authenticationMode="UserNameForCertificate" />  
        ```  
  
    5. Especifique la codificación de mensajes agregando un elemento de codificación, [ \<como textMessageEncoding >](../../../../docs/framework/configure-apps/file-schema/wcf/textmessageencoding.md).  
  
        ```xml  
        <textMessageEncoding />  
        ```  
  
    6. Especifique el transporte agregando un elemento de transporte, como el [ \<> httpTransport](../../../../docs/framework/configure-apps/file-schema/wcf/httptransport.md).  
  
        ```xml  
        <httpTransport />  
        ```  
  
     El ejemplo de código siguiente utiliza la configuración para especificar un enlace personalizado que los mensajes puedan utilizar con SCT con estado en una sesión segura.  
  
    ```xml  
    <customBinding>  
      <binding name="StatefulSCTSecureSession">  
        <security authenticationMode="SecureConversation"  
                  requireSecurityContextCancellation="false">  
          <secureConversationBootstrap authenticationMode="UserNameForCertificate" />  
        </security>  
        <textMessageEncoding />  
        <httpTransport />  
      </binding>  
    </customBinding>  
    ```  
  
## <a name="example"></a>Ejemplo  
 El ejemplo de código siguiente crea un enlace personalizado que utiliza el modo de autenticación <xref:System.ServiceModel.Configuration.AuthenticationMode.MutualCertificate> para arrancar una sesión segura.  
  
 [!code-csharp[c_CreateStatefulSCT#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_createstatefulsct/cs/secureservice.cs#2)]
 [!code-vb[c_CreateStatefulSCT#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_createstatefulsct/vb/secureservice.vb#2)]  
  
 Cuando se usa la autenticación de Windows en combinación con un SCT con estado, WCF no rellena <xref:System.ServiceModel.ServiceSecurityContext.WindowsIdentity%2A> la propiedad con la identidad del llamador real, sino que establece la propiedad en anónimo. Dado que la seguridad de WCF debe volver a crear el contenido del contexto de seguridad del servicio para cada solicitud del SCT entrante, el servidor no realiza un seguimiento de la sesión de seguridad en la memoria. Dado que es imposible serializar la instancia de <xref:System.Security.Principal.WindowsIdentity> en SCT, la propiedad <xref:System.ServiceModel.ServiceSecurityContext.WindowsIdentity%2A> devuelve una identidad anónima.  
  
 La siguiente configuración exhibe este comportamiento.  
  
```xml  
<customBinding>  
  <binding name="Cancellation">  
       <textMessageEncoding />  
        <security   
            requireSecurityContextCancellation="false">  
              <secureConversationBootstrap />  
      </security>  
    <httpTransport />  
  </binding>  
</customBinding>  
```  
  
## <a name="see-also"></a>Vea también

- [\<customBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
