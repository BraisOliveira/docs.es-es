---
title: Elemento <memoryCache> (configuración de caché)
ms.date: 03/30/2017
helpviewer_keywords:
- <memoryCache> element
- caching [.NET Framework], configuration
- memoryCache element
ms.assetid: 182a622f-f7cf-472d-9d0b-451d2fd94525
ms.openlocfilehash: 4f1dd270ee1b317ec0d3a32e341680646ff0b69d
ms.sourcegitcommit: 9b1ac36b6c80176fd4e20eb5bfcbd9d56c3264cf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/28/2019
ms.locfileid: "67423286"
---
# <a name="memorycache-element-cache-settings"></a><span data-ttu-id="03ab9-102">\<memoryCache > elemento (configuración de caché)</span><span class="sxs-lookup"><span data-stu-id="03ab9-102">\<memoryCache> Element (Cache Settings)</span></span>
<span data-ttu-id="03ab9-103">Define un elemento que se usa para configurar una memoria caché basada en la clase <xref:System.Runtime.Caching.MemoryCache> .</span><span class="sxs-lookup"><span data-stu-id="03ab9-103">Defines an element that is used to configure a cache that is based on the <xref:System.Runtime.Caching.MemoryCache> class.</span></span> <span data-ttu-id="03ab9-104">La clase <xref:System.Runtime.Caching.Configuration.MemoryCacheElement> define un elemento [memoryCache](../../../../../docs/framework/configure-apps/file-schema/runtime/memorycache-element-cache-settings.md) que se puede usar para configurar la memoria caché.</span><span class="sxs-lookup"><span data-stu-id="03ab9-104">The <xref:System.Runtime.Caching.Configuration.MemoryCacheElement> class defines a [memoryCache](../../../../../docs/framework/configure-apps/file-schema/runtime/memorycache-element-cache-settings.md) element that you can use to configure the cache.</span></span> <span data-ttu-id="03ab9-105">Se pueden usar varias instancias de la clase <xref:System.Runtime.Caching.MemoryCache> en una sola aplicación.</span><span class="sxs-lookup"><span data-stu-id="03ab9-105">Multiple instances of the <xref:System.Runtime.Caching.MemoryCache> class can be used in a single application.</span></span> <span data-ttu-id="03ab9-106">Cada elemento `memoryCache` del archivo de configuración puede contener valores de configuración para una instancia de <xref:System.Runtime.Caching.MemoryCache> con nombre.</span><span class="sxs-lookup"><span data-stu-id="03ab9-106">Each `memoryCache` element in the configuration file can contain settings for a named <xref:System.Runtime.Caching.MemoryCache> instance.</span></span>  
  
 <span data-ttu-id="03ab9-107">\<configuration></span><span class="sxs-lookup"><span data-stu-id="03ab9-107">\<configuration></span></span>  
<span data-ttu-id="03ab9-108">\<system.runtime.caching></span><span class="sxs-lookup"><span data-stu-id="03ab9-108">\<system.runtime.caching></span></span>  
<span data-ttu-id="03ab9-109">\<memoryCache></span><span class="sxs-lookup"><span data-stu-id="03ab9-109">\<memoryCache></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="03ab9-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="03ab9-110">Syntax</span></span>  
  
```xml  
<memoryCache>   
    <namedCaches>  
        <!-- child elements -->  
    </namedCaches>   
</memoryCache>  
```  
  
## <a name="type"></a><span data-ttu-id="03ab9-111">Tipo</span><span class="sxs-lookup"><span data-stu-id="03ab9-111">Type</span></span>  
 <span data-ttu-id="03ab9-112">Clase<xref:System.Runtime.Caching.MemoryCache> .</span><span class="sxs-lookup"><span data-stu-id="03ab9-112"><xref:System.Runtime.Caching.MemoryCache> class.</span></span>  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="03ab9-113">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="03ab9-113">Attributes and Elements</span></span>  
 <span data-ttu-id="03ab9-114">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="03ab9-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="03ab9-115">Atributos</span><span class="sxs-lookup"><span data-stu-id="03ab9-115">Attributes</span></span>  
  
