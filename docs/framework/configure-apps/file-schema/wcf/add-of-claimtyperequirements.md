---
title: <add> de <claimTypeRequirements>
ms.date: 03/30/2017
ms.assetid: c68e83c9-39e8-4264-b1ce-b6a9eb5b98aa
ms.openlocfilehash: 7e7f0eac41e69e959aa6c4f8f3cfb488d4ea2917
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69926791"
---
# <a name="add-of-claimtyperequirements"></a><span data-ttu-id="e6f01-102">\<Agregar > de \<claimTypeRequirements ></span><span class="sxs-lookup"><span data-stu-id="e6f01-102">\<add> of \<claimTypeRequirements></span></span>
<span data-ttu-id="e6f01-103">Especifica los tipos de notificaciones necesarias y opcionales que se espera que aparezcan en una credencial aliada.</span><span class="sxs-lookup"><span data-stu-id="e6f01-103">Specifies the types of required and optional claims expected to appear in the federated credential.</span></span> <span data-ttu-id="e6f01-104">Por ejemplo, los servicios indican los requisitos en las credenciales de entrada, que deben poseer un cierto conjunto de tipos de notificaciones.</span><span class="sxs-lookup"><span data-stu-id="e6f01-104">For example, services state the requirements on incoming credentials, which must possess a certain set of claim types.</span></span>  
  
 <span data-ttu-id="e6f01-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="e6f01-105">\<system.serviceModel></span></span>  
<span data-ttu-id="e6f01-106">\<bindings></span><span class="sxs-lookup"><span data-stu-id="e6f01-106">\<bindings></span></span>  
<span data-ttu-id="e6f01-107">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="e6f01-107">\<customBinding></span></span>  
<span data-ttu-id="e6f01-108">\<binding></span><span class="sxs-lookup"><span data-stu-id="e6f01-108">\<binding></span></span>  
<span data-ttu-id="e6f01-109">\<> de seguridad</span><span class="sxs-lookup"><span data-stu-id="e6f01-109">\<security></span></span>  
<span data-ttu-id="e6f01-110">\<issuedTokenParameters></span><span class="sxs-lookup"><span data-stu-id="e6f01-110">\<issuedTokenParameters></span></span>  
<span data-ttu-id="e6f01-111">\<claimTypeRequirements></span><span class="sxs-lookup"><span data-stu-id="e6f01-111">\<claimTypeRequirements></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e6f01-112">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e6f01-112">Syntax</span></span>  
  
