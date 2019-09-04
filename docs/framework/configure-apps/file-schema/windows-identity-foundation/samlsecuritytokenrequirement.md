---
title: <samlSecurityTokenRequirement>
ms.date: 03/30/2017
ms.assetid: 09202d12-88d3-49cc-953b-703bcc1690eb
author: BrucePerlerMS
ms.openlocfilehash: cab7572518a7a6dc26f8bbcf67cd424fa1c01085
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251905"
---
# <a name="samlsecuritytokenrequirement"></a><span data-ttu-id="e4a84-101">\<samlSecurityTokenRequirement></span><span class="sxs-lookup"><span data-stu-id="e4a84-101">\<samlSecurityTokenRequirement></span></span>
<span data-ttu-id="e4a84-102">Proporciona la configuración para <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> la clase, <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> la clase o una clase derivada de cualquiera de estas clases.</span><span class="sxs-lookup"><span data-stu-id="e4a84-102">Provides configuration for the <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> class, the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> class, or a derived class of either of these classes.</span></span> <span data-ttu-id="e4a84-103">Se representa mediante <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> la clase.</span><span class="sxs-lookup"><span data-stu-id="e4a84-103">Represented by the <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> class.</span></span>  
  
<span data-ttu-id="e4a84-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="e4a84-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="e4a84-105">&nbsp;&nbsp;[ **\<System. identityModel >** ](system-identitymodel.md)</span><span class="sxs-lookup"><span data-stu-id="e4a84-105">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span></span>\
<span data-ttu-id="e4a84-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> identityConfiguration**](identityconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="e4a84-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span></span>\
<span data-ttu-id="e4a84-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> securityTokenHandlers**](securitytokenhandlers.md)</span><span class="sxs-lookup"><span data-stu-id="e4a84-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)</span></span>\
<span data-ttu-id="e4a84-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Agregar >** ](add.md)</span><span class="sxs-lookup"><span data-stu-id="e4a84-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<add>**](add.md)</span></span>\
<span data-ttu-id="e4a84-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> samlSecurityTokenRequirement**</span><span class="sxs-lookup"><span data-stu-id="e4a84-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<samlSecurityTokenRequirement>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e4a84-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e4a84-110">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <add>  
        <samlSecurityTokenRequirement   
            issuerCertificateValidationMode="None||ChainTrust||PeerTrust||PeerOrChainTrust||Custom"  
            issuerCertificateRevocationMode="NoCheck||Offline||Online"  
            issuerCertificateTrustedStoreLocation="CurrentLocation||LocalMachine"  
            issuerCertificateValidator="Namespace.Class Assembly"  
            mapToWindows=xs:boolean  
          <nameClaimType value=xs:string />  
          <roleClaimType value=xs:string />  
        </samlSecurityTokenRequirement>  
      </add>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e4a84-111">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="e4a84-111">Attributes and Elements</span></span>  
 <span data-ttu-id="e4a84-112">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="e4a84-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e4a84-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="e4a84-113">Attributes</span></span>  
  
|<span data-ttu-id="e4a84-114">Atributo</span><span class="sxs-lookup"><span data-stu-id="e4a84-114">Attribute</span></span>|<span data-ttu-id="e4a84-115">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="e4a84-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e4a84-116">mapToWindows</span><span class="sxs-lookup"><span data-stu-id="e4a84-116">mapToWindows</span></span>|<span data-ttu-id="e4a84-117">Especifica si el controlador de token debe asignar el token de validación a una cuenta de Windows mediante la notificaciones de UPN entrantes.</span><span class="sxs-lookup"><span data-stu-id="e4a84-117">Specifies whether the token handler should map the validating token to a Windows account by using the incoming UPN claim.</span></span> <span data-ttu-id="e4a84-118">El valor predeterminado es "false".</span><span class="sxs-lookup"><span data-stu-id="e4a84-118">The default is "false".</span></span>|  
|<span data-ttu-id="e4a84-119">issuerCertificateRevocationMode</span><span class="sxs-lookup"><span data-stu-id="e4a84-119">issuerCertificateRevocationMode</span></span>|<span data-ttu-id="e4a84-120"><xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> Valor que especifica el modo de revocación que se va a usar para el certificado X. 509.</span><span class="sxs-lookup"><span data-stu-id="e4a84-120">An <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> value that specifies the revocation mode to use for the X.509 certificate.</span></span> <span data-ttu-id="e4a84-121">El valor predeterminado es "online".</span><span class="sxs-lookup"><span data-stu-id="e4a84-121">The default value is "Online".</span></span>|  
|<span data-ttu-id="e4a84-122">issuerCertificateValidationMode</span><span class="sxs-lookup"><span data-stu-id="e4a84-122">issuerCertificateValidationMode</span></span>|<span data-ttu-id="e4a84-123"><xref:System.ServiceModel.Security.X509CertificateValidationMode> Valor que especifica el modo de validación que se va a usar para el certificado X. 509.</span><span class="sxs-lookup"><span data-stu-id="e4a84-123">An <xref:System.ServiceModel.Security.X509CertificateValidationMode> value that specifies the validation mode to use for the X.509 certificate.</span></span> <span data-ttu-id="e4a84-124">El valor predeterminado es "PeerOrChainTrust".</span><span class="sxs-lookup"><span data-stu-id="e4a84-124">The default value is "PeerOrChainTrust".</span></span>|  
|<span data-ttu-id="e4a84-125">issuerCertificateTrustedStoreLocation</span><span class="sxs-lookup"><span data-stu-id="e4a84-125">issuerCertificateTrustedStoreLocation</span></span>|<span data-ttu-id="e4a84-126"><xref:System.Security.Cryptography.X509Certificates.StoreLocation> Valor que especifica el almacén de certificados X. 509.</span><span class="sxs-lookup"><span data-stu-id="e4a84-126">A <xref:System.Security.Cryptography.X509Certificates.StoreLocation> value that specifies the X.509 certificate store.</span></span> <span data-ttu-id="e4a84-127">El valor predeterminado es "LocalMachine".</span><span class="sxs-lookup"><span data-stu-id="e4a84-127">The default value is "LocalMachine".</span></span>|  
|<span data-ttu-id="e4a84-128">issuerCertificateValidator</span><span class="sxs-lookup"><span data-stu-id="e4a84-128">issuerCertificateValidator</span></span>|<span data-ttu-id="e4a84-129">Un tipo personalizado que se deriva de <xref:System.IdentityModel.Selectors.X509CertificateValidator>.</span><span class="sxs-lookup"><span data-stu-id="e4a84-129">A custom type that derives from <xref:System.IdentityModel.Selectors.X509CertificateValidator>.</span></span> <span data-ttu-id="e4a84-130">Si el `issuerCertificateValidationMode` atributo es "Custom", se usa una instancia de este tipo para la validación del certificado del emisor.</span><span class="sxs-lookup"><span data-stu-id="e4a84-130">If the `issuerCertificateValidationMode` attribute is "Custom", an instance of this type is used for issuer certificate validation.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e4a84-131">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="e4a84-131">Child Elements</span></span>  
  
