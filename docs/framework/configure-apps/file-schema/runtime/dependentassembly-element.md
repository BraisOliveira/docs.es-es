---
title: <dependentAssembly> (Elemento)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/assemblyBinding/dependentAssembly
- http://schemas.microsoft.com/.NetConfiguration/v2.0#dependentAssembly
helpviewer_keywords:
- container tags, <dependentAssembly> element
- dependentAssembly element
- <dependentAssembly> element
ms.assetid: 14e95627-dd79-4b82-ac85-e682aa3a31d8
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3a0604161ed6e7c3ead4a2e518daebc8414689af
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252704"
---
# <a name="dependentassembly-element"></a><span data-ttu-id="3dd52-102">\<Elemento > de dependentAssembly</span><span class="sxs-lookup"><span data-stu-id="3dd52-102">\<dependentAssembly> Element</span></span>
<span data-ttu-id="3dd52-103">Encapsula la directiva de enlace y la ubicación de cada ensamblado.</span><span class="sxs-lookup"><span data-stu-id="3dd52-103">Encapsulates binding policy and assembly location for each assembly.</span></span> <span data-ttu-id="3dd52-104">Use un `dependentAssembly` elemento para cada ensamblado.</span><span class="sxs-lookup"><span data-stu-id="3dd52-104">Use one `dependentAssembly` element for each assembly.</span></span>  
  
<span data-ttu-id="3dd52-105">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="3dd52-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="3dd52-106">&nbsp;&nbsp;[ **\<> en tiempo de ejecución**](runtime-element.md)</span><span class="sxs-lookup"><span data-stu-id="3dd52-106">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="3dd52-107">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> assemblyBinding**](assemblybinding-element-for-runtime.md)</span><span class="sxs-lookup"><span data-stu-id="3dd52-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<assemblyBinding>**](assemblybinding-element-for-runtime.md)</span></span>\
<span data-ttu-id="3dd52-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<dependentAssembly>**</span><span class="sxs-lookup"><span data-stu-id="3dd52-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<dependentAssembly>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3dd52-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3dd52-109">Syntax</span></span>  
  
```xml  
<dependentAssembly>   
</dependentAssembly>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3dd52-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="3dd52-110">Attributes and Elements</span></span>  
 <span data-ttu-id="3dd52-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="3dd52-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3dd52-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="3dd52-112">Attributes</span></span>  
 <span data-ttu-id="3dd52-113">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="3dd52-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="3dd52-114">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="3dd52-114">Child Elements</span></span>  
  
|<span data-ttu-id="3dd52-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="3dd52-115">Element</span></span>|<span data-ttu-id="3dd52-116">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="3dd52-116">Description</span></span>|  
|-------------|-----------------|  
|`assemblyIdentity`|<span data-ttu-id="3dd52-117">Contiene información de identificación sobre el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="3dd52-117">Contains identifying information about the assembly.</span></span> <span data-ttu-id="3dd52-118">Este elemento debe estar incluido en cada `dependentAssembly` elemento.</span><span class="sxs-lookup"><span data-stu-id="3dd52-118">This element must be included in each `dependentAssembly` element.</span></span>|  
|`codeBase`|<span data-ttu-id="3dd52-119">Especifica dónde puede encontrar el tiempo de ejecución un ensamblado compartido si no está instalado en el equipo.</span><span class="sxs-lookup"><span data-stu-id="3dd52-119">Specifies where the runtime can find a shared assembly if it is not installed on the computer.</span></span>|  
|`bindingRedirect`|<span data-ttu-id="3dd52-120">Redirige una versión de ensamblado a otra versión.</span><span class="sxs-lookup"><span data-stu-id="3dd52-120">Redirects one assembly version to another.</span></span>|  
|`publisherPolicy`|<span data-ttu-id="3dd52-121">Especifica si el tiempo de ejecución aplica la Directiva de edición para este ensamblado.</span><span class="sxs-lookup"><span data-stu-id="3dd52-121">Specifies whether the runtime applies publisher policy for this assembly.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="3dd52-122">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="3dd52-122">Parent Elements</span></span>  
  
|<span data-ttu-id="3dd52-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="3dd52-123">Element</span></span>|<span data-ttu-id="3dd52-124">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="3dd52-124">Description</span></span>|  
|-------------|-----------------|  
|`assemblyBinding`|<span data-ttu-id="3dd52-125">Contiene información sobre la redirección de versiones de ensamblado y las ubicaciones de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="3dd52-125">Contains information about assembly version redirection and the locations of assemblies.</span></span>|  
|`configuration`|<span data-ttu-id="3dd52-126">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="3dd52-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="3dd52-127">Contiene información del enlace del ensamblado y de la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="3dd52-127">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="3dd52-128">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="3dd52-128">Example</span></span>  
 <span data-ttu-id="3dd52-129">En el ejemplo siguiente se muestra cómo encapsular la información de ensamblado para dos ensamblados.</span><span class="sxs-lookup"><span data-stu-id="3dd52-129">The following example shows how to encapsulate assembly information for two assemblies.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
         <dependentAssembly>  
            <assemblyIdentity name="myAssembly"  
                              publicKeyToken="32ab4ba45e0a69a1"  
                              culture="neutral" />  
            <!--Redirection and codeBase policy for myAssembly.-->  
         </dependentAssembly>  
         <dependentAssembly>  
            <assemblyIdentity name="mySecondAssembly"  
                              publicKeyToken="32ab4ba45e0a69a1"  
                              culture="neutral" />  
            <!--Redirection and codeBase policy for mySecondAssembly.-->  
         </dependentAssembly>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="3dd52-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="3dd52-130">See also</span></span>

- [<span data-ttu-id="3dd52-131">Esquema de la configuración de Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="3dd52-131">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="3dd52-132">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="3dd52-132">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="3dd52-133">Redirigir versiones de ensamblado</span><span class="sxs-lookup"><span data-stu-id="3dd52-133">Redirecting Assembly Versions</span></span>](../../redirect-assembly-versions.md)
