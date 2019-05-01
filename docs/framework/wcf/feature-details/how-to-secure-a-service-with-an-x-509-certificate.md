---
title: Procedimiento para proteger un servicio con un certificado X.509
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 2d06c2aa-d0d7-4e5e-ad7e-77416aa1c10b
ms.openlocfilehash: 75c7a0e50301ce80d51b9b2a10ed650a1600ec79
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62047742"
---
# <a name="how-to-secure-a-service-with-an-x509-certificate"></a><span data-ttu-id="10b4b-102">Procedimiento para proteger un servicio con un certificado X.509</span><span class="sxs-lookup"><span data-stu-id="10b4b-102">How to: Secure a Service with an X.509 Certificate</span></span>
<span data-ttu-id="10b4b-103">Protección de un servicio con un certificado X.509 es una técnica básica que utilizan la mayoría de los enlaces de Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="10b4b-103">Securing a service with an X.509 certificate is a basic technique that most bindings in Windows Communication Foundation (WCF) use.</span></span> <span data-ttu-id="10b4b-104">En este tema se describen los pasos necesarios para configurar un servicio autoalojado con un certificado X.509.</span><span class="sxs-lookup"><span data-stu-id="10b4b-104">This topic walks through the steps of configuring a self-hosted service with an X.509 certificate.</span></span>  
  
 <span data-ttu-id="10b4b-105">Un requisito previo es un certificado válido que se puede utilizar para autenticar el servidor.</span><span class="sxs-lookup"><span data-stu-id="10b4b-105">A prerequisite is a valid certificate that can be used to authenticate the server.</span></span> <span data-ttu-id="10b4b-106">Una entidad emisora de certificados de confianza debe emitir el certificado.</span><span class="sxs-lookup"><span data-stu-id="10b4b-106">The certificate must be issued to the server by a trusted certificate authority.</span></span> <span data-ttu-id="10b4b-107">Si el certificado no es válido, cualquier cliente que intente usar el servicio no confiará en el servicio y, por tanto, no se realizará ninguna conexión.</span><span class="sxs-lookup"><span data-stu-id="10b4b-107">If the certificate is not valid, any client trying to use the service will not trust the service, and consequently no connection will be made.</span></span> <span data-ttu-id="10b4b-108">Para obtener más información sobre el uso de certificados, consulte [trabajar con certificados](../../../../docs/framework/wcf/feature-details/working-with-certificates.md).</span><span class="sxs-lookup"><span data-stu-id="10b4b-108">For more information about using certificates, see [Working with Certificates](../../../../docs/framework/wcf/feature-details/working-with-certificates.md).</span></span>  
  
### <a name="to-configure-a-service-with-a-certificate-using-code"></a><span data-ttu-id="10b4b-109">Configuración de un servicio con un certificado mediante código</span><span class="sxs-lookup"><span data-stu-id="10b4b-109">To configure a service with a certificate using code</span></span>  
  
1. <span data-ttu-id="10b4b-110">Cree el contrato de servicio y el servicio implementado.</span><span class="sxs-lookup"><span data-stu-id="10b4b-110">Create the service contract and the implemented service.</span></span> <span data-ttu-id="10b4b-111">Para obtener más información, consulte [diseño e implementación de servicios](../../../../docs/framework/wcf/designing-and-implementing-services.md).</span><span class="sxs-lookup"><span data-stu-id="10b4b-111">For more information, see [Designing and Implementing Services](../../../../docs/framework/wcf/designing-and-implementing-services.md).</span></span>  
  
