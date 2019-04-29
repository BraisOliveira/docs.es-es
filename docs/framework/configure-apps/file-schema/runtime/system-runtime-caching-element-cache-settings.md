---
title: Elemento <system.runtime.caching> (configuración de caché)
ms.date: 03/30/2017
helpviewer_keywords:
- <system.runtime.caching> element
- caching [.NET Framework], configuration
- system.runtime.caching element
ms.assetid: 9b44daee-874a-4bd1-954e-83bf53565590
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: da059e1be7c685eba7792045abf4ffa691525d2e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61701481"
---
# <a name="systemruntimecaching-element-cache-settings"></a><span data-ttu-id="823b9-102">\<System.Runtime.Caching > elemento (configuración de caché)</span><span class="sxs-lookup"><span data-stu-id="823b9-102">\<system.runtime.caching> Element (Cache Settings)</span></span>
<span data-ttu-id="823b9-103">Proporciona la configuración para la implementación predeterminada en memoria de la clase <xref:System.Runtime.Caching.ObjectCache> mediante la entrada `memoryCache` en el archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="823b9-103">Provides configuration for the default in-memory <xref:System.Runtime.Caching.ObjectCache> implementation through the `memoryCache` entry in the configuration file.</span></span>  
  
 <span data-ttu-id="823b9-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="823b9-104">\<configuration></span></span>  
<span data-ttu-id="823b9-105">\<system.runtime.caching></span><span class="sxs-lookup"><span data-stu-id="823b9-105">\<system.runtime.caching></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="823b9-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="823b9-106">Syntax</span></span>  
  
```xml  
<system.runtime.caching >  
   <!-- child elements -->  
</system.runtime.caching >  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="823b9-107">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="823b9-107">Attributes and Elements</span></span>  
 <span data-ttu-id="823b9-108">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="823b9-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="823b9-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="823b9-109">Attributes</span></span>  
 `None`  
  
### <a name="child-elements"></a><span data-ttu-id="823b9-110">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="823b9-110">Child Elements</span></span>  
  
|<span data-ttu-id="823b9-111">Elemento</span><span class="sxs-lookup"><span data-stu-id="823b9-111">Element</span></span>|<span data-ttu-id="823b9-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="823b9-112">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="823b9-113">\<memoryCache></span><span class="sxs-lookup"><span data-stu-id="823b9-113">\<memoryCache></span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/memorycache-element-cache-settings.md)|<span data-ttu-id="823b9-114">Define un elemento que se usa para configurar una memoria caché basada en la clase <xref:System.Runtime.Caching.MemoryCache> .</span><span class="sxs-lookup"><span data-stu-id="823b9-114">Defines an element that is used to configure a cache that is based on the <xref:System.Runtime.Caching.MemoryCache> class.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="823b9-115">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="823b9-115">Parent Elements</span></span>  
  
|<span data-ttu-id="823b9-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="823b9-116">Element</span></span>|<span data-ttu-id="823b9-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="823b9-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="823b9-118">\<configuration></span><span class="sxs-lookup"><span data-stu-id="823b9-118">\<configuration></span></span>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)|<span data-ttu-id="823b9-119">Especifica el elemento raíz necesario en cada archivo de configuración usado por Common Language Runtime y por las aplicaciones de [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="823b9-119">Specifies the root element in every configuration file that is used by the common language runtime and [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)] applications.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="823b9-120">Comentarios</span><span class="sxs-lookup"><span data-stu-id="823b9-120">Remarks</span></span>  
 <span data-ttu-id="823b9-121">Las clases de este espacio de nombres proporcionan una manera de usar las funciones de almacenamiento en caché, como las de ASP.NET, pero sin una dependencia en el ensamblado `System.Web` .</span><span class="sxs-lookup"><span data-stu-id="823b9-121">The classes in this namespace provide a way to use caching facilities like those in ASP.NET, but without a dependency on the `System.Web` assembly.</span></span> <span data-ttu-id="823b9-122">Para obtener más información, consulta [Caching in .NET Framework Applications](../../../../../docs/framework/performance/caching-in-net-framework-applications.md).</span><span class="sxs-lookup"><span data-stu-id="823b9-122">For more information, see [Caching in .NET Framework Applications](../../../../../docs/framework/performance/caching-in-net-framework-applications.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="823b9-123">La funcionalidad y los tipos de almacenamiento en caché de salida del espacio de nombres <xref:System.Runtime.Caching> son nuevos en [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="823b9-123">The output caching functionality and types in the <xref:System.Runtime.Caching> namespace are new in [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="example"></a><span data-ttu-id="823b9-124">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="823b9-124">Example</span></span>  
 <span data-ttu-id="823b9-125">En el ejemplo siguiente se muestra cómo configurar una memoria caché basada en la clase <xref:System.Runtime.Caching.MemoryCache> .</span><span class="sxs-lookup"><span data-stu-id="823b9-125">The following example shows how to configure a cache that is based on the <xref:System.Runtime.Caching.MemoryCache> class.</span></span> <span data-ttu-id="823b9-126">En el ejemplo se muestra cómo configurar una instancia de la entrada `namedCaches` de la memoria caché.</span><span class="sxs-lookup"><span data-stu-id="823b9-126">The example shows how to configure an instance of the `namedCaches` entry for memory cache.</span></span> <span data-ttu-id="823b9-127">El nombre de la memoria caché se establece en el nombre predeterminado de la entrada de caché estableciendo el atributo `name` en "default".</span><span class="sxs-lookup"><span data-stu-id="823b9-127">The name of the cache is set to the default cache entry name by setting the `name` attribute to "default".</span></span>  
  
 <span data-ttu-id="823b9-128">Los atributos `cacheMemoryLimitMegabytes` y `physicalMemoryPercentage` se establecen en cero.</span><span class="sxs-lookup"><span data-stu-id="823b9-128">The `cacheMemoryLimitMegabytes` attribute and the `physicalMemoryPercentage` attribute are set to zero.</span></span> <span data-ttu-id="823b9-129">El hecho de establecer estos atributos en cero implica que la heurística de ajuste automático de tamaño de <xref:System.Runtime.Caching.MemoryCache> se usa de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="823b9-129">Setting these attributes to zero means that the <xref:System.Runtime.Caching.MemoryCache> autosizing heuristics are used by default.</span></span> <span data-ttu-id="823b9-130">La implementación de la memoria caché debe comparar cada dos minutos la carga de memoria actual con los límites de memoria absoluto y de porcentaje.</span><span class="sxs-lookup"><span data-stu-id="823b9-130">The cache implementation should compare the current memory load against the absolute and percentage-based memory limits every two minutes.</span></span>  
  
```xml  
<configuration>  
  <system.runtime.caching>  
    <memoryCache>  
      <namedCaches>  
          <add name="default"   
               cacheMemoryLimitMegabytes="0"   
               physicalMemoryLimitPercentage="0"  
               pollingInterval="00:02:00" />  
      </namedCaches>  
    </memoryCache>  
  </system.runtime.caching>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="823b9-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="823b9-131">See also</span></span>

- [<span data-ttu-id="823b9-132">\<memoryCache > elemento (configuración de caché)</span><span class="sxs-lookup"><span data-stu-id="823b9-132">\<memoryCache> Element (Cache Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/memorycache-element-cache-settings.md)
