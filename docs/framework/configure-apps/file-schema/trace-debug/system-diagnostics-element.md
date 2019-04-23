---
title: < System.diagnostics > (elemento)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#system.diagnostics
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics
helpviewer_keywords:
- <system.diagnostics> element
- system.diagnostics element
ms.assetid: 3f348f42-fa72-4ff2-aa1c-bb9eecad4bb2
ms.openlocfilehash: 026805ffb9b89aa55e84cf9a5c4afb8ed63cec09
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59142719"
---
# <a name="systemdiagnostics-element"></a><span data-ttu-id="44ca9-102">\<System.Diagnostics > elemento</span><span class="sxs-lookup"><span data-stu-id="44ca9-102">\<system.diagnostics> Element</span></span>
<span data-ttu-id="44ca9-103">Especifica los agentes de escucha de seguimiento que recopilan, almacenan y enrutan mensajes, así como el nivel en el que está establecido un modificador de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="44ca9-103">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>  
  
 <span data-ttu-id="44ca9-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="44ca9-104">\<configuration></span></span>  
<span data-ttu-id="44ca9-105">\<system.diagnostics></span><span class="sxs-lookup"><span data-stu-id="44ca9-105">\<system.diagnostics></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="44ca9-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="44ca9-106">Syntax</span></span>  
  
