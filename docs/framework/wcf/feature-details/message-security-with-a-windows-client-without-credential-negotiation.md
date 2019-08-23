---
title: Seguridad de los mensajes con un cliente de Windows sin negociación de credenciales
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: fc07a26c-cbee-41c5-8fb0-329085fef749
ms.openlocfilehash: 699ea45d67658ab9c768bf938d5336be7a5427c4
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69955361"
---
# <a name="message-security-with-a-windows-client-without-credential-negotiation"></a><span data-ttu-id="b2942-102">Seguridad de los mensajes con un cliente de Windows sin negociación de credenciales</span><span class="sxs-lookup"><span data-stu-id="b2942-102">Message Security with a Windows Client without Credential Negotiation</span></span>
<span data-ttu-id="b2942-103">En el escenario siguiente se muestra un servicio y un cliente de Windows Communication Foundation (WCF) protegidos por el protocolo Kerberos.</span><span class="sxs-lookup"><span data-stu-id="b2942-103">The following scenario shows a Windows Communication Foundation (WCF) client and service secured by the Kerberos protocol.</span></span>  
  
 <span data-ttu-id="b2942-104">Tanto el servicio como el cliente están en el mismo dominio, o dominios, de confianza.</span><span class="sxs-lookup"><span data-stu-id="b2942-104">Both the service and the client are in the same domain or trusted domains.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b2942-105">La diferencia entre este escenario y la [seguridad de los mensajes con un cliente de Windows](../../../../docs/framework/wcf/feature-details/message-security-with-a-windows-client.md) es que este escenario no negocia la credencial de servicio con el servicio antes de enviar el mensaje de aplicación.</span><span class="sxs-lookup"><span data-stu-id="b2942-105">The difference between this scenario and [Message Security with a Windows Client](../../../../docs/framework/wcf/feature-details/message-security-with-a-windows-client.md) is that this scenario does not negotiate the service credential with the service prior to sending the application message.</span></span> <span data-ttu-id="b2942-106">Además, debido a la necesidad del protocolo Kerberos, este escenario requiere un entorno de dominio de Windows.</span><span class="sxs-lookup"><span data-stu-id="b2942-106">Additionally, because this requires the Kerberos protocol, this scenario requires a Windows domain environment.</span></span>  
  
 <span data-ttu-id="b2942-107">![Seguridad de mensajes sin negociación] de credenciales (../../../../docs/framework/wcf/feature-details/media/0c9f9baa-2439-4ef9-92f4-43c242d85d0d.gif "0c9f9baa-2439-4ef9-92f4-43c242d85d0d")</span><span class="sxs-lookup"><span data-stu-id="b2942-107">![Message security without credential negotiation](../../../../docs/framework/wcf/feature-details/media/0c9f9baa-2439-4ef9-92f4-43c242d85d0d.gif "0c9f9baa-2439-4ef9-92f4-43c242d85d0d")</span></span>  
  
