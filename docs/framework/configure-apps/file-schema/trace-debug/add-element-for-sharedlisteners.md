---
title: <add> (elemento) para <sharedListeners>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sharedListeners/add
helpviewer_keywords:
- initializeData attribute
- <add> element for <sharedListeners>
- add element for <sharedListeners>
ms.assetid: 1595e1bc-2492-421f-8384-7f382eb8eb57
ms.openlocfilehash: e7934ed5e71005cfd28271298ff6ce1eb8829a0d
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59095638"
---
# <a name="add-element-for-sharedlisteners"></a><span data-ttu-id="40804-102">\<Agregar > elemento para \<sharedListeners ></span><span class="sxs-lookup"><span data-stu-id="40804-102">\<add> Element for \<sharedListeners></span></span>
<span data-ttu-id="40804-103">Agrega un agente de escucha a la colección `sharedListeners`.</span><span class="sxs-lookup"><span data-stu-id="40804-103">Adds a listener to the `sharedListeners` collection.</span></span> `sharedListeners` <span data-ttu-id="40804-104">es una colección de agentes de escucha que cualquier [ \<origen >](../../../../../docs/framework/configure-apps/file-schema/trace-debug/source-element.md) o [ \<seguimiento >](../../../../../docs/framework/configure-apps/file-schema/trace-debug/trace-element.md) puede hacer referencia.</span><span class="sxs-lookup"><span data-stu-id="40804-104">is a collection of listeners that any [\<source>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/source-element.md) or [\<trace>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/trace-element.md) can reference.</span></span>  <span data-ttu-id="40804-105">De forma predeterminada, los agentes de escucha en el `sharedListeners` colección no se colocan en un `Listeners` colección.</span><span class="sxs-lookup"><span data-stu-id="40804-105">By default, listeners in the `sharedListeners` collection are not placed in a `Listeners` collection.</span></span> <span data-ttu-id="40804-106">Deben agregarse por el nombre a la [ \<origen >](../../../../../docs/framework/configure-apps/file-schema/trace-debug/source-element.md) o [ \<seguimiento >](../../../../../docs/framework/configure-apps/file-schema/trace-debug/trace-element.md).</span><span class="sxs-lookup"><span data-stu-id="40804-106">They must be added by name to the [\<source>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/source-element.md) or [\<trace>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/trace-element.md).</span></span> <span data-ttu-id="40804-107">No es posible obtener los agentes de escucha en el `sharedListeners` colección en el código en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="40804-107">It is not possible to get the listeners in the `sharedListeners` collection in code at run time.</span></span>  
  
 <span data-ttu-id="40804-108">\<configuration></span><span class="sxs-lookup"><span data-stu-id="40804-108">\<configuration></span></span>  
<span data-ttu-id="40804-109">&nbsp;&nbsp;\<system.diagnostics></span><span class="sxs-lookup"><span data-stu-id="40804-109">&nbsp;&nbsp;\<system.diagnostics></span></span>  
<span data-ttu-id="40804-110">&nbsp;&nbsp;&nbsp;&nbsp;\<sharedListeners > elemento</span><span class="sxs-lookup"><span data-stu-id="40804-110">&nbsp;&nbsp;&nbsp;&nbsp;\<sharedListeners> Element</span></span>  
<span data-ttu-id="40804-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<add></span><span class="sxs-lookup"><span data-stu-id="40804-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="40804-112">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="40804-112">Syntax</span></span>  
  
```xml  
<add name="name"   
  type="TraceListenerClassName, Version, Culture, PublicKeyToken"  
  initializeData="data"
  traceOutputOptions = "None"
/>  
```
  
## <a name="attributes-and-elements"></a><span data-ttu-id="40804-113">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="40804-113">Attributes and Elements</span></span>  
 <span data-ttu-id="40804-114">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="40804-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="40804-115">Atributos</span><span class="sxs-lookup"><span data-stu-id="40804-115">Attributes</span></span>  
  
