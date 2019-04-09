---
title: <remove> Elemento para <listeners> para <trace>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace/listeners/remove
helpviewer_keywords:
- remove element
- <remove> element
ms.assetid: 9a5cd1b5-be1a-485f-8f0c-2890ad3ef3e0
ms.openlocfilehash: adf00394bc0bfe808836e74214003cd2078204e4
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59164260"
---
# <a name="remove-element-for-listeners-for-trace"></a><span data-ttu-id="081b8-102">\<Quitar > (elemento) para \<los agentes de escucha > para \<seguimiento ></span><span class="sxs-lookup"><span data-stu-id="081b8-102">\<remove> Element for \<listeners> for \<trace></span></span>
<span data-ttu-id="081b8-103">Quita un agente de escucha el **los agentes de escucha** colección.</span><span class="sxs-lookup"><span data-stu-id="081b8-103">Removes a listener from the **Listeners** collection.</span></span>  
  
 <span data-ttu-id="081b8-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="081b8-104">\<configuration></span></span>  
<span data-ttu-id="081b8-105">\<system.diagnostics></span><span class="sxs-lookup"><span data-stu-id="081b8-105">\<system.diagnostics></span></span>  
<span data-ttu-id="081b8-106">\<trace></span><span class="sxs-lookup"><span data-stu-id="081b8-106">\<trace></span></span>  
<span data-ttu-id="081b8-107">\<listeners></span><span class="sxs-lookup"><span data-stu-id="081b8-107">\<listeners></span></span>  
<span data-ttu-id="081b8-108">\<remove></span><span class="sxs-lookup"><span data-stu-id="081b8-108">\<remove></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="081b8-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="081b8-109">Syntax</span></span>  
  
```xml  
<remove name="listener name" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="081b8-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="081b8-110">Attributes and Elements</span></span>  
 <span data-ttu-id="081b8-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="081b8-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="081b8-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="081b8-112">Attributes</span></span>  
  
|<span data-ttu-id="081b8-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="081b8-113">Attribute</span></span>|<span data-ttu-id="081b8-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="081b8-114">Description</span></span>|  
|---------------|-----------------|  
|**<span data-ttu-id="081b8-115">name</span><span class="sxs-lookup"><span data-stu-id="081b8-115">name</span></span>**|<span data-ttu-id="081b8-116">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="081b8-116">Required attribute.</span></span><br /><br /> <span data-ttu-id="081b8-117">El nombre del agente de escucha que se va a quitar de la **los agentes de escucha** colección.</span><span class="sxs-lookup"><span data-stu-id="081b8-117">The name of the listener to remove from the **Listeners** collection.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="081b8-118">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="081b8-118">Child Elements</span></span>  
 <span data-ttu-id="081b8-119">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="081b8-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="081b8-120">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="081b8-120">Parent Elements</span></span>  
  
|<span data-ttu-id="081b8-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="081b8-121">Element</span></span>|<span data-ttu-id="081b8-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="081b8-122">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="081b8-123">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="081b8-123">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`listeners`|<span data-ttu-id="081b8-124">Especifica un agente de escucha que recopila, almacena y enruta los mensajes.</span><span class="sxs-lookup"><span data-stu-id="081b8-124">Specifies a listener that collects, stores, and routes messages.</span></span> <span data-ttu-id="081b8-125">Los agentes de escucha dirigen los resultados de seguimiento a un destino apropiado.</span><span class="sxs-lookup"><span data-stu-id="081b8-125">Listeners direct the tracing output to an appropriate target.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="081b8-126">Especifica los agentes de escucha de seguimiento que recopilan, almacenan y enrutan mensajes, así como el nivel en el que está establecido un modificador de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="081b8-126">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`trace`|<span data-ttu-id="081b8-127">Configura el servicio de seguimiento ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="081b8-127">Configures the ASP.NET trace service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="081b8-128">Comentarios</span><span class="sxs-lookup"><span data-stu-id="081b8-128">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="081b8-129">Quitar el <xref:System.Diagnostics.DefaultTraceListener> desde el `Listeners` colección modifica el comportamiento de la <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>, <xref:System.Diagnostics.Trace.Assert%2A?displayProperty=nameWithType>, <xref:System.Diagnostics.Debug.Fail%2A?displayProperty=nameWithType>, y <xref:System.Diagnostics.Trace.Fail%2A?displayProperty=nameWithType> métodos.</span><span class="sxs-lookup"><span data-stu-id="081b8-129">Removing the <xref:System.Diagnostics.DefaultTraceListener> from the `Listeners` collection alters the behavior of the <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>, <xref:System.Diagnostics.Trace.Assert%2A?displayProperty=nameWithType>, <xref:System.Diagnostics.Debug.Fail%2A?displayProperty=nameWithType>, and <xref:System.Diagnostics.Trace.Fail%2A?displayProperty=nameWithType> methods.</span></span> <span data-ttu-id="081b8-130">Una llamada a un `Assert` o `Fail` método normalmente da como resultado la presentación de un cuadro de mensaje, pero no se muestra el cuadro de mensaje si el <xref:System.Diagnostics.DefaultTraceListener> no está en el `Listeners` colección.</span><span class="sxs-lookup"><span data-stu-id="081b8-130">Calling an `Assert` or `Fail` method normally results in the display of a message box, however the message box is not displayed if the <xref:System.Diagnostics.DefaultTraceListener> is not in the `Listeners` collection.</span></span>  
  
## <a name="example"></a><span data-ttu-id="081b8-131">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="081b8-131">Example</span></span>  
 <span data-ttu-id="081b8-132">El ejemplo siguiente muestra cómo quitar el agente de escucha de seguimiento predeterminado de la traza **los agentes de escucha** colección.</span><span class="sxs-lookup"><span data-stu-id="081b8-132">The following example shows how to remove the default trace listener from the trace **Listeners** collection.</span></span>  
  
```xml  
<configuration>  
   <system.diagnostics>  
      <trace autoflush="true" indentsize="0">  
         <listeners>  
            <remove name="Default" />  
         </listeners>  
      </trace>  
   </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="081b8-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="081b8-133">See also</span></span>

- <xref:System.Diagnostics.TraceListener>
- <xref:System.Diagnostics.DefaultTraceListener>
- <xref:System.Diagnostics.TextWriterTraceListener>
- <xref:System.Diagnostics.EventLogTraceListener>
- [<span data-ttu-id="081b8-134">Esquema de la configuración de seguimiento y depuración</span><span class="sxs-lookup"><span data-stu-id="081b8-134">Trace and Debug Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)
