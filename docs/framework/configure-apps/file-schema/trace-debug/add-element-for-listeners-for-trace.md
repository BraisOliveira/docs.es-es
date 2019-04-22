---
title: <add> Elemento para <listeners> para <trace>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace/listeners/add
helpviewer_keywords:
- initializeData attribute
- <add> element for <listeners>
- add element for <listeners>
ms.assetid: 81e804a3-ef11-4d39-bbde-bfa012c179e2
ms.openlocfilehash: ba0ffc4f95b9af7fcd319068501ce0bb9714c2ad
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59089587"
---
# <a name="add-element-for-listeners-for-trace"></a><span data-ttu-id="2d87d-102">\<Agregar > elemento para \<los agentes de escucha > para \<seguimiento ></span><span class="sxs-lookup"><span data-stu-id="2d87d-102">\<add> Element for \<listeners> for \<trace></span></span>
<span data-ttu-id="2d87d-103">Agrega un agente de escucha para el **los agentes de escucha** colección.</span><span class="sxs-lookup"><span data-stu-id="2d87d-103">Adds a listener to the **Listeners** collection.</span></span>  
  
 <span data-ttu-id="2d87d-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="2d87d-104">\<configuration></span></span>  
<span data-ttu-id="2d87d-105">\<system.diagnostics></span><span class="sxs-lookup"><span data-stu-id="2d87d-105">\<system.diagnostics></span></span>  
<span data-ttu-id="2d87d-106">\<trace></span><span class="sxs-lookup"><span data-stu-id="2d87d-106">\<trace></span></span>  
<span data-ttu-id="2d87d-107">\<listeners></span><span class="sxs-lookup"><span data-stu-id="2d87d-107">\<listeners></span></span>  
<span data-ttu-id="2d87d-108">\<add></span><span class="sxs-lookup"><span data-stu-id="2d87d-108">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2d87d-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2d87d-109">Syntax</span></span>  
  
