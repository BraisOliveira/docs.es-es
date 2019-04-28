---
title: Elemento <proxy> (configuración de red)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/defaultProxy/proxy
- http://schemas.microsoft.com/.NetConfiguration/v2.0#proxy
helpviewer_keywords:
- <proxy> element
- proxy element
ms.assetid: 37a548d8-fade-4ac5-82ec-b49b6c6cb22a
ms.openlocfilehash: 8df9bbf2615776c2e023f03401785da95b2226eb
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61674504"
---
# <a name="proxy-element-network-settings"></a><span data-ttu-id="c88e9-102">\<proxy > elemento (configuración de red)</span><span class="sxs-lookup"><span data-stu-id="c88e9-102">\<proxy> Element (Network Settings)</span></span>
<span data-ttu-id="c88e9-103">Define un servidor proxy.</span><span class="sxs-lookup"><span data-stu-id="c88e9-103">Defines a proxy server.</span></span>  
  
 <span data-ttu-id="c88e9-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="c88e9-104">\<configuration></span></span>  
<span data-ttu-id="c88e9-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="c88e9-105">\<system.net></span></span>  
<span data-ttu-id="c88e9-106">\<defaultProxy></span><span class="sxs-lookup"><span data-stu-id="c88e9-106">\<defaultProxy></span></span>  
<span data-ttu-id="c88e9-107">\<proxy></span><span class="sxs-lookup"><span data-stu-id="c88e9-107">\<proxy></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c88e9-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c88e9-108">Syntax</span></span>  
  
```xml  
<proxy
  autoDetect="true|false|unspecified" 
  bypassonlocal="true|false|unspecified"
  proxyaddress="uriString"
  scriptLocation="uriString"
  usesystemdefault="true|false|unspecified"
/>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c88e9-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="c88e9-109">Attributes and Elements</span></span>  
 <span data-ttu-id="c88e9-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="c88e9-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c88e9-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="c88e9-111">Attributes</span></span>  
  
|<span data-ttu-id="c88e9-112">**Attribute**</span><span class="sxs-lookup"><span data-stu-id="c88e9-112">**Attribute**</span></span>|<span data-ttu-id="c88e9-113">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="c88e9-113">**Description**</span></span>|  
|-------------------|---------------------|  
|`autoDetect`|<span data-ttu-id="c88e9-114">Especifica si el proxy se detecta automáticamente.</span><span class="sxs-lookup"><span data-stu-id="c88e9-114">Specifies whether the proxy is automatically detected.</span></span> <span data-ttu-id="c88e9-115">El valor predeterminado es `unspecified`.</span><span class="sxs-lookup"><span data-stu-id="c88e9-115">The default value is `unspecified`.</span></span>|  
|`bypassonlocal`|<span data-ttu-id="c88e9-116">Especifica si se omite el proxy para los recursos locales.</span><span class="sxs-lookup"><span data-stu-id="c88e9-116">Specifies whether the proxy is bypassed for local resources.</span></span> <span data-ttu-id="c88e9-117">Los recursos locales incluyen el servidor local (`http://localhost`, `http://loopback`, o `http://127.0.0.1`) y un URI sin un punto (`http://webserver`).</span><span class="sxs-lookup"><span data-stu-id="c88e9-117">Local resources include the local server (`http://localhost`, `http://loopback`, or `http://127.0.0.1`) and a URI without a period (`http://webserver`).</span></span> <span data-ttu-id="c88e9-118">El valor predeterminado es `unspecified`.</span><span class="sxs-lookup"><span data-stu-id="c88e9-118">The default value is `unspecified`.</span></span>|  
|`proxyaddress`|<span data-ttu-id="c88e9-119">Especifica al proxy de URI que se utiliza.</span><span class="sxs-lookup"><span data-stu-id="c88e9-119">Specifies the proxy URI to use.</span></span>|  
|`scriptLocation`|<span data-ttu-id="c88e9-120">Especifica la ubicación del script de configuración.</span><span class="sxs-lookup"><span data-stu-id="c88e9-120">Specifies the location of the configuration script.</span></span> <span data-ttu-id="c88e9-121">No utilice el `bypassonlocal` atributo con este atributo.</span><span class="sxs-lookup"><span data-stu-id="c88e9-121">Do not use the `bypassonlocal` attribute with this attribute.</span></span> |  
|`usesystemdefault`|<span data-ttu-id="c88e9-122">Especifica si se debe usar la configuración de proxy de Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="c88e9-122">Specifies whether to use Internet Explorer proxy settings.</span></span> <span data-ttu-id="c88e9-123">Si establece en `true`, atributos subsiguientes invalidarán la configuración de proxy de Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="c88e9-123">If set to `true`, subsequent attributes will override Internet Explorer proxy settings.</span></span> <span data-ttu-id="c88e9-124">El valor predeterminado es `unspecified`.</span><span class="sxs-lookup"><span data-stu-id="c88e9-124">The default value is `unspecified`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c88e9-125">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="c88e9-125">Child Elements</span></span>  
 <span data-ttu-id="c88e9-126">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="c88e9-126">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c88e9-127">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="c88e9-127">Parent Elements</span></span>  
  
