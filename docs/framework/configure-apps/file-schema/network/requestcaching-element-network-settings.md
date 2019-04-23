---
title: Elemento <requestCaching> (configuración de red)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#requestCaching
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/requestCaching
helpviewer_keywords:
- requestCaching element
- <requestCaching> element
ms.assetid: 9962a2fe-cbda-41a6-9377-571811eaea84
ms.openlocfilehash: af290e4b9258a08425a15e297ff538502edea916
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59164858"
---
# <a name="requestcaching-element-network-settings"></a><span data-ttu-id="5acb7-102">\<requestCaching > elemento (configuración de red)</span><span class="sxs-lookup"><span data-stu-id="5acb7-102">\<requestCaching> Element (Network Settings)</span></span>
<span data-ttu-id="5acb7-103">Controla el mecanismo de almacenamiento en caché para las solicitudes de red.</span><span class="sxs-lookup"><span data-stu-id="5acb7-103">Controls the caching mechanism for network requests.</span></span>  
  
 <span data-ttu-id="5acb7-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="5acb7-104">\<configuration></span></span>  
<span data-ttu-id="5acb7-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="5acb7-105">\<system.net></span></span>  
<span data-ttu-id="5acb7-106">\<requestCaching></span><span class="sxs-lookup"><span data-stu-id="5acb7-106">\<requestCaching></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5acb7-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5acb7-107">Syntax</span></span>  
  