|<span data-ttu-id="b2942-108">Característica</span><span class="sxs-lookup"><span data-stu-id="b2942-108">Characteristic</span></span>|<span data-ttu-id="b2942-109">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="b2942-109">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="b2942-110">Modo de seguridad</span><span class="sxs-lookup"><span data-stu-id="b2942-110">Security Mode</span></span>|<span data-ttu-id="b2942-111">Message</span><span class="sxs-lookup"><span data-stu-id="b2942-111">Message</span></span>|  
|<span data-ttu-id="b2942-112">Interoperabilidad</span><span class="sxs-lookup"><span data-stu-id="b2942-112">Interoperability</span></span>|<span data-ttu-id="b2942-113">Sí, WS-Security con clientes Kerberos compatibles con el perfil del token</span><span class="sxs-lookup"><span data-stu-id="b2942-113">Yes, WS-Security with Kerberos token-profile compatible clients</span></span>|  
|<span data-ttu-id="b2942-114">Autenticación (servidor)</span><span class="sxs-lookup"><span data-stu-id="b2942-114">Authentication (Server)</span></span>|<span data-ttu-id="b2942-115">Autenticación mutua del servidor y el cliente</span><span class="sxs-lookup"><span data-stu-id="b2942-115">Mutual authentication of the server and client</span></span>|  
|<span data-ttu-id="b2942-116">Autenticación (cliente)</span><span class="sxs-lookup"><span data-stu-id="b2942-116">Authentication (Client)</span></span>|<span data-ttu-id="b2942-117">Autenticación mutua del servidor y el cliente</span><span class="sxs-lookup"><span data-stu-id="b2942-117">Mutual authentication of the server and client</span></span>|  
|<span data-ttu-id="b2942-118">Integridad</span><span class="sxs-lookup"><span data-stu-id="b2942-118">Integrity</span></span>|<span data-ttu-id="b2942-119">Sí</span><span class="sxs-lookup"><span data-stu-id="b2942-119">Yes</span></span>|  
|<span data-ttu-id="b2942-120">Confidencialidad</span><span class="sxs-lookup"><span data-stu-id="b2942-120">Confidentiality</span></span>|<span data-ttu-id="b2942-121">Sí</span><span class="sxs-lookup"><span data-stu-id="b2942-121">Yes</span></span>|  
|<span data-ttu-id="b2942-122">Transporte</span><span class="sxs-lookup"><span data-stu-id="b2942-122">Transport</span></span>|<span data-ttu-id="b2942-123">HTTP</span><span class="sxs-lookup"><span data-stu-id="b2942-123">HTTP</span></span>|  
|<span data-ttu-id="b2942-124">Enlace</span><span class="sxs-lookup"><span data-stu-id="b2942-124">Binding</span></span>|<xref:System.ServiceModel.WSHttpBinding>|  
  
## <a name="service"></a><span data-ttu-id="b2942-125">Servicio</span><span class="sxs-lookup"><span data-stu-id="b2942-125">Service</span></span>  
 <span data-ttu-id="b2942-126">El código y la configuración siguientes están diseñados para ejecutarse de forma independiente.</span><span class="sxs-lookup"><span data-stu-id="b2942-126">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="b2942-127">Realice una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="b2942-127">Do one of the following:</span></span>  
  
- <span data-ttu-id="b2942-128">Cree un servicio independiente mediante el código sin configuración.</span><span class="sxs-lookup"><span data-stu-id="b2942-128">Create a stand-alone service using the code with no configuration.</span></span>  
  
- <span data-ttu-id="b2942-129">Cree un servicio mediante la configuración proporcionada, pero sin definir ningún punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="b2942-129">Create a service using the supplied configuration, but do not define any endpoints.</span></span>  
  
### <a name="code"></a><span data-ttu-id="b2942-130">Código</span><span class="sxs-lookup"><span data-stu-id="b2942-130">Code</span></span>  
 <span data-ttu-id="b2942-131">El código siguiente crea un extremo de servicio que utiliza el modo de seguridad.</span><span class="sxs-lookup"><span data-stu-id="b2942-131">The following code creates a service endpoint that uses message security.</span></span> <span data-ttu-id="b2942-132">El código deshabilita la negociación de la credencial de servicio, y el establecimiento de un token de contexto de seguridad (SCT).</span><span class="sxs-lookup"><span data-stu-id="b2942-132">The code disables service credential negotiation, and the establishment of a security context token (SCT).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b2942-133">Para utilizar el tipo de credencial de Windows sin negociación, la cuenta de usuario del servicio debe tener acceso al nombre de entidad de seguridad de servicio (SPN) registrado en el dominio de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="b2942-133">To use the Windows credential type without negotiation, the service's user account must have access to service principal name (SPN) that is registered with the Active Directory domain.</span></span> <span data-ttu-id="b2942-134">Existen dos maneras de hacerlo:</span><span class="sxs-lookup"><span data-stu-id="b2942-134">You can do this in two ways:</span></span>  
  
1. <span data-ttu-id="b2942-135">Utilice el `NetworkService`, o la cuenta `LocalSystem`, para ejecutar el servicio.</span><span class="sxs-lookup"><span data-stu-id="b2942-135">Use the `NetworkService` or `LocalSystem` account to run your service.</span></span> <span data-ttu-id="b2942-136">Dado que esas cuentas tienen acceso al SPN del equipo que se establece cuando el equipo se une al dominio Active Directory, WCF genera automáticamente el elemento SPN apropiado dentro del punto de conexión del servicio en los metadatos del servicio (Descripción de servicios web). Language o WSDL).</span><span class="sxs-lookup"><span data-stu-id="b2942-136">Because those accounts have access to the machine SPN that is established when the machine joins the Active Directory domain, WCF automatically generates the proper SPN element inside the service's endpoint in the service's metadata (Web Services Description Language, or WSDL).</span></span>  
  
