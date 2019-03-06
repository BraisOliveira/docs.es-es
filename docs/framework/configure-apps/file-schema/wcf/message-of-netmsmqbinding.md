---
title: <message> de <netMsmqBinding>
ms.date: 03/30/2017
ms.assetid: 6ebf0240-d7be-4493-b0fe-f00fd5989d77
ms.openlocfilehash: 306bc56820cdbcba17cce9fc50d426260eb0e0d4
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2019
ms.locfileid: "57360672"
---
# <a name="message-of-netmsmqbinding"></a><span data-ttu-id="9a07a-102">\<mensaje > de \<netMsmqBinding ></span><span class="sxs-lookup"><span data-stu-id="9a07a-102">\<message> of \<netMsmqBinding></span></span>

<span data-ttu-id="9a07a-103">Define la configuración de seguridad del mensaje SOAP en este enlace `netMsmqBinding`.</span><span class="sxs-lookup"><span data-stu-id="9a07a-103">Defines the SOAP message security settings on this `netMsmqBinding` binding.</span></span>

<span data-ttu-id="9a07a-104">\<system.ServiceModel>\\</span><span class="sxs-lookup"><span data-stu-id="9a07a-104">\<system.ServiceModel>\\</span></span>
<span data-ttu-id="9a07a-105">\<bindings>\\</span><span class="sxs-lookup"><span data-stu-id="9a07a-105">\<bindings>\\</span></span>
<span data-ttu-id="9a07a-106">\<netMsmqBinding>\\</span><span class="sxs-lookup"><span data-stu-id="9a07a-106">\<netMsmqBinding>\\</span></span>
<span data-ttu-id="9a07a-107">\<binding>\\</span><span class="sxs-lookup"><span data-stu-id="9a07a-107">\<binding>\\</span></span>
<span data-ttu-id="9a07a-108">\<seguridad > \\</span><span class="sxs-lookup"><span data-stu-id="9a07a-108">\<security>\\</span></span>
<span data-ttu-id="9a07a-109">\<message></span><span class="sxs-lookup"><span data-stu-id="9a07a-109">\<message></span></span>

## <a name="syntax"></a><span data-ttu-id="9a07a-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9a07a-110">Syntax</span></span>

