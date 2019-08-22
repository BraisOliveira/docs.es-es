---
title: Elemento <memoryCache> (configuración de caché)
ms.date: 03/30/2017
helpviewer_keywords:
- <memoryCache> element
- caching [.NET Framework], configuration
- memoryCache element
ms.assetid: 182a622f-f7cf-472d-9d0b-451d2fd94525
ms.openlocfilehash: 46f430f7cf112da40aa3b25bfb280c5014612eae
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/21/2019
ms.locfileid: "69663616"
---
# <a name="memorycache-element-cache-settings"></a><span data-ttu-id="4f944-102">\<memoryCache > elemento (configuración de caché)</span><span class="sxs-lookup"><span data-stu-id="4f944-102">\<memoryCache> Element (Cache Settings)</span></span>
<span data-ttu-id="4f944-103">Define un elemento que se usa para configurar una memoria caché basada en la clase <xref:System.Runtime.Caching.MemoryCache> .</span><span class="sxs-lookup"><span data-stu-id="4f944-103">Defines an element that is used to configure a cache that is based on the <xref:System.Runtime.Caching.MemoryCache> class.</span></span> <span data-ttu-id="4f944-104">La clase <xref:System.Runtime.Caching.Configuration.MemoryCacheElement> define un elemento [memoryCache](memorycache-element-cache-settings.md) que se puede usar para configurar la memoria caché.</span><span class="sxs-lookup"><span data-stu-id="4f944-104">The <xref:System.Runtime.Caching.Configuration.MemoryCacheElement> class defines a [memoryCache](memorycache-element-cache-settings.md) element that you can use to configure the cache.</span></span> <span data-ttu-id="4f944-105">Se pueden usar varias instancias de la clase <xref:System.Runtime.Caching.MemoryCache> en una sola aplicación.</span><span class="sxs-lookup"><span data-stu-id="4f944-105">Multiple instances of the <xref:System.Runtime.Caching.MemoryCache> class can be used in a single application.</span></span> <span data-ttu-id="4f944-106">Cada elemento `memoryCache` del archivo de configuración puede contener valores de configuración para una instancia de <xref:System.Runtime.Caching.MemoryCache> con nombre.</span><span class="sxs-lookup"><span data-stu-id="4f944-106">Each `memoryCache` element in the configuration file can contain settings for a named <xref:System.Runtime.Caching.MemoryCache> instance.</span></span>  
  
 <span data-ttu-id="4f944-107">\<configuration></span><span class="sxs-lookup"><span data-stu-id="4f944-107">\<configuration></span></span>  
<span data-ttu-id="4f944-108">\<system.runtime.caching></span><span class="sxs-lookup"><span data-stu-id="4f944-108">\<system.runtime.caching></span></span>  
<span data-ttu-id="4f944-109">\<memoryCache></span><span class="sxs-lookup"><span data-stu-id="4f944-109">\<memoryCache></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4f944-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4f944-110">Syntax</span></span>  
  
```xml  
<memoryCache>   
    <namedCaches>  
        <!-- child elements -->  
    </namedCaches>   
</memoryCache>  
```  
  
## <a name="type"></a><span data-ttu-id="4f944-111">Type</span><span class="sxs-lookup"><span data-stu-id="4f944-111">Type</span></span>  
 <span data-ttu-id="4f944-112">Clase<xref:System.Runtime.Caching.MemoryCache> .</span><span class="sxs-lookup"><span data-stu-id="4f944-112"><xref:System.Runtime.Caching.MemoryCache> class.</span></span>  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4f944-113">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="4f944-113">Attributes and Elements</span></span>  
 <span data-ttu-id="4f944-114">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="4f944-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4f944-115">Atributos</span><span class="sxs-lookup"><span data-stu-id="4f944-115">Attributes</span></span>  
  