|<span data-ttu-id="03ab9-116">Atributo</span><span class="sxs-lookup"><span data-stu-id="03ab9-116">Attribute</span></span>|<span data-ttu-id="03ab9-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="03ab9-117">Description</span></span>|  
|---------------|-----------------|  
|`CacheMemoryLimitMegabytes`|<span data-ttu-id="03ab9-118">Tamaño máximo de memoria (en megabytes) que puede alcanzar una instancia de un objeto <xref:System.Runtime.Caching.MemoryCache> .</span><span class="sxs-lookup"><span data-stu-id="03ab9-118">The maximum memory size, in megabytes, that an instance of a <xref:System.Runtime.Caching.MemoryCache> object can grow to.</span></span> <span data-ttu-id="03ab9-119">El valor predeterminado es 0, lo que significa que se usa de forma predeterminada la heurística de ajuste automático de tamaño de la clase <xref:System.Runtime.Caching.MemoryCache> .</span><span class="sxs-lookup"><span data-stu-id="03ab9-119">The default value is 0, which means that the <xref:System.Runtime.Caching.MemoryCache> class's autosize heuristics are used by default.</span></span>|  
|`Name`|<span data-ttu-id="03ab9-120">Nombre de la configuración de la memoria caché.</span><span class="sxs-lookup"><span data-stu-id="03ab9-120">The name of the cache configuration.</span></span>|  
|`PhysicalMemoryLimitPercentage`|<span data-ttu-id="03ab9-121">Porcentaje de memoria física que la memoria caché puede usar.</span><span class="sxs-lookup"><span data-stu-id="03ab9-121">The percentage of physical memory that can be used by the cache.</span></span> <span data-ttu-id="03ab9-122">El valor predeterminado es 0, lo que significa que se usa de forma predeterminada la heurística de ajuste automático de tamaño de la clase <xref:System.Runtime.Caching.MemoryCache> .</span><span class="sxs-lookup"><span data-stu-id="03ab9-122">The default value is 0, which means that the <xref:System.Runtime.Caching.MemoryCache> class's autosize heuristics are used by default.</span></span>|  
|`PollingInterval`|<span data-ttu-id="03ab9-123">Valor que indica el intervalo de tiempo después del cual la implementación de caché compara la carga de memoria actual con los límites de memoria absoluto y de porcentaje que están establecidos para la instancia de caché.</span><span class="sxs-lookup"><span data-stu-id="03ab9-123">A value that indicates the time interval after which the cache implementation compares the current memory load against the absolute and percentage-based memory limits that are set for the cache instance.</span></span> <span data-ttu-id="03ab9-124">El valor se especifica en formato "HH:MM:SS".</span><span class="sxs-lookup"><span data-stu-id="03ab9-124">The value is entered in "HH:MM:SS" format.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="03ab9-125">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="03ab9-125">Child Elements</span></span>  
  
|<span data-ttu-id="03ab9-126">Elemento</span><span class="sxs-lookup"><span data-stu-id="03ab9-126">Element</span></span>|<span data-ttu-id="03ab9-127">Descripción</span><span class="sxs-lookup"><span data-stu-id="03ab9-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="03ab9-128">\<namedCaches></span><span class="sxs-lookup"><span data-stu-id="03ab9-128">\<namedCaches></span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/namedcaches-element-cache-settings.md)|<span data-ttu-id="03ab9-129">Contiene una colección de valores de configuración para la instancia de `namedCache` .</span><span class="sxs-lookup"><span data-stu-id="03ab9-129">Contains a collection of configuration settings for the `namedCache` instance.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="03ab9-130">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="03ab9-130">Parent Elements</span></span>  
  
