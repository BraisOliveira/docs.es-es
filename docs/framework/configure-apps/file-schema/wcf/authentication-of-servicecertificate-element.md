---
title: <authentication>del <serviceCertificate> elemento
ms.date: 03/30/2017
ms.assetid: 733b67b4-08a1-4d25-9741-10046f9357ef
ms.openlocfilehash: d770ba1f9a0a18c927b3a4bf6d4141286e3a380c
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69919983"
---
# <a name="authentication-of-servicecertificate-element"></a><span data-ttu-id="4e899-102">\<> de autenticación \<del elemento de > serviceCertificate</span><span class="sxs-lookup"><span data-stu-id="4e899-102">\<authentication> of \<serviceCertificate> Element</span></span>
<span data-ttu-id="4e899-103">Especifica la configuración utilizada por el proxy del cliente para autenticar certificados del servicio que se obtienen utilizando la negociación de SSL/TLS.</span><span class="sxs-lookup"><span data-stu-id="4e899-103">Specifies the settings used by the client proxy to authenticate service certificates that are obtained using SSL/TLS negotiation.</span></span>  
  
 <span data-ttu-id="4e899-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="4e899-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="4e899-105">\<comportamientos ></span><span class="sxs-lookup"><span data-stu-id="4e899-105">\<behaviors></span></span>  
<span data-ttu-id="4e899-106">sección endpointBehaviors</span><span class="sxs-lookup"><span data-stu-id="4e899-106">endpointBehaviors section</span></span>  
<span data-ttu-id="4e899-107">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="4e899-107">\<behavior></span></span>  
<span data-ttu-id="4e899-108">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="4e899-108">\<clientCredentials></span></span>  
<span data-ttu-id="4e899-109">\<serviceCertificate></span><span class="sxs-lookup"><span data-stu-id="4e899-109">\<serviceCertificate></span></span>  
<span data-ttu-id="4e899-110">\<> de autenticación</span><span class="sxs-lookup"><span data-stu-id="4e899-110">\<authentication></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4e899-111">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4e899-111">Syntax</span></span>  
  
