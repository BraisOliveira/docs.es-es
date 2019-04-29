---
title: <userNameSecurityTokenHandlerRequirement>
ms.date: 03/30/2017
ms.assetid: 6ec3bac1-b014-49ae-843c-c54518cb709a
author: BrucePerlerMS
ms.openlocfilehash: 18769794da8528f085c567264827db5aa6b214f1
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61790460"
---
# <a name="usernamesecuritytokenhandlerrequirement"></a><span data-ttu-id="7347e-101">\<userNameSecurityTokenHandlerRequirement></span><span class="sxs-lookup"><span data-stu-id="7347e-101">\<userNameSecurityTokenHandlerRequirement></span></span>
<span data-ttu-id="7347e-102">Proporciona la configuración de la <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> clase o clases derivadas.</span><span class="sxs-lookup"><span data-stu-id="7347e-102">Provides configuration for the <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> class or derived classes.</span></span>  
  
 <span data-ttu-id="7347e-103">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="7347e-103">\<system.identityModel></span></span>  
<span data-ttu-id="7347e-104">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="7347e-104">\<identityConfiguration></span></span>  
<span data-ttu-id="7347e-105">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="7347e-105">\<securityTokenHandlers></span></span>  
<span data-ttu-id="7347e-106">\<add></span><span class="sxs-lookup"><span data-stu-id="7347e-106">\<add></span></span>  
<span data-ttu-id="7347e-107">\<userNameSecurityTokenHandlerRequirement></span><span class="sxs-lookup"><span data-stu-id="7347e-107">\<userNameSecurityTokenHandlerRequirement></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7347e-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7347e-108">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <add type="System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler, System.IdentityModel.Services">  
        <userNameSecurityTokenHandlerRequirement membershipProviderName=xs:string >  
        </userNameSecurityTokenHandlerRequirement>  
      </add>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7347e-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="7347e-109">Attributes and Elements</span></span>  
 <span data-ttu-id="7347e-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="7347e-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7347e-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="7347e-111">Attributes</span></span>  
  
|<span data-ttu-id="7347e-112">Atributo</span><span class="sxs-lookup"><span data-stu-id="7347e-112">Attribute</span></span>|<span data-ttu-id="7347e-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="7347e-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="7347e-114">membershipProviderName</span><span class="sxs-lookup"><span data-stu-id="7347e-114">membershipProviderName</span></span>|<span data-ttu-id="7347e-115">Especifica el <xref:System.Web.Security.MembershipProvider> que debe usar el controlador de token de seguridad.</span><span class="sxs-lookup"><span data-stu-id="7347e-115">Specifies the <xref:System.Web.Security.MembershipProvider> that should be used by the security token handler.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7347e-116">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="7347e-116">Child Elements</span></span>  
 <span data-ttu-id="7347e-117">Ninguna</span><span class="sxs-lookup"><span data-stu-id="7347e-117">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="7347e-118">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="7347e-118">Parent Elements</span></span>  
  
|<span data-ttu-id="7347e-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="7347e-119">Element</span></span>|<span data-ttu-id="7347e-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="7347e-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7347e-121">\<add></span><span class="sxs-lookup"><span data-stu-id="7347e-121">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/add.md)|<span data-ttu-id="7347e-122">Agrega el controlador de token de seguridad especificado a la colección de controladores de token.</span><span class="sxs-lookup"><span data-stu-id="7347e-122">Adds the specified security token handler to the token handler collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7347e-123">Comentarios</span><span class="sxs-lookup"><span data-stu-id="7347e-123">Remarks</span></span>  
 <span data-ttu-id="7347e-124">El `<userNameSecurityTokenHandlerRequirement>` conjuntos de elementos del <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler.MembershipProvider%2A> propiedad cuando un <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> se inicializa el objeto de configuración.</span><span class="sxs-lookup"><span data-stu-id="7347e-124">The `<userNameSecurityTokenHandlerRequirement>` element sets the <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler.MembershipProvider%2A> property when a <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> object is initialized from configuration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7347e-125">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="7347e-125">Example</span></span>  
  
```xml  
<add type="System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler, System.IdentityModel.Services">  
    <userNameSecurityTokenHandlerRequirement membershipProviderName="AspNetSqlProvider/>  
</add>  
```