|<span data-ttu-id="40804-116">Atributo</span><span class="sxs-lookup"><span data-stu-id="40804-116">Attribute</span></span>|<span data-ttu-id="40804-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="40804-117">Description</span></span>|  
|---------------|-----------------|  
|`name`|<span data-ttu-id="40804-118">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="40804-118">Required attribute.</span></span><br /><br /> <span data-ttu-id="40804-119">Especifica el nombre del agente de escucha que se usa para agregar el agente de escucha compartido una `Listeners` colección.</span><span class="sxs-lookup"><span data-stu-id="40804-119">Specifies the name of the listener that is used to add the shared listener to a `Listeners` collection.</span></span>|  
|`type`|<span data-ttu-id="40804-120">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="40804-120">Required attribute.</span></span><br /><br /> <span data-ttu-id="40804-121">Especifica el tipo del agente de escucha.</span><span class="sxs-lookup"><span data-stu-id="40804-121">Specifies the type of the listener.</span></span> <span data-ttu-id="40804-122">Debe usar una cadena que cumpla los requisitos especificados en [especificar nombres de tipo completos](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md).</span><span class="sxs-lookup"><span data-stu-id="40804-122">You must use a string that meets the requirements specified in [Specifying Fully Qualified Type Names](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md).</span></span>|  
|`initializeData`|<span data-ttu-id="40804-123">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="40804-123">Optional attribute.</span></span><br /><br /> <span data-ttu-id="40804-124">La cadena pasada al constructor de la clase especificada.</span><span class="sxs-lookup"><span data-stu-id="40804-124">The string passed to the constructor for the specified class.</span></span>|  
|`traceOutputOptions`|<span data-ttu-id="40804-125">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="40804-125">Optional attribute.</span></span><br/><br/><span data-ttu-id="40804-126">La representación de cadena de uno o varios <xref:System.Diagnostics.TraceOptions> miembros de enumeración que indica los datos se escriban en el resultado del seguimiento.</span><span class="sxs-lookup"><span data-stu-id="40804-126">The string representation of one or more <xref:System.Diagnostics.TraceOptions> enumeration members that indicates the data to be written to the trace output.</span></span> <span data-ttu-id="40804-127">Varios elementos se separan mediante comas.</span><span class="sxs-lookup"><span data-stu-id="40804-127">Multiple items are separated by commas.</span></span> <span data-ttu-id="40804-128">El valor predeterminado es "None".</span><span class="sxs-lookup"><span data-stu-id="40804-128">The default value is "None".</span></span>|

### <a name="child-elements"></a><span data-ttu-id="40804-129">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="40804-129">Child Elements</span></span>  
  
|<span data-ttu-id="40804-130">Elemento</span><span class="sxs-lookup"><span data-stu-id="40804-130">Element</span></span>|<span data-ttu-id="40804-131">Descripción</span><span class="sxs-lookup"><span data-stu-id="40804-131">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="40804-132">\<filter></span><span class="sxs-lookup"><span data-stu-id="40804-132">\<filter></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/filter-element-for-add-for-sharedlisteners.md)|<span data-ttu-id="40804-133">Agrega un filtro a un agente de escucha en la colección `sharedListeners`.</span><span class="sxs-lookup"><span data-stu-id="40804-133">Adds a filter to a listener in the `sharedListeners` collection.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="40804-134">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="40804-134">Parent Elements</span></span>  
  