```xml  
<authentication customCertificateValidatorType="String"
                certificateValidationMode="None/PeerTrust/ChainTrust/PeerOrChainTrust/Custom"
                revocationMode="NoCheck/Online/Offline"
                trustedStoreLocation="LocalMachine/CurrentUser" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4e899-112">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="4e899-112">Attributes and Elements</span></span>  
 <span data-ttu-id="4e899-113">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios</span><span class="sxs-lookup"><span data-stu-id="4e899-113">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4e899-114">Atributos</span><span class="sxs-lookup"><span data-stu-id="4e899-114">Attributes</span></span>  
  
|<span data-ttu-id="4e899-115">Atributo</span><span class="sxs-lookup"><span data-stu-id="4e899-115">Attribute</span></span>|<span data-ttu-id="4e899-116">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="4e899-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="4e899-117">customCertificateValidatorType</span><span class="sxs-lookup"><span data-stu-id="4e899-117">customCertificateValidatorType</span></span>|<span data-ttu-id="4e899-118">Cadena.</span><span class="sxs-lookup"><span data-stu-id="4e899-118">String.</span></span> <span data-ttu-id="4e899-119">Tipo y ensamblado utilizados para validar un tipo personalizado.</span><span class="sxs-lookup"><span data-stu-id="4e899-119">A type and assembly used to validate a custom type.</span></span>|  
|<span data-ttu-id="4e899-120">certificateValidationMode</span><span class="sxs-lookup"><span data-stu-id="4e899-120">certificateValidationMode</span></span>|<span data-ttu-id="4e899-121">Especifica uno de los tres modos utilizados para validar las credenciales.</span><span class="sxs-lookup"><span data-stu-id="4e899-121">Specifies one of three modes used to validate credentials.</span></span> <span data-ttu-id="4e899-122">Si se establece en `Custom`, también debe proporcionarse un customCertificateValidator.</span><span class="sxs-lookup"><span data-stu-id="4e899-122">If set to `Custom`, then a customCertificateValidator must also be supplied.</span></span> <span data-ttu-id="4e899-123">El valor predeterminado es `ChainTrust`.</span><span class="sxs-lookup"><span data-stu-id="4e899-123">The default is `ChainTrust`.</span></span>|  
|<span data-ttu-id="4e899-124">revocationMode</span><span class="sxs-lookup"><span data-stu-id="4e899-124">revocationMode</span></span>|<span data-ttu-id="4e899-125">Uno de los modos utilizados para comprobar listas de certificados revocadas (CRL).</span><span class="sxs-lookup"><span data-stu-id="4e899-125">One of the modes used to check for a revoked certificate lists (CRL).</span></span> <span data-ttu-id="4e899-126">El valor predeterminado es `Online`.</span><span class="sxs-lookup"><span data-stu-id="4e899-126">The default is `Online`.</span></span>|  
|<span data-ttu-id="4e899-127">trustedStoreLocation</span><span class="sxs-lookup"><span data-stu-id="4e899-127">trustedStoreLocation</span></span>|<span data-ttu-id="4e899-128">Una de las dos ubicaciones de almacenamiento del sistema: `LocalMachine` o `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="4e899-128">One of the two system store locations: `LocalMachine` or `CurrentUser`.</span></span> <span data-ttu-id="4e899-129">Se utiliza este valor cuando un certificado del servicio se negocia al cliente.</span><span class="sxs-lookup"><span data-stu-id="4e899-129">This value is used when a service certificate is negotiated to the client.</span></span> <span data-ttu-id="4e899-130">La validación se realiza en el almacén de **personas de confianza** en la ubicación de almacén especificada.</span><span class="sxs-lookup"><span data-stu-id="4e899-130">Validation is performed against the **Trusted People** store in the specified store location.</span></span> <span data-ttu-id="4e899-131">El valor predeterminado es `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="4e899-131">The default is `CurrentUser`.</span></span>|  
  
## <a name="customcertificatevalidator-attribute"></a><span data-ttu-id="4e899-132">Atributo customCertificateValidator</span><span class="sxs-lookup"><span data-stu-id="4e899-132">customCertificateValidator Attribute</span></span>  
  
|<span data-ttu-id="4e899-133">Valor</span><span class="sxs-lookup"><span data-stu-id="4e899-133">Value</span></span>|<span data-ttu-id="4e899-134">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="4e899-134">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="4e899-135">string</span><span class="sxs-lookup"><span data-stu-id="4e899-135">String</span></span>|<span data-ttu-id="4e899-136">Especifica el nombre de tipo y el ensamblado y otros datos utilizados para buscar el tipo.</span><span class="sxs-lookup"><span data-stu-id="4e899-136">Specifies the type name and assembly and other data used to find the type.</span></span>|  
  
## <a name="certificatevalidationmode-attribute"></a><span data-ttu-id="4e899-137">Atributo certificateValidationMode</span><span class="sxs-lookup"><span data-stu-id="4e899-137">certificateValidationMode Attribute</span></span>  
  
|<span data-ttu-id="4e899-138">Valor</span><span class="sxs-lookup"><span data-stu-id="4e899-138">Value</span></span>|<span data-ttu-id="4e899-139">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="4e899-139">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="4e899-140">Enumeración</span><span class="sxs-lookup"><span data-stu-id="4e899-140">Enumeration</span></span>|<span data-ttu-id="4e899-141">Uno de los siguientes valores: None, confianza, ChainTrust, PeerOrChainTrust, Custom.</span><span class="sxs-lookup"><span data-stu-id="4e899-141">One of the following values: None, PeerTrust, ChainTrust, PeerOrChainTrust, Custom.</span></span><br /><br /> <span data-ttu-id="4e899-142">Para obtener más información, consulte [trabajar con certificados](../../../wcf/feature-details/working-with-certificates.md).</span><span class="sxs-lookup"><span data-stu-id="4e899-142">For more information, see [Working with Certificates](../../../wcf/feature-details/working-with-certificates.md).</span></span>|  
  
## <a name="revocationmode-attribute"></a><span data-ttu-id="4e899-143">Atributo revocationMode</span><span class="sxs-lookup"><span data-stu-id="4e899-143">revocationMode Attribute</span></span>  
  
|<span data-ttu-id="4e899-144">Valor</span><span class="sxs-lookup"><span data-stu-id="4e899-144">Value</span></span>|<span data-ttu-id="4e899-145">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="4e899-145">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="4e899-146">Enumeración</span><span class="sxs-lookup"><span data-stu-id="4e899-146">Enumeration</span></span>|<span data-ttu-id="4e899-147">Uno de los siguientes valores: Nocheck, en línea, sin conexión.</span><span class="sxs-lookup"><span data-stu-id="4e899-147">One of the following values: NoCheck, Online, Offline.</span></span><br /><br /> <span data-ttu-id="4e899-148">Para obtener más información, consulte [trabajar con certificados](../../../wcf/feature-details/working-with-certificates.md).</span><span class="sxs-lookup"><span data-stu-id="4e899-148">For more information, see [Working with Certificates](../../../wcf/feature-details/working-with-certificates.md).</span></span>|  
  
## <a name="trustedstorelocation-attribute"></a><span data-ttu-id="4e899-149">Atributo trustedStoreLocation</span><span class="sxs-lookup"><span data-stu-id="4e899-149">trustedStoreLocation Attribute</span></span>  
  
|<span data-ttu-id="4e899-150">Valor</span><span class="sxs-lookup"><span data-stu-id="4e899-150">Value</span></span>|<span data-ttu-id="4e899-151">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="4e899-151">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="4e899-152">Enumeración</span><span class="sxs-lookup"><span data-stu-id="4e899-152">Enumeration</span></span>|<span data-ttu-id="4e899-153">Uno de los siguientes valores: LocalMachine o CurrentUser.</span><span class="sxs-lookup"><span data-stu-id="4e899-153">One of the following values: LocalMachine or CurrentUser.</span></span> <span data-ttu-id="4e899-154">El valor predeterminado es CurrentUser.</span><span class="sxs-lookup"><span data-stu-id="4e899-154">The default is CurrentUser.</span></span> <span data-ttu-id="4e899-155">Si la aplicación cliente se está ejecutando bajo una cuenta del sistema, entonces el certificado está normalmente en LocalMachine.</span><span class="sxs-lookup"><span data-stu-id="4e899-155">If the client application is running under a system account, then the certificate is typically under LocalMachine.</span></span> <span data-ttu-id="4e899-156">Si la aplicación cliente se está ejecutando en una cuenta de usuario, entonces el certificado se encuentra normalmente en CurrentUser.</span><span class="sxs-lookup"><span data-stu-id="4e899-156">If the client application is running under a user account, then the certificate is typically in CurrentUser.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4e899-157">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="4e899-157">Child Elements</span></span>  
 <span data-ttu-id="4e899-158">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="4e899-158">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="4e899-159">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="4e899-159">Parent Elements</span></span>  
  
|<span data-ttu-id="4e899-160">Elemento</span><span class="sxs-lookup"><span data-stu-id="4e899-160">Element</span></span>|<span data-ttu-id="4e899-161">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="4e899-161">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4e899-162">\<serviceCertificate></span><span class="sxs-lookup"><span data-stu-id="4e899-162">\<serviceCertificate></span></span>](servicecertificate-of-clientcredentials-element.md)|<span data-ttu-id="4e899-163">Especifica el certificado que se va a utilizar al autenticar un servicio al cliente.</span><span class="sxs-lookup"><span data-stu-id="4e899-163">Specifies a certificate to use when authenticating a service to the client.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4e899-164">Comentarios</span><span class="sxs-lookup"><span data-stu-id="4e899-164">Remarks</span></span>  
 <span data-ttu-id="4e899-165">El atributo `certificateValidationMode` de este elemento de configuración especifica el nivel de confianza utilizado para autenticar certificados.</span><span class="sxs-lookup"><span data-stu-id="4e899-165">The `certificateValidationMode` attribute of this configuration element specifies the level of trust used to authenticate certificates.</span></span> <span data-ttu-id="4e899-166">De forma predeterminada, el nivel se establece en `ChainTrust`, que especifica que cada certificado debe encontrarse en una jerarquía de certificados que finalizan en una entidad emisora de certificados de confianza en la parte superior de la cadena.</span><span class="sxs-lookup"><span data-stu-id="4e899-166">By default, the level is set to `ChainTrust`, which specifies that each certificate must be found in a hierarchy of certificates ending in a trusted certification authority at the top of the chain.</span></span> <span data-ttu-id="4e899-167">Este es el modo más seguro.</span><span class="sxs-lookup"><span data-stu-id="4e899-167">This is the most secure mode.</span></span> <span data-ttu-id="4e899-168">También puede establecer el valor en `PeerOrChainTrust`, que especifica que los certificados autoemitidos (confianza del mismo nivel) se aceptan, así como los certificados que están en una cadena de confianza.</span><span class="sxs-lookup"><span data-stu-id="4e899-168">You can also set the value to `PeerOrChainTrust`, which specifies that self-issued certificates (peer trust) are accepted as well as certificates that are in a trusted chain.</span></span> <span data-ttu-id="4e899-169">Se utiliza este valor cuando se desarrollan y depuran clientes y servicios porque los certificados autoemitidos no necesitan adquirirse desde una autoridad de confianza.</span><span class="sxs-lookup"><span data-stu-id="4e899-169">This value is used when developing and debugging clients and services because self-issued certificates need not be purchased from a trusted authority.</span></span> <span data-ttu-id="4e899-170">Al implementar un cliente, utilice en su lugar el valor `ChainTrust`.</span><span class="sxs-lookup"><span data-stu-id="4e899-170">When deploying a client, use the `ChainTrust` value instead.</span></span> <span data-ttu-id="4e899-171">También puede establecer el valor como `Custom` o `None`.</span><span class="sxs-lookup"><span data-stu-id="4e899-171">You can also set the value to `Custom` or `None`.</span></span> <span data-ttu-id="4e899-172">Para utilizar el valor `Custom`, también debe establecer el atributo `customCertificateValidator` en un ensamblado y tipo utilizado para validar el certificado.</span><span class="sxs-lookup"><span data-stu-id="4e899-172">To use the `Custom` value, you must also set the `customCertificateValidator` attribute to an assembly and type used to validate the certificate.</span></span> <span data-ttu-id="4e899-173">Para crear su propio validador personalizado, debe heredar a partir de la clase abstracta X509CertificateValidator.</span><span class="sxs-lookup"><span data-stu-id="4e899-173">To create your own custom validator, you must inherit from the abstract X509CertificateValidator class.</span></span> <span data-ttu-id="4e899-174">Para obtener más información, consulte [Cómo Cree un servicio que emplee un validador](../../../wcf/extending/how-to-create-a-service-that-employs-a-custom-certificate-validator.md)de certificado personalizado.</span><span class="sxs-lookup"><span data-stu-id="4e899-174">For more information, see [How to: Create a Service that Employs a Custom Certificate Validator](../../../wcf/extending/how-to-create-a-service-that-employs-a-custom-certificate-validator.md).</span></span>  
  
 <span data-ttu-id="4e899-175">El atributo `revocationMode` especifica cómo se comprueba la revocación de los certificados.</span><span class="sxs-lookup"><span data-stu-id="4e899-175">The `revocationMode` attribute specifies how certificates are checked for revocation.</span></span> <span data-ttu-id="4e899-176">El valor predeterminado es `online` que indica que se comprobará automáticamente la revocación de los certificados.</span><span class="sxs-lookup"><span data-stu-id="4e899-176">The default is `online` which indicates that certificates will be checked automatically for revocation.</span></span> <span data-ttu-id="4e899-177">Para obtener más información, consulte [trabajar con certificados](../../../wcf/feature-details/working-with-certificates.md).</span><span class="sxs-lookup"><span data-stu-id="4e899-177">For more information, see [Working with Certificates](../../../wcf/feature-details/working-with-certificates.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="4e899-178">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="4e899-178">Example</span></span>  
 <span data-ttu-id="4e899-179">El siguiente ejemplo realiza dos tareas:</span><span class="sxs-lookup"><span data-stu-id="4e899-179">The following example does two tasks.</span></span> <span data-ttu-id="4e899-180">En primer lugar, especifica un certificado de servicio para que el cliente lo utilice al comunicarse con puntos de `www.contoso.com` conexión cuyo nombre de dominio está por encima del protocolo http.</span><span class="sxs-lookup"><span data-stu-id="4e899-180">It first specifies a service certificate for the client to use when communicating with endpoints whose domain name is `www.contoso.com` over the HTTP protocol.</span></span> <span data-ttu-id="4e899-181">En segundo lugar, especifica el modo de revocación y ubicación del almacén utilizado durante la autenticación.</span><span class="sxs-lookup"><span data-stu-id="4e899-181">Second, it specifies the revocation mode and store location used during authentication.</span></span>  
  
```xml  
<serviceCertificate>
  <defaultCertificate findValue="www.contoso.com"
                      storeLocation="LocalMachine"
                      storeName="TrustedPeople"
                      x509FindType="FindByIssuerDistinguishedName" />
  <scopedCertificates>
     <add targetUri="http://www.contoso.com"
          findValue="www.contoso.com"
          storeLocation="LocalMachine"
          storeName="Root"
          x509FindType="FindByIssuerName" />
  </scopedCertificates>
  <authentication revocationMode="Online"
                  trustedStoreLocation="LocalMachine" />