|<span data-ttu-id="03ab9-131">Elemento</span><span class="sxs-lookup"><span data-stu-id="03ab9-131">Element</span></span>|<span data-ttu-id="03ab9-132">Descripción</span><span class="sxs-lookup"><span data-stu-id="03ab9-132">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="03ab9-133">\<system.runtime.caching></span><span class="sxs-lookup"><span data-stu-id="03ab9-133">\<system.runtime.caching></span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/system-runtime-caching-element-cache-settings.md)|<span data-ttu-id="03ab9-134">Contiene tipos que permiten implementar el almacenamiento en caché de salida en las aplicaciones que están integradas en .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="03ab9-134">Contains types that let you implement output caching in applications that are built into the .NET Framework.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="03ab9-135">Comentarios</span><span class="sxs-lookup"><span data-stu-id="03ab9-135">Remarks</span></span>  
 <span data-ttu-id="03ab9-136">La clase <xref:System.Runtime.Caching.MemoryCache> es una implementación concreta de la clase abstracta <xref:System.Runtime.Caching.ObjectCache> .</span><span class="sxs-lookup"><span data-stu-id="03ab9-136">The <xref:System.Runtime.Caching.MemoryCache> class is a concrete implementation of the abstract <xref:System.Runtime.Caching.ObjectCache> class.</span></span> <span data-ttu-id="03ab9-137">Se puede proporcionar información de configuración a las instancias de la clase <xref:System.Runtime.Caching.MemoryCache> a partir de archivos de configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="03ab9-137">Instances of the <xref:System.Runtime.Caching.MemoryCache> class can be supplied with configuration information from application configuration files.</span></span> <span data-ttu-id="03ab9-138">La sección de configuración [memoryCache](../../../../../docs/framework/configure-apps/file-schema/runtime/memorycache-element-cache-settings.md) contiene una colección de configuración `namedCaches` .</span><span class="sxs-lookup"><span data-stu-id="03ab9-138">The [memoryCache](../../../../../docs/framework/configure-apps/file-schema/runtime/memorycache-element-cache-settings.md) configuration section contains a `namedCaches` configuration collection.</span></span>  
  
 <span data-ttu-id="03ab9-139">Cuando se inicializa un objeto de la caché basada en memoria, primero intenta encontrar una entrada `namedCaches` que coincida con el nombre del parámetro que se pasa al constructor de memoria caché.</span><span class="sxs-lookup"><span data-stu-id="03ab9-139">When a memory-based cache object is initialized, it first tries to find a `namedCaches` entry that matches the name in the parameter that is passed to the memory cache constructor.</span></span> <span data-ttu-id="03ab9-140">Si se encuentra una entrada `namedCaches` , se recupera la información de sondeo y administración de memoria del archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="03ab9-140">If a `namedCaches` entry is found, the polling and memory-management information are retrieved from the configuration file.</span></span>  
  
 <span data-ttu-id="03ab9-141">Después, el proceso de inicialización determina si se ha reemplazado alguna entrada de configuración. Para ello, usa la colección opcional de pares nombre-valor de la información de configuración del constructor.</span><span class="sxs-lookup"><span data-stu-id="03ab9-141">The initialization process then determines whether any configuration entries were overridden, by using the optional collection of name/value pairs of configuration information in the constructor.</span></span> <span data-ttu-id="03ab9-142">Si pasa alguno de los valores siguientes en la colección de pares nombre-valor, estos valores reemplazarán la información obtenida del archivo de configuración:</span><span class="sxs-lookup"><span data-stu-id="03ab9-142">If you pass any one of the following values in the name/value pair collection, these values override information obtained from the configuration file:</span></span>  
  
- <xref:System.Runtime.Caching.Configuration.MemoryCacheElement.CacheMemoryLimitMegabytes%2A>  
  
- <xref:System.Runtime.Caching.Configuration.MemoryCacheElement.PhysicalMemoryLimitPercentage%2A>  
  
- <xref:System.Runtime.Caching.MemoryCache.PollingInterval%2A>  
  
## <a name="example"></a><span data-ttu-id="03ab9-143">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="03ab9-143">Example</span></span>  
 <span data-ttu-id="03ab9-144">El ejemplo siguiente muestra cómo establecer el nombre de la <xref:System.Runtime.Caching.MemoryCache> objeto en el nombre de objeto de caché predeterminado estableciendo la `name` atributo en "Default".</span><span class="sxs-lookup"><span data-stu-id="03ab9-144">The following example shows how to set the name of the <xref:System.Runtime.Caching.MemoryCache> object to the default cache object name by setting the `name` attribute to "Default".</span></span>  
  
 <span data-ttu-id="03ab9-145">Los atributos `cacheMemoryLimitMegabytes` y `physicalMemoryLimitPercentage` se establecen en cero.</span><span class="sxs-lookup"><span data-stu-id="03ab9-145">The `cacheMemoryLimitMegabytes` attribute and the `physicalMemoryLimitPercentage` attribute are set to zero.</span></span> <span data-ttu-id="03ab9-146">El hecho de establecer estos atributos en cero implica que la heurística de ajuste automático de tamaño de <xref:System.Runtime.Caching.MemoryCache> se usa de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="03ab9-146">Setting these attributes to zero means that the <xref:System.Runtime.Caching.MemoryCache> autosizing heuristics are used by default.</span></span> <span data-ttu-id="03ab9-147">La implementación de la memoria caché debe comparar cada dos minutos la carga de memoria actual con los límites de memoria absoluto y de porcentaje.</span><span class="sxs-lookup"><span data-stu-id="03ab9-147">The cache implementation should compare the current memory load against the absolute and percentage-based memory limits every two minutes.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="03ab9-148">Vea también</span><span class="sxs-lookup"><span data-stu-id="03ab9-148">See also</span></span>

- <xref:System.Runtime.Caching.MemoryCache>
- [<span data-ttu-id="03ab9-149">\<System.Runtime.Caching > elemento (configuración de caché)</span><span class="sxs-lookup"><span data-stu-id="03ab9-149">\<system.runtime.caching> Element (Cache Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/system-runtime-caching-element-cache-settings.md)
- [<span data-ttu-id="03ab9-150">\<namedCaches > elemento (configuración de caché)</span><span class="sxs-lookup"><span data-stu-id="03ab9-150">\<namedCaches> Element (Cache Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/namedcaches-element-cache-settings.md)