2. <span data-ttu-id="b2942-137">Utilice una cuenta de dominio arbitraria de Active Directory para ejecutar el servicio.</span><span class="sxs-lookup"><span data-stu-id="b2942-137">Use an arbitrary Active Directory domain account to run your service.</span></span> <span data-ttu-id="b2942-138">En este caso, es necesario establecer un SPN para esa cuenta de dominio.</span><span class="sxs-lookup"><span data-stu-id="b2942-138">In this case, you need to establish an SPN for that domain account.</span></span> <span data-ttu-id="b2942-139">Una manera de hacerlo es utilizar la herramienta de la utilidad Setspn.exe.</span><span class="sxs-lookup"><span data-stu-id="b2942-139">One way of doing this is to use the Setspn.exe utility tool.</span></span> <span data-ttu-id="b2942-140">Una vez creado el SPN para la cuenta del servicio, configure WCF para publicar ese SPN en los clientes del servicio a través de sus metadatos (WSDL).</span><span class="sxs-lookup"><span data-stu-id="b2942-140">Once the SPN is created for the service's account, configure WCF to publish that SPN to the service's clients through its metadata (WSDL).</span></span> <span data-ttu-id="b2942-141">Esto se consigue estableciendo la identidad del punto de conexión expuesto, mediante un archivo de configuración de la aplicación o el código.</span><span class="sxs-lookup"><span data-stu-id="b2942-141">This is done by setting the endpoint identity for the exposed endpoint, either though an application configuration file or code.</span></span> <span data-ttu-id="b2942-142">El siguiente ejemplo publica la identidad mediante programación.</span><span class="sxs-lookup"><span data-stu-id="b2942-142">The following example publishes the identity programmatically.</span></span>  
  
 <span data-ttu-id="b2942-143">Para obtener más información acerca de los SPN, el protocolo Kerberos y Active Directory, vea el [suplemento técnico de Kerberos para Windows](https://go.microsoft.com/fwlink/?LinkId=88330).</span><span class="sxs-lookup"><span data-stu-id="b2942-143">For more information about SPNs, the Kerberos protocol, and Active Directory, see [Kerberos Technical Supplement for Windows](https://go.microsoft.com/fwlink/?LinkId=88330).</span></span> <span data-ttu-id="b2942-144">Para obtener más información sobre las identidades del extremo, vea [modos de autenticación de SecurityBindingElement](../../../../docs/framework/wcf/feature-details/securitybindingelement-authentication-modes.md).</span><span class="sxs-lookup"><span data-stu-id="b2942-144">For more information about endpoint identities, see [SecurityBindingElement Authentication Modes](../../../../docs/framework/wcf/feature-details/securitybindingelement-authentication-modes.md).</span></span>  
  
 [!code-csharp[C_SecurityScenarios#12](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#12)]
 [!code-vb[C_SecurityScenarios#12](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#12)]  
  
### <a name="configuration"></a><span data-ttu-id="b2942-145">Configuración</span><span class="sxs-lookup"><span data-stu-id="b2942-145">Configuration</span></span>  
 <span data-ttu-id="b2942-146">En lugar del código, se puede utilizar la siguiente configuración.</span><span class="sxs-lookup"><span data-stu-id="b2942-146">The following configuration can be used instead of the code.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
  <system.serviceModel>  
    <behaviors />  
    <services>  
      <service behaviorConfiguration="" name="ServiceModel.Calculator">  
        <endpoint address="http://localhost/Calculator"   
                  binding="wsHttpBinding"  
                  bindingConfiguration="KerberosBinding"  
                  name="WSHttpBinding_ICalculator"  
                  contract="ServiceModel.ICalculator"   
                  listenUri="net.tcp://localhost/metadata" >  
         <identity>  
            <servicePrincipalName value="service_spn_name" />  
         </identity>  
        </endpoint>  
      </service>  
    </services>  
    <bindings>  
      <wsHttpBinding>  
        <binding name="KerberosBinding">  
          <security>  
            <message negotiateServiceCredential="false"   
                     establishSecurityContext="false" />  
          </security>  
        </binding>  
      </wsHttpBinding>  
    </bindings>  
    <client />  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="client"></a><span data-ttu-id="b2942-147">Cliente</span><span class="sxs-lookup"><span data-stu-id="b2942-147">Client</span></span>  
 <span data-ttu-id="b2942-148">El código y la configuración siguientes están diseñados para ejecutarse de forma independiente.</span><span class="sxs-lookup"><span data-stu-id="b2942-148">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="b2942-149">Realice una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="b2942-149">Do one of the following:</span></span>  
  
- <span data-ttu-id="b2942-150">Cree un cliente independiente mediante el código (y el código de cliente).</span><span class="sxs-lookup"><span data-stu-id="b2942-150">Create a stand-alone client using the code (and client code).</span></span>  
  
- <span data-ttu-id="b2942-151">Cree un cliente que no defina direcciones de punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="b2942-151">Create a client that does not define any endpoint addresses.</span></span> <span data-ttu-id="b2942-152">En su lugar, utilice el constructor de cliente que adopta el nombre de configuración como un argumento.</span><span class="sxs-lookup"><span data-stu-id="b2942-152">Instead, use the client constructor that takes the configuration name as an argument.</span></span> <span data-ttu-id="b2942-153">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="b2942-153">For example:</span></span>  
  
     [!code-csharp[C_SecurityScenarios#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#0)]
     [!code-vb[C_SecurityScenarios#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#0)]  
  
### <a name="code"></a><span data-ttu-id="b2942-154">Código</span><span class="sxs-lookup"><span data-stu-id="b2942-154">Code</span></span>  
 <span data-ttu-id="b2942-155">El siguiente código configura el cliente.</span><span class="sxs-lookup"><span data-stu-id="b2942-155">The following code configures the client.</span></span> <span data-ttu-id="b2942-156">El modo de seguridad se establece en mensaje, y el tipo de credencial de cliente se establece en Windows.</span><span class="sxs-lookup"><span data-stu-id="b2942-156">The security mode is set to Message, and the client credential type is set to Windows.</span></span> <span data-ttu-id="b2942-157">Tenga en cuenta que las propiedades <xref:System.ServiceModel.MessageSecurityOverHttp.NegotiateServiceCredential%2A> y <xref:System.ServiceModel.NonDualMessageSecurityOverHttp.EstablishSecurityContext%2A> se establecen en `false`.</span><span class="sxs-lookup"><span data-stu-id="b2942-157">Note that the <xref:System.ServiceModel.MessageSecurityOverHttp.NegotiateServiceCredential%2A> and <xref:System.ServiceModel.NonDualMessageSecurityOverHttp.EstablishSecurityContext%2A> properties are set to `false`.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b2942-158">Para utilizar el tipo de credencial de Windows sin negociación, el cliente debe configurarse con el SPN de la cuenta del servicio, antes de iniciar la comunicación con el servicio.</span><span class="sxs-lookup"><span data-stu-id="b2942-158">To use Windows credential type without negotiation, the client must be configured with the service's account SPN prior to commencing the communication with the service.</span></span> <span data-ttu-id="b2942-159">El cliente utiliza el SPN para obtener el token de Kerberos para autenticar y proteger la comunicación con el servicio.</span><span class="sxs-lookup"><span data-stu-id="b2942-159">The client uses the SPN to get the Kerberos token to authenticate and secure the communication with the service.</span></span> <span data-ttu-id="b2942-160">El ejemplo siguiente muestra cómo configurar el cliente con el SPN del servicio.</span><span class="sxs-lookup"><span data-stu-id="b2942-160">The following sample shows how to configure the client with the service's SPN.</span></span> <span data-ttu-id="b2942-161">Si usa la herramienta de [utilidad de metadatos de ServiceModel (SvcUtil. exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) para generar el cliente, el SPN del servicio se propagará automáticamente al cliente desde los metadatos del servicio (WSDL), si los metadatos del servicio contienen esa información.</span><span class="sxs-lookup"><span data-stu-id="b2942-161">If you are using the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) to generate the client, the service's SPN will be automatically propagated to the client from the service's metadata (WSDL), if the service's metadata contains that information.</span></span> <span data-ttu-id="b2942-162">Para obtener más información sobre cómo configurar el servicio para incluir su SPN en los metadatos del servicio, vea la sección "servicio" más adelante en este tema.</span><span class="sxs-lookup"><span data-stu-id="b2942-162">For more information about how to configure the service to include its SPN in the service's metadata, see the "Service" section later in this topic .</span></span>  
>   
>  <span data-ttu-id="b2942-163">Para obtener más información acerca de los SPN, Kerberos y Active Directory, vea el [suplemento técnico de Kerberos para Windows](https://go.microsoft.com/fwlink/?LinkId=88330).</span><span class="sxs-lookup"><span data-stu-id="b2942-163">For more information about SPNs, Kerberos, and Active Directory, see [Kerberos Technical Supplement for Windows](https://go.microsoft.com/fwlink/?LinkId=88330).</span></span> <span data-ttu-id="b2942-164">Para obtener más información sobre las identidades del extremo, vea el tema [modos de autenticación de SecurityBindingElement](../../../../docs/framework/wcf/feature-details/securitybindingelement-authentication-modes.md) .</span><span class="sxs-lookup"><span data-stu-id="b2942-164">For more information about endpoint identities, see [SecurityBindingElement Authentication Modes](../../../../docs/framework/wcf/feature-details/securitybindingelement-authentication-modes.md) topic.</span></span>  
  
 [!code-csharp[C_SecurityScenarios#19](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#19)]
 [!code-vb[C_SecurityScenarios#19](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#19)]  
  
### <a name="configuration"></a><span data-ttu-id="b2942-165">Configuración</span><span class="sxs-lookup"><span data-stu-id="b2942-165">Configuration</span></span>  
 <span data-ttu-id="b2942-166">El siguiente código configura el cliente.</span><span class="sxs-lookup"><span data-stu-id="b2942-166">The following code configures the client.</span></span> <span data-ttu-id="b2942-167">Tenga en cuenta que el [ \<elemento servicePrincipalName >](../../../../docs/framework/configure-apps/file-schema/wcf/serviceprincipalname.md) debe establecerse para que coincida con el SPN del servicio registrado para la cuenta del servicio en el dominio Active Directory.</span><span class="sxs-lookup"><span data-stu-id="b2942-167">Note that the [\<servicePrincipalName>](../../../../docs/framework/configure-apps/file-schema/wcf/serviceprincipalname.md) element must be set to match the service's SPN as registered for the service's account in the Active Directory domain.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
  <system.serviceModel>  
    <bindings>  
      <wsHttpBinding>  
        <binding name="WSHttpBinding_ICalculator" >  
          <security mode="Message">  
            <message clientCredentialType="Windows"   
                     negotiateServiceCredential="false"  
                     establishSecurityContext="false" />  
          </security>  
        </binding>  
      </wsHttpBinding>  
    </bindings>  
    <client>  
      <endpoint address="http://localhost/Calculator"   
                binding="wsHttpBinding"  
                bindingConfiguration="WSHttpBinding_ICalculator"  
                contract="ICalculator"  
                name="WSHttpBinding_ICalculator">  
        <identity>  
          <servicePrincipalName value="service_spn_name" />  
        </identity>  
      </endpoint>  
    </client>  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="b2942-168">Vea también</span><span class="sxs-lookup"><span data-stu-id="b2942-168">See also</span></span>

- [<span data-ttu-id="b2942-169">Información general sobre seguridad</span><span class="sxs-lookup"><span data-stu-id="b2942-169">Security Overview</span></span>](../../../../docs/framework/wcf/feature-details/security-overview.md)
- [<span data-ttu-id="b2942-170">Identidad del servicio y autenticación</span><span class="sxs-lookup"><span data-stu-id="b2942-170">Service Identity and Authentication</span></span>](../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="b2942-171">Modelo de seguridad para Windows Server App fabric</span><span class="sxs-lookup"><span data-stu-id="b2942-171">Security Model for Windows Server App Fabric</span></span>](https://go.microsoft.com/fwlink/?LinkID=201279&clcid=0x409)
