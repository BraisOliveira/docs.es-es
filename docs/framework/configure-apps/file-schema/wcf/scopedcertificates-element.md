---
title: <scopedCertificates> (Elemento)
ms.date: 03/30/2017
ms.assetid: c7b6fc35-d4b2-4c18-98bd-83e09591f1d3
ms.openlocfilehash: 73e78a6ca27ed45e1eadc7121987b75f79bc6aa5
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61670643"
---
# <a name="scopedcertificates-element"></a><span data-ttu-id="0cea5-102">\<scopedCertificates > elemento</span><span class="sxs-lookup"><span data-stu-id="0cea5-102">\<scopedCertificates> Element</span></span>
<span data-ttu-id="0cea5-103">Representa una colección de certificados X.509 proporcionada por servicios concretos (con ámbito) para la autenticación.</span><span class="sxs-lookup"><span data-stu-id="0cea5-103">Represents a collection of X.509 certificates provided by specific services (scoped) for authentication.</span></span> <span data-ttu-id="0cea5-104">Esta colección se utiliza normalmente para especificar los certificados de servicio para los servicios de token de seguridad en un escenario asociado externo.</span><span class="sxs-lookup"><span data-stu-id="0cea5-104">This collection is typically used to specify the service certificates for Security Token Services in a federated scenario.</span></span>  
  
 <span data-ttu-id="0cea5-105">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="0cea5-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="0cea5-106">\<comportamientos ></span><span class="sxs-lookup"><span data-stu-id="0cea5-106">\<behaviors></span></span>  
<span data-ttu-id="0cea5-107">sección endpointBehaviors</span><span class="sxs-lookup"><span data-stu-id="0cea5-107">endpointBehaviors section</span></span>  
<span data-ttu-id="0cea5-108">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="0cea5-108">\<behavior></span></span>  
<span data-ttu-id="0cea5-109">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="0cea5-109">\<clientCredentials></span></span>  
<span data-ttu-id="0cea5-110">\<serviceCertificate></span><span class="sxs-lookup"><span data-stu-id="0cea5-110">\<serviceCertificate></span></span>  
<span data-ttu-id="0cea5-111">\<scopedCertificates > elemento</span><span class="sxs-lookup"><span data-stu-id="0cea5-111">\<scopedCertificates> Element</span></span>  
<span data-ttu-id="0cea5-112">\<Agregar > elemento para \<scopedCertificates ></span><span class="sxs-lookup"><span data-stu-id="0cea5-112">\<add> element for \<scopedCertificates></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0cea5-113">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0cea5-113">Syntax</span></span>  
  
