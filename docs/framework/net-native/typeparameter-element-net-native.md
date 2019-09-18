---
title: <TypeParameter>Elemento (.NET Native)
ms.date: 03/30/2017
ms.assetid: d37bb1b7-1ddc-4c6d-8ecf-583f804a2479
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0de00b9313b60b3a527dd0380ae90d82731a8c02
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/17/2019
ms.locfileid: "71049061"
---
# <a name="typeparameter-element-net-native"></a><span data-ttu-id="8af53-102">\<Elemento > TypeParameter (.NET Native)</span><span class="sxs-lookup"><span data-stu-id="8af53-102">\<TypeParameter> Element (.NET Native)</span></span>
<span data-ttu-id="8af53-103">Aplica la directiva al tipo representado por un argumento de tipo pasado a un método.</span><span class="sxs-lookup"><span data-stu-id="8af53-103">Applies policy to the type represented by a Type argument passed to a method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8af53-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8af53-104">Syntax</span></span>  
  
```xml  
<Parameter Name="parameter_name"  
           Activate="policy_type"  
           Browse="policy_type"  
           Dynamic="policy_type"  
           Serialize="policy_type"  
           DataContractSerializer="policy_type"  
           DataContractJsonSerializer="policy_type"  
           XmlSerializer="policy_type"  
           MarshalObject="policy_type"  
           MarshalDelegate="policy_type"  
           MarshalStructure="policy_type" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8af53-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="8af53-105">Attributes and Elements</span></span>  
 <span data-ttu-id="8af53-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="8af53-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8af53-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="8af53-107">Attributes</span></span>  
  
|<span data-ttu-id="8af53-108">Atributo</span><span class="sxs-lookup"><span data-stu-id="8af53-108">Attribute</span></span>|<span data-ttu-id="8af53-109">Tipo de atributo</span><span class="sxs-lookup"><span data-stu-id="8af53-109">Attribute type</span></span>|<span data-ttu-id="8af53-110">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="8af53-110">Description</span></span>|  
|---------------|--------------------|-----------------|  
|`Name`|<span data-ttu-id="8af53-111">General</span><span class="sxs-lookup"><span data-stu-id="8af53-111">General</span></span>|<span data-ttu-id="8af53-112">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="8af53-112">Required attribute.</span></span> <span data-ttu-id="8af53-113">Nombre del parámetro de tipo <xref:System.Type>.</span><span class="sxs-lookup"><span data-stu-id="8af53-113">The name of the parameter of type <xref:System.Type>.</span></span> <span data-ttu-id="8af53-114">Por ejemplo, en la firma de método `Type.GetInterfaceMap(Type interfaceType)`, el valor del atributo `Name` es "interfaceType".</span><span class="sxs-lookup"><span data-stu-id="8af53-114">For example, for the method signature `Type.GetInterfaceMap(Type interfaceType)`, the value of the `Name` attribute is "interfaceType".</span></span>|  
|`Activate`|<span data-ttu-id="8af53-115">Reflexión</span><span class="sxs-lookup"><span data-stu-id="8af53-115">Reflection</span></span>|<span data-ttu-id="8af53-116">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="8af53-116">Optional attribute.</span></span> <span data-ttu-id="8af53-117">Controla el acceso en tiempo de ejecución a los constructores para permitir la activación de instancias.</span><span class="sxs-lookup"><span data-stu-id="8af53-117">Controls runtime access to constructors to enable activation of instances.</span></span>|  
|`Browse`|<span data-ttu-id="8af53-118">Reflexión</span><span class="sxs-lookup"><span data-stu-id="8af53-118">Reflection</span></span>|<span data-ttu-id="8af53-119">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="8af53-119">Optional attribute.</span></span> <span data-ttu-id="8af53-120">Controla la consulta para obtener información sobre los elementos de programa, pero no permite el acceso en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="8af53-120">Controls querying for information about program elements, but does not enable any runtime access.</span></span>|  
|`Dynamic`|<span data-ttu-id="8af53-121">Reflexión</span><span class="sxs-lookup"><span data-stu-id="8af53-121">Reflection</span></span>|<span data-ttu-id="8af53-122">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="8af53-122">Optional attribute.</span></span> <span data-ttu-id="8af53-123">Controla el acceso en tiempo de ejecución a todos los miembros de tipo (incluidos constructores, métodos, campos, propiedades y eventos) para permitir la programación dinámica.</span><span class="sxs-lookup"><span data-stu-id="8af53-123">Controls runtime access to all type members, including constructors, methods, fields, properties, and events, to enable dynamic programming.</span></span>|  
|`Serialize`|<span data-ttu-id="8af53-124">Serialización</span><span class="sxs-lookup"><span data-stu-id="8af53-124">Serialization</span></span>|<span data-ttu-id="8af53-125">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="8af53-125">Optional attribute.</span></span> <span data-ttu-id="8af53-126">Controla el acceso en tiempo de ejecución a constructores, campos y propiedades para permitir que bibliotecas como el serializador JSON Newtonsoft puedan serializar y deserializar instancias de tipo.</span><span class="sxs-lookup"><span data-stu-id="8af53-126">Controls runtime access to constructors, fields, and properties, to enable type instances to be serialized and deserialized by libraries such as the Newtonsoft JSON serializer.</span></span>|  
|`DataContractSerializer`|<span data-ttu-id="8af53-127">Serialización</span><span class="sxs-lookup"><span data-stu-id="8af53-127">Serialization</span></span>|<span data-ttu-id="8af53-128">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="8af53-128">Optional attribute.</span></span> <span data-ttu-id="8af53-129">Controla la directiva de serialización que usa la clase <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="8af53-129">Controls policy for serialization that uses the <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType> class.</span></span>|  
|`DataContractJsonSerializer`|<span data-ttu-id="8af53-130">Serialización</span><span class="sxs-lookup"><span data-stu-id="8af53-130">Serialization</span></span>|<span data-ttu-id="8af53-131">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="8af53-131">Optional attribute.</span></span> <span data-ttu-id="8af53-132">Controla la directiva de serialización JSON que usa la clase <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="8af53-132">Controls policy for JSON serialization that uses the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer?displayProperty=nameWithType> class.</span></span>|  
|`XmlSerializer`|<span data-ttu-id="8af53-133">Serialización</span><span class="sxs-lookup"><span data-stu-id="8af53-133">Serialization</span></span>|<span data-ttu-id="8af53-134">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="8af53-134">Optional attribute.</span></span> <span data-ttu-id="8af53-135">Controla la directiva de serialización XML que usa la clase <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="8af53-135">Controls policy for XML serialization that uses the <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType> class.</span></span>|  
|`MarshalObject`|<span data-ttu-id="8af53-136">Interop</span><span class="sxs-lookup"><span data-stu-id="8af53-136">Interop</span></span>|<span data-ttu-id="8af53-137">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="8af53-137">Optional attribute.</span></span> <span data-ttu-id="8af53-138">Controla la directiva de serialización de tipos de referencia a Windows Runtime y COM.</span><span class="sxs-lookup"><span data-stu-id="8af53-138">Controls policy for marshaling reference types to Windows Runtime and COM.</span></span>|  
|`MarshalDelegate`|<span data-ttu-id="8af53-139">Interop</span><span class="sxs-lookup"><span data-stu-id="8af53-139">Interop</span></span>|<span data-ttu-id="8af53-140">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="8af53-140">Optional attribute.</span></span> <span data-ttu-id="8af53-141">Controla la directiva de serialización de tipos de delegado como punteros de función a código nativo.</span><span class="sxs-lookup"><span data-stu-id="8af53-141">Controls policy for marshaling delegate types as function pointers to native code.</span></span>|  
|`MarshalStructure`|<span data-ttu-id="8af53-142">Interop</span><span class="sxs-lookup"><span data-stu-id="8af53-142">Interop</span></span>|<span data-ttu-id="8af53-143">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="8af53-143">Optional attribute.</span></span> <span data-ttu-id="8af53-144">Controla la directiva de cálculo de referencias de tipos de valor a código nativo.</span><span class="sxs-lookup"><span data-stu-id="8af53-144">Controls policy for marshaling value types to native code.</span></span>|  
  
## <a name="name-attribute"></a><span data-ttu-id="8af53-145">Name (atributo)</span><span class="sxs-lookup"><span data-stu-id="8af53-145">Name attribute</span></span>  
  
|<span data-ttu-id="8af53-146">Value</span><span class="sxs-lookup"><span data-stu-id="8af53-146">Value</span></span>|<span data-ttu-id="8af53-147">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="8af53-147">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="8af53-148">*parameter_name*</span><span class="sxs-lookup"><span data-stu-id="8af53-148">*parameter_name*</span></span>|<span data-ttu-id="8af53-149">Nombre del parámetro de tipo <xref:System.Type>.</span><span class="sxs-lookup"><span data-stu-id="8af53-149">The name of the parameter of type <xref:System.Type>.</span></span> <span data-ttu-id="8af53-150">Por ejemplo, en la firma de método `Type.GetInterfaceMap(Type interfaceType)`, el valor del atributo `Name` es "interfaceType".</span><span class="sxs-lookup"><span data-stu-id="8af53-150">For example, for the method signature `Type.GetInterfaceMap(Type interfaceType)`, the value of the `Name` attribute is "interfaceType".</span></span>|  
  
## <a name="all-other-attributes"></a><span data-ttu-id="8af53-151">Resto de atributos</span><span class="sxs-lookup"><span data-stu-id="8af53-151">All other attributes</span></span>  
  
|<span data-ttu-id="8af53-152">Valor</span><span class="sxs-lookup"><span data-stu-id="8af53-152">Value</span></span>|<span data-ttu-id="8af53-153">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="8af53-153">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="8af53-154">*policy_setting*</span><span class="sxs-lookup"><span data-stu-id="8af53-154">*policy_setting*</span></span>|<span data-ttu-id="8af53-155">Configuración que se va a aplicar a este tipo de directiva.</span><span class="sxs-lookup"><span data-stu-id="8af53-155">The setting to apply to this policy type.</span></span> <span data-ttu-id="8af53-156">Los valores posibles son `All`, `Public`, `PublicAndInternal`, `Required Public`, `Required PublicAndInternal` y `Required All`.</span><span class="sxs-lookup"><span data-stu-id="8af53-156">Possible values are `All`, `Public`, `PublicAndInternal`, `Required Public`, `Required PublicAndInternal`, and `Required All`.</span></span> <span data-ttu-id="8af53-157">Para obtener más información, vea [Runtime Directive Policy Settings](runtime-directive-policy-settings.md) (Configuración de directiva de la directiva en tiempo de ejecución).</span><span class="sxs-lookup"><span data-stu-id="8af53-157">For more information, see [Runtime Directive Policy Settings](runtime-directive-policy-settings.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8af53-158">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="8af53-158">Child Elements</span></span>  
 <span data-ttu-id="8af53-159">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="8af53-159">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="8af53-160">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="8af53-160">Parent Elements</span></span>  
  
|<span data-ttu-id="8af53-161">Elemento</span><span class="sxs-lookup"><span data-stu-id="8af53-161">Element</span></span>|<span data-ttu-id="8af53-162">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="8af53-162">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8af53-163">\<Method></span><span class="sxs-lookup"><span data-stu-id="8af53-163">\<Method></span></span>](method-element-net-native.md)|<span data-ttu-id="8af53-164">Aplica la directiva de reflexión en tiempo de ejecución a un constructor o método.</span><span class="sxs-lookup"><span data-stu-id="8af53-164">Applies runtime reflection policy to a constructor or method.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8af53-165">Comentarios</span><span class="sxs-lookup"><span data-stu-id="8af53-165">Remarks</span></span>  
 <span data-ttu-id="8af53-166">El elemento `<TypeParameter>` es similar al elemento [\<Parameter>](parameter-element-net-native.md), salvo que únicamente se puede aplicar a los parámetros de tipo <xref:System.Type>.</span><span class="sxs-lookup"><span data-stu-id="8af53-166">The `<TypeParameter>` element is similar to the [\<Parameter>](parameter-element-net-native.md) element, except that it can be applied only to parameters of type <xref:System.Type>.</span></span> <span data-ttu-id="8af53-167">Aplica la directiva a cualquier tipo que se represente en tiempo de ejecución mediante el argumento de tipo especificado por el atributo `Name`.</span><span class="sxs-lookup"><span data-stu-id="8af53-167">It applies policy to whatever type is represented at run time by the type argument specified by the `Name` attribute.</span></span>  
  
 <span data-ttu-id="8af53-168">Por ejemplo, el serializador JSON NewtonSoft incluye un método `JsonConvert.DeserializeObject(String value, Type type)` estático.</span><span class="sxs-lookup"><span data-stu-id="8af53-168">For example, the NewtonSoft JSON serializer includes a static `JsonConvert.DeserializeObject(String value, Type type)` method.</span></span> <span data-ttu-id="8af53-169">Las siguientes directivas de reflexión:</span><span class="sxs-lookup"><span data-stu-id="8af53-169">The following reflection directives:</span></span>  
  
```xml  
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">  
   <Type Name="Newtonsoft.Json.JsonConvert" >  
      <Method Name="DeserializeObject">  
         <GenericParameter Name="type" Serialize="Required All" />  
      </Method>  
   </Type>  