|<span data-ttu-id="40804-135">Elemento</span><span class="sxs-lookup"><span data-stu-id="40804-135">Element</span></span>|<span data-ttu-id="40804-136">Descripción</span><span class="sxs-lookup"><span data-stu-id="40804-136">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="40804-137">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="40804-137">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="40804-138">Especifica los agentes de escucha de seguimiento que recopilan, almacenan y enrutan mensajes, así como el nivel en el que está establecido un modificador de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="40804-138">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sharedListeners`|<span data-ttu-id="40804-139">Una colección de agentes de escucha que se puede hacer referencia a cualquier origen o elemento de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="40804-139">A collection of listeners that any source or trace element can reference.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="40804-140">Comentarios</span><span class="sxs-lookup"><span data-stu-id="40804-140">Remarks</span></span>  
 <span data-ttu-id="40804-141">Las clases de agente de escucha incluidas en .NET Framework se derivan de la <xref:System.Diagnostics.TraceListener> clase.</span><span class="sxs-lookup"><span data-stu-id="40804-141">The listener classes shipped with the .NET Framework derive from the <xref:System.Diagnostics.TraceListener> class.</span></span> <span data-ttu-id="40804-142">El valor de la `name` atributo se utiliza para agregar el agente de escucha compartido una `Listeners` colección para un seguimiento o un origen de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="40804-142">The value for the `name` attribute is used to add the shared listener to a `Listeners` collection for either a trace or a trace source.</span></span> <span data-ttu-id="40804-143">El valor de la `initializeData` atributo depende del tipo de agente de escucha que cree.</span><span class="sxs-lookup"><span data-stu-id="40804-143">The value for the `initializeData` attribute depends on the type of listener you create.</span></span> <span data-ttu-id="40804-144">No todos los agentes de escucha de seguimiento requieren que se especifique `initializeData`.</span><span class="sxs-lookup"><span data-stu-id="40804-144">Not all trace listeners require that you specify `initializeData`.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="40804-145">Cuando se usa el `initializeData` atributo, es posible que obtenga el compilador advertencia "no se declara el atributo 'initializeData'".</span><span class="sxs-lookup"><span data-stu-id="40804-145">When you use the `initializeData` attribute, you may get the compiler warning "The 'initializeData' attribute is not declared."</span></span> <span data-ttu-id="40804-146">Esta advertencia se produce porque se validan los valores de configuración con la clase base abstracta <xref:System.Diagnostics.TraceListener>, que no reconoce el `initializeData` atributo.</span><span class="sxs-lookup"><span data-stu-id="40804-146">This warning occurs because the configuration settings are validated against the abstract base class <xref:System.Diagnostics.TraceListener>, which does not recognize the `initializeData` attribute.</span></span> <span data-ttu-id="40804-147">Por lo general, puede omitir esta advertencia para las implementaciones de agente de escucha de seguimiento que tiene un constructor que toma un parámetro.</span><span class="sxs-lookup"><span data-stu-id="40804-147">Typically, you can ignore this warning for trace listener implementations that have a constructor that takes a parameter.</span></span>  
  
 <span data-ttu-id="40804-148">En la tabla siguiente se muestran los agentes de escucha de seguimiento que se incluyen con .NET Framework y se describe el valor de sus `initializeData` atributos.</span><span class="sxs-lookup"><span data-stu-id="40804-148">The following table shows the trace listeners that are included with the .NET Framework and describes the value of their `initializeData` attributes.</span></span>  
  
|<span data-ttu-id="40804-149">Clase de agente de escucha de seguimiento</span><span class="sxs-lookup"><span data-stu-id="40804-149">Trace listener class</span></span>|<span data-ttu-id="40804-150">valor del atributo initializeData</span><span class="sxs-lookup"><span data-stu-id="40804-150">initializeData attribute value</span></span>|  
|--------------------------|------------------------------------|  
|<xref:System.Diagnostics.ConsoleTraceListener>|<span data-ttu-id="40804-151">El `useErrorStream` valor para el <xref:System.Diagnostics.ConsoleTraceListener.%23ctor%2A> constructor.</span><span class="sxs-lookup"><span data-stu-id="40804-151">The `useErrorStream` value for the <xref:System.Diagnostics.ConsoleTraceListener.%23ctor%2A> constructor.</span></span>  <span data-ttu-id="40804-152">Establecer el `initializeData` atributo para "`true`"escribir trace y debug de salida a la secuencia de error estándar; establézcalo en"`false`" para escribir en el flujo de salida estándar.</span><span class="sxs-lookup"><span data-stu-id="40804-152">Set the `initializeData` attribute to "`true`" to write trace and debug output to the standard error stream; set it to "`false`" to write to the standard output stream.</span></span>|  
|<xref:System.Diagnostics.DelimitedListTraceListener>|<span data-ttu-id="40804-153">El nombre del archivo de la <xref:System.Diagnostics.DelimitedListTraceListener> escribe en.</span><span class="sxs-lookup"><span data-stu-id="40804-153">The name of the file the <xref:System.Diagnostics.DelimitedListTraceListener> writes to.</span></span>|  
|<xref:System.Diagnostics.EventLogTraceListener?displayProperty=nameWithType>|<span data-ttu-id="40804-154">El nombre de un origen de registro de eventos existente.</span><span class="sxs-lookup"><span data-stu-id="40804-154">The name of an existing event log source.</span></span>|  
|<xref:System.Diagnostics.EventSchemaTraceListener?displayProperty=nameWithType>|<span data-ttu-id="40804-155">El nombre del archivo que el <xref:System.Diagnostics.EventSchemaTraceListener> escribe en.</span><span class="sxs-lookup"><span data-stu-id="40804-155">The name of the file that the <xref:System.Diagnostics.EventSchemaTraceListener> writes to.</span></span>|  
|<xref:System.Diagnostics.TextWriterTraceListener?displayProperty=nameWithType>|<span data-ttu-id="40804-156">El nombre del archivo que el <xref:System.Diagnostics.TextWriterTraceListener> escribe en.</span><span class="sxs-lookup"><span data-stu-id="40804-156">The name of the file that the <xref:System.Diagnostics.TextWriterTraceListener> writes to.</span></span>|  
|<xref:System.Diagnostics.XmlWriterTraceListener>|<span data-ttu-id="40804-157">El nombre del archivo que el <xref:System.Diagnostics.XmlWriterTraceListener> escribe en.</span><span class="sxs-lookup"><span data-stu-id="40804-157">The name of the file that the <xref:System.Diagnostics.XmlWriterTraceListener> writes to.</span></span>|  
  
## <a name="configuration-file"></a><span data-ttu-id="40804-158">Archivo de configuración</span><span class="sxs-lookup"><span data-stu-id="40804-158">Configuration File</span></span>  
 <span data-ttu-id="40804-159">Este elemento se puede usar en el archivo de configuración del equipo (Machine.config) y el archivo de configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="40804-159">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="40804-160">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="40804-160">Example</span></span>  
 <span data-ttu-id="40804-161">El ejemplo siguiente muestra cómo usar `<add>` elementos que se va a agregar el <xref:System.Diagnostics.TextWriterTraceListener>`textListener` a la `sharedListeners` colección.</span><span class="sxs-lookup"><span data-stu-id="40804-161">The following example shows how to use `<add>` elements to add the <xref:System.Diagnostics.TextWriterTraceListener>`textListener` to the `sharedListeners` collection.</span></span>   `textListener` <span data-ttu-id="40804-162">se agrega por el nombre a la `Listeners` recopilación para el origen de seguimiento `TraceSourceApp`.</span><span class="sxs-lookup"><span data-stu-id="40804-162">is added by name to the `Listeners` collection for the trace source `TraceSourceApp`.</span></span> <span data-ttu-id="40804-163">La `textListener` agente de escucha escribe la salida de seguimiento en el archivo myListener.log.</span><span class="sxs-lookup"><span data-stu-id="40804-163">The `textListener` listener writes trace output to the file myListener.log.</span></span>  
  
```xml  
<configuration>  
  <system.diagnostics>  
    <sources>  
      <source name="TraceSourceApp" switchName="sourceSwitch"   
        switchType="System.Diagnostics.SourceSwitch">  
        <listeners>  
          <add name="console"   
            type="System.Diagnostics.ConsoleTraceListener"/>  
          <add name="textListener"/>  
          <remove name="Default"/>  
        </listeners>  
      </source>  
    </sources>  
    <sharedListeners>  
      <add name="textListener"   
        type="System.Diagnostics.TextWriterTraceListener"   
        initializeData="myListener.log"/>  
    </sharedListeners>  
    <switches>  
      <add name="sourceSwitch" value="Warning"/>  
    </switches>  
  </system.diagnostics>  
</configuration>   
```  
  
## <a name="see-also"></a><span data-ttu-id="40804-164">Vea también</span><span class="sxs-lookup"><span data-stu-id="40804-164">See also</span></span>

- <xref:System.Diagnostics.TraceSource>
- <xref:System.Diagnostics.TraceListener>
- [<span data-ttu-id="40804-165">Esquema de la configuración de seguimiento y depuración</span><span class="sxs-lookup"><span data-stu-id="40804-165">Trace and Debug Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)
- [<span data-ttu-id="40804-166">Agentes de escucha de seguimiento</span><span class="sxs-lookup"><span data-stu-id="40804-166">Trace Listeners</span></span>](../../../../../docs/framework/debug-trace-profile/trace-listeners.md)
