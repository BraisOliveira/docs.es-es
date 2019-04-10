---
title: Filtrar para crear un comprobador de identidad de cliente personalizado
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: f2d34e43-fa8b-46d2-91cf-d2960e13e16b
ms.openlocfilehash: d8529929870b14611c136221f1eefe3eb4ba3d42
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/09/2019
ms.locfileid: "59339000"
---
# <a name="how-to-create-a-custom-client-identity-verifier"></a><span data-ttu-id="76778-102">Filtrar para crear un comprobador de identidad de cliente personalizado</span><span class="sxs-lookup"><span data-stu-id="76778-102">How to: Create a Custom Client Identity Verifier</span></span>
<span data-ttu-id="76778-103">El *identidad* característica de Windows Communication Foundation (WCF) permite a un cliente especificar de antemano la identidad esperada del servicio.</span><span class="sxs-lookup"><span data-stu-id="76778-103">The *identity* feature of Windows Communication Foundation (WCF) enables a client to specify in advance the expected identity of the service.</span></span> <span data-ttu-id="76778-104">Siempre que un servidor se autentica al cliente, se comprueba la identidad frente a la identidad prevista.</span><span class="sxs-lookup"><span data-stu-id="76778-104">Whenever a server authenticates itself to the client, the identity is checked against the expected identity.</span></span> <span data-ttu-id="76778-105">(Para obtener una explicación de la identidad y cómo funciona, consulte [autenticación e identidad de servicio](../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md).)</span><span class="sxs-lookup"><span data-stu-id="76778-105">(For an explanation of identity and how it works, see [Service Identity and Authentication](../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md).)</span></span>  
  
 <span data-ttu-id="76778-106">En caso necesario, la comprobación puede personalizarse mediante un comprobador de identidad personalizado.</span><span class="sxs-lookup"><span data-stu-id="76778-106">If needed, the verification can be customized using a custom identity verifier.</span></span> <span data-ttu-id="76778-107">Por ejemplo, puede realizar controles adicionales de comprobación de identidad del servicio.</span><span class="sxs-lookup"><span data-stu-id="76778-107">For example, you can perform additional service identity verification checks.</span></span> <span data-ttu-id="76778-108">En este ejemplo, el comprobador de identidad personalizado controla las notificaciones adicionales del certificado X.509 devueltas desde el servidor.</span><span class="sxs-lookup"><span data-stu-id="76778-108">In this example, the custom identity verifier checks additional claims in the X.509 certificate returned from the server.</span></span> <span data-ttu-id="76778-109">Para una aplicación de ejemplo, vea [ejemplo de identidad de servicio](../../../../docs/framework/wcf/samples/service-identity-sample.md).</span><span class="sxs-lookup"><span data-stu-id="76778-109">For a sample application, see [Service Identity Sample](../../../../docs/framework/wcf/samples/service-identity-sample.md).</span></span>  
  
### <a name="to-extend-the-endpointidentity-class"></a><span data-ttu-id="76778-110">Para extender la clase EndpointIdentity</span><span class="sxs-lookup"><span data-stu-id="76778-110">To extend the EndpointIdentity class</span></span>  
  
1. <span data-ttu-id="76778-111">Defina una nueva clase derivada de la clase <xref:System.ServiceModel.EndpointIdentity>.</span><span class="sxs-lookup"><span data-stu-id="76778-111">Define a new class that derives from the <xref:System.ServiceModel.EndpointIdentity> class.</span></span> <span data-ttu-id="76778-112">Este ejemplo asigna nombre a la `OrgEndpointIdentity` de la extensión</span><span class="sxs-lookup"><span data-stu-id="76778-112">This example names the extension `OrgEndpointIdentity`.</span></span>  
  
