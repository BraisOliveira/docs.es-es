---
title: <providerOption> Elemento
ms.date: 03/30/2017
f1_keywords:
- provideroption
helpviewer_keywords:
- <provideroption> element
- providerOptions
- provideroption element
ms.assetid: 014f2e0b-c0b5-4fc4-92d3-73f02978b2a1
ms.openlocfilehash: 9c69ea7bf95b311a796ec29d90410a77b748c3c6
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59229789"
---
# <a name="provideroption-element"></a><span data-ttu-id="b06c7-102">\<providerOption > elemento</span><span class="sxs-lookup"><span data-stu-id="b06c7-102">\<providerOption> Element</span></span>
<span data-ttu-id="b06c7-103">Especifica los atributos de versión del compilador para un proveedor de lenguaje.</span><span class="sxs-lookup"><span data-stu-id="b06c7-103">Specifies the compiler version attributes for a language provider.</span></span>  
  
 <span data-ttu-id="b06c7-104">\<Elemento de configuración ></span><span class="sxs-lookup"><span data-stu-id="b06c7-104">\<configuration Element></span></span>  
<span data-ttu-id="b06c7-105">\<system.codedom Element></span><span class="sxs-lookup"><span data-stu-id="b06c7-105">\<system.codedom Element></span></span>  
<span data-ttu-id="b06c7-106">\<Elemento compilers ></span><span class="sxs-lookup"><span data-stu-id="b06c7-106">\<compilers Element></span></span>  
<span data-ttu-id="b06c7-107">\<compilador > elemento</span><span class="sxs-lookup"><span data-stu-id="b06c7-107">\<compiler> Element</span></span>  
<span data-ttu-id="b06c7-108">\<providerOption > elemento</span><span class="sxs-lookup"><span data-stu-id="b06c7-108">\<providerOption> Element</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b06c7-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b06c7-109">Syntax</span></span>  
  
