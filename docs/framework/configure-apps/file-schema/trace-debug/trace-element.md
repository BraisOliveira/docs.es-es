---
title: <trace> (Elemento)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace
- http://schemas.microsoft.com/.NetConfiguration/v2.0#trace
helpviewer_keywords:
- <trace> element
- listeners
- trace element
- trace listener, <trace> element
ms.assetid: 7931c942-63c1-47c3-a045-9d9de3cacdbf
ms.openlocfilehash: fd90d271591a47849b3f70aea50cbe909b6fd613
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69920408"
---
# <a name="trace-element"></a><span data-ttu-id="0ac2d-102">\<Elemento > de seguimiento</span><span class="sxs-lookup"><span data-stu-id="0ac2d-102">\<trace> Element</span></span>
<span data-ttu-id="0ac2d-103">Contiene agentes de escucha que recopilan, almacenan y enrutan los mensajes de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="0ac2d-103">Contains listeners that collect, store, and route tracing messages.</span></span>  
  
 <span data-ttu-id="0ac2d-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="0ac2d-104">\<configuration></span></span>  
<span data-ttu-id="0ac2d-105">\<system.diagnostics></span><span class="sxs-lookup"><span data-stu-id="0ac2d-105">\<system.diagnostics></span></span>  
<span data-ttu-id="0ac2d-106">\<> de seguimiento</span><span class="sxs-lookup"><span data-stu-id="0ac2d-106">\<trace></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0ac2d-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0ac2d-107">Syntax</span></span>  
  
