---
title: Elemento <serviceAuthorization>
ms.date: 03/30/2017
ms.assetid: 18cddad5-ddcb-4839-a0ac-1d6f6ab783ca
ms.openlocfilehash: b73e2049afb460bf9be8b76ee272ba0547b61453
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69936394"
---
# <a name="serviceauthorization-element"></a><span data-ttu-id="bd0b1-102">\<serviceAuthorization >, elemento</span><span class="sxs-lookup"><span data-stu-id="bd0b1-102">\<serviceAuthorization> element</span></span>
<span data-ttu-id="bd0b1-103">Especifica valores que autorizan que el acceso repare las operaciones</span><span class="sxs-lookup"><span data-stu-id="bd0b1-103">Specifies settings that authorize access to service operations</span></span>  
  
 <span data-ttu-id="bd0b1-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="bd0b1-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="bd0b1-105">\<comportamientos ></span><span class="sxs-lookup"><span data-stu-id="bd0b1-105">\<behaviors></span></span>  
<span data-ttu-id="bd0b1-106">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="bd0b1-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="bd0b1-107">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="bd0b1-107">\<behavior></span></span>  
<span data-ttu-id="bd0b1-108">\<serviceAuthorization></span><span class="sxs-lookup"><span data-stu-id="bd0b1-108">\<serviceAuthorization></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bd0b1-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="bd0b1-109">Syntax</span></span>  
  