```xml  
<providerOption  
  name="option-name"  
  value="option-value"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b06c7-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="b06c7-110">Attributes and Elements</span></span>  
 <span data-ttu-id="b06c7-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="b06c7-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b06c7-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="b06c7-112">Attributes</span></span>  
  
|<span data-ttu-id="b06c7-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="b06c7-113">Attribute</span></span>|<span data-ttu-id="b06c7-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="b06c7-114">Description</span></span>|  
|---------------|-----------------|  
|`name`|<span data-ttu-id="b06c7-115">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="b06c7-115">Required attribute.</span></span><br /><br /> <span data-ttu-id="b06c7-116">Especifica el nombre de la opción; Por ejemplo, "CompilerVersion".</span><span class="sxs-lookup"><span data-stu-id="b06c7-116">Specifies the name of the option; for example, "CompilerVersion".</span></span>|  
|`value`|<span data-ttu-id="b06c7-117">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="b06c7-117">Required attribute.</span></span><br /><br /> <span data-ttu-id="b06c7-118">Especifica el valor de la opción; Por ejemplo, "v3.5".</span><span class="sxs-lookup"><span data-stu-id="b06c7-118">Specifies the value for the option; for example, "v3.5".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b06c7-119">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="b06c7-119">Child Elements</span></span>  
 <span data-ttu-id="b06c7-120">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="b06c7-120">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b06c7-121">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="b06c7-121">Parent Elements</span></span>  
  
|<span data-ttu-id="b06c7-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="b06c7-122">Element</span></span>|<span data-ttu-id="b06c7-123">Descripción</span><span class="sxs-lookup"><span data-stu-id="b06c7-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b06c7-124">\<Configuración > elemento</span><span class="sxs-lookup"><span data-stu-id="b06c7-124">\<configuration> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)|<span data-ttu-id="b06c7-125">Elemento raíz necesario en cada archivo de configuración utilizado por Common Language Runtime y las aplicaciones de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="b06c7-125">The root element in every configuration file that is used by the common language runtime and .NET Framework applications.</span></span>|  
|[<span data-ttu-id="b06c7-126">\<system.codedom> Element</span><span class="sxs-lookup"><span data-stu-id="b06c7-126">\<system.codedom> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/compiler/system-codedom-element.md)|<span data-ttu-id="b06c7-127">Especifica los valores de configuración del compilador para los proveedores de lenguaje disponibles.</span><span class="sxs-lookup"><span data-stu-id="b06c7-127">Specifies compiler configuration settings for available language providers.</span></span>|  
|[<span data-ttu-id="b06c7-128">\<los compiladores > elemento</span><span class="sxs-lookup"><span data-stu-id="b06c7-128">\<compilers> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/compiler/compilers-element.md)|<span data-ttu-id="b06c7-129">Contenedor para los elementos de configuración de compilador; contiene cero o más `<compiler>` elementos.</span><span class="sxs-lookup"><span data-stu-id="b06c7-129">Container for compiler configuration elements; contains zero or more `<compiler>` elements.</span></span>|  
|[<span data-ttu-id="b06c7-130">\<compilador > elemento</span><span class="sxs-lookup"><span data-stu-id="b06c7-130">\<compiler> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md)|<span data-ttu-id="b06c7-131">Especifica los atributos de configuración del compilador para un proveedor de lenguaje.</span><span class="sxs-lookup"><span data-stu-id="b06c7-131">Specifies the compiler configuration attributes for a language provider.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b06c7-132">Comentarios</span><span class="sxs-lookup"><span data-stu-id="b06c7-132">Remarks</span></span>  
 <span data-ttu-id="b06c7-133">En la versión 3.5 de .NET Framework, los proveedores de código de Code Document Object Model (CodeDOM) pueden admitir opciones específicas del proveedor utilizando el `<providerOption>` elemento.</span><span class="sxs-lookup"><span data-stu-id="b06c7-133">In the .NET Framework version 3.5, Code Document Object Model (CodeDOM) code providers can support provider-specific options by using the `<providerOption>` element.</span></span>  
  
 <span data-ttu-id="b06c7-134">.NET Framework 3.5 incluye ensamblados de .NET Framework 2.0 actualizados y proporciona nuevos ensamblados de la versión 3.5 que contienen nuevos tipos.</span><span class="sxs-lookup"><span data-stu-id="b06c7-134">The .NET Framework 3.5 includes updated .NET Framework 2.0 assemblies and provides new version 3.5 assemblies that contain new types.</span></span> <span data-ttu-id="b06c7-135">Los proveedores de código de Microsoft C# y Visual Basic se encuentran en ensamblados de .NET Framework 2.0, pero se han actualizado para admitir los compiladores de la versión 3.5.</span><span class="sxs-lookup"><span data-stu-id="b06c7-135">The Microsoft C# and Visual Basic code providers are contained in .NET Framework 2.0 assemblies but have been updated to support version 3.5 compilers.</span></span> <span data-ttu-id="b06c7-136">De forma predeterminada, los proveedores de código actualizado generan código para los compiladores de la versión 2.0.</span><span class="sxs-lookup"><span data-stu-id="b06c7-136">By default, the updated code providers generate code for version 2.0 compilers.</span></span> <span data-ttu-id="b06c7-137">Puede usar el `<providerOption>` elemento para cambiar la versión del compilador de destino a la versión 3.5.</span><span class="sxs-lookup"><span data-stu-id="b06c7-137">You can use the `<providerOption>` element to change the target compiler version to 3.5.</span></span> <span data-ttu-id="b06c7-138">Para ello, especifique "CompilerVersion" para el `name` atributo y "v3.5" para el `value` atributo.</span><span class="sxs-lookup"><span data-stu-id="b06c7-138">To do this, specify "CompilerVersion" for the `name` attribute and "v3.5" for the `value` attribute.</span></span> <span data-ttu-id="b06c7-139">Debe preceder el número de versión con una letra minúscula "v".</span><span class="sxs-lookup"><span data-stu-id="b06c7-139">You must precede the version number with a lower-case "v".</span></span>  
  
 <span data-ttu-id="b06c7-140">Puede hacer que la especificación de versión global añadiendo el `<providerOption>` elemento al archivo raíz Web.config o Machine.config de .NET Framework 2.0.</span><span class="sxs-lookup"><span data-stu-id="b06c7-140">You can make the version specification global by adding the `<providerOption>` element to the .NET Framework 2.0 Machine.config or root Web.config file.</span></span> <span data-ttu-id="b06c7-141">Si actualiza la versión del compilador predeterminada a 3.5 en el archivo Machine.config, puede cambiar a 2.0 por la aplicación mediante el `<providerOption>` elemento en el archivo de configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="b06c7-141">If you update the default compiler version to 3.5 in the Machine.config file, you can change it back to 2.0 on a per-application basis by using the `<providerOption>` element in the application configuration file.</span></span>  
  
 <span data-ttu-id="b06c7-142">Los implementadores de proveedor de código codeDOM pueden procesar opciones personalizadas proporcionando un constructor que toma un `providerOptions` parámetro de tipo <xref:System.Collections.Generic.IDictionary%602>.</span><span class="sxs-lookup"><span data-stu-id="b06c7-142">CodeDOM code provider implementers can process custom options by providing a constructor that takes a `providerOptions` parameter of type <xref:System.Collections.Generic.IDictionary%602>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b06c7-143">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="b06c7-143">Example</span></span>  
 <span data-ttu-id="b06c7-144">El ejemplo siguiente muestra cómo especificar que se debe usar esa versión 3.5 del proveedor de código C#.</span><span class="sxs-lookup"><span data-stu-id="b06c7-144">The following example demonstrates how to specify that version 3.5 of the C# code provider should be used.</span></span>  
  
```xml  
<configuration>  
  <system.codedom>  
    <compilers>  
      <!-- zero or more compiler elements -->  
      <compiler  
        language="c#;cs;csharp"  
        extension=".cs"  
        type="Microsoft.CSharp.CSharpCodeProvider, System,   
          Version=2.0.3600.0, Culture=neutral,   
          PublicKeyToken=b77a5c561934e089"  
        compilerOptions="/optimize"  
        warningLevel="1" >  
          <providerOption  
            name="CompilerVersion"  
            value="v3.5" />  
      </compiler>  
    </compilers>  
  </system.codedom>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="b06c7-145">Vea también</span><span class="sxs-lookup"><span data-stu-id="b06c7-145">See also</span></span>

- <xref:System.CodeDom.Compiler.CompilerInfo>
- <xref:System.CodeDom.Compiler.CodeDomProvider>
- [<span data-ttu-id="b06c7-146">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="b06c7-146">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
- [<span data-ttu-id="b06c7-147">\<los compiladores > elemento</span><span class="sxs-lookup"><span data-stu-id="b06c7-147">\<compilers> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/compiler/compilers-element.md)
- [<span data-ttu-id="b06c7-148">Especificar nombres de tipo completos</span><span class="sxs-lookup"><span data-stu-id="b06c7-148">Specifying Fully Qualified Type Names</span></span>](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md)
- [<span data-ttu-id="b06c7-149">Elemento compiler aplicado a compilers para compilation (Esquema de configuración de ASP.NET)</span><span class="sxs-lookup"><span data-stu-id="b06c7-149">compiler Element for compilers for compilation (ASP.NET Settings Schema)</span></span>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/a15ebt6c(v=vs.100))
