---
title: Procedimiento para establecer un sesgo de reloj máximo
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- MaxClockSkew property
- WCF, custom bindings
ms.assetid: 491d1705-eb29-43c2-a44c-c0cf996f74eb
ms.openlocfilehash: 3bcd128e6e9f53f662dd3fc99336b5b45faebf5f
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69943118"
---
# <a name="how-to-set-a-max-clock-skew"></a>Procedimiento para establecer un sesgo de reloj máximo
Las funciones críticas en el tiempo se pueden desbaratar si los ajustes del reloj en dos equipos son diferentes. Para mitigar esta posibilidad, puede establecer la propiedad `MaxClockSkew` en <xref:System.TimeSpan>. Esta propiedad está disponible en dos clases:  
  
 <xref:System.ServiceModel.Channels.LocalClientSecuritySettings>  
  
 <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings>  
  
> [!IMPORTANT]
> En el caso de una conversación segura, `MaxClockSkew` se deben realizar cambios en la propiedad cuando se arranque el servicio o el cliente. Para ello, debe establecer la propiedad en la <xref:System.ServiceModel.Channels.SecurityBindingElement> devuelta por la <xref:System.ServiceModel.Security.Tokens.SecureConversationSecurityTokenParameters.BootstrapSecurityBindingElement%2A?displayProperty=nameWithType> propiedad.  
  
 Para cambiar la propiedad en uno de los enlaces proporcionados por el sistema, debe encontrar el elemento de enlace de seguridad en la colección de enlaces y establecer la propiedad `MaxClockSkew` en un nuevo valor. Dos clases derivan de <xref:System.ServiceModel.Channels.SecurityBindingElement>: <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> y <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement>. Al recuperar el enlace de seguridad de la colección, debe convertir a uno de estos tipos para establecer correctamente la propiedad `MaxClockSkew`. El siguiente ejemplo usa un <xref:System.ServiceModel.WSHttpBinding>, que utiliza el <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement>. Para obtener una lista que especifica qué tipo de enlace de seguridad utilizar en cada enlace proporcionado por el sistema, consulte [enlaces proporcionados](../../../../docs/framework/wcf/system-provided-bindings.md)por el sistema.  
  
## <a name="to-create-a-custom-binding-with-a-new-clock-skew-value-in-code"></a>Para crear un enlace personalizado con un nuevo valor de sesgo de reloj en código  
  
> [!WARNING]
> Agregue referencias a los siguientes espacios de nombres en el código <xref:System.ServiceModel.Channels>: <xref:System.ServiceModel.Description> <xref:System.Security.Permissions>,, y <xref:System.ServiceModel.Security.Tokens>.  
  
1. Cree una instancia de una clase <xref:System.ServiceModel.WSHttpBinding> y establezca su modo de seguridad en <xref:System.ServiceModel.SecurityMode.Message?displayProperty=nameWithType>.  
  
2. Cree una nueva instancia de la clase <xref:System.ServiceModel.Channels.BindingElementCollection> llamando al método <xref:System.ServiceModel.WSHttpBinding.CreateBindingElements%2A>.  
  
3. Utilice el método <xref:System.ServiceModel.Channels.BindingElementCollection.Find%2A> de la clase <xref:System.ServiceModel.Channels.BindingElementCollection> para encontrar el elemento del enlace de seguridad.  
  
4. Al utilizar el método <xref:System.ServiceModel.Channels.BindingElementCollection.Find%2A>, convierta al tipo real. El ejemplo siguiente convierte al tipo <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement>.  
  
5. Establezca la propiedad <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings.MaxClockSkew%2A> en el elemento del enlace de seguridad.  
  
6. Cree un <xref:System.ServiceModel.ServiceHost> con un tipo de servicio y dirección base adecuados.  
  
7. Utilice el método <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%2A> para agregar un extremo e incluir el <xref:System.ServiceModel.Channels.CustomBinding>.  
  
     [!code-csharp[c_MaxClockSkew#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_maxclockskew/cs/source.cs#1)]
     [!code-vb[c_MaxClockSkew#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_maxclockskew/vb/source.vb#1)]  
  
## <a name="to-set-the-maxclockskew-in-configuration"></a>Para establecer MaxClockSkew en la configuración  
  
1. Cree una [ \<> customBinding](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) en la [ \<sección de enlaces >](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) elemento.  
  
2. Cree un [ \<enlace >](../../../../docs/framework/misc/binding.md) elemento y establezca el `name` atributo en un valor adecuado. El siguiente ejemplo lo define en `MaxClockSkewBinding`.  
  
3. Agregue un elemento de codificación. En el ejemplo siguiente se agrega una [ \<> textMessageEncoding](../../../../docs/framework/configure-apps/file-schema/wcf/textmessageencoding.md).  
  
4. Agregue un [ \<](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) elemento de > de seguridad y `authenticationMode` establezca el atributo en un valor adecuado. El siguiente ejemplo establece el atributo en `Kerberos` para especificar que el servicio usa autenticación de Windows.  
  
5. Agregue un [ \<> localServiceSettings](../../../../docs/framework/configure-apps/file-schema/wcf/localservicesettings-element.md) y establezca el `maxClockSkew` atributo `"##:##:##"`en un valor con el formato. El siguiente ejemplo lo establece en 7 minutos. Opcionalmente, agregue un [ \<> localServiceSettings](../../../../docs/framework/configure-apps/file-schema/wcf/localservicesettings-element.md) y establezca el `maxClockSkew` atributo en un valor adecuado.  
  
6. Agregue un elemento de transporte. En el ejemplo siguiente se usa un [ \<> httpTransport](../../../../docs/framework/configure-apps/file-schema/wcf/httptransport.md).  
  
7. En el caso de una conversación segura, la configuración de seguridad se debe producir [ \<](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md) en el bootstrap en el elemento > de secureConversationBootstrap.  
  
    ```xml  
    <bindings>  
      <customBinding>  
        <binding name="MaxClockSkewBinding">  
            <textMessageEncoding />  
            <security authenticationMode="Kerberos">  
               <localClientSettings maxClockSkew="00:07:00" />  
               <localServiceSettings maxClockSkew="00:07:00" />  
               <secureConversationBootstrap>  
                  <localClientSettings maxClockSkew="00:30:00" />  
                  <localServiceSettings maxClockSkew="00:30:00" />  
               </secureConversationBootstrap>  
            </security>  
            <httpTransport />  
        </binding>  
      </customBinding>  
    </bindings>  
    ```  
  
## <a name="see-also"></a>Vea también

- <xref:System.ServiceModel.Channels.LocalClientSecuritySettings>
- <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [Procedimientos: Crear un enlace personalizado mediante SecurityBindingElement](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)