```xml  
<serviceAuthorization impersonateCallerForAllOperations="Boolean"
                      principalPermissionMode="None/UseWindowsGroups/UseAspNetRoles/Custom"
                      roleProviderName="String"
                      serviceAuthorizationManagerType="String">
  <authorizationPolicies>
    <add policyType="String" />
  </authorizationPolicies>
</serviceAuthorization>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="bd0b1-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="bd0b1-110">Attributes and Elements</span></span>  
 <span data-ttu-id="bd0b1-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="bd0b1-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="bd0b1-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="bd0b1-112">Attributes</span></span>  
  
|<span data-ttu-id="bd0b1-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="bd0b1-113">Attribute</span></span>|<span data-ttu-id="bd0b1-114">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="bd0b1-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="bd0b1-115">impersonateCallerForAllOperations</span><span class="sxs-lookup"><span data-stu-id="bd0b1-115">impersonateCallerForAllOperations</span></span>|<span data-ttu-id="bd0b1-116">Un valor booleano que especifica si todas las operaciones en el servicio suplantan al autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="bd0b1-116">A Boolean value that specifies if all the operations in the service impersonate the caller.</span></span> <span data-ttu-id="bd0b1-117">El valor predeterminado es `false`.</span><span class="sxs-lookup"><span data-stu-id="bd0b1-117">The default is `false`.</span></span><br /><br /> <span data-ttu-id="bd0b1-118">Cuando una operación de servicio concreta suplanta al llamador, el contexto del subproceso se intercambia al contexto del llamador antes de ejecutar el servicio especificado.</span><span class="sxs-lookup"><span data-stu-id="bd0b1-118">When a specific service operation impersonates the caller, the thread context is switched to the caller context before executing the specified service.</span></span>|  
|<span data-ttu-id="bd0b1-119">principalPermissionMode</span><span class="sxs-lookup"><span data-stu-id="bd0b1-119">principalPermissionMode</span></span>|<span data-ttu-id="bd0b1-120">Establece la entidad de seguridad usada para llevar a cabo las operaciones en el servidor.</span><span class="sxs-lookup"><span data-stu-id="bd0b1-120">Sets the principal used to carry out operations on the server.</span></span> <span data-ttu-id="bd0b1-121">Los valores son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="bd0b1-121">Values include the following:</span></span><br /><br /> <span data-ttu-id="bd0b1-122">-Ninguno</span><span class="sxs-lookup"><span data-stu-id="bd0b1-122">-   None</span></span><br /><span data-ttu-id="bd0b1-123">-   UseWindowsGroups</span><span class="sxs-lookup"><span data-stu-id="bd0b1-123">-   UseWindowsGroups</span></span><br /><span data-ttu-id="bd0b1-124">-   UseAspNetRoles</span><span class="sxs-lookup"><span data-stu-id="bd0b1-124">-   UseAspNetRoles</span></span><br /><span data-ttu-id="bd0b1-125">-Personalizado</span><span class="sxs-lookup"><span data-stu-id="bd0b1-125">-   Custom</span></span><br /><br /> <span data-ttu-id="bd0b1-126">El valor predeterminado es UseWindowsGroups.</span><span class="sxs-lookup"><span data-stu-id="bd0b1-126">The default value is UseWindowsGroups.</span></span> <span data-ttu-id="bd0b1-127">El valor es del tipo <xref:System.ServiceModel.Description.PrincipalPermissionMode>.</span><span class="sxs-lookup"><span data-stu-id="bd0b1-127">The value is of type <xref:System.ServiceModel.Description.PrincipalPermissionMode>.</span></span> <span data-ttu-id="bd0b1-128">Para obtener más información sobre el uso de este [atributo, consulte Cómo: Restrinja el acceso con la clase](../../../wcf/how-to-restrict-access-with-the-principalpermissionattribute-class.md)PrincipalPermissionAttribute.</span><span class="sxs-lookup"><span data-stu-id="bd0b1-128">For more information on using this attribute, see [How to: Restrict Access with the PrincipalPermissionAttribute Class](../../../wcf/how-to-restrict-access-with-the-principalpermissionattribute-class.md).</span></span>|  
|<span data-ttu-id="bd0b1-129">roleProviderName</span><span class="sxs-lookup"><span data-stu-id="bd0b1-129">roleProviderName</span></span>|<span data-ttu-id="bd0b1-130">Una cadena que especifica el nombre del proveedor de roles, que proporciona información de rol para una aplicación Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="bd0b1-130">A string that specifies the name of the role provider, which provides role information for a Windows Communication Foundation (WCF) application.</span></span> <span data-ttu-id="bd0b1-131">El valor predeterminado es una cadena vacía.</span><span class="sxs-lookup"><span data-stu-id="bd0b1-131">The default is an empty string.</span></span>|  
|<span data-ttu-id="bd0b1-132">ServiceAuthorizationManagerType</span><span class="sxs-lookup"><span data-stu-id="bd0b1-132">ServiceAuthorizationManagerType</span></span>|<span data-ttu-id="bd0b1-133">Una cadena que contiene el tipo de administrador de autorización de servicio.</span><span class="sxs-lookup"><span data-stu-id="bd0b1-133">A string containing the type of the service authorization manager.</span></span> <span data-ttu-id="bd0b1-134">Para obtener más información, consulta <xref:System.ServiceModel.ServiceAuthorizationManager>.</span><span class="sxs-lookup"><span data-stu-id="bd0b1-134">For more information, see <xref:System.ServiceModel.ServiceAuthorizationManager>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="bd0b1-135">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="bd0b1-135">Child Elements</span></span>  
  
|<span data-ttu-id="bd0b1-136">Elemento</span><span class="sxs-lookup"><span data-stu-id="bd0b1-136">Element</span></span>|<span data-ttu-id="bd0b1-137">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="bd0b1-137">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="bd0b1-138">authorizationPolicies</span><span class="sxs-lookup"><span data-stu-id="bd0b1-138">authorizationPolicies</span></span>|<span data-ttu-id="bd0b1-139">Contiene una colección de tipos de directiva de autorización, que se pueden agregar utilizando la palabra clave `add`.</span><span class="sxs-lookup"><span data-stu-id="bd0b1-139">Contains a collection of authorization policy types, which can be added using the `add` keyword.</span></span> <span data-ttu-id="bd0b1-140">Cada directiva de autorización contiene un atributo `policyType` necesario único que es una cadena.</span><span class="sxs-lookup"><span data-stu-id="bd0b1-140">Each authorization policy contains a single required `policyType` attribute that is a string.</span></span> <span data-ttu-id="bd0b1-141">El atributo especifica una directiva de autorización que permite la transformación de un conjunto de demandas de entrada en otro conjunto de demandas.</span><span class="sxs-lookup"><span data-stu-id="bd0b1-141">The attribute specifies an authorization policy, which enables transformation of one set of input claims into another set of claims.</span></span> <span data-ttu-id="bd0b1-142">Se puede permitir o denegar el acceso en base a eso.</span><span class="sxs-lookup"><span data-stu-id="bd0b1-142">Access control can be granted or denied based on that.</span></span> <span data-ttu-id="bd0b1-143">Para obtener más información, consulta <xref:System.ServiceModel.Configuration.AuthorizationPolicyTypeElement>.</span><span class="sxs-lookup"><span data-stu-id="bd0b1-143">For more information, see <xref:System.ServiceModel.Configuration.AuthorizationPolicyTypeElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="bd0b1-144">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="bd0b1-144">Parent Elements</span></span>  
  
|<span data-ttu-id="bd0b1-145">Elemento</span><span class="sxs-lookup"><span data-stu-id="bd0b1-145">Element</span></span>|<span data-ttu-id="bd0b1-146">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="bd0b1-146">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="bd0b1-147">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="bd0b1-147">\<behavior></span></span>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="bd0b1-148">Contiene una colección de valores para el comportamiento de un servicio.</span><span class="sxs-lookup"><span data-stu-id="bd0b1-148">Contains a collection of settings for the behavior of a service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bd0b1-149">Comentarios</span><span class="sxs-lookup"><span data-stu-id="bd0b1-149">Remarks</span></span>  
 <span data-ttu-id="bd0b1-150">Esta sección contiene elementos que afectan a la autorización, a los proveedores de roles personalizados y a la suplantación.</span><span class="sxs-lookup"><span data-stu-id="bd0b1-150">This section contains elements affecting authorization, custom role providers, and impersonation.</span></span>  
  
 <span data-ttu-id="bd0b1-151">El atributo `principalPermissionMode` especifica los grupos de usuarios que se han de utilizar al autorizar el uso de un método protegido.</span><span class="sxs-lookup"><span data-stu-id="bd0b1-151">The `principalPermissionMode` attribute specifies the groups of users to use when authorizing use of a protected method.</span></span> <span data-ttu-id="bd0b1-152">El valor predeterminado es `UseWindowsGroups` y especifica que en los grupos de Windows, como "Administradores" o "Usuarios", se busca una identidad que intente obtener acceso a un recurso.</span><span class="sxs-lookup"><span data-stu-id="bd0b1-152">The default value is `UseWindowsGroups` and specifies that Windows groups, such as "Administrators" or "Users," are searched for an identity trying to access a resource.</span></span> <span data-ttu-id="bd0b1-153">También puede especificar `UseAspNetRoles` que se use un proveedor de roles personalizado que esté configurado en \<el elemento System. Web >, tal y como se muestra en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="bd0b1-153">You can also specify `UseAspNetRoles` to use a custom role provider that is configured under the \<system.web> element, as shown in the following code.</span></span>  
  
```xml  
<system.web>
  <membership defaultProvider="SqlProvider"
              userIsOnlineTimeWindow="15">
    <providers>
      <clear />
      <add name="SqlProvider"
           type="System.Web.Security.SqlMembershipProvider"
           connectionStringName="SqlConn"
           applicationName="MembershipProvider"
           enablePasswordRetrieval="false"
           enablePasswordReset="false"
           requiresQuestionAndAnswer="false"
           requiresUniqueEmail="true"
           passwordFormat="Hashed" />
    </providers>
  </membership>
  <!-- Other configuration code not shown. -->
