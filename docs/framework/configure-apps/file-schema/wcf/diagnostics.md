---
title: <diagnostics>
ms.date: 03/30/2017
ms.assetid: 0c2f95c4-cc12-4fb5-a70c-7fc6fa95db58
ms.openlocfilehash: 170cae5b328c86073c1d8e7710bb19e98ab5688c
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69925872"
---
# <a name="diagnostics"></a><span data-ttu-id="109e6-101">\<diagnóstico ></span><span class="sxs-lookup"><span data-stu-id="109e6-101">\<diagnostics></span></span>
<span data-ttu-id="109e6-102">El elemento `diagnostics` define valores que pueden ser utilizados por un administrador para la inspección y control en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="109e6-102">The `diagnostics` element defines settings that can be used by an administrator for run-time inspection and control.</span></span>  
  
 <span data-ttu-id="109e6-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="109e6-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="109e6-104">\<diagnóstico ></span><span class="sxs-lookup"><span data-stu-id="109e6-104">\<diagnostics></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="109e6-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="109e6-105">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <diagnostics etwProviderId="String"
               performanceCounters="Off/ServiceOnly/All/Default"
               wmiProviderEnabled="Boolean">
    <endToEndTracing activityTracing="Boolean"
                     messageFlowTracing="Boolean"
                     propagateActivity="Boolean" />
    <messageLogging logEntireMessage="Boolean"
                    logMalformedMessages="Boolean"
                    logMessagesAtServiceLevel="Boolean"
                    logMessagesAtTransportLevel="Boolean"
                    maxMessagesToLog="Integer"
                    maxSizeOfMessageToLog="Integer">
      <filters>
        <clear />
      </filters>
    </messageLogging>
  </diagnostics>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="109e6-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="109e6-106">Attributes and Elements</span></span>  
 <span data-ttu-id="109e6-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="109e6-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="109e6-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="109e6-108">Attributes</span></span>  
  
|<span data-ttu-id="109e6-109">Atributo</span><span class="sxs-lookup"><span data-stu-id="109e6-109">Attribute</span></span>|<span data-ttu-id="109e6-110">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="109e6-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="109e6-111">etwProviderId</span><span class="sxs-lookup"><span data-stu-id="109e6-111">etwProviderId</span></span>|<span data-ttu-id="109e6-112">Cadena que especifica el identificador del proveedor de la traza de eventos, que escribe los eventos en las sesiones de ETW.</span><span class="sxs-lookup"><span data-stu-id="109e6-112">A string that specifies the identifier for the Event-Tracing provider, which writes events to ETW sessions.</span></span>|  
|<span data-ttu-id="109e6-113">performanceCounters</span><span class="sxs-lookup"><span data-stu-id="109e6-113">performanceCounters</span></span>|<span data-ttu-id="109e6-114">Especifica si se habilitan los contadores de rendimiento para el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="109e6-114">Specifies whether performance counters for the assembly are enabled.</span></span> <span data-ttu-id="109e6-115">Los valores válidos son</span><span class="sxs-lookup"><span data-stu-id="109e6-115">Valid values are</span></span><br /><br /> <span data-ttu-id="109e6-116">Habilitar Los contadores de rendimiento están deshabilitados.</span><span class="sxs-lookup"><span data-stu-id="109e6-116">-   Off: Performance counters are disabled.</span></span><br /><span data-ttu-id="109e6-117">ServiceOnly Solo los contadores de rendimiento relevantes para este servicio están habilitados.</span><span class="sxs-lookup"><span data-stu-id="109e6-117">-   ServiceOnly: Only performance counters relevant to this service is enabled.</span></span><br /><span data-ttu-id="109e6-118">Todos Los contadores de rendimiento se pueden ver en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="109e6-118">-   All: Performance counters can be viewed at runtime.</span></span><br /><span data-ttu-id="109e6-119">Predeterminada Se crea un _WCF_Admin de instancia de contador de rendimiento único.</span><span class="sxs-lookup"><span data-stu-id="109e6-119">-   Default: A single performance counter instance _WCF_Admin is created.</span></span> <span data-ttu-id="109e6-120">Esta instancia se utiliza para habilitar la colección de datos de SQM usados por la infraestructura.</span><span class="sxs-lookup"><span data-stu-id="109e6-120">This instance is used to enable the collection of SQM data for used by the infrastructure.</span></span> <span data-ttu-id="109e6-121">Ninguno de los valores de contador para esta instancia está actualizado y por consiguiente permanecerá a cero.</span><span class="sxs-lookup"><span data-stu-id="109e6-121">None of the counter values for this instance are updated and therefore will remain at zero.</span></span> <span data-ttu-id="109e6-122">Éste es el valor predeterminado si ninguna configuración está presente para WCF.</span><span class="sxs-lookup"><span data-stu-id="109e6-122">This is the default value if no configuration is present for WCF.</span></span>|  
|<span data-ttu-id="109e6-123">wmiProviderEnabled</span><span class="sxs-lookup"><span data-stu-id="109e6-123">wmiProviderEnabled</span></span>|<span data-ttu-id="109e6-124">Un valor booleano que especifica si el proveedor de WMI para el ensamblado está habilitado.</span><span class="sxs-lookup"><span data-stu-id="109e6-124">A Boolean value that specifies whether the WMI provider for the assembly is enabled.</span></span> <span data-ttu-id="109e6-125">El proveedor de WMI se requiere para que el usuario obtenga acceso en tiempo de ejecución a las características de control e inspección de Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="109e6-125">The WMI provider is required for user to gain run-time access to the inspection and control features of Windows Communication Foundation (WCF).</span></span> <span data-ttu-id="109e6-126">El valor predeterminado es `false`.</span><span class="sxs-lookup"><span data-stu-id="109e6-126">The default is `false`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="109e6-127">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="109e6-127">Child Elements</span></span>  
  
