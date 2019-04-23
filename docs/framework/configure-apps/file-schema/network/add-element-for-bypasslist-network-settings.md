---
title: Elemento <add> para bypasslist (configuración de red)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/defaultProxy/bypasslist/add
- http://schemas.microsoft.com/.NetConfiguration/v2.0#add
helpviewer_keywords:
- <bypasslist>, add element
- bypasslist, add element
- <add> element, bypasslist
- add element, bypasslist
ms.assetid: a0b86e28-86b4-4497-abe8-d5fd614c7926
ms.openlocfilehash: 904c8e23f7a09a975a6f3b9322ed6bc4148d9ba4
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59098291"
---
# <a name="add-element-for-bypasslist-network-settings"></a><span data-ttu-id="3f528-102">\<Agregar > elemento para bypasslist (configuración de red)</span><span class="sxs-lookup"><span data-stu-id="3f528-102">\<add> Element for bypasslist (Network Settings)</span></span>
<span data-ttu-id="3f528-103">Agrega una dirección IP o nombre DNS a la lista de omisión de proxy.</span><span class="sxs-lookup"><span data-stu-id="3f528-103">Adds an IP address or DNS name to the proxy bypass list.</span></span>  
  
 <span data-ttu-id="3f528-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="3f528-104">\<configuration></span></span>  
<span data-ttu-id="3f528-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="3f528-105">\<system.net></span></span>  
<span data-ttu-id="3f528-106">\<defaultProxy></span><span class="sxs-lookup"><span data-stu-id="3f528-106">\<defaultProxy></span></span>  
<span data-ttu-id="3f528-107">\<bypasslist></span><span class="sxs-lookup"><span data-stu-id="3f528-107">\<bypasslist></span></span>  
<span data-ttu-id="3f528-108">\<add></span><span class="sxs-lookup"><span data-stu-id="3f528-108">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3f528-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3f528-109">Syntax</span></span>  
  
```xml  
<add   
  address="regular expression"   
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3f528-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="3f528-110">Attributes and Elements</span></span>  
 <span data-ttu-id="3f528-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="3f528-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3f528-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="3f528-112">Attributes</span></span>  
  
|<span data-ttu-id="3f528-113">**Attribute**</span><span class="sxs-lookup"><span data-stu-id="3f528-113">**Attribute**</span></span>|<span data-ttu-id="3f528-114">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="3f528-114">**Description**</span></span>|  
|-------------------|---------------------|  
|<span data-ttu-id="3f528-115">**address**</span><span class="sxs-lookup"><span data-stu-id="3f528-115">**address**</span></span>|<span data-ttu-id="3f528-116">Una expresión regular que describe una dirección IP o nombre DNS.</span><span class="sxs-lookup"><span data-stu-id="3f528-116">A regular expression describing an IP address or DNS name.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3f528-117">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="3f528-117">Child Elements</span></span>  
 <span data-ttu-id="3f528-118">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="3f528-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="3f528-119">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="3f528-119">Parent Elements</span></span>  
  
|<span data-ttu-id="3f528-120">**Element**</span><span class="sxs-lookup"><span data-stu-id="3f528-120">**Element**</span></span>|<span data-ttu-id="3f528-121">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="3f528-121">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="3f528-122">bypasslist</span><span class="sxs-lookup"><span data-stu-id="3f528-122">bypasslist</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/bypasslist-element-network-settings.md)|<span data-ttu-id="3f528-123">Proporciona un conjunto de expresiones regulares que describen direcciones que no se usa a un proxy.</span><span class="sxs-lookup"><span data-stu-id="3f528-123">Provides a set of regular expressions that describe addresses that do not use a proxy.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3f528-124">Comentarios</span><span class="sxs-lookup"><span data-stu-id="3f528-124">Remarks</span></span>  
 <span data-ttu-id="3f528-125">El `add` elemento inserta expresiones regulares que describen direcciones IP o nombres de los servidores DNS a la lista de direcciones que omitir un servidor proxy.</span><span class="sxs-lookup"><span data-stu-id="3f528-125">The `add` element inserts regular expressions describing IP addresses or DNS server names to the list of addresses that bypass a proxy server.</span></span>  
  
 <span data-ttu-id="3f528-126">El valor de la `address` atributo debe ser una expresión regular que describe un conjunto de direcciones IP o nombres de host.</span><span class="sxs-lookup"><span data-stu-id="3f528-126">The value of the `address` attribute should be a regular expression that describes a set of IP addresses or host names.</span></span>  
  
 <span data-ttu-id="3f528-127">Se debe tener cuidado al especificar una expresión regular para este elemento.</span><span class="sxs-lookup"><span data-stu-id="3f528-127">You should use caution when specifying a regular expression for this element.</span></span> <span data-ttu-id="3f528-128">La expresión regular "[a-z] +\\.contoso\\.com" coincide con cualquier host en el dominio contoso.com, pero también coincide con cualquier host del dominio contoso.com.cpandl.com.</span><span class="sxs-lookup"><span data-stu-id="3f528-128">The regular expression "[a-z]+\\.contoso\\.com" matches any host in the contoso.com domain, but it also matches any host in the contoso.com.cpandl.com domain.</span></span> <span data-ttu-id="3f528-129">Para que coincida con un host en el dominio contoso.com, use un delimitador ("$"): "[a-z] +\\.contoso\\.com$".</span><span class="sxs-lookup"><span data-stu-id="3f528-129">To match only a host in the contoso.com domain, use an anchor ("$"): "[a-z]+\\.contoso\\.com$".</span></span>  
  
 <span data-ttu-id="3f528-130">Para obtener más información sobre las expresiones regulares, vea. [Expresiones regulares de .NET framework](../../../../../docs/standard/base-types/regular-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="3f528-130">For more information about regular expressions, see .[.NET Framework Regular Expressions](../../../../../docs/standard/base-types/regular-expressions.md).</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="3f528-131">Archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="3f528-131">Configuration Files</span></span>  
 <span data-ttu-id="3f528-132">Este elemento se puede usar en el archivo de configuración de la aplicación o en el archivo de configuración del equipo (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="3f528-132">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="3f528-133">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="3f528-133">Example</span></span>  
 <span data-ttu-id="3f528-134">El ejemplo siguiente agrega dos direcciones a la lista de omisión.</span><span class="sxs-lookup"><span data-stu-id="3f528-134">The following example adds two addresses to the bypass list.</span></span> <span data-ttu-id="3f528-135">La primera omite al proxy para todos los servidores en el dominio contoso.com; la segunda omite al proxy para todos los servidores cuya dirección IP comienza con 192.168.</span><span class="sxs-lookup"><span data-stu-id="3f528-135">The first bypasses the proxy for all servers in the contoso.com domain; the second bypasses the proxy for all servers whose IP address begins with 192.168.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="3f528-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="3f528-136">See also</span></span>

- <xref:System.Net.WebProxy?displayProperty=nameWithType>
- [<span data-ttu-id="3f528-137">Esquema de la configuración de red</span><span class="sxs-lookup"><span data-stu-id="3f528-137">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
