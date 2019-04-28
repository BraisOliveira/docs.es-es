---
title: Elemento <bypasslist> (configuración de red)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#bypasslist
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/defaultProxy/bypasslist
helpviewer_keywords:
- bypasslist element
- <bypasslist> element
ms.assetid: 124446b7-abb1-4e5e-a492-b64398f268f1
ms.openlocfilehash: d3d986dae478f49504dae21b9f39574b7887b4d2
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61674628"
---
# <a name="bypasslist-element-network-settings"></a><span data-ttu-id="7e450-102">\<bypasslist > elemento (configuración de red)</span><span class="sxs-lookup"><span data-stu-id="7e450-102">\<bypasslist> Element (Network Settings)</span></span>
<span data-ttu-id="7e450-103">Proporciona un conjunto de expresiones regulares que describen direcciones que no se usa a un proxy.</span><span class="sxs-lookup"><span data-stu-id="7e450-103">Provides a set of regular expressions that describe addresses that do not use a proxy.</span></span>  
  
 <span data-ttu-id="7e450-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="7e450-104">\<configuration></span></span>  
<span data-ttu-id="7e450-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="7e450-105">\<system.net></span></span>  
<span data-ttu-id="7e450-106">\<defaultProxy></span><span class="sxs-lookup"><span data-stu-id="7e450-106">\<defaultProxy></span></span>  
<span data-ttu-id="7e450-107">\<bypasslist></span><span class="sxs-lookup"><span data-stu-id="7e450-107">\<bypasslist></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7e450-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7e450-108">Syntax</span></span>  
  
```xml  
<bypasslist>   
</bypasslist>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7e450-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="7e450-109">Attributes and Elements</span></span>  
 <span data-ttu-id="7e450-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="7e450-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7e450-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="7e450-111">Attributes</span></span>  
 <span data-ttu-id="7e450-112">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="7e450-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="7e450-113">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="7e450-113">Child Elements</span></span>  
  
|<span data-ttu-id="7e450-114">**Element**</span><span class="sxs-lookup"><span data-stu-id="7e450-114">**Element**</span></span>|<span data-ttu-id="7e450-115">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="7e450-115">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="7e450-116">add</span><span class="sxs-lookup"><span data-stu-id="7e450-116">add</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/add-element-for-bypasslist-network-settings.md)|<span data-ttu-id="7e450-117">Agrega una dirección IP o nombre DNS a la lista de omisión de proxy.</span><span class="sxs-lookup"><span data-stu-id="7e450-117">Adds an IP address or DNS name to the proxy bypass list.</span></span>|  
|[<span data-ttu-id="7e450-118">clear</span><span class="sxs-lookup"><span data-stu-id="7e450-118">clear</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/clear-element-for-bypasslist-network-settings.md)|<span data-ttu-id="7e450-119">Borra la lista de omisión.</span><span class="sxs-lookup"><span data-stu-id="7e450-119">Clears the bypass list.</span></span>|  
|[<span data-ttu-id="7e450-120">remove</span><span class="sxs-lookup"><span data-stu-id="7e450-120">remove</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/remove-element-for-bypasslist-network-settings.md)|<span data-ttu-id="7e450-121">Quita una dirección IP o nombre DNS de la lista de omisión de proxy.</span><span class="sxs-lookup"><span data-stu-id="7e450-121">Removes an IP address or DNS name from the proxy bypass list.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="7e450-122">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="7e450-122">Parent Elements</span></span>  
  
|<span data-ttu-id="7e450-123">**Element**</span><span class="sxs-lookup"><span data-stu-id="7e450-123">**Element**</span></span>|<span data-ttu-id="7e450-124">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="7e450-124">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="7e450-125">defaultProxy</span><span class="sxs-lookup"><span data-stu-id="7e450-125">defaultProxy</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/defaultproxy-element-network-settings.md)|<span data-ttu-id="7e450-126">Configura el servidor proxy de Protocolo de transferencia de hipertexto (HTTP).</span><span class="sxs-lookup"><span data-stu-id="7e450-126">Configures the Hypertext Transfer Protocol (HTTP) proxy server.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7e450-127">Comentarios</span><span class="sxs-lookup"><span data-stu-id="7e450-127">Remarks</span></span>  
 <span data-ttu-id="7e450-128">La lista de omisión contiene expresiones regulares que describen las direcciones URI que <xref:System.Net.WebRequest> instancias directamente en lugar de tener acceso a través del servidor proxy.</span><span class="sxs-lookup"><span data-stu-id="7e450-128">The bypass list contains regular expressions that describe URIs that <xref:System.Net.WebRequest> instances access directly instead of through the proxy server.</span></span>  
  
 <span data-ttu-id="7e450-129">Se debe tener cuidado al especificar una expresión regular para este elemento.</span><span class="sxs-lookup"><span data-stu-id="7e450-129">You should use caution when specifying a regular expression for this element.</span></span> <span data-ttu-id="7e450-130">La expresión regular "[a-z] +\\.contoso\\.com" coincide con cualquier host en el dominio contoso.com, pero también coincide con cualquier host del dominio contoso.com.cpandl.com.</span><span class="sxs-lookup"><span data-stu-id="7e450-130">The regular expression "[a-z]+\\.contoso\\.com" matches any host in the contoso.com domain, but it also matches any host in the contoso.com.cpandl.com domain.</span></span> <span data-ttu-id="7e450-131">Para que coincida con un host en el dominio contoso.com, use un delimitador ("$"): "[a-z] +\\.contoso\\.com$".</span><span class="sxs-lookup"><span data-stu-id="7e450-131">To match only a host in the contoso.com domain, use an anchor ("$"): "[a-z]+\\.contoso\\.com$".</span></span>  
  
 <span data-ttu-id="7e450-132">Para obtener más información sobre las expresiones regulares, vea. [Expresiones regulares de .NET framework](../../../../../docs/standard/base-types/regular-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="7e450-132">For more information about regular expressions, see .[.NET Framework Regular Expressions](../../../../../docs/standard/base-types/regular-expressions.md).</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="7e450-133">Archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="7e450-133">Configuration Files</span></span>  
 <span data-ttu-id="7e450-134">Este elemento se puede usar en el archivo de configuración de la aplicación o en el archivo de configuración del equipo (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="7e450-134">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="7e450-135">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="7e450-135">Example</span></span>  
 <span data-ttu-id="7e450-136">El ejemplo siguiente agrega dos direcciones a la lista de omisión.</span><span class="sxs-lookup"><span data-stu-id="7e450-136">The following example adds two addresses to the bypass list.</span></span> <span data-ttu-id="7e450-137">La primera omite al proxy para todos los servidores en el dominio contoso.com; la segunda omite al proxy para todos los servidores cuyas direcciones IP comienzan con 192.168.</span><span class="sxs-lookup"><span data-stu-id="7e450-137">The first bypasses the proxy for all servers in the contoso.com domain; the second bypasses the proxy for all servers whose IP addresses begin with 192.168.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <defaultProxy>  
      <bypasslist>  
        <add address="[a-z]+\.contoso\.com$" />  
        <add address="192\.168\.\d{1,3}\.\d{1,3}" />  
      </bypasslist>  
    </defaultProxy>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="7e450-138">Vea también</span><span class="sxs-lookup"><span data-stu-id="7e450-138">See also</span></span>

- <xref:System.Net.WebProxy?displayProperty=nameWithType>
- [<span data-ttu-id="7e450-139">Esquema de la configuración de red</span><span class="sxs-lookup"><span data-stu-id="7e450-139">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