```xml  
<requestCaching  
  isPrivateCache ="true|false"  
  disableAllCaching="true|false"  
  defaultPolicyLevel="BypassCache|Default|CacheOnly|CacheIfAvailable|Revalidate|Reload|NoCacheNoStore|Revalidate"  
  unspecifiedMaximumAge= "d.hh.mm.ss">  
    <defaultHttpCachePolicy>...</defaultHttpCachePolicy>  
    <defaultFtpCachePolicy>...</defaultFtpCachePolicy>  
</requestCaching>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5acb7-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="5acb7-108">Attributes and Elements</span></span>  
 <span data-ttu-id="5acb7-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="5acb7-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5acb7-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="5acb7-110">Attributes</span></span>  
  
|<span data-ttu-id="5acb7-111">Atributo</span><span class="sxs-lookup"><span data-stu-id="5acb7-111">Attribute</span></span>|<span data-ttu-id="5acb7-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="5acb7-112">Description</span></span>|  
|---------------|-----------------|  
|`isPrivateCache`|<span data-ttu-id="5acb7-113">Especifica si la memoria caché proporciona aislamiento entre la información de usuarios diferentes.</span><span class="sxs-lookup"><span data-stu-id="5acb7-113">Specifies whether the cache provides isolation between the information of different users.</span></span> <span data-ttu-id="5acb7-114">El valor predeterminado es `true`.</span><span class="sxs-lookup"><span data-stu-id="5acb7-114">The default value is `true`.</span></span> <span data-ttu-id="5acb7-115">Este valor debe ser `false` para aplicaciones de nivel intermedio.</span><span class="sxs-lookup"><span data-stu-id="5acb7-115">This value should be `false` for middle tier applications.</span></span>|  
|`disableAllCaching`|<span data-ttu-id="5acb7-116">Especifica que la opción de almacenamiento en caché está deshabilitada para todas las respuestas de Web y no se puede invalidar mediante programación.</span><span class="sxs-lookup"><span data-stu-id="5acb7-116">Specifies that caching is disabled for all Web responses, and cannot be overridden programmatically.</span></span>|  
|`defaultPolicyLevel`|<span data-ttu-id="5acb7-117">Uno de los valores de la enumeración <xref:System.Net.Cache.RequestCacheLevel>.</span><span class="sxs-lookup"><span data-stu-id="5acb7-117">One of the values in the <xref:System.Net.Cache.RequestCacheLevel> enumeration.</span></span> <span data-ttu-id="5acb7-118">El valor predeterminado es `BypassCache`.</span><span class="sxs-lookup"><span data-stu-id="5acb7-118">The default value is `BypassCache`.</span></span>|  
|`unspecifiedMaximumAge`|<span data-ttu-id="5acb7-119">Especifica el tiempo predeterminado después del cual el contenido se marca como caducada.</span><span class="sxs-lookup"><span data-stu-id="5acb7-119">Specifies the default time after which content is marked as expired.</span></span>|  
  
## <a name="policylevel-attribute"></a><span data-ttu-id="5acb7-120">Atributo policyLevel</span><span class="sxs-lookup"><span data-stu-id="5acb7-120">policyLevel Attribute</span></span>  
  
|<span data-ttu-id="5acb7-121">Valor</span><span class="sxs-lookup"><span data-stu-id="5acb7-121">Value</span></span>|<span data-ttu-id="5acb7-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="5acb7-122">Description</span></span>|  
|-----------|-----------------|  
|`Default`|<span data-ttu-id="5acb7-123">Devuelve el recurso almacenado en caché si el recurso está actualizado, la longitud del contenido es precisa y están presentes los atributos de la longitud del contenido, modificación y caducidad.</span><span class="sxs-lookup"><span data-stu-id="5acb7-123">Returns the cached resource if the resource is fresh, the content length is accurate, and the expiration, modification, and content length attributes are present.</span></span>|  
|`BypassCache`|<span data-ttu-id="5acb7-124">Devuelve el recurso desde el servidor.</span><span class="sxs-lookup"><span data-stu-id="5acb7-124">Returns the resource from the server.</span></span>|  
|`CacheOnly`|<span data-ttu-id="5acb7-125">Devuelve el recurso almacenado en caché si la longitud del contenido está presente y coincide con el tamaño de entrada.</span><span class="sxs-lookup"><span data-stu-id="5acb7-125">Returns the cached resource if the content length is present and matches the entry size.</span></span>|  
|`CacheIfAvailable`|<span data-ttu-id="5acb7-126">Devuelve el recurso almacenado en caché si la longitud del contenido se proporciona y coincide con el tamaño de la entrada; en caso contrario, el recurso se descarga desde el servidor y se devuelve al llamador.</span><span class="sxs-lookup"><span data-stu-id="5acb7-126">Returns the cached resource if the content length is provided and matches the entry size; otherwise, the resource is downloaded from the server and is returned to the caller.</span></span>|  
|`Revalidate`|<span data-ttu-id="5acb7-127">Devuelve el recurso almacenado en caché si la marca de tiempo del recurso almacenado en caché es igual que la marca de tiempo del recurso en el servidor. en caso contrario, el recurso se descarga desde el servidor, almacenado en la memoria caché y se devuelve al llamador.</span><span class="sxs-lookup"><span data-stu-id="5acb7-127">Returns the cached resource if the timestamp of the cached resource is the same as the timestamp of the resource on the server; otherwise, the resource is downloaded from the server, stored in the cache, and is returned to the caller.</span></span>|  
|`Reload`|<span data-ttu-id="5acb7-128">Descarga el recurso desde el servidor, lo almacena en la memoria caché y devuelve el recurso al llamador.</span><span class="sxs-lookup"><span data-stu-id="5acb7-128">Downloads the resource from the server, stores it in the cache, and returns the resource to the caller.</span></span>|  
|`NoCacheNoStore`|<span data-ttu-id="5acb7-129">Si existe un recurso almacenado en caché, se elimina.</span><span class="sxs-lookup"><span data-stu-id="5acb7-129">If a cached resource exists, it is deleted.</span></span> <span data-ttu-id="5acb7-130">El recurso se descarga desde el servidor y se devuelve al llamador.</span><span class="sxs-lookup"><span data-stu-id="5acb7-130">The resource is downloaded from the server and is returned to the caller.</span></span>|  
|`Revalidate`|<span data-ttu-id="5acb7-131">Atiende una solicitud mediante el uso de la copia en caché del recurso si la marca de tiempo es igual que la marca de tiempo del recurso en el servidor. en caso contrario, el recurso se descarga desde el servidor, se presenta al llamador y se almacena en la memoria caché,</span><span class="sxs-lookup"><span data-stu-id="5acb7-131">Satisfies a request by using the cached copy of the resource if the timestamp is the same as the timestamp of the resource on the server; otherwise, the resource is downloaded from the server, presented to the caller, and is stored in the cache,</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5acb7-132">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="5acb7-132">Child Elements</span></span>  
  
|<span data-ttu-id="5acb7-133">Elemento</span><span class="sxs-lookup"><span data-stu-id="5acb7-133">Element</span></span>|<span data-ttu-id="5acb7-134">Descripción</span><span class="sxs-lookup"><span data-stu-id="5acb7-134">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5acb7-135">defaultHttpCachePolicy</span><span class="sxs-lookup"><span data-stu-id="5acb7-135">defaultHttpCachePolicy</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/defaulthttpcachepolicy-element-network-settings.md)|<span data-ttu-id="5acb7-136">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="5acb7-136">Optional element.</span></span><br /><br /> <span data-ttu-id="5acb7-137">Describe si el almacenamiento en caché de HTTP está activo y describe la directiva de caché de predeterminada.</span><span class="sxs-lookup"><span data-stu-id="5acb7-137">Describes whether HTTP caching is active and describes the default caching policy.</span></span>|  
|[<span data-ttu-id="5acb7-138">\<defaultFtpCachePolicy > elemento (configuración de red)</span><span class="sxs-lookup"><span data-stu-id="5acb7-138">\<defaultFtpCachePolicy> Element (Network Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/defaultftpcachepolicy-element-network-settings.md)|<span data-ttu-id="5acb7-139">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="5acb7-139">Optional element.</span></span><br /><br /> <span data-ttu-id="5acb7-140">Describe si el almacenamiento en caché de FTP está activo y describe la directiva de caché de predeterminada.</span><span class="sxs-lookup"><span data-stu-id="5acb7-140">Describes whether FTP caching is active and describes the default caching policy.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="5acb7-141">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="5acb7-141">Parent Elements</span></span>  
  
|<span data-ttu-id="5acb7-142">Elemento</span><span class="sxs-lookup"><span data-stu-id="5acb7-142">Element</span></span>|<span data-ttu-id="5acb7-143">Descripción</span><span class="sxs-lookup"><span data-stu-id="5acb7-143">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5acb7-144">system.net</span><span class="sxs-lookup"><span data-stu-id="5acb7-144">system.net</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/system-net-element-network-settings.md)|<span data-ttu-id="5acb7-145">Contiene valores que especifican cómo se conecta .NET Framework a la red.</span><span class="sxs-lookup"><span data-stu-id="5acb7-145">Contains settings that specify how the .NET Framework connects to the network.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="5acb7-146">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="5acb7-146">Example</span></span>  
 <span data-ttu-id="5acb7-147">El ejemplo siguiente muestra cómo deshabilitar todo almacenamiento en caché.</span><span class="sxs-lookup"><span data-stu-id="5acb7-147">The following example shows how to disable all caching.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <requestCaching  
      disableAllCaching="true"  
    />  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="5acb7-148">Vea también</span><span class="sxs-lookup"><span data-stu-id="5acb7-148">See also</span></span>

- <xref:System.Net.Cache?displayProperty=nameWithType>
- [<span data-ttu-id="5acb7-149">Esquema de la configuración de red</span><span class="sxs-lookup"><span data-stu-id="5acb7-149">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