2. <span data-ttu-id="76778-113">Agregue los miembros privados y las propiedades que utilizará la clase <xref:System.ServiceModel.Security.IdentityVerifier> extendida para realizar la comprobación de identidad frente a las notificaciones del token de seguridad devueltas por el servicio.</span><span class="sxs-lookup"><span data-stu-id="76778-113">Add private members along with properties that will be used by the extended <xref:System.ServiceModel.Security.IdentityVerifier> class to perform the identity check against claims in the security token returned from the service.</span></span> <span data-ttu-id="76778-114">Este ejemplo define una propiedad: `OrganizationClaim`.</span><span class="sxs-lookup"><span data-stu-id="76778-114">This example defines one property: the `OrganizationClaim` property.</span></span>  
  
     [!code-csharp[c_HowToSetCustomClientIdentity#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howtosetcustomclientidentity/cs/source.cs#6)]
     [!code-vb[c_HowToSetCustomClientIdentity#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howtosetcustomclientidentity/vb/source.vb#6)]  
  
### <a name="to-extend-the-identityverifier-class"></a><span data-ttu-id="76778-115">Para extender la clase IdentityVerifier</span><span class="sxs-lookup"><span data-stu-id="76778-115">To extend the IdentityVerifier class</span></span>  
  
1. <span data-ttu-id="76778-116">Defina una nueva clase derivada de <xref:System.ServiceModel.Security.IdentityVerifier>.</span><span class="sxs-lookup"><span data-stu-id="76778-116">Define a new class that derives from <xref:System.ServiceModel.Security.IdentityVerifier>.</span></span> <span data-ttu-id="76778-117">Este ejemplo asigna nombre a la `CustomIdentityVerifier` de la extensión</span><span class="sxs-lookup"><span data-stu-id="76778-117">This example names the extension `CustomIdentityVerifier`.</span></span>  
  
     [!code-csharp[c_HowToSetCustomClientIdentity#7](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howtosetcustomclientidentity/cs/source.cs#7)]
     [!code-vb[c_HowToSetCustomClientIdentity#7](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howtosetcustomclientidentity/vb/source.vb#7)]  
  
2. <span data-ttu-id="76778-118">Invalide el método <xref:System.ServiceModel.Security.IdentityVerifier.CheckAccess%2A> .</span><span class="sxs-lookup"><span data-stu-id="76778-118">Override the <xref:System.ServiceModel.Security.IdentityVerifier.CheckAccess%2A> method.</span></span> <span data-ttu-id="76778-119">El método determina si la comprobación de la identidad tuvo éxito o fue fallida.</span><span class="sxs-lookup"><span data-stu-id="76778-119">The method determines whether the identity check succeeded or failed.</span></span>  
  
3. <span data-ttu-id="76778-120">El método `CheckAccess` posee dos parámetros.</span><span class="sxs-lookup"><span data-stu-id="76778-120">The `CheckAccess` method has two parameters.</span></span> <span data-ttu-id="76778-121">El primero es una instancia de la clase <xref:System.ServiceModel.EndpointIdentity>.</span><span class="sxs-lookup"><span data-stu-id="76778-121">The first is an instance of the <xref:System.ServiceModel.EndpointIdentity> class.</span></span> <span data-ttu-id="76778-122">El segundo es una instancia de la clase <xref:System.IdentityModel.Policy.AuthorizationContext>.</span><span class="sxs-lookup"><span data-stu-id="76778-122">The second is an instance of the <xref:System.IdentityModel.Policy.AuthorizationContext> class.</span></span>  
  
     <span data-ttu-id="76778-123">En la implementación del método, examine la colección de notificaciones devuelta por la propiedad <xref:System.IdentityModel.Policy.AuthorizationContext.ClaimSets%2A> de la clase <xref:System.IdentityModel.Policy.AuthorizationContext>, y realice las comprobaciones de autenticación necesarias.</span><span class="sxs-lookup"><span data-stu-id="76778-123">In the method implementation, examine the collection of claims returned by the <xref:System.IdentityModel.Policy.AuthorizationContext.ClaimSets%2A> property of the <xref:System.IdentityModel.Policy.AuthorizationContext> class, and perform authentication checks as required.</span></span> <span data-ttu-id="76778-124">Este ejemplo comienza buscando cualquier notificación de tipo "Nombre distintivo" y, a continuación, compara el nombre con la extensión de <xref:System.ServiceModel.EndpointIdentity> (`OrgEndpointIdentity`).</span><span class="sxs-lookup"><span data-stu-id="76778-124">This example begins by finding any claim that is of type "Distinguished Name" and then compares the name to the extension of the <xref:System.ServiceModel.EndpointIdentity> (`OrgEndpointIdentity`).</span></span>  
  
     [!code-csharp[c_HowToSetCustomClientIdentity#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howtosetcustomclientidentity/cs/source.cs#1)]
     [!code-vb[c_HowToSetCustomClientIdentity#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howtosetcustomclientidentity/vb/source.vb#1)]  
  
### <a name="to-implement-the-trygetidentity-method"></a><span data-ttu-id="76778-125">Para implementar el método TryGetIdentity</span><span class="sxs-lookup"><span data-stu-id="76778-125">To implement the TryGetIdentity method</span></span>  
  
1. <span data-ttu-id="76778-126">Implemente el método <xref:System.ServiceModel.Security.IdentityVerifier.TryGetIdentity%2A>, que determina si el cliente puede devolver una instancia de la clase <xref:System.ServiceModel.EndpointIdentity>.</span><span class="sxs-lookup"><span data-stu-id="76778-126">Implement the <xref:System.ServiceModel.Security.IdentityVerifier.TryGetIdentity%2A> method, which determines whether an instance of the <xref:System.ServiceModel.EndpointIdentity> class can be returned by the client.</span></span> <span data-ttu-id="76778-127">La infraestructura de WCF llama a la implementación de la `TryGetIdentity` método primero para recuperar la identidad del servicio desde el mensaje.</span><span class="sxs-lookup"><span data-stu-id="76778-127">The WCF infrastructure calls the implementation of the `TryGetIdentity` method first to retrieve the service's identity from the message.</span></span> <span data-ttu-id="76778-128">Después, la infraestructura llama a la implementación `CheckAccess` con la `EndpointIdentity` devuelta y a <xref:System.IdentityModel.Policy.AuthorizationContext>.</span><span class="sxs-lookup"><span data-stu-id="76778-128">Next, the infrastructure calls the `CheckAccess` implementation with the returned `EndpointIdentity` and <xref:System.IdentityModel.Policy.AuthorizationContext>.</span></span>  
  
2. <span data-ttu-id="76778-129">En el método `TryGetIdentity`, agregue el siguiente código:</span><span class="sxs-lookup"><span data-stu-id="76778-129">In the `TryGetIdentity` method, put the following code:</span></span>  
  
     [!code-csharp[c_HowToSetCustomClientIdentity#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howtosetcustomclientidentity/cs/source.cs#2)]
     [!code-vb[c_HowToSetCustomClientIdentity#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howtosetcustomclientidentity/vb/source.vb#2)]  
  
### <a name="to-implement-a-custom-binding-and-set-the-custom-identityverifier"></a><span data-ttu-id="76778-130">Para implementar un enlace personalizado y establecer el método IdentityVerifier personalizado</span><span class="sxs-lookup"><span data-stu-id="76778-130">To implement a custom binding and set the custom IdentityVerifier</span></span>  
  
1. <span data-ttu-id="76778-131">Cree un método que devuelva un objeto <xref:System.ServiceModel.Channels.Binding>.</span><span class="sxs-lookup"><span data-stu-id="76778-131">Create a method that returns a <xref:System.ServiceModel.Channels.Binding> object.</span></span> <span data-ttu-id="76778-132">Este ejemplo comienza creando una instancia de la clase <xref:System.ServiceModel.WSHttpBinding> y estableciendo su modo de seguridad en <xref:System.ServiceModel.SecurityMode.Message>, y su <xref:System.ServiceModel.MessageSecurityOverHttp.ClientCredentialType%2A> en <xref:System.ServiceModel.MessageCredentialType.None>.</span><span class="sxs-lookup"><span data-stu-id="76778-132">This example begins creates an instance of the <xref:System.ServiceModel.WSHttpBinding> class and sets its security mode to <xref:System.ServiceModel.SecurityMode.Message>, and its <xref:System.ServiceModel.MessageSecurityOverHttp.ClientCredentialType%2A> to <xref:System.ServiceModel.MessageCredentialType.None>.</span></span>  
  
2. <span data-ttu-id="76778-133">Cree una <xref:System.ServiceModel.Channels.BindingElementCollection> mediante el método <xref:System.ServiceModel.WSHttpBinding.CreateBindingElements%2A>.</span><span class="sxs-lookup"><span data-stu-id="76778-133">Create a <xref:System.ServiceModel.Channels.BindingElementCollection> using the <xref:System.ServiceModel.WSHttpBinding.CreateBindingElements%2A> method.</span></span>  
  
3. <span data-ttu-id="76778-134">Recupere el <xref:System.ServiceModel.Channels.SecurityBindingElement> de la colección y conviértalo a una variable <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement>.</span><span class="sxs-lookup"><span data-stu-id="76778-134">Return the <xref:System.ServiceModel.Channels.SecurityBindingElement> from the collection and cast it to a <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> variable.</span></span>  
  
4. <span data-ttu-id="76778-135">Establezca la propiedad <xref:System.ServiceModel.Channels.LocalClientSecuritySettings.IdentityVerifier%2A> de la clase <xref:System.ServiceModel.Channels.LocalClientSecuritySettings> a una nueva instancia de la clase `CustomIdentityVerifier` creada anteriormente.</span><span class="sxs-lookup"><span data-stu-id="76778-135">Set the <xref:System.ServiceModel.Channels.LocalClientSecuritySettings.IdentityVerifier%2A> property of the <xref:System.ServiceModel.Channels.LocalClientSecuritySettings> class to a new instance of the `CustomIdentityVerifier` class created previously.</span></span>  
  
     [!code-csharp[c_HowToSetCustomClientIdentity#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howtosetcustomclientidentity/cs/source.cs#3)]
     [!code-vb[c_HowToSetCustomClientIdentity#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howtosetcustomclientidentity/vb/source.vb#3)]  
  
5. <span data-ttu-id="76778-136">El enlace personalizado devuelto se utiliza para crear una instancia del cliente y la clase.</span><span class="sxs-lookup"><span data-stu-id="76778-136">The custom binding that is returned is used to create an instance of the client and class.</span></span> <span data-ttu-id="76778-137">El cliente puede realizar un control de comprobación de identidad personalizada del servicio, como muestra el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="76778-137">The client can then perform a custom identity verification check of the service as shown in the following code.</span></span>  
  
     [!code-csharp[c_HowToSetCustomClientIdentity#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howtosetcustomclientidentity/cs/source.cs#4)]
     [!code-vb[c_HowToSetCustomClientIdentity#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howtosetcustomclientidentity/vb/source.vb#4)]  
  
## <a name="example"></a><span data-ttu-id="76778-138">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="76778-138">Example</span></span>  
 <span data-ttu-id="76778-139">En el siguiente ejemplo se muestra una implementación de la clase <xref:System.ServiceModel.Security.IdentityVerifier> completa.</span><span class="sxs-lookup"><span data-stu-id="76778-139">The following example shows a complete implementation of the <xref:System.ServiceModel.Security.IdentityVerifier> class.</span></span>  
  
 [!code-csharp[c_HowToSetCustomClientIdentity#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howtosetcustomclientidentity/cs/source.cs#5)]
 [!code-vb[c_HowToSetCustomClientIdentity#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howtosetcustomclientidentity/vb/source.vb#5)]  
  
## <a name="example"></a><span data-ttu-id="76778-140">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="76778-140">Example</span></span>  
 <span data-ttu-id="76778-141">En el siguiente ejemplo se muestra una implementación de la clase <xref:System.ServiceModel.EndpointIdentity> completa.</span><span class="sxs-lookup"><span data-stu-id="76778-141">The following example shows a complete implementation of the <xref:System.ServiceModel.EndpointIdentity> class.</span></span>  
  
 [!code-csharp[c_HowToSetCustomClientIdentity#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howtosetcustomclientidentity/cs/source.cs#6)]
 [!code-vb[c_HowToSetCustomClientIdentity#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howtosetcustomclientidentity/vb/source.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="76778-142">Vea también</span><span class="sxs-lookup"><span data-stu-id="76778-142">See also</span></span>

- <xref:System.ServiceModel.ServiceAuthorizationManager>
- <xref:System.ServiceModel.EndpointIdentity>
- <xref:System.ServiceModel.Security.IdentityVerifier>
- [<span data-ttu-id="76778-143">Ejemplo de identidad de servicio</span><span class="sxs-lookup"><span data-stu-id="76778-143">Service Identity Sample</span></span>](../../../../docs/framework/wcf/samples/service-identity-sample.md)
- [<span data-ttu-id="76778-144">Directiva de autorización</span><span class="sxs-lookup"><span data-stu-id="76778-144">Authorization Policy</span></span>](../../../../docs/framework/wcf/samples/authorization-policy.md)
