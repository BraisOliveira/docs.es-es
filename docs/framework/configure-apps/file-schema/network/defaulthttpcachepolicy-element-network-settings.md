---
title: <defaultHttpCachePolicy> Elemento (configuración de red)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/requestCaching/defaultHttpCachePolicy
- http://schemas.microsoft.com/.NetConfiguration/v2.0#defaultHttpCachePolicy
helpviewer_keywords:
- defaultHttpCachePolicy element
- <defaultHttpCachePolicy> element
ms.assetid: 2c1247d0-39b0-4c12-919a-a925ce075c79
ms.openlocfilehash: 20d9b92ca2bbffd6b98b8641e5cef5e567cb84cc
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59177389"
---
# <a name="defaulthttpcachepolicy-element-network-settings"></a><span data-ttu-id="e7a12-102">\<defaultHttpCachePolicy > elemento (configuración de red)</span><span class="sxs-lookup"><span data-stu-id="e7a12-102">\<defaultHttpCachePolicy> Element (Network Settings)</span></span>
<span data-ttu-id="e7a12-103">Describe si el almacenamiento en caché de HTTP está activo y describe la directiva de caché de predeterminada.</span><span class="sxs-lookup"><span data-stu-id="e7a12-103">Describes whether HTTP caching is active and describes the default caching policy.</span></span>  
  
 <span data-ttu-id="e7a12-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="e7a12-104">\<configuration></span></span>  
<span data-ttu-id="e7a12-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="e7a12-105">\<system.net></span></span>  
<span data-ttu-id="e7a12-106">\<requestCaching></span><span class="sxs-lookup"><span data-stu-id="e7a12-106">\<requestCaching></span></span>  
<span data-ttu-id="e7a12-107">\<defaultHttpCachePolicy></span><span class="sxs-lookup"><span data-stu-id="e7a12-107">\<defaultHttpCachePolicy></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e7a12-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e7a12-108">Syntax</span></span>  
  
```xml  
<defaultHttpCachePolicy  
  policyLevel="BypassCache|Default"  
  minimumFresh="d.hh:mm:ss|minValue|maxValue"  
  maximumAge="d.hh:mm:ss|minValue|maxValue"  
  maximumStale="d.hh:mm:ss|minValue|maxValue"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e7a12-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="e7a12-109">Attributes and Elements</span></span>  
 <span data-ttu-id="e7a12-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="e7a12-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e7a12-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="e7a12-111">Attributes</span></span>  
  
|<span data-ttu-id="e7a12-112">Atributo</span><span class="sxs-lookup"><span data-stu-id="e7a12-112">Attribute</span></span>|<span data-ttu-id="e7a12-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="e7a12-113">Description</span></span>|  
|---------------|-----------------|  
|`maximumAge`|<span data-ttu-id="e7a12-114">Especifica el intervalo de tiempo máximo antes de que un objeto almacenado en caché se marca como caducada.</span><span class="sxs-lookup"><span data-stu-id="e7a12-114">Specifies the maximum time interval before a cached object is marked as expired.</span></span>|  
|`maximumStale`|<span data-ttu-id="e7a12-115">Especifica el tiempo máximo después de la hora de actualización calculada antes de que un objeto almacenado en caché se marca como caducada.</span><span class="sxs-lookup"><span data-stu-id="e7a12-115">Specifies the maximum time past the computed freshness time before a cached object is marked as expired.</span></span>|  
|`minimumFresh`|<span data-ttu-id="e7a12-116">Especifica el tiempo mínimo para un objeto almacenado en caché se considerará actualizado.</span><span class="sxs-lookup"><span data-stu-id="e7a12-116">Specifies the minimum time for a cached object to be considered fresh.</span></span>|  
|`policyLevel`|<span data-ttu-id="e7a12-117">Especifica si la directiva de caché es automática, o si se omite la memoria caché.</span><span class="sxs-lookup"><span data-stu-id="e7a12-117">Specifies whether the caching policy is automatic, or whether the cache is bypassed.</span></span> <span data-ttu-id="e7a12-118">El valor predeterminado es `BypassCache`.</span><span class="sxs-lookup"><span data-stu-id="e7a12-118">The default value is `BypassCache`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e7a12-119">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="e7a12-119">Child Elements</span></span>  
 <span data-ttu-id="e7a12-120">Ninguna</span><span class="sxs-lookup"><span data-stu-id="e7a12-120">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e7a12-121">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="e7a12-121">Parent Elements</span></span>  
  
|<span data-ttu-id="e7a12-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="e7a12-122">Element</span></span>|<span data-ttu-id="e7a12-123">Descripción</span><span class="sxs-lookup"><span data-stu-id="e7a12-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e7a12-124">requestCaching</span><span class="sxs-lookup"><span data-stu-id="e7a12-124">requestCaching</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/requestcaching-element-network-settings.md)|<span data-ttu-id="e7a12-125">Controla el mecanismo de almacenamiento en caché para las solicitudes de red.</span><span class="sxs-lookup"><span data-stu-id="e7a12-125">Controls the caching mechanism for network requests.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e7a12-126">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e7a12-126">Remarks</span></span>  
 <span data-ttu-id="e7a12-127">El valor de la `policyLevel` atributo sea `BypassCache` o `Default`.</span><span class="sxs-lookup"><span data-stu-id="e7a12-127">The value for the `policyLevel` attribute is either `BypassCache` or `Default`.</span></span>  
  
 <span data-ttu-id="e7a12-128">Los valores de la `maximumAge`, `maximumStale`, y `minimumFresh` elementos son intervalos de tiempo explícitos con un formato de *d.*. *hh*:*mm*:*ss* (días, horas, minutos y segundos) o las constantes `minValue` o `maxValue`, según corresponda.</span><span class="sxs-lookup"><span data-stu-id="e7a12-128">Values for the `maximumAge`, `maximumStale`, and `minimumFresh` elements are either an explicit time interval with a format of *d*.*hh*:*mm*:*ss* (days, hours, minutes, and seconds), or the constants `minValue` or `maxValue`, as appropriate.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="e7a12-129">Archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="e7a12-129">Configuration Files</span></span>  
 <span data-ttu-id="e7a12-130">Este elemento se puede usar en el archivo de configuración de la aplicación o en el archivo de configuración del equipo (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="e7a12-130">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="e7a12-131">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e7a12-131">Example</span></span>  
 <span data-ttu-id="e7a12-132">El ejemplo siguiente muestra cómo especificar un intervalo de actualización mínimo de seis horas, una hora de antigüedad máxima de dos días y un obsoleto el tiempo máximo de cuatro horas.</span><span class="sxs-lookup"><span data-stu-id="e7a12-132">The following example shows how to specify a minimum fresh time of six hours, a maximum age time of two days, and a maximum stale time of four hours.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <requestCaching>  
      <defaultHttpCachePolicy  
        minimumFresh="0.06:00:00"  
        maximumAge="2.00:00:00"  
        maximumStale="0.04:00:00"
      />  
    </requestCaching>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="e7a12-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="e7a12-133">See also</span></span>

- <xref:System.Net.Cache>
- <xref:System.Net.WebRequest>
- <xref:System.Net.Cache.RequestCacheLevel>
- [<span data-ttu-id="e7a12-134">Esquema de la configuración de red</span><span class="sxs-lookup"><span data-stu-id="e7a12-134">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