```xml  
<add name="name"   
     type="trace listener class name, Version, Culture, PublicKeyToken"  
     initializeData="data"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2d87d-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="2d87d-110">Attributes and Elements</span></span>  
 <span data-ttu-id="2d87d-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="2d87d-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2d87d-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="2d87d-112">Attributes</span></span>  
  
|<span data-ttu-id="2d87d-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="2d87d-113">Attribute</span></span>|<span data-ttu-id="2d87d-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="2d87d-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="2d87d-115">**type**</span><span class="sxs-lookup"><span data-stu-id="2d87d-115">**type**</span></span>|<span data-ttu-id="2d87d-116">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="2d87d-116">Required attribute.</span></span><br /><br /> <span data-ttu-id="2d87d-117">Especifica el tipo del agente de escucha.</span><span class="sxs-lookup"><span data-stu-id="2d87d-117">Specifies the type of the listener.</span></span> <span data-ttu-id="2d87d-118">Debe usar una cadena que cumpla los requisitos especificados en [especificar nombres de tipo completos](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md).</span><span class="sxs-lookup"><span data-stu-id="2d87d-118">You must use a string that meets the requirements specified in [Specifying Fully Qualified Type Names](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md).</span></span>|  
|<span data-ttu-id="2d87d-119">**initializeData**</span><span class="sxs-lookup"><span data-stu-id="2d87d-119">**initializeData**</span></span>|<span data-ttu-id="2d87d-120">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="2d87d-120">Optional attribute.</span></span><br /><br /> <span data-ttu-id="2d87d-121">La cadena pasada al constructor de la clase especificada.</span><span class="sxs-lookup"><span data-stu-id="2d87d-121">The string passed to the constructor for the specified class.</span></span>|  
|<span data-ttu-id="2d87d-122">**name**</span><span class="sxs-lookup"><span data-stu-id="2d87d-122">**name**</span></span>|<span data-ttu-id="2d87d-123">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="2d87d-123">Optional attribute.</span></span><br /><br /> <span data-ttu-id="2d87d-124">Especifica el nombre del agente de escucha.</span><span class="sxs-lookup"><span data-stu-id="2d87d-124">Specifies the name of the listener.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2d87d-125">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="2d87d-125">Child Elements</span></span>  
  
|<span data-ttu-id="2d87d-126">Elemento</span><span class="sxs-lookup"><span data-stu-id="2d87d-126">Element</span></span>|<span data-ttu-id="2d87d-127">Descripción</span><span class="sxs-lookup"><span data-stu-id="2d87d-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2d87d-128">\<filter></span><span class="sxs-lookup"><span data-stu-id="2d87d-128">\<filter></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/filter-element-for-add-for-listeners-for-trace.md)|<span data-ttu-id="2d87d-129">Agrega un filtro a un agente de escucha en el `Listeners` colección para un seguimiento.</span><span class="sxs-lookup"><span data-stu-id="2d87d-129">Adds a filter to a listener in the `Listeners` collection for a trace.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="2d87d-130">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="2d87d-130">Parent Elements</span></span>  
  
|<span data-ttu-id="2d87d-131">Elemento</span><span class="sxs-lookup"><span data-stu-id="2d87d-131">Element</span></span>|<span data-ttu-id="2d87d-132">Descripción</span><span class="sxs-lookup"><span data-stu-id="2d87d-132">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="2d87d-133">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="2d87d-133">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`listeners`|<span data-ttu-id="2d87d-134">Especifica un agente de escucha que recopila, almacena y enruta los mensajes.</span><span class="sxs-lookup"><span data-stu-id="2d87d-134">Specifies a listener that collects, stores, and routes messages.</span></span> <span data-ttu-id="2d87d-135">Los agentes de escucha dirigen los resultados de seguimiento a un destino apropiado.</span><span class="sxs-lookup"><span data-stu-id="2d87d-135">Listeners direct the tracing output to an appropriate target.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="2d87d-136">Especifica el elemento raíz de la sección de configuración de ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="2d87d-136">Specifies the root element for the ASP.NET configuration section.</span></span>|  
|`trace`|<span data-ttu-id="2d87d-137">Contiene agentes de escucha que recopilan, almacenan y enrutan los mensajes de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="2d87d-137">Contains listeners that collect, store, and route tracing messages.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2d87d-138">Comentarios</span><span class="sxs-lookup"><span data-stu-id="2d87d-138">Remarks</span></span>  
 <span data-ttu-id="2d87d-139">El <xref:System.Diagnostics.Debug> y <xref:System.Diagnostics.Trace> clases comparten el mismo **los agentes de escucha** colección.</span><span class="sxs-lookup"><span data-stu-id="2d87d-139">The <xref:System.Diagnostics.Debug> and <xref:System.Diagnostics.Trace> classes share the same **Listeners** collection.</span></span> <span data-ttu-id="2d87d-140">Si agrega un objeto de escucha a la colección en una de estas clases, la otra clase usa el mismo agente de escucha.</span><span class="sxs-lookup"><span data-stu-id="2d87d-140">If you add a listener object to the collection in one of these classes, the other class uses the same listener.</span></span> <span data-ttu-id="2d87d-141">El agente de escucha clases se derivan de la <xref:System.Diagnostics.TraceListener>.</span><span class="sxs-lookup"><span data-stu-id="2d87d-141">The listener classes derive from the <xref:System.Diagnostics.TraceListener>.</span></span>  
  
 <span data-ttu-id="2d87d-142">Si no especifica la `name` atributo del agente de escucha de seguimiento, la <xref:System.Diagnostics.TraceListener.Name%2A> de los valores predeterminados del agente de escucha de seguimiento en una cadena vacía ("").</span><span class="sxs-lookup"><span data-stu-id="2d87d-142">If you do not specify the `name` attribute of the trace listener, the <xref:System.Diagnostics.TraceListener.Name%2A> of the trace listener defaults to an empty string ("").</span></span> <span data-ttu-id="2d87d-143">Si la aplicación tiene sólo un agente de escucha, puede agregarlo sin especificar un nombre y quitarlo especificando una cadena vacía para el nombre.</span><span class="sxs-lookup"><span data-stu-id="2d87d-143">If your application has only one listener, you can add it without specifying a name, and remove it by specifying an empty string for the name.</span></span> <span data-ttu-id="2d87d-144">Sin embargo, si la aplicación tiene más de un agente de escucha, debe especificar nombres únicos para cada agente de escucha de seguimiento, lo que permite identificar y administrar los agentes de escucha de seguimiento individuales dentro de la <xref:System.Diagnostics.Debug.Listeners%2A> y <xref:System.Diagnostics.Trace.Listeners%2A> colecciones.</span><span class="sxs-lookup"><span data-stu-id="2d87d-144">However, if your application has more than one listener, you should specify unique names for each trace listener, which allows you to identify and manage individual trace listeners within the <xref:System.Diagnostics.Debug.Listeners%2A> and <xref:System.Diagnostics.Trace.Listeners%2A> collections.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2d87d-145">Agregar más de un agente de escucha de seguimiento del mismo tipo y con el mismo nombre da como resultado del agente de escucha de solo seguimiento de ese tipo y nombre que se va a agregar a la `Listeners` colección.</span><span class="sxs-lookup"><span data-stu-id="2d87d-145">Adding more than one trace listener of the same type and with the same name results in only one trace listener of that type and name being added to the `Listeners` collection.</span></span> <span data-ttu-id="2d87d-146">Sin embargo, puede agregar mediante programación varios agentes de escucha idénticos a los `Listeners` colección.</span><span class="sxs-lookup"><span data-stu-id="2d87d-146">However, you can programmatically add multiple identical listeners to the `Listeners` collection.</span></span>  
  
 <span data-ttu-id="2d87d-147">El valor de la **initializeData** atributo depende del tipo de agente de escucha que cree.</span><span class="sxs-lookup"><span data-stu-id="2d87d-147">The value for the **initializeData** attribute depends on the type of listener you create.</span></span> <span data-ttu-id="2d87d-148">No todos los agentes de escucha de seguimiento requieren que se especifique **initializeData**.</span><span class="sxs-lookup"><span data-stu-id="2d87d-148">Not all trace listeners require that you specify **initializeData**.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2d87d-149">Cuando se usa el `initializeData` atributo, es posible que obtenga el compilador advertencia "no se declara el atributo 'initializeData'".</span><span class="sxs-lookup"><span data-stu-id="2d87d-149">When you use the `initializeData` attribute, you may get the compiler warning "The 'initializeData' attribute is not declared."</span></span> <span data-ttu-id="2d87d-150">Esta advertencia se produce porque se validan los valores de configuración con la clase base abstracta <xref:System.Diagnostics.TraceListener>, que no reconoce el `initializeData` atributo.</span><span class="sxs-lookup"><span data-stu-id="2d87d-150">This warning occurs because the configuration settings are validated against the abstract base class <xref:System.Diagnostics.TraceListener>, which does not recognize the `initializeData` attribute.</span></span> <span data-ttu-id="2d87d-151">Por lo general, puede omitir esta advertencia para las implementaciones de agente de escucha de seguimiento que tiene un constructor que toma un parámetro.</span><span class="sxs-lookup"><span data-stu-id="2d87d-151">Typically, you can ignore this warning for trace listener implementations that have a constructor that takes a parameter.</span></span>  
  
 <span data-ttu-id="2d87d-152">En la tabla siguiente se muestran los agentes de escucha de seguimiento que se incluyen con .NET Framework y se describe el valor de sus **initializeData** atributos.</span><span class="sxs-lookup"><span data-stu-id="2d87d-152">The following table shows the trace listeners that are included with the .NET Framework and describes the value of their **initializeData** attributes.</span></span>  
  
|<span data-ttu-id="2d87d-153">Clase de agente de escucha de seguimiento</span><span class="sxs-lookup"><span data-stu-id="2d87d-153">Trace listener class</span></span>|<span data-ttu-id="2d87d-154">valor del atributo initializeData</span><span class="sxs-lookup"><span data-stu-id="2d87d-154">initializeData attribute value</span></span>|  
|--------------------------|------------------------------------|  
|<xref:System.Diagnostics.ConsoleTraceListener?displayProperty=nameWithType>|<span data-ttu-id="2d87d-155">El `useErrorStream` valor para el <xref:System.Diagnostics.ConsoleTraceListener.%23ctor%2A> constructor.</span><span class="sxs-lookup"><span data-stu-id="2d87d-155">The `useErrorStream` value for the <xref:System.Diagnostics.ConsoleTraceListener.%23ctor%2A> constructor.</span></span>  <span data-ttu-id="2d87d-156">Establecer el `initializeData` atributo para "`true`" escribir, trace y debug de salida a <xref:System.Console.Error%2A?displayProperty=nameWithType>; "`false`" para escribir en <xref:System.Console.Out%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="2d87d-156">Set the `initializeData` attribute to "`true`" to write trace and debug output to <xref:System.Console.Error%2A?displayProperty=nameWithType>; "`false`" to write to <xref:System.Console.Out%2A?displayProperty=nameWithType>.</span></span>|  
|<xref:System.Diagnostics.DelimitedListTraceListener?displayProperty=nameWithType>|<span data-ttu-id="2d87d-157">El nombre del archivo de la <xref:System.Diagnostics.DelimitedListTraceListener> escribe en.</span><span class="sxs-lookup"><span data-stu-id="2d87d-157">The name of the file the <xref:System.Diagnostics.DelimitedListTraceListener> writes to.</span></span>|  
|<xref:System.Diagnostics.EventLogTraceListener?displayProperty=nameWithType>|<span data-ttu-id="2d87d-158">El nombre del nombre de un origen de registro de eventos existente.</span><span class="sxs-lookup"><span data-stu-id="2d87d-158">The name of the name of an existing event log source.</span></span>|  
|<xref:System.Diagnostics.EventSchemaTraceListener?displayProperty=nameWithType>|<span data-ttu-id="2d87d-159">El nombre del archivo que el <xref:System.Diagnostics.EventSchemaTraceListener> escribe en.</span><span class="sxs-lookup"><span data-stu-id="2d87d-159">The name of the file that the <xref:System.Diagnostics.EventSchemaTraceListener> writes to.</span></span>|  
|<xref:System.Diagnostics.TextWriterTraceListener?displayProperty=nameWithType>|<span data-ttu-id="2d87d-160">El nombre del archivo que el <xref:System.Diagnostics.TextWriterTraceListener> escribe en.</span><span class="sxs-lookup"><span data-stu-id="2d87d-160">The name of the file that the <xref:System.Diagnostics.TextWriterTraceListener> writes to.</span></span>|  
|<xref:System.Diagnostics.XmlWriterTraceListener?displayProperty=nameWithType>|<span data-ttu-id="2d87d-161">El nombre del archivo que el <xref:System.Diagnostics.XmlWriterTraceListener> escribe en.</span><span class="sxs-lookup"><span data-stu-id="2d87d-161">The name of the file that the <xref:System.Diagnostics.XmlWriterTraceListener> writes to.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="2d87d-162">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="2d87d-162">Example</span></span>  
 <span data-ttu-id="2d87d-163">El ejemplo siguiente muestra cómo usar  **\<Agregar >** elementos para agregar los agentes de escucha `MyListener` y `MyEventListener` a la **los agentes de escucha** colección.</span><span class="sxs-lookup"><span data-stu-id="2d87d-163">The following example shows how to use **\<add>** elements to add the listeners `MyListener` and `MyEventListener` to the **Listeners** collection.</span></span> <span data-ttu-id="2d87d-164">`MyListener` crea un archivo denominado `MyListener.log` y escribe el resultado en el archivo.</span><span class="sxs-lookup"><span data-stu-id="2d87d-164">`MyListener` creates a file called `MyListener.log` and writes the output to the file.</span></span> <span data-ttu-id="2d87d-165">`MyEventListener` crea una entrada en el registro de eventos.</span><span class="sxs-lookup"><span data-stu-id="2d87d-165">`MyEventListener` creates an entry in the event log.</span></span>  
  
```xml  
<configuration>  
   <system.diagnostics>  
      <trace autoflush="true" indentsize="0">  
         <listeners>  
            <add name="myListener" type="System.Diagnostics.TextWriterTraceListener, system, version=1.0.3300.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" initializeData="c:\myListener.log" />  
            <add name="MyEventListener"  
                 type="System.Diagnostics.EventLogTraceListener, system, version=1.0.3300.0, Culture=neutral, PublicKeyToken=b77a5c561934e089"                 initializeData="MyConfigEventLog"/>  
            <add name="configConsoleListener"  
                 type="System.Diagnostics.ConsoleTraceListener, system, version=1.0.3300.0, Culture=neutral, PublicKeyToken=b77a5c561934e089"/>  
         </listeners>  
      </trace>  
   </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="2d87d-166">Vea también</span><span class="sxs-lookup"><span data-stu-id="2d87d-166">See also</span></span>

- <xref:System.Diagnostics.Trace>
- <xref:System.Diagnostics.Debug>
- <xref:System.Diagnostics.EventLogTraceListener>
- <xref:System.Diagnostics.ConsoleTraceListener>
- <xref:System.Diagnostics.TextWriterTraceListener>
- [<span data-ttu-id="2d87d-167">Esquema de la configuración de seguimiento y depuración</span><span class="sxs-lookup"><span data-stu-id="2d87d-167">Trace and Debug Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)
- [<span data-ttu-id="2d87d-168">Agentes de escucha de seguimiento</span><span class="sxs-lookup"><span data-stu-id="2d87d-168">Trace Listeners</span></span>](../../../../../docs/framework/debug-trace-profile/trace-listeners.md)
