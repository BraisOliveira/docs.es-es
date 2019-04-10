---
title: Elemento <Thread_UseAllCpuGroups>
ms.date: 03/30/2017
ms.assetid: d30fe7c5-8469-46e2-b804-e3eec7b24256
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 236953cc1a430a1dd2a2fbb633c7ef06e6ba200f
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59230842"
---
# <a name="threaduseallcpugroups-element"></a><span data-ttu-id="4f47d-102">\<Thread_UseAllCpuGroups > elemento</span><span class="sxs-lookup"><span data-stu-id="4f47d-102">\<Thread_UseAllCpuGroups> Element</span></span>
<span data-ttu-id="4f47d-103">Especifica si el runtime distribuye subprocesos administrados en todos los grupos de CPU.</span><span class="sxs-lookup"><span data-stu-id="4f47d-103">Specifies whether the runtime distributes managed threads across all CPU groups.</span></span>  
  
 <span data-ttu-id="4f47d-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="4f47d-104">\<configuration></span></span>  
<span data-ttu-id="4f47d-105">\<runtime></span><span class="sxs-lookup"><span data-stu-id="4f47d-105">\<runtime></span></span>  
<span data-ttu-id="4f47d-106"><Thread_UseAllCpuGroups></span><span class="sxs-lookup"><span data-stu-id="4f47d-106"><Thread_UseAllCpuGroups></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4f47d-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4f47d-107">Syntax</span></span>  
  
```xml
<Thread_UseAllCpuGroups    
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4f47d-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="4f47d-108">Attributes and Elements</span></span>  
 <span data-ttu-id="4f47d-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="4f47d-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4f47d-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="4f47d-110">Attributes</span></span>  
  
|<span data-ttu-id="4f47d-111">Atributo</span><span class="sxs-lookup"><span data-stu-id="4f47d-111">Attribute</span></span>|<span data-ttu-id="4f47d-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="4f47d-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="4f47d-113">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="4f47d-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="4f47d-114">Especifica si el runtime distribuye subprocesos administrados en todos los grupos de CPU.</span><span class="sxs-lookup"><span data-stu-id="4f47d-114">Specifies whether the runtime distributes managed threads across all CPU groups.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="4f47d-115">Atributo enabled</span><span class="sxs-lookup"><span data-stu-id="4f47d-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="4f47d-116">Valor</span><span class="sxs-lookup"><span data-stu-id="4f47d-116">Value</span></span>|<span data-ttu-id="4f47d-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="4f47d-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="4f47d-118">El runtime no distribuye los subprocesos administrados en varios grupos de CPU.</span><span class="sxs-lookup"><span data-stu-id="4f47d-118">The runtime does not distribute managed threads across multiple CPU groups.</span></span> <span data-ttu-id="4f47d-119">Este es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="4f47d-119">This is the default.</span></span>|  
|`true`|<span data-ttu-id="4f47d-120">El runtime distribuye subprocesos administrados en varios grupos de CPU, si el equipo tiene varios grupos de CPU y la [ \<GCCpuGroup >](../../../../../docs/framework/configure-apps/file-schema/runtime/gccpugroup-element.md) elemento está habilitado.</span><span class="sxs-lookup"><span data-stu-id="4f47d-120">The runtime distributes managed threads across multiple CPU groups, if the computer has multiple CPU groups and the [\<GCCpuGroup>](../../../../../docs/framework/configure-apps/file-schema/runtime/gccpugroup-element.md) element is enabled.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4f47d-121">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="4f47d-121">Child Elements</span></span>  
 <span data-ttu-id="4f47d-122">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="4f47d-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="4f47d-123">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="4f47d-123">Parent Elements</span></span>  
  
|<span data-ttu-id="4f47d-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="4f47d-124">Element</span></span>|<span data-ttu-id="4f47d-125">Descripción</span><span class="sxs-lookup"><span data-stu-id="4f47d-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="4f47d-126">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="4f47d-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="4f47d-127">Contiene información del enlace del ensamblado y de la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="4f47d-127">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4f47d-128">Comentarios</span><span class="sxs-lookup"><span data-stu-id="4f47d-128">Remarks</span></span>  
 <span data-ttu-id="4f47d-129">Cuando un equipo tiene varios grupos de CPU, si se habilita este elemento, el runtime pueda distribuir subprocesos administrados en todos los grupos de CPU.</span><span class="sxs-lookup"><span data-stu-id="4f47d-129">When a computer has multiple CPU groups, enabling this element causes the runtime to distribute managed threads across all CPU groups.</span></span> <span data-ttu-id="4f47d-130">Para usar esta característica, debe habilitar también la [ \<GCCpuGroup >](../../../../../docs/framework/configure-apps/file-schema/runtime/gccpugroup-element.md) elemento, que extiende la recolección para todos los grupos de CPU y tiene todos los núcleos en cuenta al crear y equilibra montones.</span><span class="sxs-lookup"><span data-stu-id="4f47d-130">To use this feature, you must also enable the [\<GCCpuGroup>](../../../../../docs/framework/configure-apps/file-schema/runtime/gccpugroup-element.md) element, which extends garbage collection to all CPU groups and takes all cores into account when creating and balancing heaps.</span></span> <span data-ttu-id="4f47d-131">Habilitar la [ \<GCCpuGroup >](../../../../../docs/framework/configure-apps/file-schema/runtime/gccpugroup-element.md) elemento requiere la habilitación de la [ \<gcServer >](../../../../../docs/framework/configure-apps/file-schema/runtime/gcserver-element.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="4f47d-131">Enabling the [\<GCCpuGroup>](../../../../../docs/framework/configure-apps/file-schema/runtime/gccpugroup-element.md) element requires enabling the [\<gcServer>](../../../../../docs/framework/configure-apps/file-schema/runtime/gcserver-element.md) element.</span></span> <span data-ttu-id="4f47d-132">Si estos elementos no están habilitados, habilite el `<Thread_UseAllCpuGroups>` elemento no tiene ningún efecto.</span><span class="sxs-lookup"><span data-stu-id="4f47d-132">If these elements are not enabled, enabling the `<Thread_UseAllCpuGroups>` element has no effect.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4f47d-133">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="4f47d-133">Example</span></span>  
 <span data-ttu-id="4f47d-134">El ejemplo siguiente muestra cómo habilitar la compatibilidad con varios grupos de CPU.</span><span class="sxs-lookup"><span data-stu-id="4f47d-134">The following example shows how to enable support for multiple CPU groups.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <Thread_UseAllCpuGroups enabled="true"/>  
      <GCCpuGroup enabled="true"/>  
      <gcServer enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="4f47d-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="4f47d-135">See also</span></span>

- [<span data-ttu-id="4f47d-136">Esquema de la configuración de Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="4f47d-136">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [<span data-ttu-id="4f47d-137">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="4f47d-137">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
- [<span data-ttu-id="4f47d-138">\<GCCpuGroup > elemento</span><span class="sxs-lookup"><span data-stu-id="4f47d-138">\<GCCpuGroup> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/gccpugroup-element.md)