</Directives>  
```  
  
 <span data-ttu-id="8af53-170">especifican que debe haber disponibles metadatos para el tipo en tiempo de ejecución representado por el argumento `type` para poder realizar la serialización.</span><span class="sxs-lookup"><span data-stu-id="8af53-170">specify that metadata for the runtime type represented by the `type` argument should be made available for serialization.</span></span> <span data-ttu-id="8af53-171">Si estas directivas en tiempo de ejecución se aplican a un proyecto que incluye el siguiente código fuente:</span><span class="sxs-lookup"><span data-stu-id="8af53-171">If these runtime directives apply to a project that includes the following source code:</span></span>  
  
```csharp  
Type t = typeof(StockQuote);  
Object obj = JsonConvert.DeserializeObject(data, t);  
```  
  
 <span data-ttu-id="8af53-172">las directivas de reflexión hacen que haya metadatos disponibles para el tipo `StockQuote` para el serializador JSON NewtonSoft en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="8af53-172">the reflection directives make metadata for the `StockQuote` type available for the NewtonSoft JSON serializer at run time.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8af53-173">Vea también</span><span class="sxs-lookup"><span data-stu-id="8af53-173">See also</span></span>

- [<span data-ttu-id="8af53-174">Elemento \<Method></span><span class="sxs-lookup"><span data-stu-id="8af53-174">\<Method> Element</span></span>](method-element-net-native.md)
- [<span data-ttu-id="8af53-175">Runtime Directives (rd.xml) Configuration File Reference (Referencia del archivo de configuración de directivas en tiempo de ejecución (rd.xml))</span><span class="sxs-lookup"><span data-stu-id="8af53-175">Runtime Directives (rd.xml) Configuration File Reference</span></span>](runtime-directives-rd-xml-configuration-file-reference.md)
- <span data-ttu-id="8af53-176">[Runtime Directive Policy Settings](runtime-directive-policy-settings.md) (Configuración de directiva de la directiva en tiempo de ejecución)</span><span class="sxs-lookup"><span data-stu-id="8af53-176">[Runtime Directive Policy Settings](runtime-directive-policy-settings.md)</span></span>
- [<span data-ttu-id="8af53-177">Runtime Directive Elements (Elementos de directivas en tiempo de ejecución)</span><span class="sxs-lookup"><span data-stu-id="8af53-177">Runtime Directive Elements</span></span>](runtime-directive-elements.md)
