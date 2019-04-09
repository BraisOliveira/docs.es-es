---
title: Elemento <system.Net> (configuración de red)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#system.Net
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.Net
helpviewer_keywords:
- system.Net element
- <system.Net> element
ms.assetid: 52de4d6c-b24d-44aa-ba7d-6b5061f1357e
ms.openlocfilehash: febea73ddbc45276f97835eb4af7ee0d0d68dda5
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59095275"
---
# <a name="systemnet-element-network-settings"></a><span data-ttu-id="88613-102">\<system.Net > elemento (configuración de red)</span><span class="sxs-lookup"><span data-stu-id="88613-102">\<system.Net> Element (Network Settings)</span></span>
<span data-ttu-id="88613-103">Contiene valores que especifican cómo se conecta .NET Framework a la red.</span><span class="sxs-lookup"><span data-stu-id="88613-103">Contains settings that specify how the .NET Framework connects to the network.</span></span>  
  
 <span data-ttu-id="88613-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="88613-104">\<configuration></span></span>  
<span data-ttu-id="88613-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="88613-105">\<system.net></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="88613-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="88613-106">Syntax</span></span>  
  
```xml  
<system.net>   
</system.net>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="88613-107">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="88613-107">Attributes and Elements</span></span>  
 <span data-ttu-id="88613-108">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="88613-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="88613-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="88613-109">Attributes</span></span>  
 <span data-ttu-id="88613-110">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="88613-110">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="88613-111">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="88613-111">Child Elements</span></span>  
  
|**<span data-ttu-id="88613-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="88613-112">Element</span></span>**|**<span data-ttu-id="88613-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="88613-113">Description</span></span>**|  
|-----------------|---------------------|  
|[<span data-ttu-id="88613-114">authenticationModules</span><span class="sxs-lookup"><span data-stu-id="88613-114">authenticationModules</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/authenticationmodules-element-network-settings.md)|<span data-ttu-id="88613-115">Especifica los módulos que se usa para autenticar las solicitudes de Internet.</span><span class="sxs-lookup"><span data-stu-id="88613-115">Specifies modules used to authenticate Internet requests.</span></span>|  
|[<span data-ttu-id="88613-116">connectionManagement</span><span class="sxs-lookup"><span data-stu-id="88613-116">connectionManagement</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/connectionmanagement-element-network-settings.md)|<span data-ttu-id="88613-117">Especifica el número máximo de conexiones a un host de Internet.</span><span class="sxs-lookup"><span data-stu-id="88613-117">Specifies the maximum number of connections to an Internet host.</span></span>|  
|[<span data-ttu-id="88613-118">defaultProxy</span><span class="sxs-lookup"><span data-stu-id="88613-118">defaultProxy</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/defaultproxy-element-network-settings.md)|<span data-ttu-id="88613-119">Configura el servidor proxy de Protocolo de transferencia de hipertexto (HTTP).</span><span class="sxs-lookup"><span data-stu-id="88613-119">Configures the Hypertext Transfer Protocol (HTTP) proxy server.</span></span>|  
|[<span data-ttu-id="88613-120">mailSettings</span><span class="sxs-lookup"><span data-stu-id="88613-120">mailSettings</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/mailsettings-element-network-settings.md)|<span data-ttu-id="88613-121">Configura las opciones de envío de correo de Protocolo Simple de transferencia de correo (SMTP).</span><span class="sxs-lookup"><span data-stu-id="88613-121">Configures Simple Mail Transport Protocol (SMTP) mail sending options.</span></span>|  
|[<span data-ttu-id="88613-122">requestCaching</span><span class="sxs-lookup"><span data-stu-id="88613-122">requestCaching</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/requestcaching-element-network-settings.md)|<span data-ttu-id="88613-123">Controla el mecanismo de almacenamiento en caché para las solicitudes de red.</span><span class="sxs-lookup"><span data-stu-id="88613-123">Controls the caching mechanism for network requests.</span></span>|  
|[<span data-ttu-id="88613-124">configuración</span><span class="sxs-lookup"><span data-stu-id="88613-124">settings</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/settings-element-network-settings.md)|<span data-ttu-id="88613-125">Configura las opciones de red básica para las clases en el <xref:System.Net> y espacios de nombres secundarios relacionados.</span><span class="sxs-lookup"><span data-stu-id="88613-125">Configures basic network options for classes in the <xref:System.Net> and related child namespaces.</span></span>|  
|[<span data-ttu-id="88613-126">webRequestModules</span><span class="sxs-lookup"><span data-stu-id="88613-126">webRequestModules</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/webrequestmodules-element-network-settings.md)|<span data-ttu-id="88613-127">Especifica los módulos que se utilizan para solicitar información de hosts de Internet.</span><span class="sxs-lookup"><span data-stu-id="88613-127">Specifies modules to use to request information from Internet hosts.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="88613-128">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="88613-128">Parent Elements</span></span>  
  
|**<span data-ttu-id="88613-129">Elemento</span><span class="sxs-lookup"><span data-stu-id="88613-129">Element</span></span>**|**<span data-ttu-id="88613-130">Descripción</span><span class="sxs-lookup"><span data-stu-id="88613-130">Description</span></span>**|  
|-----------------|---------------------|  
|[<span data-ttu-id="88613-131">configuración</span><span class="sxs-lookup"><span data-stu-id="88613-131">configuration</span></span>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)|<span data-ttu-id="88613-132">Contiene la configuración para todos los espacios de nombres.</span><span class="sxs-lookup"><span data-stu-id="88613-132">Contains settings for all namespaces.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="88613-133">Comentarios</span><span class="sxs-lookup"><span data-stu-id="88613-133">Remarks</span></span>  
 <span data-ttu-id="88613-134">El [ \<system.net >](../../../../../docs/framework/configure-apps/file-schema/network/system-net-element-network-settings.md) elemento contiene los valores de las clases de la <xref:System.Net> y espacios de nombres secundarios relacionados.</span><span class="sxs-lookup"><span data-stu-id="88613-134">The [\<system.net>](../../../../../docs/framework/configure-apps/file-schema/network/system-net-element-network-settings.md) element contains settings for classes in the <xref:System.Net> and related child namespaces.</span></span> <span data-ttu-id="88613-135">Configuración de la configuración de módulos de autenticación, administración de conexiones, configuración de correo, el servidor proxy y los módulos de solicitud de Internet para recibir información de hosts de Internet.</span><span class="sxs-lookup"><span data-stu-id="88613-135">The settings configure authentication modules, connection management, mail settings, the proxy server, and Internet request modules for receiving information from Internet hosts.</span></span>  
  
## <a name="example"></a><span data-ttu-id="88613-136">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="88613-136">Example</span></span>  
 <span data-ttu-id="88613-137">En el ejemplo siguiente se muestra una configuración típica usa <xref:System.Net> clases.</span><span class="sxs-lookup"><span data-stu-id="88613-137">The following example shows a typical configuration used by <xref:System.Net> classes.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <authenticationModules>  
      <add type="System.Net.DigestClient" />  
      <add type="System.Net.NegotiateClient" />  
      <add type="System.Net.KerberosClient" />  
      <add type="System.Net.NtlmClient" />  
      <add type="System.Net.BasicClient" />  
    </authenticationModules>  
    <connectionManagement>  
      <add address="*" maxconnection="2" />  
    </connectionManagement>  
    <defaultProxy>  
      <proxy  
        usesystemdefault="true"  
        bypassonlocal="true"  
      />  
    </defaultProxy>  
    <webRequestModules>  
      <add prefix="http"  
           type="System.Net.HttpRequestCreator"  
      />  
      <add prefix="https"  
           type="System.Net.HttpRequestCreator"  
      />  
      <add prefix="file"  
           type="System.Net.FileWebRequestCreator"  
      />  
    </webRequestModules>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="88613-138">Vea también</span><span class="sxs-lookup"><span data-stu-id="88613-138">See also</span></span>

- [<span data-ttu-id="88613-139">Esquema de la configuración de red</span><span class="sxs-lookup"><span data-stu-id="88613-139">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