|<span data-ttu-id="e4a84-132">Elemento</span><span class="sxs-lookup"><span data-stu-id="e4a84-132">Element</span></span>|<span data-ttu-id="e4a84-133">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="e4a84-133">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e4a84-134">\<nameClaimType></span><span class="sxs-lookup"><span data-stu-id="e4a84-134">\<nameClaimType></span></span>](nameclaimtype.md)|<span data-ttu-id="e4a84-135">Establece el tipo de demanda que especifica <xref:System.Security.Principal.IIdentity.Name%2A> la propiedad.</span><span class="sxs-lookup"><span data-stu-id="e4a84-135">Sets the claim type that specifies the <xref:System.Security.Principal.IIdentity.Name%2A> property.</span></span>|  
|[<span data-ttu-id="e4a84-136">\<roleClaimType></span><span class="sxs-lookup"><span data-stu-id="e4a84-136">\<roleClaimType></span></span>](roleclaimtype.md)|<span data-ttu-id="e4a84-137">Especifica el tipo de notificación que define las notificaciones de tipo de rol <xref:System.Security.Claims.ClaimsIdentity> en la colección de <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A> objetos devuelta por el método del controlador de token.</span><span class="sxs-lookup"><span data-stu-id="e4a84-137">Specifies the claim type that defines the role type claims in the collection of <xref:System.Security.Claims.ClaimsIdentity> objects returned by the <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A> method of the token handler.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="e4a84-138">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="e4a84-138">Parent Elements</span></span>  
  
|<span data-ttu-id="e4a84-139">Elemento</span><span class="sxs-lookup"><span data-stu-id="e4a84-139">Element</span></span>|<span data-ttu-id="e4a84-140">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="e4a84-140">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e4a84-141">\<add></span><span class="sxs-lookup"><span data-stu-id="e4a84-141">\<add></span></span>](add.md)|<span data-ttu-id="e4a84-142">Agrega el controlador de tokens de seguridad especificado a la colección de controladores de tokens.</span><span class="sxs-lookup"><span data-stu-id="e4a84-142">Adds the specified security token handler to the token handler collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e4a84-143">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e4a84-143">Remarks</span></span>  
 <span data-ttu-id="e4a84-144">La `<samlSecurityTokenRequirement>` <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> clase representa el elemento en el modelo de objetos y se usa para <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> configurar la `SamlSecurityTokenRequirement` propiedad en o <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>.</span><span class="sxs-lookup"><span data-stu-id="e4a84-144">The `<samlSecurityTokenRequirement>` element is represented by the <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> class in the object model and is used to configure the `SamlSecurityTokenRequirement` property on a <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> or a <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e4a84-145">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e4a84-145">Example</span></span>  
  
```xml  
<add type="System.IdentityModel.Tokens.SamlSecurityTokenHandler, System.IdentityModel">  
    <samlSecurityTokenRequirement issuerCertificateValidationMode="PeerOrChainTrust"  
                                  issuerCertificateRevocationMode="Online"  
                                  issuerCertificateTrustedStoreLocation="LocalMachine"  
                                  mapToWindows="false">  
  
        <nameClaimType value="http://schemas.xmlsoap.org/ws/2005/05/identity/claims/name" />  
        <roleClaimType value="schemas.microsoft.com/ws/2006/04/identity/claims/role" />  
    </samlSecurityTokenRequirement>  
</add>  
```