|<span data-ttu-id="c88e9-128">**Element**</span><span class="sxs-lookup"><span data-stu-id="c88e9-128">**Element**</span></span>|<span data-ttu-id="c88e9-129">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="c88e9-129">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="c88e9-130">defaultProxy</span><span class="sxs-lookup"><span data-stu-id="c88e9-130">defaultProxy</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/defaultproxy-element-network-settings.md)|<span data-ttu-id="c88e9-131">Configura el servidor proxy de Protocolo de transferencia de hipertexto (HTTP).</span><span class="sxs-lookup"><span data-stu-id="c88e9-131">Configures the Hypertext Transfer Protocol (HTTP) proxy server.</span></span>|  
  
## <a name="text-value"></a><span data-ttu-id="c88e9-132">Valor de texto</span><span class="sxs-lookup"><span data-stu-id="c88e9-132">Text Value</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c88e9-133">Comentarios</span><span class="sxs-lookup"><span data-stu-id="c88e9-133">Remarks</span></span>  
 <span data-ttu-id="c88e9-134">El `proxy` elemento define un servidor proxy para una aplicación.</span><span class="sxs-lookup"><span data-stu-id="c88e9-134">The `proxy` element defines a proxy server for an application.</span></span> <span data-ttu-id="c88e9-135">Si este elemento no aparece en el archivo de configuración, .NET Framework usará la configuración de proxy en Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="c88e9-135">If this element is missing from the configuration file, then the .NET Framework will use the proxy settings in Internet Explorer.</span></span>  
  
 <span data-ttu-id="c88e9-136">El valor de la `proxyaddress` atributo debe ser un indicador de recursos uniforme (URI) tiene el formato correcto.</span><span class="sxs-lookup"><span data-stu-id="c88e9-136">The value for the `proxyaddress` attribute should be a well-formed Uniform Resource Indicator (URI).</span></span>  
  
 <span data-ttu-id="c88e9-137">El `scriptLocation` atributo hace referencia a la detección automática de scripts de configuración de proxy.</span><span class="sxs-lookup"><span data-stu-id="c88e9-137">The `scriptLocation` attribute refers to the automatic detection of proxy configuration scripts.</span></span> <span data-ttu-id="c88e9-138">El <xref:System.Net.WebProxy> clase intentará encontrar un script de configuración (normalmente con nombre Wpad.dat) cuando el **usar scripts de configuración automática** está seleccionada en el Explorador de Internet.</span><span class="sxs-lookup"><span data-stu-id="c88e9-138">The <xref:System.Net.WebProxy> class will attempt to locate a configuration script (usually named Wpad.dat) when the **Use automatic configuration script** option is selected in Internet Explorer.</span></span> <span data-ttu-id="c88e9-139">Si `bypassonlocal` se establece en cualquier valor, `scriptLocation` se omite.</span><span class="sxs-lookup"><span data-stu-id="c88e9-139">If `bypassonlocal` is set to any value, `scriptLocation` is ignored.</span></span>
  
 <span data-ttu-id="c88e9-140">Use el `usesystemdefault` atributo para las aplicaciones de la versión 1.1 de .NET Framework que se va a migrar a la versión 2.0.</span><span class="sxs-lookup"><span data-stu-id="c88e9-140">Use the `usesystemdefault` attribute for .NET Framework version 1.1 applications that are migrating to version 2.0.</span></span>  
  
 <span data-ttu-id="c88e9-141">Se produce una excepción si el `proxyaddress` atributo especifica un proxy predeterminado no válido.</span><span class="sxs-lookup"><span data-stu-id="c88e9-141">An exception is thrown if the `proxyaddress` attribute specifies an invalid default proxy.</span></span> <span data-ttu-id="c88e9-142">La propiedad <xref:System.Exception.InnerException%2A> en la excepción debería tener más información acerca de la causa principal del error.</span><span class="sxs-lookup"><span data-stu-id="c88e9-142">The <xref:System.Exception.InnerException%2A> property on the exception should have more information about the root cause of the error.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="c88e9-143">Archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="c88e9-143">Configuration Files</span></span>  
 <span data-ttu-id="c88e9-144">Este elemento se puede usar en el archivo de configuración de la aplicación o en el archivo de configuración del equipo (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="c88e9-144">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="c88e9-145">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c88e9-145">Example</span></span>  
 <span data-ttu-id="c88e9-146">El ejemplo siguiente utiliza los valores predeterminados desde el proxy de Internet Explorer, especifica la dirección del proxy y omite al proxy para el acceso local.</span><span class="sxs-lookup"><span data-stu-id="c88e9-146">The following example uses the defaults from the Internet Explorer proxy, specifies the proxy address, and bypasses the proxy for local access.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <defaultProxy>  
      <proxy  
        usesystemdefault="true"  
        proxyaddress="http://192.168.1.10:3128"  
        bypassonlocal="true"  
      />  
    </defaultProxy>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="c88e9-147">Vea también</span><span class="sxs-lookup"><span data-stu-id="c88e9-147">See also</span></span>

- <xref:System.Net.WebProxy?displayProperty=nameWithType>
- [<span data-ttu-id="c88e9-148">Esquema de la configuración de red</span><span class="sxs-lookup"><span data-stu-id="c88e9-148">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
