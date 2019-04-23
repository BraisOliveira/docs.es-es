---
title: <EnableAmPmParseAdjustment> (Elemento)
ms.date: 03/30/2017
ms.assetid: fda998a5-f538-4f8b-a18c-ee7f35e16938
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 57d1a14199debbb90827c1ea95347d485a636329
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59222515"
---
# <a name="enableampmparseadjustment-element"></a><span data-ttu-id="a62db-102">\<EnableAmPmParseAdjustment > elemento</span><span class="sxs-lookup"><span data-stu-id="a62db-102">\<EnableAmPmParseAdjustment> Element</span></span>
<span data-ttu-id="a62db-103">Determina si la fecha y hora en que los métodos de análisis usan un conjunto ajustado de reglas para analizar las cadenas de fecha que contienen un día, mes, hora y designador AM/PM.</span><span class="sxs-lookup"><span data-stu-id="a62db-103">Determines whether date and time parsing methods use an adjusted set of rules to parse date strings that contain a day, month, hour, and AM/PM designator.</span></span>  
  
 <span data-ttu-id="a62db-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="a62db-104">\<configuration></span></span>  
 <span data-ttu-id="a62db-105">\<runtime></span><span class="sxs-lookup"><span data-stu-id="a62db-105">\<runtime></span></span>  
<span data-ttu-id="a62db-106">\<EnableAmPmParseAdjustment></span><span class="sxs-lookup"><span data-stu-id="a62db-106">\<EnableAmPmParseAdjustment></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a62db-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a62db-107">Syntax</span></span>  
  
