---
title: <issuerNameRegistry>
ms.date: 03/30/2017
ms.assetid: 58b39d12-c953-40c4-88af-d7eb3343ca28
author: BrucePerlerMS
ms.openlocfilehash: ae263a4590cc523c64306ff5d53e54b5190ca510
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59202526"
---
# <a name="issuernameregistry"></a><span data-ttu-id="26d20-101">\<issuerNameRegistry></span><span class="sxs-lookup"><span data-stu-id="26d20-101">\<issuerNameRegistry></span></span>
<span data-ttu-id="26d20-102">Configura el registro de nombre del emisor que se usa los controladores en la colección de controladores de token.</span><span class="sxs-lookup"><span data-stu-id="26d20-102">Configures the issuer name registry that is used by handlers in the token handler collection.</span></span>  
  
 <span data-ttu-id="26d20-103">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="26d20-103">\<system.identityModel></span></span>  
<span data-ttu-id="26d20-104">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="26d20-104">\<identityConfiguration></span></span>  
<span data-ttu-id="26d20-105">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="26d20-105">\<securityTokenHandlers></span></span>  
<span data-ttu-id="26d20-106">\<securityTokenHandlerConfiguration></span><span class="sxs-lookup"><span data-stu-id="26d20-106">\<securityTokenHandlerConfiguration></span></span>  
<span data-ttu-id="26d20-107">\<issuerNameRegistry></span><span class="sxs-lookup"><span data-stu-id="26d20-107">\<issuerNameRegistry></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="26d20-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="26d20-108">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <securityTokenHandlerConfiguration>  
        <issuerNameRegistry type=xs:string>  
          <optionalCustomConfigurationElements />  
        </issuerNameRegistry>  
      </securityTokenHandlerConfiguration>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="26d20-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="26d20-109">Attributes and Elements</span></span>  
 <span data-ttu-id="26d20-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="26d20-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="26d20-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="26d20-111">Attributes</span></span>  
  
|<span data-ttu-id="26d20-112">Atributo</span><span class="sxs-lookup"><span data-stu-id="26d20-112">Attribute</span></span>|<span data-ttu-id="26d20-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="26d20-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="26d20-114">type</span><span class="sxs-lookup"><span data-stu-id="26d20-114">type</span></span>|<span data-ttu-id="26d20-115">Un tipo que deriva la <xref:System.IdentityModel.Tokens.IssuerNameRegistry> clase.</span><span class="sxs-lookup"><span data-stu-id="26d20-115">A type that derives from the <xref:System.IdentityModel.Tokens.IssuerNameRegistry> class.</span></span> <span data-ttu-id="26d20-116">Para obtener más información acerca de cómo especificar un personalizado `type`, consulte la sección [referencias de tipo personalizado].</span><span class="sxs-lookup"><span data-stu-id="26d20-116">For more information about how to specify a custom `type`, see [Custom Type References].</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="26d20-117">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="26d20-117">Child Elements</span></span>  
  
|<span data-ttu-id="26d20-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="26d20-118">Element</span></span>|<span data-ttu-id="26d20-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="26d20-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="26d20-120">\<trustedIssuers></span><span class="sxs-lookup"><span data-stu-id="26d20-120">\<trustedIssuers></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/trustedissuers.md)|<span data-ttu-id="26d20-121">Cuando el `type` atributo especifica el registro de nombres de emisores basada en la configuración (el <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> clase), el [ \<trustedIssuers >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/trustedissuers.md) debe especificarse el elemento.</span><span class="sxs-lookup"><span data-stu-id="26d20-121">When the `type` attribute specifies the configuration-based issuer name registry (the <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> class), the [\<trustedIssuers>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/trustedissuers.md) element must be specified.</span></span> <span data-ttu-id="26d20-122">El [ \<trustedIssuers >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/trustedissuers.md) puede tomar el elemento `<add>`, `<clear>`, o `<remove>` elementos como elementos secundarios.</span><span class="sxs-lookup"><span data-stu-id="26d20-122">The [\<trustedIssuers>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/trustedissuers.md) element can take `<add>`, `<clear>`, or `<remove>` elements as child elements.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="26d20-123">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="26d20-123">Parent Elements</span></span>  
  