2. <span data-ttu-id="10b4b-112">Cree una instancia de la clase <xref:System.ServiceModel.WSHttpBinding> y establezca su modo de seguridad en <xref:System.ServiceModel.SecurityMode.Message>, tal y como se muestra en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="10b4b-112">Create an instance of the <xref:System.ServiceModel.WSHttpBinding> class and set its security mode to <xref:System.ServiceModel.SecurityMode.Message>, as shown in the following code.</span></span>  
  
     [!code-csharp[C_SecureWithCertificate#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securewithcertificate/cs/source.cs#1)]
     [!code-vb[C_SecureWithCertificate#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securewithcertificate/vb/source.vb#1)]  
  
3. <span data-ttu-id="10b4b-113">Cree dos variables <xref:System.Type>, una para el tipo de contrato y otra para el contrato implementado, tal y como se muestra en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="10b4b-113">Create two <xref:System.Type> variables, one each for the contract type and the implemented contract, as shown in the following code.</span></span>  
  
     [!code-csharp[C_SecureWithCertificate#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securewithcertificate/cs/source.cs#2)]
     [!code-vb[C_SecureWithCertificate#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securewithcertificate/vb/source.vb#2)]  
  
4. <span data-ttu-id="10b4b-114">Cree una instancia de la clase <xref:System.Uri> para la dirección base del servicio.</span><span class="sxs-lookup"><span data-stu-id="10b4b-114">Create an instance of the <xref:System.Uri> class for the base address of the service.</span></span> <span data-ttu-id="10b4b-115">Dado que el `WSHttpBinding` utiliza el transporte HTTP, el identificador uniforme de recursos (URI) debe comenzar con ese esquema o Windows Communication Foundation (WCF) se iniciará una excepción cuando se abre el servicio.</span><span class="sxs-lookup"><span data-stu-id="10b4b-115">Because the `WSHttpBinding` uses the HTTP transport, the Uniform Resource Identifier (URI) must begin with that schema, or Windows Communication Foundation (WCF) will throw an exception when the service is opened.</span></span>  
  
     [!code-csharp[C_SecureWithCertificate#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securewithcertificate/cs/source.cs#3)]
     [!code-vb[C_SecureWithCertificate#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securewithcertificate/vb/source.vb#3)]  
  
5. <span data-ttu-id="10b4b-116">Cree una nueva instancia de la clase <xref:System.ServiceModel.ServiceHost> con la variable del tipo de contrato implementado y el URI.</span><span class="sxs-lookup"><span data-stu-id="10b4b-116">Create a new instance of the <xref:System.ServiceModel.ServiceHost> class with the implemented contract type variable and the URI.</span></span>  
  
     [!code-csharp[C_SecureWithCertificate#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securewithcertificate/cs/source.cs#4)]
     [!code-vb[C_SecureWithCertificate#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securewithcertificate/vb/source.vb#4)]  
  
6. <span data-ttu-id="10b4b-117">Agregue un <xref:System.ServiceModel.Description.ServiceEndpoint> al servicio mediante el método <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%2A>.</span><span class="sxs-lookup"><span data-stu-id="10b4b-117">Add a <xref:System.ServiceModel.Description.ServiceEndpoint> to the service using the <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%2A> method.</span></span> <span data-ttu-id="10b4b-118">Pase el contrato, enlace y una dirección del extremo al constructor, tal y como se muestra en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="10b4b-118">Pass the contract, binding, and an endpoint address to the constructor, as shown in the following code.</span></span>  
  
     [!code-csharp[C_SecureWithCertificate#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securewithcertificate/cs/source.cs#5)]
     [!code-vb[C_SecureWithCertificate#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securewithcertificate/vb/source.vb#5)]  
  
7. <span data-ttu-id="10b4b-119">Opcional.</span><span class="sxs-lookup"><span data-stu-id="10b4b-119">Optional.</span></span> <span data-ttu-id="10b4b-120">Para recuperar los metadatos del servicio, cree un nuevo objeto <xref:System.ServiceModel.Description.ServiceMetadataBehavior> y establezca la propiedad <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpGetEnabled%2A> en `true`.</span><span class="sxs-lookup"><span data-stu-id="10b4b-120">To retrieve metadata from the service, create a new <xref:System.ServiceModel.Description.ServiceMetadataBehavior> object and set the <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpGetEnabled%2A> property to `true`.</span></span>  
  
     [!code-csharp[C_SecureWithCertificate#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securewithcertificate/cs/source.cs#6)]
     [!code-vb[C_SecureWithCertificate#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securewithcertificate/vb/source.vb#6)]  
  
8. <span data-ttu-id="10b4b-121">Use el método <xref:System.ServiceModel.Security.X509CertificateRecipientServiceCredential.SetCertificate%2A> de la clase <xref:System.ServiceModel.Security.X509CertificateRecipientServiceCredential> para agregar al servicio el certificado válido.</span><span class="sxs-lookup"><span data-stu-id="10b4b-121">Use the <xref:System.ServiceModel.Security.X509CertificateRecipientServiceCredential.SetCertificate%2A> method of the <xref:System.ServiceModel.Security.X509CertificateRecipientServiceCredential> class to add the valid certificate to the service.</span></span> <span data-ttu-id="10b4b-122">El método puede utilizar un método de varios para encontrar un certificado.</span><span class="sxs-lookup"><span data-stu-id="10b4b-122">The method can use one of several methods to find a certificate.</span></span> <span data-ttu-id="10b4b-123">Este ejemplo usa la enumeración <xref:System.Security.Cryptography.X509Certificates.X509FindType.FindBySubjectName>.</span><span class="sxs-lookup"><span data-stu-id="10b4b-123">This example uses the <xref:System.Security.Cryptography.X509Certificates.X509FindType.FindBySubjectName> enumeration.</span></span> <span data-ttu-id="10b4b-124">La enumeración especifica que el valor proporcionado es el nombre de la entidad a la que se emitió el certificado.</span><span class="sxs-lookup"><span data-stu-id="10b4b-124">The enumeration specifies that the supplied value is the name of the entity that the certificate was issued to.</span></span>  
  
     [!code-csharp[C_SecureWithCertificate#7](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securewithcertificate/cs/source.cs#7)]
     [!code-vb[C_SecureWithCertificate#7](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securewithcertificate/vb/source.vb#7)]  
  
9. <span data-ttu-id="10b4b-125">Llame al método <xref:System.ServiceModel.Channels.CommunicationObject.Open%2A> para iniciar la escucha del servicio.</span><span class="sxs-lookup"><span data-stu-id="10b4b-125">Call the <xref:System.ServiceModel.Channels.CommunicationObject.Open%2A> method to start the service listening.</span></span> <span data-ttu-id="10b4b-126">Si está creando una aplicación de consola, llame al método <xref:System.Console.ReadLine%2A> para mantener el servicio en el estado de escucha.</span><span class="sxs-lookup"><span data-stu-id="10b4b-126">If you are creating a console application, call the <xref:System.Console.ReadLine%2A> method to keep the service in the listening state.</span></span>  
  
     [!code-csharp[C_SecureWithCertificate#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securewithcertificate/cs/source.cs#8)]
     [!code-vb[C_SecureWithCertificate#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securewithcertificate/vb/source.vb#8)]  
  
## <a name="example"></a><span data-ttu-id="10b4b-127">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="10b4b-127">Example</span></span>  
 <span data-ttu-id="10b4b-128">El ejemplo siguiente utiliza el método <xref:System.ServiceModel.Security.X509CertificateRecipientServiceCredential.SetCertificate%2A> para configurar un servicio con un certificado X.509.</span><span class="sxs-lookup"><span data-stu-id="10b4b-128">The following example uses the <xref:System.ServiceModel.Security.X509CertificateRecipientServiceCredential.SetCertificate%2A> method to configure a service with an X.509 certificate.</span></span>  
  
 [!code-csharp[C_SecureWithCertificate#9](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securewithcertificate/cs/source.cs#9)]
 [!code-vb[C_SecureWithCertificate#9](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securewithcertificate/vb/source.vb#9)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="10b4b-129">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="10b4b-129">Compiling the Code</span></span>  
 <span data-ttu-id="10b4b-130">Los espacios de nombres siguientes son necesarios para compilar el código:</span><span class="sxs-lookup"><span data-stu-id="10b4b-130">The following namespaces are required to compile the code:</span></span>  
  
- <xref:System>  
  
- <xref:System.ServiceModel>  
  
- <xref:System.ServiceModel.Channels>  
  
- <xref:System.Web.Services.Description>  
  
- <xref:System.Security.Cryptography.X509Certificates>  
  
- <xref:System.Runtime.Serialization>  
  
## <a name="see-also"></a><span data-ttu-id="10b4b-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="10b4b-131">See also</span></span>

- [<span data-ttu-id="10b4b-132">Trabajo con certificados</span><span class="sxs-lookup"><span data-stu-id="10b4b-132">Working with Certificates</span></span>](../../../../docs/framework/wcf/feature-details/working-with-certificates.md)