```xml  
<EnableAmPmParseAdjustment enabled="0"|"1" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a62db-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="a62db-108">Attributes and Elements</span></span>  
 <span data-ttu-id="a62db-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="a62db-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a62db-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="a62db-110">Attributes</span></span>  
  
|<span data-ttu-id="a62db-111">Atributo</span><span class="sxs-lookup"><span data-stu-id="a62db-111">Attribute</span></span>|<span data-ttu-id="a62db-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="a62db-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="a62db-113">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="a62db-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="a62db-114">Especifica si la fecha y hora en que los métodos de análisis utilizan un conjunto ajustado de reglas para analizar las cadenas de fecha que contienen solo un día, mes, hora y designador AM/PM.</span><span class="sxs-lookup"><span data-stu-id="a62db-114">Specifies whether date and time parsing methods use an adjusted set of rules to parse date strings that contain only a day, month, hour, and AM/PM designator.</span></span>|  
  
### <a name="enabled-attribute"></a><span data-ttu-id="a62db-115">Atributo enabled</span><span class="sxs-lookup"><span data-stu-id="a62db-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="a62db-116">Valor</span><span class="sxs-lookup"><span data-stu-id="a62db-116">Value</span></span>|<span data-ttu-id="a62db-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="a62db-117">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="a62db-118">0</span><span class="sxs-lookup"><span data-stu-id="a62db-118">0</span></span>|<span data-ttu-id="a62db-119">Fecha y hora en que los métodos de análisis no utilizan reglas ajustadas para analizar cadenas de fecha que contienen solo un día, mes, hora y designador AM/PM.</span><span class="sxs-lookup"><span data-stu-id="a62db-119">Date and time parsing methods do not use adjusted rules for parsing date strings that contain only a day, month, hour, and AM/PM designator.</span></span>|  
|<span data-ttu-id="a62db-120">1</span><span class="sxs-lookup"><span data-stu-id="a62db-120">1</span></span>|<span data-ttu-id="a62db-121">Fecha y hora en que los métodos de análisis usan ajustadas reglas para analizar las cadenas de fecha que contienen solo un día, mes, hora y designador AM/PM.</span><span class="sxs-lookup"><span data-stu-id="a62db-121">Date and time parsing methods use adjusted rules for parsing date strings that contain only a day, month, hour, and AM/PM designator.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a62db-122">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="a62db-122">Child Elements</span></span>  
 <span data-ttu-id="a62db-123">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="a62db-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a62db-124">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="a62db-124">Parent Elements</span></span>  
  
|<span data-ttu-id="a62db-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="a62db-125">Element</span></span>|<span data-ttu-id="a62db-126">Descripción</span><span class="sxs-lookup"><span data-stu-id="a62db-126">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="a62db-127">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="a62db-127">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="a62db-128">Contiene información sobre las opciones de inicialización del motor en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="a62db-128">Contains information about runtime initialization options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a62db-129">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a62db-129">Remarks</span></span>  
 <span data-ttu-id="a62db-130">El `<EnableAmPmParseAdjustment>` elemento controla cómo los métodos siguientes para analizar una cadena de fecha que contiene un número de día y mes seguido de una hora y un designador AM/PM (por ejemplo, "4/10 6 a. M."):</span><span class="sxs-lookup"><span data-stu-id="a62db-130">The `<EnableAmPmParseAdjustment>` element controls how the following methods parse a date string that contains a numeric day and month followed by an hour and an AM/PM designator (such as "4/10 6 AM"):</span></span>  
  
-   <xref:System.DateTime.Parse%2A?displayProperty=nameWithType>  
  
-   <xref:System.DateTimeOffset.Parse%2A?displayProperty=nameWithType>  
  
-   <xref:System.DateTime.TryParse%2A?displayProperty=nameWithType>  
  
-   <xref:System.DateTimeOffset.TryParse%2A?displayProperty=nameWithType>  
  
-   <xref:System.Convert.ToDateTime%2A?displayProperty=nameWithType>  
  
 <span data-ttu-id="a62db-131">No hay otros patrones se ven afectados.</span><span class="sxs-lookup"><span data-stu-id="a62db-131">No other patterns are affected.</span></span>  
  
 <span data-ttu-id="a62db-132">El `<EnableAmPmParseAdjustment>` elemento no tiene ningún efecto el <xref:System.DateTime.ParseExact%2A?displayProperty=nameWithType>, <xref:System.DateTime.TryParseExact%2A?displayProperty=nameWithType>, <xref:System.DateTimeOffset.ParseExact%2A?displayProperty=nameWithType>, y <xref:System.DateTimeOffset.TryParseExact%2A?displayProperty=nameWithType> métodos.</span><span class="sxs-lookup"><span data-stu-id="a62db-132">The `<EnableAmPmParseAdjustment>` element has no effect on the  <xref:System.DateTime.ParseExact%2A?displayProperty=nameWithType>,  <xref:System.DateTime.TryParseExact%2A?displayProperty=nameWithType>, <xref:System.DateTimeOffset.ParseExact%2A?displayProperty=nameWithType>, and <xref:System.DateTimeOffset.TryParseExact%2A?displayProperty=nameWithType> methods.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="a62db-133">En .NET Core y .NET Native, se habilitan las reglas de análisis de A.M./P.M. ajustadas de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="a62db-133">In .NET Core and .NET Native, the adjusted AM/PM parsing rules are enabled by default.</span></span>  
  
 <span data-ttu-id="a62db-134">Si no está habilitada la regla de ajuste de análisis, el primer dígito de la cadena se interpreta como la hora del reloj de 12 horas, y se omite el resto de la cadena, excepto el designador AM/PM.</span><span class="sxs-lookup"><span data-stu-id="a62db-134">If the parsing adjustment rule is not enabled, the first digit of the string is interpreted as the hour of the 12-hour clock, and the remainder of the string except for the AM/PM designator is ignored.</span></span> <span data-ttu-id="a62db-135">La fecha y hora devuelto por el método de análisis consta de la fecha actual y la hora del día extraído de la cadena de fecha.</span><span class="sxs-lookup"><span data-stu-id="a62db-135">The date and time returned by the parsing method consists of the current date and the hour of the day extracted from the date string.</span></span>  
  
 <span data-ttu-id="a62db-136">Si está habilitada la regla de ajuste de análisis, el método de análisis interpretar el día y mes como pertenecientes al año actual e interpretar al tiempo que la hora del reloj de 12 horas.</span><span class="sxs-lookup"><span data-stu-id="a62db-136">If the parsing adjustment rule is enabled, parsing method interpret the day and month as belonging to the current year, and interpret the time as the hour of the 12-hour clock.</span></span>  
  
 <span data-ttu-id="a62db-137">En la tabla siguiente se ilustra la diferencia en el <xref:System.DateTime> valor cuando la <xref:System.DateTime.Parse%28System.String%29?displayProperty=nameWithType> método se utiliza para analizar la cadena "" 4/10 6 a. M."con el `<EnableAmPmParseAdjustment>` del elemento `enabled` propiedad establecida en"0"o"1".</span><span class="sxs-lookup"><span data-stu-id="a62db-137">The following table illustrates the difference in the <xref:System.DateTime> value when the <xref:System.DateTime.Parse%28System.String%29?displayProperty=nameWithType> method is used to parse the string ""4/10 6 AM" with the `<EnableAmPmParseAdjustment>` element's `enabled` property  set to "0" or "1".</span></span> <span data-ttu-id="a62db-138">Se supone que la fecha de hoy es del 5 de enero de 2017 y muestra la fecha como si se da formato con la cadena de formato "G" de la referencia cultural especificada.</span><span class="sxs-lookup"><span data-stu-id="a62db-138">It assumes that today's date is January 5, 2017, and displays the date as if it is formatted using the specified culture's "G" format string.</span></span>  
  
|<span data-ttu-id="a62db-139">Nombre de referencia cultural</span><span class="sxs-lookup"><span data-stu-id="a62db-139">Culture name</span></span>|<span data-ttu-id="a62db-140">enabled="0"</span><span class="sxs-lookup"><span data-stu-id="a62db-140">enabled="0"</span></span>|<span data-ttu-id="a62db-141">enabled="1"</span><span class="sxs-lookup"><span data-stu-id="a62db-141">enabled="1"</span></span>|  
|------------------|------------------|------------------|  
|<span data-ttu-id="a62db-142">en-US</span><span class="sxs-lookup"><span data-stu-id="a62db-142">en-US</span></span>|<span data-ttu-id="a62db-143">1/5/2017 4:00:00 A.M.</span><span class="sxs-lookup"><span data-stu-id="a62db-143">1/5/2017 4:00:00 AM</span></span>|<span data-ttu-id="a62db-144">4/10/2017 6:00:00 A.M.</span><span class="sxs-lookup"><span data-stu-id="a62db-144">4/10/2017 6:00:00 AM</span></span>|  
|<span data-ttu-id="a62db-145">en-GB</span><span class="sxs-lookup"><span data-stu-id="a62db-145">en-GB</span></span>|<span data-ttu-id="a62db-146">5/1/2017 6:00:00</span><span class="sxs-lookup"><span data-stu-id="a62db-146">5/1/2017 6:00:00</span></span>|<span data-ttu-id="a62db-147">10/4/2017 6:00:00</span><span class="sxs-lookup"><span data-stu-id="a62db-147">10/4/2017 6:00:00</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a62db-148">Vea también</span><span class="sxs-lookup"><span data-stu-id="a62db-148">See also</span></span>

- [<span data-ttu-id="a62db-149">\<en tiempo de ejecución > elemento</span><span class="sxs-lookup"><span data-stu-id="a62db-149">\<runtime> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md)
- [<span data-ttu-id="a62db-150">Elemento \<configuration></span><span class="sxs-lookup"><span data-stu-id="a62db-150">\<configuration> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)
