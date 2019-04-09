---
title: <userNameAuthentication>
ms.date: 03/30/2017
ms.assetid: 24d8b398-770f-418f-ba23-c4325419cfa6
ms.openlocfilehash: 5a4cf8d429198b889f2bb362294ba3841c814b26
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59083151"
---
# <a name="usernameauthentication"></a><span data-ttu-id="a4cbd-101">\<userNameAuthentication></span><span class="sxs-lookup"><span data-stu-id="a4cbd-101">\<userNameAuthentication></span></span>
<span data-ttu-id="a4cbd-102">Especifica las credenciales de un servicio basadas en el nombre de usuario y contraseña.</span><span class="sxs-lookup"><span data-stu-id="a4cbd-102">Specifies a service's credentials based on user name and password.</span></span>  
  
 <span data-ttu-id="a4cbd-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="a4cbd-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="a4cbd-104">\<comportamientos ></span><span class="sxs-lookup"><span data-stu-id="a4cbd-104">\<behaviors></span></span>  
<span data-ttu-id="a4cbd-105">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="a4cbd-105">\<serviceBehaviors></span></span>  
<span data-ttu-id="a4cbd-106">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="a4cbd-106">\<behavior></span></span>  
<span data-ttu-id="a4cbd-107">\<serviceCredentials></span><span class="sxs-lookup"><span data-stu-id="a4cbd-107">\<serviceCredentials></span></span>  
<span data-ttu-id="a4cbd-108">\<userNameAuthentication></span><span class="sxs-lookup"><span data-stu-id="a4cbd-108">\<userNameAuthentication></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a4cbd-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a4cbd-109">Syntax</span></span>  
  
