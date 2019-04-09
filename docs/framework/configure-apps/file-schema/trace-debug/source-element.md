---
title: <source> Elemento
ms.date: 09/29/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source
- http://schemas.microsoft.com/.NetConfiguration/v2.0#source
helpviewer_keywords:
- <source> element
- source element
ms.openlocfilehash: 8860f5d3ed7ee0c04d1e8afd7614f3f73b470808
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59186555"
---
# <a name="source-element"></a><span data-ttu-id="f9fc3-102">\<origen > elemento</span><span class="sxs-lookup"><span data-stu-id="f9fc3-102">\<source> Element</span></span>
<span data-ttu-id="f9fc3-103">Contiene un origen de seguimiento que inicia mensajes de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="f9fc3-103">Specifies a trace source that initiates tracing messages.</span></span>  
  
 <span data-ttu-id="f9fc3-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="f9fc3-104">\<configuration></span></span>  
<span data-ttu-id="f9fc3-105">\<system.diagnostics></span><span class="sxs-lookup"><span data-stu-id="f9fc3-105">\<system.diagnostics></span></span>  
<span data-ttu-id="f9fc3-106">\<orígenes ></span><span class="sxs-lookup"><span data-stu-id="f9fc3-106">\<sources></span></span>  
<span data-ttu-id="f9fc3-107">\<source></span><span class="sxs-lookup"><span data-stu-id="f9fc3-107">\<source></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f9fc3-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f9fc3-108">Syntax</span></span>  
  
