---
title: < System. Diagnostics (elemento >)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#system.diagnostics
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics
helpviewer_keywords:
- <system.diagnostics> element
- system.diagnostics element
ms.assetid: 3f348f42-fa72-4ff2-aa1c-bb9eecad4bb2
ms.openlocfilehash: f3b4238a8d7028d47122a420526b38ee4f327332
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69926943"
---
# <a name="systemdiagnostics-element"></a><span data-ttu-id="a9963-102">\<Elemento System. Diagnostics ></span><span class="sxs-lookup"><span data-stu-id="a9963-102">\<system.diagnostics> Element</span></span>
<span data-ttu-id="a9963-103">Especifica los agentes de escucha de seguimiento que recopilan, almacenan y enrutan mensajes, así como el nivel en el que está establecido un modificador de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="a9963-103">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>  
  
 <span data-ttu-id="a9963-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="a9963-104">\<configuration></span></span>  
<span data-ttu-id="a9963-105">\<system.diagnostics></span><span class="sxs-lookup"><span data-stu-id="a9963-105">\<system.diagnostics></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a9963-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a9963-106">Syntax</span></span>  
  
```xml  
<system.diagnostics>   
</system.diagnostics>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a9963-107">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="a9963-107">Attributes and Elements</span></span>  
 <span data-ttu-id="a9963-108">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="a9963-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a9963-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="a9963-109">Attributes</span></span>  
 <span data-ttu-id="a9963-110">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="a9963-110">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="a9963-111">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="a9963-111">Child Elements</span></span>  
  
|<span data-ttu-id="a9963-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="a9963-112">Element</span></span>|<span data-ttu-id="a9963-113">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="a9963-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a9963-114">\<assert></span><span class="sxs-lookup"><span data-stu-id="a9963-114">\<assert></span></span>](assert-element.md)|<span data-ttu-id="a9963-115">Especifica si se muestra un cuadro de mensaje cuando se llama al método <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>; también indica el nombre del archivo para el que se van a escribir los mensajes.</span><span class="sxs-lookup"><span data-stu-id="a9963-115">Specifies whether to display a message box when you call the <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType> method; also specifies the name of the file to write messages to.</span></span>|  
|[<span data-ttu-id="a9963-116">\<performanceCounters></span><span class="sxs-lookup"><span data-stu-id="a9963-116">\<performanceCounters></span></span>](performancecounters-element.md)|<span data-ttu-id="a9963-117">Especifica el tamaño de la memoria global que comparten los contadores de rendimiento.</span><span class="sxs-lookup"><span data-stu-id="a9963-117">Specifies the size of the global memory shared by performance counters.</span></span>|  
|[<span data-ttu-id="a9963-118">\<sharedListeners></span><span class="sxs-lookup"><span data-stu-id="a9963-118">\<sharedListeners></span></span>](sharedlisteners-element.md)|<span data-ttu-id="a9963-119">Contiene los agentes de escucha a los que puede hacer referencia cualquier origen o elemento de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="a9963-119">Contains listeners that any source or trace element can reference.</span></span> <span data-ttu-id="a9963-120">Los agentes de escucha identificados como agentes de escucha compartidos se pueden agregar a orígenes o seguimientos por nombre.</span><span class="sxs-lookup"><span data-stu-id="a9963-120">Listeners identified as shared listeners can be added to sources or traces by name.</span></span>|  
|[<span data-ttu-id="a9963-121">\<sources></span><span class="sxs-lookup"><span data-stu-id="a9963-121">\<sources></span></span>](sources-element.md)|<span data-ttu-id="a9963-122">Especifica los orígenes de seguimiento que inician los mensajes de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="a9963-122">Specifies trace sources that initiate tracing messages.</span></span>|  
|[<span data-ttu-id="a9963-123">\<switches></span><span class="sxs-lookup"><span data-stu-id="a9963-123">\<switches></span></span>](switches-element.md)|<span data-ttu-id="a9963-124">Contiene modificadores de seguimiento y los niveles en los que se establecen los modificadores de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="a9963-124">Contains trace switches and the levels where the trace switches are set.</span></span>|  
|[<span data-ttu-id="a9963-125">\<trace></span><span class="sxs-lookup"><span data-stu-id="a9963-125">\<trace></span></span>](trace-element.md)|<span data-ttu-id="a9963-126">Contiene agentes de escucha que recopilan, almacenan y enrutan los mensajes de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="a9963-126">Contains listeners that collect, store, and route tracing messages.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="a9963-127">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="a9963-127">Parent Elements</span></span>  
  
|<span data-ttu-id="a9963-128">Elemento</span><span class="sxs-lookup"><span data-stu-id="a9963-128">Element</span></span>|<span data-ttu-id="a9963-129">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="a9963-129">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="a9963-130">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="a9963-130">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="a9963-131">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a9963-131">Example</span></span>  
 <span data-ttu-id="a9963-132">En el ejemplo siguiente se muestra cómo insertar un modificador de seguimiento y un agente de escucha de seguimiento dentro del  **\<elemento System. Diagnostics >** .</span><span class="sxs-lookup"><span data-stu-id="a9963-132">The following example shows how to embed a trace switch and a trace listener inside the **\<system.diagnostics>** element.</span></span> <span data-ttu-id="a9963-133">El `General` modificador de seguimiento se establece <xref:System.Diagnostics.TraceLevel> en el nivel.</span><span class="sxs-lookup"><span data-stu-id="a9963-133">The `General` trace switch is set to the <xref:System.Diagnostics.TraceLevel> level.</span></span> <span data-ttu-id="a9963-134">El agente de escucha `myListener` de seguimiento crea un `MyListener.log` archivo denominado y escribe el resultado en el archivo.</span><span class="sxs-lookup"><span data-stu-id="a9963-134">The trace listener `myListener` creates a file called `MyListener.log` and writes the output to the file.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a9963-135">En la versión 2.0 de .NET Framework, puede utilizar texto para especificar el valor de un modificador.</span><span class="sxs-lookup"><span data-stu-id="a9963-135">In the .NET Framework version 2.0, you can use text to specify the value for a switch.</span></span> <span data-ttu-id="a9963-136">Por ejemplo `true` , puede especificar para un <xref:System.Diagnostics.BooleanSwitch> o usar el texto que representa `Error` un <xref:System.Diagnostics.TraceSwitch>valor de enumeración como para.</span><span class="sxs-lookup"><span data-stu-id="a9963-136">For example, you can specify `true` for a <xref:System.Diagnostics.BooleanSwitch> or use the text representing an enumeration value such as `Error` for a <xref:System.Diagnostics.TraceSwitch>.</span></span> <span data-ttu-id="a9963-137">La línea `<add name="myTraceSwitch" value="Error" />` es equivalente a `<add name="myTraceSwitch" value="1" />`.</span><span class="sxs-lookup"><span data-stu-id="a9963-137">The line `<add name="myTraceSwitch" value="Error" />` is equivalent to `<add name="myTraceSwitch" value="1" />`.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="a9963-138">Vea también</span><span class="sxs-lookup"><span data-stu-id="a9963-138">See also</span></span>

- <xref:System.Diagnostics.Trace>
- <xref:System.Diagnostics.Debug>
- [<span data-ttu-id="a9963-139">Esquema de la configuración de seguimiento y depuración</span><span class="sxs-lookup"><span data-stu-id="a9963-139">Trace and Debug Settings Schema</span></span>](index.md)