</system.web>
```  
  
 <span data-ttu-id="bd0b1-154">El ejemplo de código siguiente muestra el `roleProviderName` utilizado con el atributo `principalPermissionMode`.</span><span class="sxs-lookup"><span data-stu-id="bd0b1-154">The following code shows the `roleProviderName` used with the `principalPermissionMode` attribute.</span></span>  
  
```xml  
<behaviors>
  <behavior name="ServiceBehaviour">
    <serviceAuthorization principalPermissionMode ="UseAspNetRoles"
                          roleProviderName ="SqlProvider" />
  </behavior>
  <!-- Other configuration code not shown. -->
</behaviors>
```  
  
 <span data-ttu-id="bd0b1-155">Para obtener un ejemplo detallado del uso de este elemento de configuración, vea autorizar el [acceso a las operaciones de servicio y a](../../../wcf/samples/authorizing-access-to-service-operations.md) la [Directiva de autorización](../../../wcf/samples/authorization-policy.md).</span><span class="sxs-lookup"><span data-stu-id="bd0b1-155">For a detailed example of using this configuration element, see [Authorizing Access to Service Operations](../../../wcf/samples/authorizing-access-to-service-operations.md) and [Authorization Policy](../../../wcf/samples/authorization-policy.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bd0b1-156">Vea también</span><span class="sxs-lookup"><span data-stu-id="bd0b1-156">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceAuthorizationElement>
- <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior>
- [<span data-ttu-id="bd0b1-157">Comportamientos de seguridad</span><span class="sxs-lookup"><span data-stu-id="bd0b1-157">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="bd0b1-158">Autorización de acceso a operaciones de servicio</span><span class="sxs-lookup"><span data-stu-id="bd0b1-158">Authorizing Access to Service Operations</span></span>](../../../wcf/samples/authorizing-access-to-service-operations.md)
- [<span data-ttu-id="bd0b1-159">Procedimientos: Crear un administrador de autorización personalizado para un servicio</span><span class="sxs-lookup"><span data-stu-id="bd0b1-159">How to: Create a Custom Authorization Manager for a Service</span></span>](../../../wcf/extending/how-to-create-a-custom-authorization-manager-for-a-service.md)
- [<span data-ttu-id="bd0b1-160">Procedimientos: Restringir el acceso con la clase PrincipalPermissionAttribute</span><span class="sxs-lookup"><span data-stu-id="bd0b1-160">How to: Restrict Access with the PrincipalPermissionAttribute Class</span></span>](../../../wcf/how-to-restrict-access-with-the-principalpermissionattribute-class.md)
- [<span data-ttu-id="bd0b1-161">Directiva de autorización</span><span class="sxs-lookup"><span data-stu-id="bd0b1-161">Authorization Policy</span></span>](../../../wcf/samples/authorization-policy.md)