```xml  
<system.diagnostics>   
</system.diagnostics>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="44ca9-107">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="44ca9-107">Attributes and Elements</span></span>  
 <span data-ttu-id="44ca9-108">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="44ca9-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="44ca9-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="44ca9-109">Attributes</span></span>  
 <span data-ttu-id="44ca9-110">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="44ca9-110">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="44ca9-111">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="44ca9-111">Child Elements</span></span>  
  
|<span data-ttu-id="44ca9-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="44ca9-112">Element</span></span>|<span data-ttu-id="44ca9-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="44ca9-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="44ca9-114">\<assert></span><span class="sxs-lookup"><span data-stu-id="44ca9-114">\<assert></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/assert-element.md)|<span data-ttu-id="44ca9-115">Especifica si se muestra un cuadro de mensaje cuando se llama al método <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>; también indica el nombre del archivo para el que se van a escribir los mensajes.</span><span class="sxs-lookup"><span data-stu-id="44ca9-115">Specifies whether to display a message box when you call the <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType> method; also specifies the name of the file to write messages to.</span></span>|  
|[<span data-ttu-id="44ca9-116">\<performanceCounters></span><span class="sxs-lookup"><span data-stu-id="44ca9-116">\<performanceCounters></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/performancecounters-element.md)|<span data-ttu-id="44ca9-117">Especifica el tamaño de la memoria global que comparten los contadores de rendimiento.</span><span class="sxs-lookup"><span data-stu-id="44ca9-117">Specifies the size of the global memory shared by performance counters.</span></span>|  
|[<span data-ttu-id="44ca9-118">\<sharedListeners></span><span class="sxs-lookup"><span data-stu-id="44ca9-118">\<sharedListeners></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/sharedlisteners-element.md)|<span data-ttu-id="44ca9-119">Contiene los agentes de escucha a los que puede hacer referencia cualquier origen o elemento de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="44ca9-119">Contains listeners that any source or trace element can reference.</span></span> <span data-ttu-id="44ca9-120">Los agentes de escucha identificados como agentes de escucha compartidos se pueden agregar orígenes o seguimiento por nombre.</span><span class="sxs-lookup"><span data-stu-id="44ca9-120">Listeners identified as shared listeners can be added to sources or traces by name.</span></span>|  
|[<span data-ttu-id="44ca9-121">\<sources></span><span class="sxs-lookup"><span data-stu-id="44ca9-121">\<sources></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/sources-element.md)|<span data-ttu-id="44ca9-122">Especifica los orígenes de seguimiento que inician mensajes de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="44ca9-122">Specifies trace sources that initiate tracing messages.</span></span>|  
|[<span data-ttu-id="44ca9-123">\<switches></span><span class="sxs-lookup"><span data-stu-id="44ca9-123">\<switches></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/switches-element.md)|<span data-ttu-id="44ca9-124">Contiene modificadores de seguimiento y los niveles donde se establecen los modificadores de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="44ca9-124">Contains trace switches and the levels where the trace switches are set.</span></span>|  
|[<span data-ttu-id="44ca9-125">\<trace></span><span class="sxs-lookup"><span data-stu-id="44ca9-125">\<trace></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/trace-element.md)|<span data-ttu-id="44ca9-126">Contiene agentes de escucha que recopilan, almacenan y enrutan los mensajes de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="44ca9-126">Contains listeners that collect, store, and route tracing messages.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="44ca9-127">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="44ca9-127">Parent Elements</span></span>  
  
|<span data-ttu-id="44ca9-128">Elemento</span><span class="sxs-lookup"><span data-stu-id="44ca9-128">Element</span></span>|<span data-ttu-id="44ca9-129">Descripción</span><span class="sxs-lookup"><span data-stu-id="44ca9-129">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="44ca9-130">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="44ca9-130">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="44ca9-131">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="44ca9-131">Example</span></span>  
 <span data-ttu-id="44ca9-132">El ejemplo siguiente muestra cómo incrustar un modificador de seguimiento y un agente de escucha de seguimiento dentro de la  **\<system.diagnostics >** elemento.</span><span class="sxs-lookup"><span data-stu-id="44ca9-132">The following example shows how to embed a trace switch and a trace listener inside the **\<system.diagnostics>** element.</span></span> <span data-ttu-id="44ca9-133">El `General` modificador de seguimiento está establecido en el <xref:System.Diagnostics.TraceLevel> nivel.</span><span class="sxs-lookup"><span data-stu-id="44ca9-133">The `General` trace switch is set to the <xref:System.Diagnostics.TraceLevel> level.</span></span> <span data-ttu-id="44ca9-134">El agente de escucha de seguimiento `myListener` crea un archivo denominado `MyListener.log` y escribe el resultado en el archivo.</span><span class="sxs-lookup"><span data-stu-id="44ca9-134">The trace listener `myListener` creates a file called `MyListener.log` and writes the output to the file.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="44ca9-135">En la versión 2.0 de .NET Framework, puede utilizar texto para especificar el valor de un modificador.</span><span class="sxs-lookup"><span data-stu-id="44ca9-135">In the .NET Framework version 2.0, you can use text to specify the value for a switch.</span></span> <span data-ttu-id="44ca9-136">Por ejemplo, puede especificar `true` para un <xref:System.Diagnostics.BooleanSwitch> o use el texto que representa un valor de enumeración como `Error` para un <xref:System.Diagnostics.TraceSwitch>.</span><span class="sxs-lookup"><span data-stu-id="44ca9-136">For example, you can specify `true` for a <xref:System.Diagnostics.BooleanSwitch> or use the text representing an enumeration value such as `Error` for a <xref:System.Diagnostics.TraceSwitch>.</span></span> <span data-ttu-id="44ca9-137">La línea `<add name="myTraceSwitch" value="Error" />` es equivalente a `<add name="myTraceSwitch" value="1" />`.</span><span class="sxs-lookup"><span data-stu-id="44ca9-137">The line `<add name="myTraceSwitch" value="Error" />` is equivalent to `<add name="myTraceSwitch" value="1" />`.</span></span>  
  
```xml  
<configuration>  
   <system.diagnostics>  
      <switches>  
         <add name="General" value="4" />  
      </switches>  
      <trace autoflush="true" indentsize="2">  
         <listeners>  
            <add name="myListener" type="System.Diagnostics.TextWriterTraceListener, System, Version=1.0.3300.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" initializeData="MyListener.log" traceOutputOptions="ProcessId, LogicalOperationStack, Timestamp, ThreadId, Callstack, DateTime" />  
         </listeners>  
      </trace>  
   </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="44ca9-138">Vea también</span><span class="sxs-lookup"><span data-stu-id="44ca9-138">See also</span></span>

- <xref:System.Diagnostics.Trace>
- <xref:System.Diagnostics.Debug>
- [<span data-ttu-id="44ca9-139">Esquema de la configuración de seguimiento y depuración</span><span class="sxs-lookup"><span data-stu-id="44ca9-139">Trace and Debug Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)
