---
title: <customCookieHandler>
ms.date: 03/30/2017
ms.assetid: a03b153d-5ec6-4915-9031-6f0c3fd348be
author: BrucePerlerMS
ms.openlocfilehash: 0129c63fe17b63889a77ea1a56c0d7e657def859
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59224056"
---
# <a name="customcookiehandler"></a><span data-ttu-id="6035c-101">\<customCookieHandler></span><span class="sxs-lookup"><span data-stu-id="6035c-101">\<customCookieHandler></span></span>
<span data-ttu-id="6035c-102">Establece el tipo de controlador de cookies personalizado.</span><span class="sxs-lookup"><span data-stu-id="6035c-102">Sets the custom cookie handler type.</span></span> <span data-ttu-id="6035c-103">Este elemento solo puede estar presente si el `mode` atributo de la `<cookieHandler>` elemento es "Custom".</span><span class="sxs-lookup"><span data-stu-id="6035c-103">This element may only be present if the `mode` attribute of the `<cookieHandler>` element is "Custom".</span></span> <span data-ttu-id="6035c-104">El tipo personalizado debe derivarse de la <xref:System.IdentityModel.Services.CookieHandler> clase.</span><span class="sxs-lookup"><span data-stu-id="6035c-104">The custom type must be derived from the <xref:System.IdentityModel.Services.CookieHandler> class.</span></span>  
  
 <span data-ttu-id="6035c-105">\<system.identityModel.services></span><span class="sxs-lookup"><span data-stu-id="6035c-105">\<system.identityModel.services></span></span>  
<span data-ttu-id="6035c-106">\<federationConfiguration></span><span class="sxs-lookup"><span data-stu-id="6035c-106">\<federationConfiguration></span></span>  
<span data-ttu-id="6035c-107">\<cookieHandler></span><span class="sxs-lookup"><span data-stu-id="6035c-107">\<cookieHandler></span></span>  
<span data-ttu-id="6035c-108">\<customCookieHandler></span><span class="sxs-lookup"><span data-stu-id="6035c-108">\<customCookieHandler></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6035c-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6035c-109">Syntax</span></span>  
  
```xml  
<system.identityModel.services>  
  <federationConfiguration>  
    <cookieHandler mode="Custom">  
      <customCookieHandler type="MyNamespace.MyCustomCookieHandler, MyAssembly" >  
      </customCookieHandler>  
    </cookieHandler>  
  </federationConfiguration>  
</system.identityModel.services>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6035c-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="6035c-110">Attributes and Elements</span></span>  
 <span data-ttu-id="6035c-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="6035c-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6035c-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="6035c-112">Attributes</span></span>  
  
|<span data-ttu-id="6035c-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="6035c-113">Attribute</span></span>|<span data-ttu-id="6035c-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="6035c-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="6035c-115">type</span><span class="sxs-lookup"><span data-stu-id="6035c-115">type</span></span>|<span data-ttu-id="6035c-116">Especifica un tipo personalizado que deriva la <xref:System.IdentityModel.Services.CookieHandler> clase.</span><span class="sxs-lookup"><span data-stu-id="6035c-116">Specifies a custom type that derives from the <xref:System.IdentityModel.Services.CookieHandler> class.</span></span> <span data-ttu-id="6035c-117">Para obtener más información sobre cómo especificar el `type` atributo, vea [referencias de tipos personalizado](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md).</span><span class="sxs-lookup"><span data-stu-id="6035c-117">For more information about how to specify the `type` attribute, see [Custom Type References](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="6035c-118">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="6035c-118">Child Elements</span></span>  
 <span data-ttu-id="6035c-119">Ninguna</span><span class="sxs-lookup"><span data-stu-id="6035c-119">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="6035c-120">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="6035c-120">Parent Elements</span></span>  
  
|<span data-ttu-id="6035c-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="6035c-121">Element</span></span>|<span data-ttu-id="6035c-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="6035c-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6035c-123">\<cookieHandler></span><span class="sxs-lookup"><span data-stu-id="6035c-123">\<cookieHandler></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/cookiehandler.md)|<span data-ttu-id="6035c-124">Configura el <xref:System.IdentityModel.Services.CookieHandler> que el <xref:System.IdentityModel.Services.SessionAuthenticationModule> usa para leer y escribir cookies.</span><span class="sxs-lookup"><span data-stu-id="6035c-124">Configures the <xref:System.IdentityModel.Services.CookieHandler> that the <xref:System.IdentityModel.Services.SessionAuthenticationModule> uses to read and write cookies.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6035c-125">Comentarios</span><span class="sxs-lookup"><span data-stu-id="6035c-125">Remarks</span></span>  
 <span data-ttu-id="6035c-126">Al especificar un controlador de cookies personalizado estableciendo la `mode` atributo de la `<cookieHandler>` elemento en "Custom", debe especificar el tipo del controlador de cookies personalizado mediante la inclusión de un `<customCookieHandler>` elemento secundario que hace referencia al tipo de controlador de cookie.</span><span class="sxs-lookup"><span data-stu-id="6035c-126">When you specify a custom cookie handler by setting the `mode` attribute of the `<cookieHandler>` element to "Custom", you must specify the type of the custom cookie handler by including a `<customCookieHandler>` child element that references the cookie handler type.</span></span> <span data-ttu-id="6035c-127">Este elemento no puede ser que se especificó cuando la `mode` atributo está establecido en "Chunked" o "Default".</span><span class="sxs-lookup"><span data-stu-id="6035c-127">This element cannot be specified when the `mode` attribute is set to "Chunked" or "Default".</span></span> <span data-ttu-id="6035c-128">Controladores de cookies personalizado deben derivarse de la <xref:System.IdentityModel.Services.CookieHandler> clase.</span><span class="sxs-lookup"><span data-stu-id="6035c-128">Custom cookie handlers must derive from the <xref:System.IdentityModel.Services.CookieHandler> class.</span></span>  
  
 <span data-ttu-id="6035c-129">El `<customCookieHandler>` elemento representado por la <xref:System.IdentityModel.Configuration.CustomTypeElement> clase.</span><span class="sxs-lookup"><span data-stu-id="6035c-129">The `<customCookieHandler>` element is represented by the <xref:System.IdentityModel.Configuration.CustomTypeElement> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6035c-130">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="6035c-130">Example</span></span>  
 <span data-ttu-id="6035c-131">El ejemplo siguiente configura el SAM para usar un controlador de cookies personalizado del tipo `MyNamespace.MyCustomCookieHandler`.</span><span class="sxs-lookup"><span data-stu-id="6035c-131">The following example configures the SAM to use a custom cookie handler of type `MyNamespace.MyCustomCookieHandler`.</span></span>  
  
```xml  
<cookieHandler mode="Custom">  
    <customCookieHandler type="MyNamespace.MyCustomCookieHandler, MyAssembly" />  
</cookieHandler>  
```  
  
## <a name="see-also"></a><span data-ttu-id="6035c-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="6035c-132">See also</span></span>

- <xref:System.IdentityModel.Services.CookieHandler>