```xml  
<userNameAuthentication cacheLogonTokenLifetime="TimeSpan"
                        cacheLogonTokens="Boolean"
                        customUserNamePasswordValidatorType="String"
                        includeWindowsGroups="Boolean"
                        maxCacheLogonTokens="Integer"
                        membershipProviderName="String"
                        userNamePasswordValidationMode="Windows/MembershipProvider/Custom" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a4cbd-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="a4cbd-110">Attributes and Elements</span></span>  
 <span data-ttu-id="a4cbd-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="a4cbd-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a4cbd-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="a4cbd-112">Attributes</span></span>  
  
|<span data-ttu-id="a4cbd-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="a4cbd-113">Attribute</span></span>|<span data-ttu-id="a4cbd-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="a4cbd-114">Description</span></span>|  
|---------------|-----------------|  
|`cacheLogonTokenLifetime`|<span data-ttu-id="a4cbd-115"><xref:System.TimeSpan> que especifica la duración máxima que un token está almacenado en la memoria caché.</span><span class="sxs-lookup"><span data-stu-id="a4cbd-115">A <xref:System.TimeSpan> that specifies the maximum length of time a token is cached.</span></span> <span data-ttu-id="a4cbd-116">El valor predeterminado es 00:15:00.</span><span class="sxs-lookup"><span data-stu-id="a4cbd-116">The default is 00:15:00.</span></span>|  
|`cacheLogonTokens`|<span data-ttu-id="a4cbd-117">Un valor booleano que especifica si los tokens de inicio de sesión están almacenados en memoria caché.</span><span class="sxs-lookup"><span data-stu-id="a4cbd-117">A Boolean value that specifies whether logon tokens are cached.</span></span> <span data-ttu-id="a4cbd-118">De manera predeterminada, es `false`.</span><span class="sxs-lookup"><span data-stu-id="a4cbd-118">The default is `false`.</span></span>|  
|`customUserNamePasswordValidatorType`|<span data-ttu-id="a4cbd-119">Una cadena que especifica el tipo de validador de contraseña de nombre de usuario personalizado que se va a utilizar.</span><span class="sxs-lookup"><span data-stu-id="a4cbd-119">A string that specifies the type of custom username password validator to be used.</span></span> <span data-ttu-id="a4cbd-120">El valor predeterminado es una cadena vacía.</span><span class="sxs-lookup"><span data-stu-id="a4cbd-120">The default is an empty string.</span></span>|  
|`includeWindowsGroups`|<span data-ttu-id="a4cbd-121">Un valor booleano que especifica si los grupos de Windows están incluidos en el contexto de seguridad.</span><span class="sxs-lookup"><span data-stu-id="a4cbd-121">A Boolean value that specifies whether Windows groups are included in the security context.</span></span> <span data-ttu-id="a4cbd-122">De manera predeterminada, es `true`.</span><span class="sxs-lookup"><span data-stu-id="a4cbd-122">The default is `true`.</span></span><br /><br /> <span data-ttu-id="a4cbd-123">Al establecer este atributo en `true`, se tiene un impacto de rendimiento y tiene como resultado una expansión de grupo completa.</span><span class="sxs-lookup"><span data-stu-id="a4cbd-123">Setting this attribute to `true` has a performance impact as it results in a full-group expansion.</span></span> <span data-ttu-id="a4cbd-124">Establezca esta propiedad en `false` si no necesita establecer la lista de grupos a los que un usuario pertenece.</span><span class="sxs-lookup"><span data-stu-id="a4cbd-124">Set this property to `false` if you do not need to establish the list of groups a user belongs to.</span></span>|  
|`maxCacheLogonTokens`|<span data-ttu-id="a4cbd-125">Un entero que especifica el número máximo de tokens de inicio de sesión para almacenar en memoria caché.</span><span class="sxs-lookup"><span data-stu-id="a4cbd-125">An integer that specifies the maximum number of logon tokens to cache.</span></span> <span data-ttu-id="a4cbd-126">Este valor debería ser mayor que cero.</span><span class="sxs-lookup"><span data-stu-id="a4cbd-126">This value should be larger than zero.</span></span> <span data-ttu-id="a4cbd-127">El valor predeterminado es 128.</span><span class="sxs-lookup"><span data-stu-id="a4cbd-127">The default is 128.</span></span>|  
|`membershipProviderName`|<span data-ttu-id="a4cbd-128">Cuando el atributo `clientCredentialType` de un enlace está establecido en `username`, el nombre de usuario está asignado a las cuentas de Windows.</span><span class="sxs-lookup"><span data-stu-id="a4cbd-128">When the `clientCredentialType` attribute of a binding is set to `username`, the username is mapped to Windows accounts.</span></span> <span data-ttu-id="a4cbd-129">Puede invalidar este comportamiento mediante este atributo, que es una cadena que contiene el nombre del valor <xref:System.Web.Security.MembershipProvider> que proporciona el mecanismo de validación de contraseña pertinente.</span><span class="sxs-lookup"><span data-stu-id="a4cbd-129">You can override this behavior using this attribute, which is a string that contains the name of the <xref:System.Web.Security.MembershipProvider> value that provides the relevant password validation mechanism.</span></span>|  
|`userNamePasswordValidationMode`|<span data-ttu-id="a4cbd-130">Especifica la manera en la que se valida la contraseña del nombre de usuario.</span><span class="sxs-lookup"><span data-stu-id="a4cbd-130">Specifies the manner in which username password is validated.</span></span> <span data-ttu-id="a4cbd-131">Los valores válidos son:</span><span class="sxs-lookup"><span data-stu-id="a4cbd-131">Valid values are:</span></span><br /><br /> <span data-ttu-id="a4cbd-132">-Windows</span><span class="sxs-lookup"><span data-stu-id="a4cbd-132">-   Windows</span></span><br /><span data-ttu-id="a4cbd-133">-MembershipProvider</span><span class="sxs-lookup"><span data-stu-id="a4cbd-133">-   MembershipProvider</span></span><br /><span data-ttu-id="a4cbd-134">-Custom</span><span class="sxs-lookup"><span data-stu-id="a4cbd-134">-   Custom</span></span><br /><br /> <span data-ttu-id="a4cbd-135">El valor predeterminado es Windows.</span><span class="sxs-lookup"><span data-stu-id="a4cbd-135">The default is Windows.</span></span> <span data-ttu-id="a4cbd-136">Este atributo es del tipo <xref:System.ServiceModel.Security.UserNamePasswordValidationMode>.</span><span class="sxs-lookup"><span data-stu-id="a4cbd-136">This attribute is of type <xref:System.ServiceModel.Security.UserNamePasswordValidationMode>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a4cbd-137">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="a4cbd-137">Child Elements</span></span>  
 <span data-ttu-id="a4cbd-138">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="a4cbd-138">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a4cbd-139">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="a4cbd-139">Parent Elements</span></span>  
  
|<span data-ttu-id="a4cbd-140">Elemento</span><span class="sxs-lookup"><span data-stu-id="a4cbd-140">Element</span></span>|<span data-ttu-id="a4cbd-141">Descripción</span><span class="sxs-lookup"><span data-stu-id="a4cbd-141">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a4cbd-142">\<serviceCredentials></span><span class="sxs-lookup"><span data-stu-id="a4cbd-142">\<serviceCredentials></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md)|<span data-ttu-id="a4cbd-143">Especifica la credencial que se va a utilizar para autenticar el servicio y los valores relacionados con la validación de la credencial del cliente.</span><span class="sxs-lookup"><span data-stu-id="a4cbd-143">Specifies the credential to be used in authenticating the service, and the client credential validation related settings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a4cbd-144">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a4cbd-144">Remarks</span></span>  
 <span data-ttu-id="a4cbd-145">Si ninguno de los enlaces utilizados por un servicio se configura para la autenticación mediante el nombre de usuario/contraseña, se omiten los atributos para este elemento.</span><span class="sxs-lookup"><span data-stu-id="a4cbd-145">If none of the bindings used by a service is configured for user name/password-based authentication, the attributes for this element are ignored.</span></span> <span data-ttu-id="a4cbd-146">Entre estos se incluyen los eventos `customUserNamePasswordValidatorType`, `includeWindowsGroups`, `membershipProviderName` y `userNamePasswordValidationMode`.</span><span class="sxs-lookup"><span data-stu-id="a4cbd-146">These include `customUserNamePasswordValidatorType`, `includeWindowsGroups`, `membershipProviderName`, and `userNamePasswordValidationMode`.</span></span>  
  
 <span data-ttu-id="a4cbd-147">Si ninguno de los enlaces utilizados por un servicio configurado para utilizar la autenticación de Windows para el nombre de usuario/contraseña, se omite la configuración relacionada con almacenar en memoria caché los tokens de inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="a4cbd-147">If none of the bindings used by a service is configured to use Windows authentication for user name/password, the settings related to caching of logon tokens are ignored.</span></span> <span data-ttu-id="a4cbd-148">Éstos incluyen `cacheLogonTokenLifetime`, `cacheLogonTokens` y `maxCacheLogonTokens`.</span><span class="sxs-lookup"><span data-stu-id="a4cbd-148">These include the `cacheLogonTokenLifetime`, `cacheLogonTokens`, and `maxCacheLogonTokens`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a4cbd-149">Vea también</span><span class="sxs-lookup"><span data-stu-id="a4cbd-149">See also</span></span>

- <xref:System.ServiceModel.Configuration.UserNameServiceElement>
- <xref:System.ServiceModel.Description.ServiceCredentials.UserNameAuthentication%2A>
- <xref:System.ServiceModel.Security.UserNamePasswordServiceCredential>
- <xref:System.ServiceModel.Configuration.ServiceCredentialsElement.UserNameAuthentication%2A>