|<span data-ttu-id="26d20-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="26d20-124">Element</span></span>|<span data-ttu-id="26d20-125">Descripción</span><span class="sxs-lookup"><span data-stu-id="26d20-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="26d20-126">\<securityTokenHandlerConfiguration></span><span class="sxs-lookup"><span data-stu-id="26d20-126">\<securityTokenHandlerConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md)|<span data-ttu-id="26d20-127">Proporciona la configuración para una colección de seguridad controladores de token.</span><span class="sxs-lookup"><span data-stu-id="26d20-127">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="26d20-128">Comentarios</span><span class="sxs-lookup"><span data-stu-id="26d20-128">Remarks</span></span>  
 <span data-ttu-id="26d20-129">Todos los tokens de emisor se validan mediante un registro de nombre del emisor.</span><span class="sxs-lookup"><span data-stu-id="26d20-129">All issuer tokens are validated using an issuer name registry.</span></span> <span data-ttu-id="26d20-130">Se trata de un objeto que se deriva el <xref:System.IdentityModel.Tokens.IssuerNameRegistry> clase.</span><span class="sxs-lookup"><span data-stu-id="26d20-130">This is an object that derives from the <xref:System.IdentityModel.Tokens.IssuerNameRegistry> class.</span></span> <span data-ttu-id="26d20-131">El registro de nombre del emisor se utiliza para asociar un nombre mnemotécnico al material criptográfico que se necesita para comprobar las firmas de los tokens generados por el emisor correspondiente.</span><span class="sxs-lookup"><span data-stu-id="26d20-131">The issuer name registry is used to associate a mnemonic name to the cryptographic material that is needed to verify the signatures of tokens produced by the corresponding issuer.</span></span> <span data-ttu-id="26d20-132">El registro de nombre del emisor mantiene una lista de emisores de confianza para la aplicación de confianza (RP) de usuario de confianza.</span><span class="sxs-lookup"><span data-stu-id="26d20-132">The issuer name registry maintains a list of issuers that are trusted by the relying party (RP) application.</span></span> <span data-ttu-id="26d20-133">El tipo de registro de nombres de emisor se especifica utilizando el `type` atributo.</span><span class="sxs-lookup"><span data-stu-id="26d20-133">The type of the issuer name registry is specified using the `type` attribute.</span></span> <span data-ttu-id="26d20-134">El `<issuerNameRegistry>` elemento puede tener uno o varios elementos secundarios que proporcionan la configuración para el tipo especificado.</span><span class="sxs-lookup"><span data-stu-id="26d20-134">The `<issuerNameRegistry>` element can have one or more child elements that provide configuration for the specified type.</span></span> <span data-ttu-id="26d20-135">Proporcionar la lógica que procesa estos elementos secundarios invalidando el <xref:System.IdentityModel.Tokens.IssuerNameRegistry.LoadCustomConfiguration%2A> método.</span><span class="sxs-lookup"><span data-stu-id="26d20-135">You provide the logic that processes these child elements by overriding the <xref:System.IdentityModel.Tokens.IssuerNameRegistry.LoadCustomConfiguration%2A> method.</span></span>  
  
 <span data-ttu-id="26d20-136">WIF proporciona un emisor único nombre de tipo de registro de fábrica, el <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> clase.</span><span class="sxs-lookup"><span data-stu-id="26d20-136">WIF provides a single issuer name registry type out of the box, the <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> class.</span></span> <span data-ttu-id="26d20-137">Esta clase usa un conjunto de certificados de emisor de confianza que se especifican en la configuración.</span><span class="sxs-lookup"><span data-stu-id="26d20-137">This class uses a set of trusted issuer certificates that are specified in configuration.</span></span> <span data-ttu-id="26d20-138">Requiere un elemento de configuración secundario, `<trustedIssuers>`, en la que está configurada la colección de certificados de emisor de confianza.</span><span class="sxs-lookup"><span data-stu-id="26d20-138">It requires a child configuration element, `<trustedIssuers>`, under which the collection of trusted issuer certificates is configured.</span></span> <span data-ttu-id="26d20-139">Los certificados se especifican utilizando el ASN.1 codificado de formulario de la huella digital del certificado y se agregan o quitan de la colección mediante el uso de confianza `<add>`, `<clear>`, o `<remove>` elementos.</span><span class="sxs-lookup"><span data-stu-id="26d20-139">Trusted certificates are specified using the ASN.1 encoded form of the certificate thumbprint and are added or removed from the collection by using `<add>`, `<clear>`, or `<remove>` elements.</span></span>  
  
 <span data-ttu-id="26d20-140">El `<issuerNameRegistry>` elemento representado por la <xref:System.IdentityModel.Configuration.IssuerNameRegistryElement> clase.</span><span class="sxs-lookup"><span data-stu-id="26d20-140">The `<issuerNameRegistry>` element is represented by the <xref:System.IdentityModel.Configuration.IssuerNameRegistryElement> class.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="26d20-141">Especificar el `<issuerNameRegistry>` como un elemento secundario de la [ \<identityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) elemento en desuso, pero todavía se admite por compatibilidad con versiones anteriores.</span><span class="sxs-lookup"><span data-stu-id="26d20-141">Specifying the `<issuerNameRegistry>` element as a child element of the [\<identityConfiguration>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) element has been deprecated, but is still supported for backward compatibility.</span></span> <span data-ttu-id="26d20-142">Configuración de la `<securityTokenHandlerConfiguration>` elemento invalidan aquellas establecidas en el `<identityConfiguration>` elemento.</span><span class="sxs-lookup"><span data-stu-id="26d20-142">Settings on the `<securityTokenHandlerConfiguration>` element override those on the `<identityConfiguration>` element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="26d20-143">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="26d20-143">Example</span></span>  
 <span data-ttu-id="26d20-144">El siguiente XML muestra cómo especificar al emisor de la configuración en función de registro de nombres.</span><span class="sxs-lookup"><span data-stu-id="26d20-144">The following XML shows how to specify the configuration based issuer name registry.</span></span>  
  
```xml  
<issuerNameRegistry type="System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089">  
  <trustedIssuers>  
    <add thumbprint="9B74CB … 1EF40D0" name="LocalSTS" />  
  </trustedIssuers>  
</issuerNameRegistry>  
```  
  
## <a name="see-also"></a><span data-ttu-id="26d20-145">Vea también</span><span class="sxs-lookup"><span data-stu-id="26d20-145">See also</span></span>

- <xref:System.IdentityModel.Tokens.IssuerNameRegistry>
- <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry>