```xml  
<scopedCertificates>
  <add findValue="String"
       storeLocation="CurrentUser/LocalMachine"
       storeName=" CurrentUser/LocalMachine"
       targetUri="string"
       x509Type="FindByThumbprint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindBySerialNumber/FindByTimeExpired/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier" />
</scopedCertificates>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0cea5-114">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="0cea5-114">Attributes and Elements</span></span>  
 <span data-ttu-id="0cea5-115">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="0cea5-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0cea5-116">Atributos</span><span class="sxs-lookup"><span data-stu-id="0cea5-116">Attributes</span></span>  
 <span data-ttu-id="0cea5-117">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="0cea5-117">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="0cea5-118">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="0cea5-118">Child Elements</span></span>  
  
|<span data-ttu-id="0cea5-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="0cea5-119">Element</span></span>|<span data-ttu-id="0cea5-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="0cea5-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0cea5-121">\<add></span><span class="sxs-lookup"><span data-stu-id="0cea5-121">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-scopedcertificates-element.md)|<span data-ttu-id="0cea5-122">Agrega un certificado X.509 a la colección de certificados con ámbito.</span><span class="sxs-lookup"><span data-stu-id="0cea5-122">Adds an X.509 certificate to the collection of scoped certificates.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="0cea5-123">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="0cea5-123">Parent Elements</span></span>  
  
|<span data-ttu-id="0cea5-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="0cea5-124">Element</span></span>|<span data-ttu-id="0cea5-125">Descripción</span><span class="sxs-lookup"><span data-stu-id="0cea5-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0cea5-126">\<serviceCertificate></span><span class="sxs-lookup"><span data-stu-id="0cea5-126">\<serviceCertificate></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-servicecredentials.md)|<span data-ttu-id="0cea5-127">Especifica el certificado que se va a utilizar al autenticar un servicio al cliente.</span><span class="sxs-lookup"><span data-stu-id="0cea5-127">Specifies a certificate to use when authenticating a service to the client.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0cea5-128">Comentarios</span><span class="sxs-lookup"><span data-stu-id="0cea5-128">Remarks</span></span>  
 <span data-ttu-id="0cea5-129">Esta colección le permite al cliente configurar los certificados de servicio que se van a utilizar basándose en la dirección URL del servicio con el que se comunica.</span><span class="sxs-lookup"><span data-stu-id="0cea5-129">This collection enables the client to configure the service certificates to use based on the URL of the service it communicates with.</span></span> <span data-ttu-id="0cea5-130">Esto es especialmente útil en escenarios del token emitidos donde un cliente puede estar comunicándose con varios servicios (el servicio final, así como los servicios del token de seguridad intermediarios).</span><span class="sxs-lookup"><span data-stu-id="0cea5-130">This is especially useful in issued token scenarios where a client can be communicating to multiple services (the end service as well as intermediary security token services).</span></span> <span data-ttu-id="0cea5-131">Para los enlaces que utilizan la seguridad del mensaje basada en certificados, este certificado se utiliza para cifrar los mensajes del servicio y se espera que sea utilizado por el servicio para firmar las respuestas para el cliente.</span><span class="sxs-lookup"><span data-stu-id="0cea5-131">For bindings that use certificate-based message security, this certificate is used to encrypt messages to the service, and is expected to be used by the service for signing replies to the client.</span></span>  
  
 <span data-ttu-id="0cea5-132">Si un enlace requiere un certificado para el servicio y no se encuentra ningún certificado concreto para la dirección URL del servicio en ScopedCertificates, se utilizará el certificado predeterminado.</span><span class="sxs-lookup"><span data-stu-id="0cea5-132">If a binding requires a certificate for the service and no specific certificate for the service URL is found in the ScopedCertificates, the default certificate is used.</span></span>  
  
 <span data-ttu-id="0cea5-133">Para obtener más información, vea la sección "Certificados con ámbito" de [Cómo: Crear un cliente federado](../../../../../docs/framework/wcf/feature-details/how-to-create-a-federated-client.md).</span><span class="sxs-lookup"><span data-stu-id="0cea5-133">For more information, see the "Scoped Certificates" section of [How to: Create a Federated Client](../../../../../docs/framework/wcf/feature-details/how-to-create-a-federated-client.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="0cea5-134">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="0cea5-134">Example</span></span>  
 <span data-ttu-id="0cea5-135">El ejemplo siguiente especifica un certificado de servicio para el cliente que se usará al comunicarse con puntos de conexión cuyo nombre de dominio es `http://www.contoso.com` a través del protocolo HTTP.</span><span class="sxs-lookup"><span data-stu-id="0cea5-135">The following example specifies a service certificate for the client to use when communicating with endpoints whose domain name is `http://www.contoso.com` over the HTTP protocol.</span></span>  
  
```xml  
<serviceCertificate>
  <scopedCertificates>
    <add targetUri="http://www.contoso.com"
         findValue="www.contoso.com"
         storeLocation="LocalMachine"
         storeName="Root"
         x509FindType="FindByIssuerName" />
  </scopedCertificates>
</serviceCertificate>
```  
  
## <a name="see-also"></a><span data-ttu-id="0cea5-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="0cea5-136">See also</span></span>

- <xref:System.ServiceModel.Configuration.X509RecipientCertificateClientElement.ScopedCertificates%2A>
- <xref:System.ServiceModel.Configuration.X509ScopedServiceCertificateElementCollection>
- <xref:System.ServiceModel.Configuration.X509ScopedServiceCertificateElement>
- <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential>
- <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential.ScopedCertificates%2A>
- [<span data-ttu-id="0cea5-137">Trabajo con certificados</span><span class="sxs-lookup"><span data-stu-id="0cea5-137">Working with Certificates</span></span>](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="0cea5-138">Cómo: Crear a un cliente federado</span><span class="sxs-lookup"><span data-stu-id="0cea5-138">How to: Create a Federated Client</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-create-a-federated-client.md)
- [<span data-ttu-id="0cea5-139">\<add></span><span class="sxs-lookup"><span data-stu-id="0cea5-139">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-scopedcertificates-element.md)
- [<span data-ttu-id="0cea5-140">Protección de clientes</span><span class="sxs-lookup"><span data-stu-id="0cea5-140">Securing Clients</span></span>](../../../../../docs/framework/wcf/securing-clients.md)
- [<span data-ttu-id="0cea5-141">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="0cea5-141">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