```xml  
<source>   
  <listeners>...</listeners>  
</source>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f9fc3-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="f9fc3-109">Attributes and Elements</span></span>  
 <span data-ttu-id="f9fc3-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="f9fc3-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f9fc3-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="f9fc3-111">Attributes</span></span>  
  
|<span data-ttu-id="f9fc3-112">Atributo</span><span class="sxs-lookup"><span data-stu-id="f9fc3-112">Attribute</span></span>|<span data-ttu-id="f9fc3-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="f9fc3-113">Description</span></span>|  
|---------------|-----------------|  
|`name`|<span data-ttu-id="f9fc3-114">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="f9fc3-114">Optional attribute.</span></span><br /><br /> <span data-ttu-id="f9fc3-115">Especifica el nombre del origen de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="f9fc3-115">Specifies the name of the trace source.</span></span>|  
|`switchName`|<span data-ttu-id="f9fc3-116">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="f9fc3-116">Optional attribute.</span></span><br /><br /> <span data-ttu-id="f9fc3-117">Especifica el nombre de una instancia de conmutador de seguimiento en la aplicación.</span><span class="sxs-lookup"><span data-stu-id="f9fc3-117">Specifies the name of a trace switch instance in the application.</span></span> <span data-ttu-id="f9fc3-118">Si el conmutador no se identifica en un `<switches>` elemento, el valor especifica el nivel del modificador.</span><span class="sxs-lookup"><span data-stu-id="f9fc3-118">If the switch is not identified in a `<switches>` element, the value specifies the level for the switch.</span></span>|  
|`switchType`|<span data-ttu-id="f9fc3-119">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="f9fc3-119">Optional attribute.</span></span><br /><br /> <span data-ttu-id="f9fc3-120">Especifica el tipo del modificador de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="f9fc3-120">Specifies the type of the trace switch.</span></span> <span data-ttu-id="f9fc3-121">Si está presente, el tipo debe ser un nombre de clase válido y no puede ser una cadena vacía.</span><span class="sxs-lookup"><span data-stu-id="f9fc3-121">If present, the type must be a valid class name and cannot be an empty string.</span></span>|  
|`extraAttribute`|<span data-ttu-id="f9fc3-122">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="f9fc3-122">Optional attribute.</span></span><br /><br /> <span data-ttu-id="f9fc3-123">Especifica el valor de un atributo específico del origen de seguimiento identificado por el <xref:System.Diagnostics.TraceSource.GetSupportedAttributes%2A> método para ese origen de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="f9fc3-123">Specifies the value for a trace source-specific attribute identified by the <xref:System.Diagnostics.TraceSource.GetSupportedAttributes%2A> method for that trace source.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f9fc3-124">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="f9fc3-124">Child Elements</span></span>  
  
|<span data-ttu-id="f9fc3-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="f9fc3-125">Element</span></span>|<span data-ttu-id="f9fc3-126">Descripción</span><span class="sxs-lookup"><span data-stu-id="f9fc3-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f9fc3-127">\<listeners></span><span class="sxs-lookup"><span data-stu-id="f9fc3-127">\<listeners></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/listeners-element-for-source.md)|<span data-ttu-id="f9fc3-128">Contiene los agentes de escucha que recopilarán, almacenan y enrutan los mensajes.</span><span class="sxs-lookup"><span data-stu-id="f9fc3-128">Contains listeners that collect, store, and route messages.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="f9fc3-129">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="f9fc3-129">Parent Elements</span></span>  
  
|<span data-ttu-id="f9fc3-130">Elemento</span><span class="sxs-lookup"><span data-stu-id="f9fc3-130">Element</span></span>|<span data-ttu-id="f9fc3-131">Descripción</span><span class="sxs-lookup"><span data-stu-id="f9fc3-131">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="f9fc3-132">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="f9fc3-132">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="f9fc3-133">Especifica los agentes de escucha de seguimiento que recopilan, almacenan y enrutan mensajes, así como el nivel en el que está establecido un modificador de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="f9fc3-133">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sources`|<span data-ttu-id="f9fc3-134">Contiene orígenes de seguimiento que inician mensajes de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="f9fc3-134">Contains trace sources that initiate tracing messages.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f9fc3-135">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f9fc3-135">Remarks</span></span>  
 <span data-ttu-id="f9fc3-136">Este elemento se puede usar en el archivo de configuración del equipo (Machine.config) y el archivo de configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="f9fc3-136">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f9fc3-137">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f9fc3-137">Example</span></span>  
 <span data-ttu-id="f9fc3-138">El ejemplo siguiente muestra cómo usar el `<source>` elemento va a agregar el origen de seguimiento `mySource` y establecer el nivel del modificador de origen denominado `sourceSwitch`.</span><span class="sxs-lookup"><span data-stu-id="f9fc3-138">The following example shows how to use the `<source>` element to add the trace source `mySource` and to set the level for the source switch named `sourceSwitch`.</span></span> <span data-ttu-id="f9fc3-139">Se agrega un agente de escucha de seguimiento de consola que escribe información de seguimiento en la consola.</span><span class="sxs-lookup"><span data-stu-id="f9fc3-139">A console trace listener is added that writes trace information to the console.</span></span>  
  
```xml  
<configuration>  
  <system.diagnostics>  
    <sources>  
      <source name="mySource" switchName="sourceSwitch" switchType="System.Diagnostics.SourceSwitch"  >  
        <listeners>  
          <add name="console" type="System.Diagnostics.ConsoleTraceListener" >  
            <filter type="System.Diagnostics.EventTypeFilter" initializeData="Error" />  
          </add>  
          <remove name="Default" />  
        </listeners>  
      </source>  
    </sources>  
        <switches>  
           <add name="sourceSwitch" value="Warning" />  
        </switches>    
  </system.diagnostics>   
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="f9fc3-140">Vea también</span><span class="sxs-lookup"><span data-stu-id="f9fc3-140">See also</span></span>

- [<span data-ttu-id="f9fc3-141">Esquema de la configuración de seguimiento y depuración</span><span class="sxs-lookup"><span data-stu-id="f9fc3-141">Trace and Debug Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)
- [<span data-ttu-id="f9fc3-142">Modificadores de seguimiento</span><span class="sxs-lookup"><span data-stu-id="f9fc3-142">Trace Switches</span></span>](../../../../../docs/framework/debug-trace-profile/trace-switches.md)