```xml
<netMsmqBinding>
  <binding>
    <security>
      <message algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
               clientCredentialType="None/Windows/UserName/Certificate/CardSpace" />
    </security>
  </binding>
</netMsmqBinding>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="9a07a-111">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="9a07a-111">Attributes and Elements</span></span>

<span data-ttu-id="9a07a-112">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="9a07a-112">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="9a07a-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="9a07a-113">Attributes</span></span>

|<span data-ttu-id="9a07a-114">Atributo</span><span class="sxs-lookup"><span data-stu-id="9a07a-114">Attribute</span></span>|<span data-ttu-id="9a07a-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="9a07a-115">Description</span></span>|
|---------------|-----------------|
|<span data-ttu-id="9a07a-116">algorithmSuite</span><span class="sxs-lookup"><span data-stu-id="9a07a-116">algorithmSuite</span></span>|<span data-ttu-id="9a07a-117">Establece el cifrado de mensajes y algoritmos de ajuste de clave que se utilizan para lograr la seguridad basada en mensaje para los mensajes enviados sobre transporte de MSMQ.</span><span class="sxs-lookup"><span data-stu-id="9a07a-117">Sets the message encryption and key-wrap algorithms that are used to achieve message-based security for messages sent over MSMQ transport.</span></span><br /><br /> <span data-ttu-id="9a07a-118">El valor predeterminado es `Aes256`.</span><span class="sxs-lookup"><span data-stu-id="9a07a-118">The default value is `Aes256`.</span></span> <span data-ttu-id="9a07a-119">Este atributo es del tipo <xref:System.ServiceModel.Security.SecurityAlgorithmSuite>.</span><span class="sxs-lookup"><span data-stu-id="9a07a-119">This attribute is of type <xref:System.ServiceModel.Security.SecurityAlgorithmSuite>.</span></span>|
|<span data-ttu-id="9a07a-120">clientCredentialType</span><span class="sxs-lookup"><span data-stu-id="9a07a-120">clientCredentialType</span></span>|<span data-ttu-id="9a07a-121">Especifica el tipo de credencial que se va a utilizar al realizar la autenticación del cliente para los mensajes enviados sobre el transporte de MSMQ.</span><span class="sxs-lookup"><span data-stu-id="9a07a-121">Specifies the type of credential to be used when performing client authentication for messages sent over the MSMQ transport.</span></span> <span data-ttu-id="9a07a-122">Los valores válidos son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="9a07a-122">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="9a07a-123">-None: Esto permite al servicio interactuar con clientes anónimos.</span><span class="sxs-lookup"><span data-stu-id="9a07a-123">-   None: This allows the service to interact with anonymous clients.</span></span> <span data-ttu-id="9a07a-124">Ni el servicio ni el cliente requieren una credencial.</span><span class="sxs-lookup"><span data-stu-id="9a07a-124">Neither the service nor the client requires a credential.</span></span><br /><span data-ttu-id="9a07a-125">-Windows: Esto permite que los intercambios de SOAP estar bajo el contexto autenticado de una credencial de Windows.</span><span class="sxs-lookup"><span data-stu-id="9a07a-125">-   Windows: This enables the SOAP exchanges to be under the authenticated context of a Windows credential.</span></span> <span data-ttu-id="9a07a-126">Esto siempre realiza una autenticación basada en Kerberos.</span><span class="sxs-lookup"><span data-stu-id="9a07a-126">This always performs Kerberos-based authentication.</span></span><br /><span data-ttu-id="9a07a-127">-   UserName: Esto permite al servicio exigir que el cliente se autentique utilizando una credencial UserName.</span><span class="sxs-lookup"><span data-stu-id="9a07a-127">-   UserName: This enables the service to require that the client be authenticated using a UserName credential.</span></span> <span data-ttu-id="9a07a-128">La credencial en este caso necesita ser especificada utilizando el `clientCredentials` comportamiento **Precaución:**  Windows Communication Foundation (WCF) no admite enviar un resumen de contraseña ni derivar claves mediante contraseña y utilizando tales claves para seguridad de mensajes.</span><span class="sxs-lookup"><span data-stu-id="9a07a-128">The credential in this case needs to be specified using the `clientCredentials` behavior **Caution:**  Windows Communication Foundation (WCF) does not support sending a password digest or deriving keys using password and using such keys for message security.</span></span> <span data-ttu-id="9a07a-129">Por lo tanto, WCF impone que el intercambio sea seguro al usar credenciales UserName.</span><span class="sxs-lookup"><span data-stu-id="9a07a-129">Therefore, WCF enforces that the exchange is secured when using UserName credentials.</span></span> <span data-ttu-id="9a07a-130">Este modo requiere que el certificado del servicio se especifique en el lado del cliente mediante el comportamiento de `clientCredential` y `serviceCertificate`.</span><span class="sxs-lookup"><span data-stu-id="9a07a-130">This mode requires that the service certificate be specified on the client side using `clientCredential` behavior and `serviceCertificate`.</span></span> <br /><br /> <span data-ttu-id="9a07a-131">-Certificado: Esto permite al servicio exigir que el cliente se autentique utilizando un certificado.</span><span class="sxs-lookup"><span data-stu-id="9a07a-131">-   Certificate: This enables the service to require that the client be authenticated using a certificate.</span></span> <span data-ttu-id="9a07a-132">Las credenciales del cliente en este caso tienen que especificarse mediante el comportamiento `clientCredentials`.</span><span class="sxs-lookup"><span data-stu-id="9a07a-132">The client credential in this case needs to be specified using the `clientCredentials` behavior.</span></span> <span data-ttu-id="9a07a-133">La credencial del servicio en este caso necesita ser especificada utilizando el comportamiento `clientCredentials` especificando `serviceCertificate`.</span><span class="sxs-lookup"><span data-stu-id="9a07a-133">The service credential in this case needs to be specified using the `clientCredentials` behavior by specifying the `serviceCertificate`.</span></span><br /><span data-ttu-id="9a07a-134">-CardSpace: Esto permite al servicio exigir que el cliente se autentique utilizando un CardSpace.</span><span class="sxs-lookup"><span data-stu-id="9a07a-134">-   CardSpace: This allows the service to require that the client be authenticated using a CardSpace.</span></span> <span data-ttu-id="9a07a-135">Se debe proporcionar `serviceCertificate` en el comportamiento `clientCredential`.</span><span class="sxs-lookup"><span data-stu-id="9a07a-135">The `serviceCertificate` must be provisioned in the `clientCredential` behavior.</span></span><br /><br /> <span data-ttu-id="9a07a-136">El valor predeterminado es `Windows`.</span><span class="sxs-lookup"><span data-stu-id="9a07a-136">The default value is `Windows`.</span></span> <span data-ttu-id="9a07a-137">Este atributo es del tipo <xref:System.ServiceModel.MessageCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="9a07a-137">This attribute is of type <xref:System.ServiceModel.MessageCredentialType>.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="9a07a-138">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="9a07a-138">Child Elements</span></span>

<span data-ttu-id="9a07a-139">Ninguna</span><span class="sxs-lookup"><span data-stu-id="9a07a-139">None</span></span>

### <a name="parent-elements"></a><span data-ttu-id="9a07a-140">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="9a07a-140">Parent Elements</span></span>

|<span data-ttu-id="9a07a-141">Elemento</span><span class="sxs-lookup"><span data-stu-id="9a07a-141">Element</span></span>|<span data-ttu-id="9a07a-142">Descripción</span><span class="sxs-lookup"><span data-stu-id="9a07a-142">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="9a07a-143">\<security></span><span class="sxs-lookup"><span data-stu-id="9a07a-143">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-netmsmqbinding.md)|<span data-ttu-id="9a07a-144">Define la configuración de seguridad de un enlace.</span><span class="sxs-lookup"><span data-stu-id="9a07a-144">Defines the security settings for a binding.</span></span>|

## <a name="see-also"></a><span data-ttu-id="9a07a-145">Vea también</span><span class="sxs-lookup"><span data-stu-id="9a07a-145">See also</span></span>

- <xref:System.ServiceModel.Configuration.MessageSecurityOverMsmqElement>
- <xref:System.ServiceModel.Configuration.NetMsmqSecurityElement.Message%2A>
- <xref:System.ServiceModel.NetMsmqSecurity.Message%2A>
- <xref:System.ServiceModel.MessageSecurityOverMsmq>
- [<span data-ttu-id="9a07a-146">Colas en WCF</span><span class="sxs-lookup"><span data-stu-id="9a07a-146">Queues in WCF</span></span>](../../../../../docs/framework/wcf/feature-details/queues-in-wcf.md)
- [<span data-ttu-id="9a07a-147">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="9a07a-147">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="9a07a-148">Enlaces</span><span class="sxs-lookup"><span data-stu-id="9a07a-148">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="9a07a-149">Configuración de enlaces proporcionados por el sistema</span><span class="sxs-lookup"><span data-stu-id="9a07a-149">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="9a07a-150">Utilización de enlaces para configurar servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="9a07a-150">Using Bindings to Configure Services and Clients</span></span>](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="9a07a-151">\<binding></span><span class="sxs-lookup"><span data-stu-id="9a07a-151">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