|<span data-ttu-id="109e6-128">Elemento</span><span class="sxs-lookup"><span data-stu-id="109e6-128">Element</span></span>|<span data-ttu-id="109e6-129">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="109e6-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="109e6-130">\<endToEndTracing></span><span class="sxs-lookup"><span data-stu-id="109e6-130">\<endToEndTracing></span></span>](endtoendtracing.md)|<span data-ttu-id="109e6-131">Elemento de configuración que le permite habilitar y deshabilitar aspectos diferentes de traza de un extremo a otro durante el funcionamiento de una aplicación de servicio.</span><span class="sxs-lookup"><span data-stu-id="109e6-131">A configuration element that allows you to enable and disable different aspects of end-to-end tracing during the running of a service application.</span></span>|  
|[<span data-ttu-id="109e6-132">\<messageLogging></span><span class="sxs-lookup"><span data-stu-id="109e6-132">\<messageLogging></span></span>](messagelogging.md)|<span data-ttu-id="109e6-133">Describe los valores para el registro de mensajes WCF.</span><span class="sxs-lookup"><span data-stu-id="109e6-133">Describes the settings for WCF message logging.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="109e6-134">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="109e6-134">Parent Elements</span></span>  
  
|<span data-ttu-id="109e6-135">Elemento</span><span class="sxs-lookup"><span data-stu-id="109e6-135">Element</span></span>|<span data-ttu-id="109e6-136">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="109e6-136">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="109e6-137">serviceModel</span><span class="sxs-lookup"><span data-stu-id="109e6-137">serviceModel</span></span>|<span data-ttu-id="109e6-138">Elemento raíz de todos los elementos de configuración de WCF.</span><span class="sxs-lookup"><span data-stu-id="109e6-138">The root element of all WCF configuration elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="109e6-139">Comentarios</span><span class="sxs-lookup"><span data-stu-id="109e6-139">Remarks</span></span>  
 <span data-ttu-id="109e6-140">La sección `diagnostics` define los valores de diagnóstico para todos los servicios situados en un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="109e6-140">The `diagnostics` section defines the diagnostics settings for all services located in an assembly.</span></span> <span data-ttu-id="109e6-141">No es posible definir los valores de diagnóstico independientes en el nivel de servicio a menos que sólo haya un servicio en el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="109e6-141">It is not possible to define separate diagnostics settings at the service level unless there is only one service in the assembly.</span></span> <span data-ttu-id="109e6-142">Los atributos se establecen según los requisitos de la sección.</span><span class="sxs-lookup"><span data-stu-id="109e6-142">Attributes are set according to the requirements of the section.</span></span>  
  
## <a name="example"></a><span data-ttu-id="109e6-143">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="109e6-143">Example</span></span>  
  
```xml  
<diagnostics wmiProviderEnabled="false"
             performanceCounters="all">
  <messageLogging logEntireMessage="true"
                  logMalformedMessages="true"
                  logMessagesAtServiceLevel="true"
                  logMessagesAtTransportLevel="true"
                  maxMessagesToLog="42"
                  maxSizeOfMessageToLog="42">
    <filters>
      <clear />
    </filters>
  </messageLogging>
</diagnostics>
```  
  
## <a name="see-also"></a><span data-ttu-id="109e6-144">Vea también</span><span class="sxs-lookup"><span data-stu-id="109e6-144">See also</span></span>

- <xref:System.ServiceModel.Configuration.DiagnosticSection>
- <xref:System.ServiceModel.Diagnostics>