</serviceCertificate>
```  
  
## <a name="see-also"></a><span data-ttu-id="4e899-182">Vea también</span><span class="sxs-lookup"><span data-stu-id="4e899-182">See also</span></span>

- <xref:System.ServiceModel.Configuration.X509RecipientCertificateClientElement>
- <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential>
- <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential.Authentication%2A>
- <xref:System.ServiceModel.Security.X509ServiceCertificateAuthentication>
- [<span data-ttu-id="4e899-183">Comportamientos de seguridad</span><span class="sxs-lookup"><span data-stu-id="4e899-183">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="4e899-184">Trabajo con certificados</span><span class="sxs-lookup"><span data-stu-id="4e899-184">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="4e899-185">Procedimientos: Crear un servicio que emplee un validador de certificado personalizado</span><span class="sxs-lookup"><span data-stu-id="4e899-185">How to: Create a Service that Employs a Custom Certificate Validator</span></span>](../../../wcf/extending/how-to-create-a-service-that-employs-a-custom-certificate-validator.md)
- [<span data-ttu-id="4e899-186">\<authentication></span><span class="sxs-lookup"><span data-stu-id="4e899-186">\<authentication></span></span>](authentication-of-clientcertificate-element.md)
- [<span data-ttu-id="4e899-187">Protección de clientes</span><span class="sxs-lookup"><span data-stu-id="4e899-187">Securing Clients</span></span>](../../../wcf/securing-clients.md)
- [<span data-ttu-id="4e899-188">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="4e899-188">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