```xml  
<trace autoflush="true|false"   
       indentsize="indent value"  
       useGlobalLock="true| false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0ac2d-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="0ac2d-108">Attributes and Elements</span></span>  
 <span data-ttu-id="0ac2d-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="0ac2d-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0ac2d-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="0ac2d-110">Attributes</span></span>  
  
|<span data-ttu-id="0ac2d-111">Atributo</span><span class="sxs-lookup"><span data-stu-id="0ac2d-111">Attribute</span></span>|<span data-ttu-id="0ac2d-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="0ac2d-112">Description</span></span>|  
|---------------|-----------------|  
|`autoflush`|<span data-ttu-id="0ac2d-113">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="0ac2d-113">Optional attribute.</span></span><br /><br /> <span data-ttu-id="0ac2d-114">Especifica si los agentes de escucha de seguimiento vacían automáticamente el búfer de salida después de cada operación de escritura.</span><span class="sxs-lookup"><span data-stu-id="0ac2d-114">Specifies whether the trace listeners automatically flush the output buffer after every write operation.</span></span>|  
|`indentsize`|<span data-ttu-id="0ac2d-115">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="0ac2d-115">Optional attribute.</span></span><br /><br /> <span data-ttu-id="0ac2d-116">Especifica el número de espacios a los que se va a aplicar sangría.</span><span class="sxs-lookup"><span data-stu-id="0ac2d-116">Specifies the number of spaces to indent.</span></span>|  
|`useGlobalLock`|<span data-ttu-id="0ac2d-117">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="0ac2d-117">Optional attribute.</span></span><br /><br /> <span data-ttu-id="0ac2d-118">Indica si se debe usar el bloqueo global.</span><span class="sxs-lookup"><span data-stu-id="0ac2d-118">Indicates whether the global lock should be used.</span></span>|  
  
## <a name="autoflush-attribute"></a><span data-ttu-id="0ac2d-119">AutoFlush (atributo)</span><span class="sxs-lookup"><span data-stu-id="0ac2d-119">autoflush Attribute</span></span>  
  
|<span data-ttu-id="0ac2d-120">Valor</span><span class="sxs-lookup"><span data-stu-id="0ac2d-120">Value</span></span>|<span data-ttu-id="0ac2d-121">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="0ac2d-121">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="0ac2d-122">No vacía automáticamente el búfer de salida.</span><span class="sxs-lookup"><span data-stu-id="0ac2d-122">Does not automatically flush the output buffer.</span></span> <span data-ttu-id="0ac2d-123">Este es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="0ac2d-123">This is the default.</span></span>|  
|`true`|<span data-ttu-id="0ac2d-124">Vacía automáticamente el búfer de salida.</span><span class="sxs-lookup"><span data-stu-id="0ac2d-124">Automatically flushes the output buffer.</span></span>|  
  
## <a name="usegloballock-attribute"></a><span data-ttu-id="0ac2d-125">Atributo useGlobalLock</span><span class="sxs-lookup"><span data-stu-id="0ac2d-125">useGlobalLock Attribute</span></span>  
  
|<span data-ttu-id="0ac2d-126">Valor</span><span class="sxs-lookup"><span data-stu-id="0ac2d-126">Value</span></span>|<span data-ttu-id="0ac2d-127">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="0ac2d-127">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="0ac2d-128">No utiliza el bloqueo global si el agente de escucha es seguro para subprocesos; de lo contrario, utiliza el bloqueo global.</span><span class="sxs-lookup"><span data-stu-id="0ac2d-128">Does not use the global lock if the listener is thread safe; otherwise, uses the global lock.</span></span>|  
|`true`|<span data-ttu-id="0ac2d-129">Utiliza el bloqueo global independientemente de si el agente de escucha es seguro para subprocesos.</span><span class="sxs-lookup"><span data-stu-id="0ac2d-129">Uses the global lock regardless of whether the listener is thread safe.</span></span> <span data-ttu-id="0ac2d-130">Este es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="0ac2d-130">This is the default.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0ac2d-131">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="0ac2d-131">Child Elements</span></span>  
  
|<span data-ttu-id="0ac2d-132">Elemento</span><span class="sxs-lookup"><span data-stu-id="0ac2d-132">Element</span></span>|<span data-ttu-id="0ac2d-133">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="0ac2d-133">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0ac2d-134">\<listeners></span><span class="sxs-lookup"><span data-stu-id="0ac2d-134">\<listeners></span></span>](listeners-element-for-trace.md)|<span data-ttu-id="0ac2d-135">Especifica un agente de escucha que recopila, almacena y enruta los mensajes.</span><span class="sxs-lookup"><span data-stu-id="0ac2d-135">Specifies a listener that collects, stores, and routes messages.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="0ac2d-136">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="0ac2d-136">Parent Elements</span></span>  
  
|<span data-ttu-id="0ac2d-137">Elemento</span><span class="sxs-lookup"><span data-stu-id="0ac2d-137">Element</span></span>|<span data-ttu-id="0ac2d-138">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="0ac2d-138">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="0ac2d-139">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="0ac2d-139">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="0ac2d-140">Especifica los agentes de escucha de seguimiento que recopilan, almacenan y enrutan mensajes, así como el nivel en el que está establecido un modificador de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="0ac2d-140">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="0ac2d-141">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="0ac2d-141">Example</span></span>  
 <span data-ttu-id="0ac2d-142">En el ejemplo siguiente se muestra cómo usar `<trace>` el elemento para agregar el `MyListener` agente de escucha `Listeners` a la colección.</span><span class="sxs-lookup"><span data-stu-id="0ac2d-142">The following example shows how to use the `<trace>` element to add the listener `MyListener` to the `Listeners` collection.</span></span> <span data-ttu-id="0ac2d-143">`MyListener`crea un archivo denominado `MyListener.log` y escribe el resultado en el archivo.</span><span class="sxs-lookup"><span data-stu-id="0ac2d-143">`MyListener` creates a file that is named `MyListener.log` and writes the output to the file.</span></span> <span data-ttu-id="0ac2d-144">El `useGlobalLock` atributo se establece en `false`, lo que hace que no se use el bloqueo global si el agente de escucha de seguimiento es seguro para subprocesos.</span><span class="sxs-lookup"><span data-stu-id="0ac2d-144">The `useGlobalLock` attribute is set to `false`, which causes the global lock not to be used if the trace listener is thread safe.</span></span> <span data-ttu-id="0ac2d-145">El `autoflush` atributo se establece en `true`, que hace que el agente de escucha de seguimiento escriba en el archivo independientemente de <xref:System.Diagnostics.Trace.Flush%2A?displayProperty=nameWithType> si se llama al método.</span><span class="sxs-lookup"><span data-stu-id="0ac2d-145">The `autoflush` attribute is set to `true`, which causes the trace listener to write to the file regardless of whether the <xref:System.Diagnostics.Trace.Flush%2A?displayProperty=nameWithType> method is called.</span></span> <span data-ttu-id="0ac2d-146">El `indentsize` atributo se establece en 0 (cero), lo que hace que el agente de escucha Aplique sangría a <xref:System.Diagnostics.Trace.Indent%2A?displayProperty=nameWithType> cero espacios cuando se llama al método.</span><span class="sxs-lookup"><span data-stu-id="0ac2d-146">The `indentsize` attribute is set to 0 (zero), which causes the listener to indent zero spaces when the <xref:System.Diagnostics.Trace.Indent%2A?displayProperty=nameWithType> method is called.</span></span>  
  
```xml  
<configuration>  
   <system.diagnostics>  
      <trace useGlobalLock="false" autoflush="true" indentsize="0">  
         <listeners>  
            <add name="myListener" type="System.Diagnostics.TextWriterTraceListener, system version=1.0.3300.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" initializeData="c:\myListener.log" />  
         </listeners>  
      </trace>  
   </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="0ac2d-147">Vea también</span><span class="sxs-lookup"><span data-stu-id="0ac2d-147">See also</span></span>

- <xref:System.Diagnostics.TraceListener>
- <xref:System.Diagnostics.DefaultTraceListener>
- <xref:System.Diagnostics.TextWriterTraceListener>
- <xref:System.Diagnostics.EventLogTraceListener>
- [<span data-ttu-id="0ac2d-148">Esquema de la configuración de seguimiento y depuración</span><span class="sxs-lookup"><span data-stu-id="0ac2d-148">Trace and Debug Settings Schema</span></span>](index.md)