|<span data-ttu-id="4f944-116">Atributo</span><span class="sxs-lookup"><span data-stu-id="4f944-116">Attribute</span></span>|<span data-ttu-id="4f944-117">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="4f944-117">Description</span></span>|  
|---------------|-----------------|  
|`CacheMemoryLimitMegabytes`|<span data-ttu-id="4f944-118">Tamaño máximo de memoria (en megabytes) que puede alcanzar una instancia de un objeto <xref:System.Runtime.Caching.MemoryCache> .</span><span class="sxs-lookup"><span data-stu-id="4f944-118">The maximum memory size, in megabytes, that an instance of a <xref:System.Runtime.Caching.MemoryCache> object can grow to.</span></span> <span data-ttu-id="4f944-119">El valor predeterminado es 0, lo que significa que se usa de forma predeterminada la heurística de ajuste automático de tamaño de la clase <xref:System.Runtime.Caching.MemoryCache> .</span><span class="sxs-lookup"><span data-stu-id="4f944-119">The default value is 0, which means that the <xref:System.Runtime.Caching.MemoryCache> class's autosize heuristics are used by default.</span></span>|  
|`Name`|<span data-ttu-id="4f944-120">Nombre de la configuración de la memoria caché.</span><span class="sxs-lookup"><span data-stu-id="4f944-120">The name of the cache configuration.</span></span>|  
|`PhysicalMemoryLimitPercentage`|<span data-ttu-id="4f944-121">Porcentaje de memoria física que la memoria caché puede usar.</span><span class="sxs-lookup"><span data-stu-id="4f944-121">The percentage of physical memory that can be used by the cache.</span></span> <span data-ttu-id="4f944-122">El valor predeterminado es 0, lo que significa que se usa de forma predeterminada la heurística de ajuste automático de tamaño de la clase <xref:System.Runtime.Caching.MemoryCache> .</span><span class="sxs-lookup"><span data-stu-id="4f944-122">The default value is 0, which means that the <xref:System.Runtime.Caching.MemoryCache> class's autosize heuristics are used by default.</span></span>|  
|`PollingInterval`|<span data-ttu-id="4f944-123">Valor que indica el intervalo de tiempo después del cual la implementación de caché compara la carga de memoria actual con los límites de memoria absoluto y de porcentaje que están establecidos para la instancia de caché.</span><span class="sxs-lookup"><span data-stu-id="4f944-123">A value that indicates the time interval after which the cache implementation compares the current memory load against the absolute and percentage-based memory limits that are set for the cache instance.</span></span> <span data-ttu-id="4f944-124">El valor se especifica en formato "HH:MM:SS".</span><span class="sxs-lookup"><span data-stu-id="4f944-124">The value is entered in "HH:MM:SS" format.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4f944-125">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="4f944-125">Child Elements</span></span>  
  
|<span data-ttu-id="4f944-126">Elemento</span><span class="sxs-lookup"><span data-stu-id="4f944-126">Element</span></span>|<span data-ttu-id="4f944-127">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="4f944-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4f944-128">\<namedCaches></span><span class="sxs-lookup"><span data-stu-id="4f944-128">\<namedCaches></span></span>](namedcaches-element-cache-settings.md)|<span data-ttu-id="4f944-129">Contiene una colección de valores de configuración para la instancia de `namedCache` .</span><span class="sxs-lookup"><span data-stu-id="4f944-129">Contains a collection of configuration settings for the `namedCache` instance.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="4f944-130">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="4f944-130">Parent Elements</span></span>  
  
|<span data-ttu-id="4f944-131">Elemento</span><span class="sxs-lookup"><span data-stu-id="4f944-131">Element</span></span>|<span data-ttu-id="4f944-132">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="4f944-132">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4f944-133">\<system.runtime.caching></span><span class="sxs-lookup"><span data-stu-id="4f944-133">\<system.runtime.caching></span></span>](system-runtime-caching-element-cache-settings.md)|<span data-ttu-id="4f944-134">Contiene tipos que permiten implementar el almacenamiento en caché de resultados en las aplicaciones integradas en el .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="4f944-134">Contains types that let you implement output caching in applications that are built into the .NET Framework.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4f944-135">Comentarios</span><span class="sxs-lookup"><span data-stu-id="4f944-135">Remarks</span></span>  
 <span data-ttu-id="4f944-136">La clase <xref:System.Runtime.Caching.MemoryCache> es una implementación concreta de la clase abstracta <xref:System.Runtime.Caching.ObjectCache> .</span><span class="sxs-lookup"><span data-stu-id="4f944-136">The <xref:System.Runtime.Caching.MemoryCache> class is a concrete implementation of the abstract <xref:System.Runtime.Caching.ObjectCache> class.</span></span> <span data-ttu-id="4f944-137">Se puede proporcionar información de configuración a las instancias de la clase <xref:System.Runtime.Caching.MemoryCache> a partir de archivos de configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="4f944-137">Instances of the <xref:System.Runtime.Caching.MemoryCache> class can be supplied with configuration information from application configuration files.</span></span> <span data-ttu-id="4f944-138">La sección de configuración [memoryCache](memorycache-element-cache-settings.md) contiene una colección de configuración `namedCaches` .</span><span class="sxs-lookup"><span data-stu-id="4f944-138">The [memoryCache](memorycache-element-cache-settings.md) configuration section contains a `namedCaches` configuration collection.</span></span>  
  
 <span data-ttu-id="4f944-139">Cuando se inicializa un objeto de la caché basada en memoria, primero intenta encontrar una entrada `namedCaches` que coincida con el nombre del parámetro que se pasa al constructor de memoria caché.</span><span class="sxs-lookup"><span data-stu-id="4f944-139">When a memory-based cache object is initialized, it first tries to find a `namedCaches` entry that matches the name in the parameter that is passed to the memory cache constructor.</span></span> <span data-ttu-id="4f944-140">Si se encuentra una entrada `namedCaches` , se recupera la información de sondeo y administración de memoria del archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="4f944-140">If a `namedCaches` entry is found, the polling and memory-management information are retrieved from the configuration file.</span></span>  
  
 <span data-ttu-id="4f944-141">Después, el proceso de inicialización determina si se ha reemplazado alguna entrada de configuración. Para ello, usa la colección opcional de pares nombre-valor de la información de configuración del constructor.</span><span class="sxs-lookup"><span data-stu-id="4f944-141">The initialization process then determines whether any configuration entries were overridden, by using the optional collection of name/value pairs of configuration information in the constructor.</span></span> <span data-ttu-id="4f944-142">Si pasa alguno de los valores siguientes en la colección de pares nombre-valor, estos valores reemplazarán la información obtenida del archivo de configuración:</span><span class="sxs-lookup"><span data-stu-id="4f944-142">If you pass any one of the following values in the name/value pair collection, these values override information obtained from the configuration file:</span></span>  
  