```xml  
<claimTypeRequirements>
  <add claimType="URI"
       isOptional="Boolean" />
</claimTypeRequirements>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e6f01-113">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="e6f01-113">Attributes and Elements</span></span>  
 <span data-ttu-id="e6f01-114">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="e6f01-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e6f01-115">Atributos</span><span class="sxs-lookup"><span data-stu-id="e6f01-115">Attributes</span></span>  
  
|<span data-ttu-id="e6f01-116">Atributo</span><span class="sxs-lookup"><span data-stu-id="e6f01-116">Attribute</span></span>|<span data-ttu-id="e6f01-117">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="e6f01-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e6f01-118">claimType</span><span class="sxs-lookup"><span data-stu-id="e6f01-118">claimType</span></span>|<span data-ttu-id="e6f01-119">URI que define el tipo de una notificación.</span><span class="sxs-lookup"><span data-stu-id="e6f01-119">A URI that defines the type of a claim.</span></span> <span data-ttu-id="e6f01-120">Por ejemplo, para comprar un producto de un sitio web, el usuario debe presentar una tarjeta de crédito válida con límite de crédito suficiente.</span><span class="sxs-lookup"><span data-stu-id="e6f01-120">For example, to purchase a product from a Web site, the user must present a valid credit card with sufficient credit limit.</span></span> <span data-ttu-id="e6f01-121">El tipo de notificación sería el URI de la tarjeta de crédito.</span><span class="sxs-lookup"><span data-stu-id="e6f01-121">The claim type would be the credit card URI.</span></span>|  
|<span data-ttu-id="e6f01-122">isOptional</span><span class="sxs-lookup"><span data-stu-id="e6f01-122">isOptional</span></span>|<span data-ttu-id="e6f01-123">Valor de tipo booleano que especifica si se trata de una notificación opcional.</span><span class="sxs-lookup"><span data-stu-id="e6f01-123">A Boolean value that specifies if this is for an optional claim.</span></span> <span data-ttu-id="e6f01-124">Establezca este atributo en `false` si se trata de una notificación necesaria.</span><span class="sxs-lookup"><span data-stu-id="e6f01-124">Set this attribute to `false` if this is a required claim.</span></span><br /><br /> <span data-ttu-id="e6f01-125">Puede usar este atributo cuando el servicio pregunte para obtener alguna información, pero no lo requiere.</span><span class="sxs-lookup"><span data-stu-id="e6f01-125">You can use this attribute when the service asks for some information but does not require it.</span></span> <span data-ttu-id="e6f01-126">Por ejemplo, si le exige al usuario que escriba su nombre, apellido y dirección, pero decide que el número de teléfono es opcional.</span><span class="sxs-lookup"><span data-stu-id="e6f01-126">For example, if you require the user to enter his/her first name, last name and address, but decide that phone number is optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e6f01-127">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="e6f01-127">Child Elements</span></span>  
 <span data-ttu-id="e6f01-128">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="e6f01-128">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e6f01-129">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="e6f01-129">Parent Elements</span></span>  
  
|<span data-ttu-id="e6f01-130">Elemento</span><span class="sxs-lookup"><span data-stu-id="e6f01-130">Element</span></span>|<span data-ttu-id="e6f01-131">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="e6f01-131">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e6f01-132">\<claimTypeRequirements></span><span class="sxs-lookup"><span data-stu-id="e6f01-132">\<claimTypeRequirements></span></span>](claimtyperequirements-element.md)|<span data-ttu-id="e6f01-133">Especifica una colección de tipos de notificación requeridos.</span><span class="sxs-lookup"><span data-stu-id="e6f01-133">Specifies a collection of required claim types.</span></span><br /><br /> <span data-ttu-id="e6f01-134">En un escenario aliado, los servicios indican los requisitos de las credenciales de entrada.</span><span class="sxs-lookup"><span data-stu-id="e6f01-134">In a federated scenario, services state the requirements on incoming credentials.</span></span> <span data-ttu-id="e6f01-135">Por ejemplo, las credenciales de entrada deben poseer un determinado conjunto de tipos de notificación.</span><span class="sxs-lookup"><span data-stu-id="e6f01-135">For example, the incoming credentials must possess a certain set of claim types.</span></span> <span data-ttu-id="e6f01-136">Cada elemento de la colección especifica los tipos de notificaciones necesarias y opcionales que se espera que aparezcan en una credencial aliada.</span><span class="sxs-lookup"><span data-stu-id="e6f01-136">Each element in this collection specifies the types of required and optional claims expected to appear in a federated credential.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e6f01-137">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e6f01-137">Remarks</span></span>  
 <span data-ttu-id="e6f01-138">En un escenario aliado, los servicios indican los requisitos de las credenciales de entrada.</span><span class="sxs-lookup"><span data-stu-id="e6f01-138">In a federated scenario, services state the requirements on incoming credentials.</span></span> <span data-ttu-id="e6f01-139">Por ejemplo, las credenciales de entrada deben poseer un determinado conjunto de tipos de notificación.</span><span class="sxs-lookup"><span data-stu-id="e6f01-139">For example, the incoming credentials must possess a certain set of claim types.</span></span> <span data-ttu-id="e6f01-140">Este requisito se manifiesta en una directiva de seguridad.</span><span class="sxs-lookup"><span data-stu-id="e6f01-140">This requirement is manifested in a security policy.</span></span> <span data-ttu-id="e6f01-141">Cuando un cliente solicita las credenciales de un servicio aliado (por ejemplo, CardSpace), coloca los requisitos en una solicitud del token (RequestSecurityToken) para que el servicio aliado pueda emitir las credenciales que satisfacen según los requisitos.</span><span class="sxs-lookup"><span data-stu-id="e6f01-141">When a client requests credentials from a federated service (for example, CardSpace), it puts the requirements into a token request (RequestSecurityToken) so that the federated service can issue the credentials that satisfy the requirements accordingly.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e6f01-142">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e6f01-142">Example</span></span>  
 <span data-ttu-id="e6f01-143">La siguiente configuración agrega dos requisitos de tipo de notificación a un enlace de seguridad.</span><span class="sxs-lookup"><span data-stu-id="e6f01-143">The following configuration adds two claim type requirements to a security binding.</span></span>  
  
```xml  
<bindings>
  <wsFederationHttpBinding>
    <binding name="myFederatedBinding">
      <security mode="Message">
        <message issuedTokenType="urn:oasis:names:tc:SAML:1.0:assertion">
          <claimTypeRequirements>
            <add claimType="http://schemas.microsoft.com/ws/2005/05/identity/claims/EmailAddress" />
            <add claimType="http://schemas.microsoft.com/ws/2005/05/identity/claims/UserName"
                 optional="true" />
          </claimTypeRequirements>
        </message>
      </security>
    </binding>
  </wsFederationHttpBinding>
</bindings>
```  
  
## <a name="see-also"></a><span data-ttu-id="e6f01-144">Vea también</span><span class="sxs-lookup"><span data-stu-id="e6f01-144">See also</span></span>

- <xref:System.ServiceModel.Security.Tokens.ClaimTypeRequirement>
- <xref:System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters.ClaimTypeRequirements%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenParametersElement.ClaimTypeRequirements%2A>
- <xref:System.ServiceModel.Configuration.ClaimTypeElementCollection>
- <xref:System.ServiceModel.Configuration.ClaimTypeElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="e6f01-145">\<claimTypeRequirements></span><span class="sxs-lookup"><span data-stu-id="e6f01-145">\<claimTypeRequirements></span></span>](claimtyperequirements-element.md)
- [<span data-ttu-id="e6f01-146">Enlaces</span><span class="sxs-lookup"><span data-stu-id="e6f01-146">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="e6f01-147">Extensión de enlaces</span><span class="sxs-lookup"><span data-stu-id="e6f01-147">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="e6f01-148">Enlaces personalizados</span><span class="sxs-lookup"><span data-stu-id="e6f01-148">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="e6f01-149">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="e6f01-149">\<customBinding></span></span>](custombinding.md)
- [<span data-ttu-id="e6f01-150">Cómo: Crear un enlace personalizado mediante SecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="e6f01-150">How to: Create a Custom Binding Using the SecurityBindingElement</span></span>](../../../wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)
- [<span data-ttu-id="e6f01-151">Seguridad de enlace personalizado</span><span class="sxs-lookup"><span data-stu-id="e6f01-151">Custom Binding Security</span></span>](../../../wcf/samples/custom-binding-security.md)