- <xref:System.Runtime.Caching.Configuration.MemoryCacheElement.CacheMemoryLimitMegabytes%2A>  
  
- <xref:System.Runtime.Caching.Configuration.MemoryCacheElement.PhysicalMemoryLimitPercentage%2A>  
  
- <xref:System.Runtime.Caching.MemoryCache.PollingInterval%2A>  
  
## <a name="example"></a><span data-ttu-id="4f944-143">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="4f944-143">Example</span></span>  
 <span data-ttu-id="4f944-144">En el ejemplo siguiente se muestra cómo establecer el nombre del <xref:System.Runtime.Caching.MemoryCache> objeto en el nombre del objeto de caché predeterminado estableciendo `name` el atributo en "default".</span><span class="sxs-lookup"><span data-stu-id="4f944-144">The following example shows how to set the name of the <xref:System.Runtime.Caching.MemoryCache> object to the default cache object name by setting the `name` attribute to "Default".</span></span>  
  
 <span data-ttu-id="4f944-145">Los atributos `cacheMemoryLimitMegabytes` y `physicalMemoryLimitPercentage` se establecen en cero.</span><span class="sxs-lookup"><span data-stu-id="4f944-145">The `cacheMemoryLimitMegabytes` attribute and the `physicalMemoryLimitPercentage` attribute are set to zero.</span></span> <span data-ttu-id="4f944-146">El hecho de establecer estos atributos en cero implica que la heurística de ajuste automático de tamaño de <xref:System.Runtime.Caching.MemoryCache> se usa de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="4f944-146">Setting these attributes to zero means that the <xref:System.Runtime.Caching.MemoryCache> autosizing heuristics are used by default.</span></span> <span data-ttu-id="4f944-147">La implementación de la memoria caché debe comparar cada dos minutos la carga de memoria actual con los límites de memoria absoluto y de porcentaje.</span><span class="sxs-lookup"><span data-stu-id="4f944-147">The cache implementation should compare the current memory load against the absolute and percentage-based memory limits every two minutes.</span></span>  
  
```xml  
<configuration>  
  <system.runtime.caching>  
    <memoryCache>  
      <namedCaches>  
          <add name="Default"   
               cacheMemoryLimitMegabytes="0"   
               physicalMemoryLimitPercentage="0"  
               pollingInterval="00:02:00" />  
      </namedCaches>  
    </memoryCache>  
  </system.runtime.caching>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="4f944-148">Vea también</span><span class="sxs-lookup"><span data-stu-id="4f944-148">See also</span></span>

- <xref:System.Runtime.Caching.MemoryCache>
- [<span data-ttu-id="4f944-149">\<Elemento > de System. Runtime. Caching (configuración de caché)</span><span class="sxs-lookup"><span data-stu-id="4f944-149">\<system.runtime.caching> Element (Cache Settings)</span></span>](system-runtime-caching-element-cache-settings.md)
- [<span data-ttu-id="4f944-150">\<namedCaches (elemento > (configuración de caché)</span><span class="sxs-lookup"><span data-stu-id="4f944-150">\<namedCaches> Element (Cache Settings)</span></span>](namedcaches-element-cache-settings.md)
