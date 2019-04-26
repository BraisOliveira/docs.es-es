---
title: Referencia de esquema de contrato de datos
ms.date: 03/30/2017
helpviewer_keywords:
- data contracts [WCF], schema reference
ms.assetid: 9ebb0ebe-8166-4c93-980a-7c8f1f38f7c0
ms.openlocfilehash: a4ddaaea2133a8adf5271628f442644194a7f453
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61857186"
---
# <a name="data-contract-schema-reference"></a><span data-ttu-id="219df-102">Referencia de esquema de contrato de datos</span><span class="sxs-lookup"><span data-stu-id="219df-102">Data Contract Schema Reference</span></span>
<span data-ttu-id="219df-103">En este tema se describe el subconjunto del esquema XML (XSD) que <xref:System.Runtime.Serialization.DataContractSerializer> usa para describir los tipos de Common Language Runtime (CLR) para la serialización XML.</span><span class="sxs-lookup"><span data-stu-id="219df-103">This topic describes the subset of the XML Schema (XSD) used by <xref:System.Runtime.Serialization.DataContractSerializer> to describe common language runtime (CLR) types for XML serialization.</span></span>  
  
## <a name="datacontractserializer-mappings"></a><span data-ttu-id="219df-104">Asignaciones de DataContractSerializer</span><span class="sxs-lookup"><span data-stu-id="219df-104">DataContractSerializer Mappings</span></span>  
 <span data-ttu-id="219df-105">El `DataContractSerializer` asigna tipos CLR a XSD cuando los metadatos se exportan desde un servicio de Windows Communication Foundation (WCF) mediante un extremo de metadatos o el [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md).</span><span class="sxs-lookup"><span data-stu-id="219df-105">The `DataContractSerializer` maps CLR types to XSD when metadata is exported from a Windows Communication Foundation (WCF) service using a metadata endpoint or the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md).</span></span> <span data-ttu-id="219df-106">Para obtener más información, consulte [Data Contract Serializer](../../../../docs/framework/wcf/feature-details/data-contract-serializer.md).</span><span class="sxs-lookup"><span data-stu-id="219df-106">For more information, see [Data Contract Serializer](../../../../docs/framework/wcf/feature-details/data-contract-serializer.md).</span></span>  
  
 <span data-ttu-id="219df-107">El `DataContractSerializer` también asigna XSD a tipos de CLR cuando Svcutil.exe se utiliza para tener acceso al lenguaje de descripción de servicios Web (WSDL) o documentos XSD y para generar contratos de datos para servicios o clientes.</span><span class="sxs-lookup"><span data-stu-id="219df-107">The `DataContractSerializer` also maps XSD to CLR types when Svcutil.exe is used to access Web Services Description Language (WSDL) or XSD documents and generate data contracts for services or clients.</span></span>  
  
 <span data-ttu-id="219df-108">Solo las instancias de esquema XML que cumplen los requisitos mencionados en este documento pueden asignarse a tipos de CLR utilizando `DataContractSerializer`.</span><span class="sxs-lookup"><span data-stu-id="219df-108">Only XML Schema instances that conform to requirements stated in this document can be mapped to CLR types using `DataContractSerializer`.</span></span>  
  
### <a name="support-levels"></a><span data-ttu-id="219df-109">Niveles de compatibilidad</span><span class="sxs-lookup"><span data-stu-id="219df-109">Support Levels</span></span>  
 <span data-ttu-id="219df-110">El `DataContractSerializer` proporciona los niveles siguientes de compatibilidad para una característica de esquema XML determinada:</span><span class="sxs-lookup"><span data-stu-id="219df-110">The `DataContractSerializer` provides the following levels of support for a given XML Schema feature:</span></span>  
  
-   <span data-ttu-id="219df-111">**Compatible**.</span><span class="sxs-lookup"><span data-stu-id="219df-111">**Supported**.</span></span> <span data-ttu-id="219df-112">Hay asignación explícita desde esta característica a tipos o atributos CLR (o a ambos) mediante `DataContractSerializer`.</span><span class="sxs-lookup"><span data-stu-id="219df-112">There is explicit mapping from this feature to CLR types or attributes (or both) using `DataContractSerializer`.</span></span>  
  
-   <span data-ttu-id="219df-113">**Se omite**.</span><span class="sxs-lookup"><span data-stu-id="219df-113">**Ignored**.</span></span> <span data-ttu-id="219df-114">La característica se permite en esquemas importados por el `DataContractSerializer`, pero no tiene ningún efecto sobre la generación de código.</span><span class="sxs-lookup"><span data-stu-id="219df-114">The feature is allowed in schemas imported by the `DataContractSerializer`, but has no effect on code generation.</span></span>  
  
-   <span data-ttu-id="219df-115">**Se prohíbe**.</span><span class="sxs-lookup"><span data-stu-id="219df-115">**Forbidden**.</span></span> <span data-ttu-id="219df-116">El `DataContractSerializer` no permite importar un esquema mediante la característica.</span><span class="sxs-lookup"><span data-stu-id="219df-116">The `DataContractSerializer` does not support importing a schema using the feature.</span></span> <span data-ttu-id="219df-117">Por ejemplo, Svcutil.exe, al obtener acceso a un WSDL con un esquema que utiliza esta característica, vuelve a utilizar el <xref:System.Xml.Serialization.XmlSerializer> en su lugar.</span><span class="sxs-lookup"><span data-stu-id="219df-117">For example, Svcutil.exe, when accessing a WSDL with a schema that uses such a feature, falls back to using the <xref:System.Xml.Serialization.XmlSerializer> instead.</span></span> <span data-ttu-id="219df-118">Esto sucede de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="219df-118">This is by default.</span></span>  
  
## <a name="general-information"></a><span data-ttu-id="219df-119">Información general</span><span class="sxs-lookup"><span data-stu-id="219df-119">General Information</span></span>  
  
-   <span data-ttu-id="219df-120">El espacio de nombres del esquema se describe en [Esquema XML](https://go.microsoft.com/fwlink/?LinkId=95475).</span><span class="sxs-lookup"><span data-stu-id="219df-120">The schema namespace is described at [XML Schema](https://go.microsoft.com/fwlink/?LinkId=95475).</span></span> <span data-ttu-id="219df-121">El prefijo "xs" se utiliza en este documento.</span><span class="sxs-lookup"><span data-stu-id="219df-121">The prefix "xs" is used in this document.</span></span>  
  
-   <span data-ttu-id="219df-122">Cualquier atributo con un espacio de nombres que no sea del esquema Se ignora.</span><span class="sxs-lookup"><span data-stu-id="219df-122">Any attributes with a non-schema namespace are ignored.</span></span>  
  
-   <span data-ttu-id="219df-123">Se omite cualquier anotación (excepto aquellas descritas en este documento).</span><span class="sxs-lookup"><span data-stu-id="219df-123">Any annotations (except for those described in this document) are ignored.</span></span>  
  
### <a name="xsschema-attributes"></a><span data-ttu-id="219df-124">\<xs:schema>: attributes</span><span class="sxs-lookup"><span data-stu-id="219df-124">\<xs:schema>: attributes</span></span>  
  
|<span data-ttu-id="219df-125">Atributo</span><span class="sxs-lookup"><span data-stu-id="219df-125">Attribute</span></span>|<span data-ttu-id="219df-126">DataContract</span><span class="sxs-lookup"><span data-stu-id="219df-126">DataContract</span></span>|  
|---------------|------------------|  
|`attributeFormDefault`|<span data-ttu-id="219df-127">ignorado.</span><span class="sxs-lookup"><span data-stu-id="219df-127">Ignored.</span></span>|  
|`blockDefault`|<span data-ttu-id="219df-128">ignorado.</span><span class="sxs-lookup"><span data-stu-id="219df-128">Ignored.</span></span>|  
|`elementFormDefault`|<span data-ttu-id="219df-129">Se debe calificar.</span><span class="sxs-lookup"><span data-stu-id="219df-129">Must be qualified.</span></span> <span data-ttu-id="219df-130">Todos los elementos se deben calificar para un esquema para que `DataContractSerializer`los admita.</span><span class="sxs-lookup"><span data-stu-id="219df-130">All elements must be qualified for a schema to be supported by `DataContractSerializer`.</span></span> <span data-ttu-id="219df-131">Esto puede realizarse, ya sea estableciendo xs:schema/@elementFormDefault en "qualified" o estableciendo xs:element/@form en "qualified" en la declaración de cada elemento individual.</span><span class="sxs-lookup"><span data-stu-id="219df-131">This can be accomplished by either setting xs:schema/@elementFormDefault to "qualified" or by setting xs:element/@form to "qualified" on each individual element declaration.</span></span>|  
|`finalDefault`|<span data-ttu-id="219df-132">ignorado.</span><span class="sxs-lookup"><span data-stu-id="219df-132">Ignored.</span></span>|  
|`Id`|<span data-ttu-id="219df-133">ignorado.</span><span class="sxs-lookup"><span data-stu-id="219df-133">Ignored.</span></span>|  
|`targetNamespace`|<span data-ttu-id="219df-134">Admitido y asignado al espacio de nombres del contrato de datos.</span><span class="sxs-lookup"><span data-stu-id="219df-134">Supported and mapped to the data contract namespace.</span></span> <span data-ttu-id="219df-135">Si no se especifica este atributo, se utiliza el espacio de nombres en blanco.</span><span class="sxs-lookup"><span data-stu-id="219df-135">If this attribute is not specified, the blank namespace is used.</span></span> <span data-ttu-id="219df-136">No puede ser el espacio de nombres reservado `http://schemas.microsoft.com/2003/10/Serialization/`.</span><span class="sxs-lookup"><span data-stu-id="219df-136">Cannot be the reserved namespace `http://schemas.microsoft.com/2003/10/Serialization/`.</span></span>|  
|`version`|<span data-ttu-id="219df-137">ignorado.</span><span class="sxs-lookup"><span data-stu-id="219df-137">Ignored.</span></span>|  
  
### <a name="xsschema-contents"></a><span data-ttu-id="219df-138">\<xs:schema>: contents</span><span class="sxs-lookup"><span data-stu-id="219df-138">\<xs:schema>: contents</span></span>  
  
|<span data-ttu-id="219df-139">Contenido</span><span class="sxs-lookup"><span data-stu-id="219df-139">Contents</span></span>|<span data-ttu-id="219df-140">Schema</span><span class="sxs-lookup"><span data-stu-id="219df-140">Schema</span></span>|  
|--------------|------------|  
|`include`|<span data-ttu-id="219df-141">Se admite.</span><span class="sxs-lookup"><span data-stu-id="219df-141">Supported.</span></span> <span data-ttu-id="219df-142">`DataContractSerializer` admite xs:include y xs:import.</span><span class="sxs-lookup"><span data-stu-id="219df-142">`DataContractSerializer` supports xs:include and xs:import.</span></span> <span data-ttu-id="219df-143">Sin embargo, Svcutil.exe restringe las siguientes referencias `xs:include/@schemaLocation` y `xs:import/@location` cuando los metadatos se cargan desde un archivo local.</span><span class="sxs-lookup"><span data-stu-id="219df-143">However, Svcutil.exe restricts following `xs:include/@schemaLocation` and `xs:import/@location` references when metadata is loaded from a local file.</span></span> <span data-ttu-id="219df-144">La lista de archivos de esquema se debe pasar mediante un mecanismo fuera de banda y no mediante `include` en este caso; los documentos de esquema `include`se omiten.</span><span class="sxs-lookup"><span data-stu-id="219df-144">The list of schema files must be passed through an out-of-band mechanism and not through `include` in this case; `include`d schema documents are ignored.</span></span>|  
|`redefine`|<span data-ttu-id="219df-145">no autorizado.</span><span class="sxs-lookup"><span data-stu-id="219df-145">Forbidden.</span></span> <span data-ttu-id="219df-146">El uso de `xs:redefine` se prohíbe por parte de `DataContractSerializer` por razones de seguridad: `x:redefine` requiere que se siga `schemaLocation` .</span><span class="sxs-lookup"><span data-stu-id="219df-146">The use of `xs:redefine` is forbidden by `DataContractSerializer` for security reasons: `x:redefine` requires `schemaLocation` to be followed.</span></span> <span data-ttu-id="219df-147">En ciertas circunstancias, el uso de DataContract por parte de Svcutil.exe restringe el uso de `schemaLocation`.</span><span class="sxs-lookup"><span data-stu-id="219df-147">In certain circumstances, Svcutil.exe using DataContract restricts use of `schemaLocation`.</span></span>|  
|`import`|<span data-ttu-id="219df-148">Se admite.</span><span class="sxs-lookup"><span data-stu-id="219df-148">Supported.</span></span> <span data-ttu-id="219df-149">`DataContractSerializer` admite `xs:include` y `xs:import`.</span><span class="sxs-lookup"><span data-stu-id="219df-149">`DataContractSerializer` supports `xs:include` and `xs:import`.</span></span> <span data-ttu-id="219df-150">Sin embargo, Svcutil.exe restringe las siguientes referencias `xs:include/@schemaLocation` y `xs:import/@location` cuando los metadatos se cargan desde un archivo local.</span><span class="sxs-lookup"><span data-stu-id="219df-150">However, Svcutil.exe restricts following `xs:include/@schemaLocation` and `xs:import/@location` references when metadata is loaded from a local file.</span></span> <span data-ttu-id="219df-151">La lista de archivos de esquema se debe pasar mediante un mecanismo fuera de banda y no mediante `include` en este caso; los documentos de esquema `include`se omiten.</span><span class="sxs-lookup"><span data-stu-id="219df-151">The list of schema files must be passed through an out-of-band mechanism and not through `include` in this case; `include`d schema documents are ignored.</span></span>|  
|`simpleType`|<span data-ttu-id="219df-152">Se admite.</span><span class="sxs-lookup"><span data-stu-id="219df-152">Supported.</span></span> <span data-ttu-id="219df-153">Vea la sección `xs:simpleType` .</span><span class="sxs-lookup"><span data-stu-id="219df-153">See the `xs:simpleType` section.</span></span>|  
|`complexType`|<span data-ttu-id="219df-154">Admitido, se asigna a contratos de datos.</span><span class="sxs-lookup"><span data-stu-id="219df-154">Supported, maps to data contracts.</span></span> <span data-ttu-id="219df-155">Vea la sección `xs:complexType` .</span><span class="sxs-lookup"><span data-stu-id="219df-155">See the `xs:complexType` section.</span></span>|  
|`group`|<span data-ttu-id="219df-156">ignorado.</span><span class="sxs-lookup"><span data-stu-id="219df-156">Ignored.</span></span> <span data-ttu-id="219df-157">`DataContractSerializer` no admite el uso de `xs:group`, `xs:attributeGroup`ni `xs:attribute`.</span><span class="sxs-lookup"><span data-stu-id="219df-157">`DataContractSerializer` does not support use of `xs:group`, `xs:attributeGroup`, and `xs:attribute`.</span></span> <span data-ttu-id="219df-158">Estas declaraciones se ignoran como elementos secundarios de `xs:schema`, pero no se puede hacer referencia a ellas desde `complexType` u otras estructuras admitidas.</span><span class="sxs-lookup"><span data-stu-id="219df-158">These declarations are ignored as children of `xs:schema`, but cannot be referenced from within `complexType` or other supported constructs.</span></span>|  
|`attributeGroup`|<span data-ttu-id="219df-159">ignorado.</span><span class="sxs-lookup"><span data-stu-id="219df-159">Ignored.</span></span> <span data-ttu-id="219df-160">`DataContractSerializer` no admite el uso de `xs:group`, `xs:attributeGroup`ni `xs:attribute`.</span><span class="sxs-lookup"><span data-stu-id="219df-160">`DataContractSerializer` does not support use of `xs:group`, `xs:attributeGroup`, and `xs:attribute`.</span></span> <span data-ttu-id="219df-161">Estas declaraciones se ignoran como elementos secundarios de `xs:schema`, pero no se puede hacer referencia a ellas desde `complexType` u otras estructuras admitidas.</span><span class="sxs-lookup"><span data-stu-id="219df-161">These declarations are ignored as children of `xs:schema`, but cannot be referenced from within `complexType` or other supported constructs.</span></span>|  
|`element`|<span data-ttu-id="219df-162">Se admite.</span><span class="sxs-lookup"><span data-stu-id="219df-162">Supported.</span></span> <span data-ttu-id="219df-163">Vea la declaración de elemento global (GED).</span><span class="sxs-lookup"><span data-stu-id="219df-163">See Global Element Declaration (GED).</span></span>|  
|`attribute`|<span data-ttu-id="219df-164">ignorado.</span><span class="sxs-lookup"><span data-stu-id="219df-164">Ignored.</span></span> <span data-ttu-id="219df-165">`DataContractSerializer` no admite el uso de `xs:group`, `xs:attributeGroup`ni `xs:attribute`.</span><span class="sxs-lookup"><span data-stu-id="219df-165">`DataContractSerializer` does not support use of `xs:group`, `xs:attributeGroup`, and `xs:attribute`.</span></span> <span data-ttu-id="219df-166">Estas declaraciones se ignoran como elementos secundarios de `xs:schema`, pero no se puede hacer referencia a ellas desde `complexType` u otras estructuras admitidas.</span><span class="sxs-lookup"><span data-stu-id="219df-166">These declarations are ignored as children of `xs:schema`, but cannot be referenced from within `complexType` or other supported constructs.</span></span>|  
|`notation`|<span data-ttu-id="219df-167">ignorado.</span><span class="sxs-lookup"><span data-stu-id="219df-167">Ignored.</span></span>|  
  
## <a name="complex-types--xscomplextype"></a><span data-ttu-id="219df-168">Tipos complejos: \<xs: complexType ></span><span class="sxs-lookup"><span data-stu-id="219df-168">Complex Types – \<xs:complexType></span></span>  
  
### <a name="general-information"></a><span data-ttu-id="219df-169">Información general</span><span class="sxs-lookup"><span data-stu-id="219df-169">General Information</span></span>  
 <span data-ttu-id="219df-170">Cada tipo complejo \<xs: complexType > se asigna a un contrato de datos.</span><span class="sxs-lookup"><span data-stu-id="219df-170">Each complex type \<xs:complexType> maps to a data contract.</span></span>  
  
### <a name="xscomplextype-attributes"></a><span data-ttu-id="219df-171">\<xs: complexType >: atributos</span><span class="sxs-lookup"><span data-stu-id="219df-171">\<xs:complexType>: attributes</span></span>  
  
|<span data-ttu-id="219df-172">Atributo</span><span class="sxs-lookup"><span data-stu-id="219df-172">Attribute</span></span>|<span data-ttu-id="219df-173">Schema</span><span class="sxs-lookup"><span data-stu-id="219df-173">Schema</span></span>|  
|---------------|------------|  
|`abstract`|<span data-ttu-id="219df-174">Debe ser false (valor predeterminado).</span><span class="sxs-lookup"><span data-stu-id="219df-174">Must be false (default).</span></span>|  
|`block`|<span data-ttu-id="219df-175">no autorizado.</span><span class="sxs-lookup"><span data-stu-id="219df-175">Forbidden.</span></span>|  
|`final`|<span data-ttu-id="219df-176">ignorado.</span><span class="sxs-lookup"><span data-stu-id="219df-176">Ignored.</span></span>|  
|`id`|<span data-ttu-id="219df-177">ignorado.</span><span class="sxs-lookup"><span data-stu-id="219df-177">Ignored.</span></span>|  
|`mixed`|<span data-ttu-id="219df-178">Debe ser false (valor predeterminado).</span><span class="sxs-lookup"><span data-stu-id="219df-178">Must be false (default).</span></span>|  
|`name`|<span data-ttu-id="219df-179">Admitido y asignado al nombre del contrato de datos.</span><span class="sxs-lookup"><span data-stu-id="219df-179">Supported and mapped to the data contract name.</span></span> <span data-ttu-id="219df-180">Si hay puntos en el nombre, se realiza un intento de asignar el tipo a un tipo interno.</span><span class="sxs-lookup"><span data-stu-id="219df-180">If there are periods in the name, an attempt is made to map the type to an inner type.</span></span> <span data-ttu-id="219df-181">Por ejemplo, un tipo complejo denominado `A.B` asigna a un tipo de contrato de datos que es un tipo interno de un tipo con el nombre de contrato de datos `A`, pero solo si existe este tipo de contrato de datos.</span><span class="sxs-lookup"><span data-stu-id="219df-181">For example, a complex type named `A.B` maps to a data contract type that is an inner type of a type with the data contract name `A`, but only if such a data contract type exists.</span></span> <span data-ttu-id="219df-182">Es posible más de un nivel de anidación: por ejemplo, `A.B.C` puede ser un tipo interno, pero solo si existen `A` y `A.B` .</span><span class="sxs-lookup"><span data-stu-id="219df-182">More than one level of nesting is possible: for example, `A.B.C` can be an inner type, but only if `A` and `A.B` both exist.</span></span>|  
  
### <a name="xscomplextype-contents"></a><span data-ttu-id="219df-183">\<xs: complexType >: contenido</span><span class="sxs-lookup"><span data-stu-id="219df-183">\<xs:complexType>: contents</span></span>  
  
|<span data-ttu-id="219df-184">Contenido</span><span class="sxs-lookup"><span data-stu-id="219df-184">Contents</span></span>|<span data-ttu-id="219df-185">Schema</span><span class="sxs-lookup"><span data-stu-id="219df-185">Schema</span></span>|  
|--------------|------------|  
|`simpleContent`|<span data-ttu-id="219df-186">Se prohíben las extensiones.</span><span class="sxs-lookup"><span data-stu-id="219df-186">Extensions are forbidden.</span></span><br /><br /> <span data-ttu-id="219df-187">La restricción solo se permite desde `anySimpleType`.</span><span class="sxs-lookup"><span data-stu-id="219df-187">Restriction is allowed only from `anySimpleType`.</span></span>|  
|`complexContent`|<span data-ttu-id="219df-188">Se admite.</span><span class="sxs-lookup"><span data-stu-id="219df-188">Supported.</span></span> <span data-ttu-id="219df-189">Vea “Herencia”.</span><span class="sxs-lookup"><span data-stu-id="219df-189">See "Inheritance".</span></span>|  
|`group`|<span data-ttu-id="219df-190">no autorizado.</span><span class="sxs-lookup"><span data-stu-id="219df-190">Forbidden.</span></span>|  
|`all`|<span data-ttu-id="219df-191">no autorizado.</span><span class="sxs-lookup"><span data-stu-id="219df-191">Forbidden.</span></span>|  
|`choice`|<span data-ttu-id="219df-192">Se prohíbe</span><span class="sxs-lookup"><span data-stu-id="219df-192">Forbidden</span></span>|  
|`sequence`|<span data-ttu-id="219df-193">Admitido, asigna a los miembros de datos de un contrato de datos.</span><span class="sxs-lookup"><span data-stu-id="219df-193">Supported, maps to data members of a data contract.</span></span>|  
|`attribute`|<span data-ttu-id="219df-194">Prohibido, aun cuando uso = "prohibido" (con una excepción).</span><span class="sxs-lookup"><span data-stu-id="219df-194">Forbidden, even if use="prohibited" (with one exception).</span></span> <span data-ttu-id="219df-195">Solo se admiten los atributos opcionales del espacio de nombres del esquema de serialización estándar.</span><span class="sxs-lookup"><span data-stu-id="219df-195">Only optional attributes from the Standard Serialization Schema namespace are supported.</span></span> <span data-ttu-id="219df-196">No asignan a miembros de datos en el modelo de programación del contrato de datos.</span><span class="sxs-lookup"><span data-stu-id="219df-196">They do not map to data members in the data contract programming model.</span></span> <span data-ttu-id="219df-197">Actualmente, solo un atributo de este tipo tiene significado y se trata en la sección ISerializable.</span><span class="sxs-lookup"><span data-stu-id="219df-197">Currently, only one such attribute has meaning and is discussed in the ISerializable section.</span></span> <span data-ttu-id="219df-198">El resto se pasa por alto.</span><span class="sxs-lookup"><span data-stu-id="219df-198">All others are ignored.</span></span>|  
|`attributeGroup`|<span data-ttu-id="219df-199">no autorizado.</span><span class="sxs-lookup"><span data-stu-id="219df-199">Forbidden.</span></span> <span data-ttu-id="219df-200">En la versión v1 WCF, `DataContractSerializer` omite la presencia de `attributeGroup` dentro de `xs:complexType`.</span><span class="sxs-lookup"><span data-stu-id="219df-200">In the WCF v1 release, `DataContractSerializer` ignores the presence of `attributeGroup` inside `xs:complexType`.</span></span>|  
|`anyAttribute`|<span data-ttu-id="219df-201">no autorizado.</span><span class="sxs-lookup"><span data-stu-id="219df-201">Forbidden.</span></span>|  
|<span data-ttu-id="219df-202">(vacío)</span><span class="sxs-lookup"><span data-stu-id="219df-202">(empty)</span></span>|<span data-ttu-id="219df-203">Se asigna a un contrato de datos sin miembros de datos.</span><span class="sxs-lookup"><span data-stu-id="219df-203">Maps to a data contract with no data members.</span></span>|  
  
### <a name="xssequence-in-a-complex-type-attributes"></a><span data-ttu-id="219df-204">\<xs: sequence > en un tipo complejo: atributos</span><span class="sxs-lookup"><span data-stu-id="219df-204">\<xs:sequence> in a complex type: attributes</span></span>  
  
|<span data-ttu-id="219df-205">Atributo</span><span class="sxs-lookup"><span data-stu-id="219df-205">Attribute</span></span>|<span data-ttu-id="219df-206">Schema</span><span class="sxs-lookup"><span data-stu-id="219df-206">Schema</span></span>|  
|---------------|------------|  
|`id`|<span data-ttu-id="219df-207">ignorado.</span><span class="sxs-lookup"><span data-stu-id="219df-207">Ignored.</span></span>|  
|`maxOccurs`|<span data-ttu-id="219df-208">Debe ser 1 (valor predeterminado).</span><span class="sxs-lookup"><span data-stu-id="219df-208">Must be 1 (default).</span></span>|  
|`minOccurs`|<span data-ttu-id="219df-209">Debe ser 1 (valor predeterminado).</span><span class="sxs-lookup"><span data-stu-id="219df-209">Must be 1 (default).</span></span>|  
  
### <a name="xssequence-in-a-complex-type-contents"></a><span data-ttu-id="219df-210">\<xs: sequence > en un tipo complejo: contenido</span><span class="sxs-lookup"><span data-stu-id="219df-210">\<xs:sequence> in a complex type: contents</span></span>  
  
|<span data-ttu-id="219df-211">Contenido</span><span class="sxs-lookup"><span data-stu-id="219df-211">Contents</span></span>|<span data-ttu-id="219df-212">Schema</span><span class="sxs-lookup"><span data-stu-id="219df-212">Schema</span></span>|  
|--------------|------------|  
|`element`|<span data-ttu-id="219df-213">Cada instancia asigna a un miembro de datos.</span><span class="sxs-lookup"><span data-stu-id="219df-213">Each instance maps to a data member.</span></span>|  
|`group`|<span data-ttu-id="219df-214">no autorizado.</span><span class="sxs-lookup"><span data-stu-id="219df-214">Forbidden.</span></span>|  
|`choice`|<span data-ttu-id="219df-215">no autorizado.</span><span class="sxs-lookup"><span data-stu-id="219df-215">Forbidden.</span></span>|  
|`sequence`|<span data-ttu-id="219df-216">no autorizado.</span><span class="sxs-lookup"><span data-stu-id="219df-216">Forbidden.</span></span>|  
|`any`|<span data-ttu-id="219df-217">no autorizado.</span><span class="sxs-lookup"><span data-stu-id="219df-217">Forbidden.</span></span>|  
|<span data-ttu-id="219df-218">(vacío)</span><span class="sxs-lookup"><span data-stu-id="219df-218">(empty)</span></span>|<span data-ttu-id="219df-219">Se asigna a un contrato de datos sin miembros de datos.</span><span class="sxs-lookup"><span data-stu-id="219df-219">Maps to a data contract with no data members.</span></span>|  
  
## <a name="elements--xselement"></a><span data-ttu-id="219df-220">Elementos – \<xs: element ></span><span class="sxs-lookup"><span data-stu-id="219df-220">Elements – \<xs:element></span></span>  
  
### <a name="general-information"></a><span data-ttu-id="219df-221">Información general</span><span class="sxs-lookup"><span data-stu-id="219df-221">General Information</span></span>  
 <span data-ttu-id="219df-222">`<xs:element>` puede aparecer en los contextos siguientes:</span><span class="sxs-lookup"><span data-stu-id="219df-222">`<xs:element>` can occur in the following contexts:</span></span>  
  
-   <span data-ttu-id="219df-223">Puede ocurrir dentro de un `<xs:sequence>`, que describe un miembro de datos de un contrato de datos normal (no de una colección).</span><span class="sxs-lookup"><span data-stu-id="219df-223">It can occur within an `<xs:sequence>`, which describes a data member of a regular (non-collection) data contract.</span></span> <span data-ttu-id="219df-224">En este caso, el atributo `maxOccurs` debe ser 1.</span><span class="sxs-lookup"><span data-stu-id="219df-224">In this case, the `maxOccurs` attribute must be 1.</span></span> <span data-ttu-id="219df-225">(No se permite un valor de 0).</span><span class="sxs-lookup"><span data-stu-id="219df-225">(A value of 0 is not allowed).</span></span>  
  
-   <span data-ttu-id="219df-226">Puede ocurrir dentro de un `<xs:sequence>`, que describe un miembro de datos de un contrato de datos de colección.</span><span class="sxs-lookup"><span data-stu-id="219df-226">It can occur within an `<xs:sequence>`, which describes a data member of a collection data contract.</span></span> <span data-ttu-id="219df-227">En este caso, el atributo `maxOccurs` debe ser mayor que 1 o "ilimitado".</span><span class="sxs-lookup"><span data-stu-id="219df-227">In this case, the `maxOccurs` attribute must be greater than 1 or "unbounded".</span></span>  
  
-   <span data-ttu-id="219df-228">Puede ocurrir dentro de `<xs:schema>` como una declaración de elemento global (GED).</span><span class="sxs-lookup"><span data-stu-id="219df-228">It can occur within an `<xs:schema>` as a Global Element Declaration (GED).</span></span>  
  
### <a name="xselement-with-maxoccurs1-within-an-xssequence-data-members"></a><span data-ttu-id="219df-229">\<xs: element > con maxOccurs = 1 dentro de un \<xs: sequence > (miembros de datos)</span><span class="sxs-lookup"><span data-stu-id="219df-229">\<xs:element> with maxOccurs=1 within an \<xs:sequence> (Data Members)</span></span>  
  
|<span data-ttu-id="219df-230">Atributo</span><span class="sxs-lookup"><span data-stu-id="219df-230">Attribute</span></span>|<span data-ttu-id="219df-231">Schema</span><span class="sxs-lookup"><span data-stu-id="219df-231">Schema</span></span>|  
|---------------|------------|  
|`ref`|<span data-ttu-id="219df-232">no autorizado.</span><span class="sxs-lookup"><span data-stu-id="219df-232">Forbidden.</span></span>|  
|`name`|<span data-ttu-id="219df-233">Admitido, asigna al nombre del miembro de datos.</span><span class="sxs-lookup"><span data-stu-id="219df-233">Supported, maps to the data member name.</span></span>|  
|`type`|<span data-ttu-id="219df-234">Admitido, asigna al tipo de miembro de datos.</span><span class="sxs-lookup"><span data-stu-id="219df-234">Supported, maps to the data member type.</span></span> <span data-ttu-id="219df-235">Para obtener más información, vea Asignación de tipo/primitivo.</span><span class="sxs-lookup"><span data-stu-id="219df-235">For more information, see Type/primitive mapping.</span></span> <span data-ttu-id="219df-236">Si no se especifica (y el elemento no contiene un tipo anónimo), se supone `xs:anyType` .</span><span class="sxs-lookup"><span data-stu-id="219df-236">If not specified (and the element does not contain an anonymous type), `xs:anyType` is assumed.</span></span>|  
|`block`|<span data-ttu-id="219df-237">ignorado.</span><span class="sxs-lookup"><span data-stu-id="219df-237">Ignored.</span></span>|  
|`default`|<span data-ttu-id="219df-238">no autorizado.</span><span class="sxs-lookup"><span data-stu-id="219df-238">Forbidden.</span></span>|  
|`fixed`|<span data-ttu-id="219df-239">no autorizado.</span><span class="sxs-lookup"><span data-stu-id="219df-239">Forbidden.</span></span>|  
|`form`|<span data-ttu-id="219df-240">Se debe calificar.</span><span class="sxs-lookup"><span data-stu-id="219df-240">Must be qualified.</span></span> <span data-ttu-id="219df-241">Este atributo se puede establecer mediante `elementFormDefault` en `xs:schema`.</span><span class="sxs-lookup"><span data-stu-id="219df-241">This attribute can be set through `elementFormDefault` on `xs:schema`.</span></span>|  
|`id`|<span data-ttu-id="219df-242">ignorado.</span><span class="sxs-lookup"><span data-stu-id="219df-242">Ignored.</span></span>|  
|`maxOccurs`|<span data-ttu-id="219df-243">1</span><span class="sxs-lookup"><span data-stu-id="219df-243">1</span></span>|  
|`minOccurs`|<span data-ttu-id="219df-244">Se asigna a la propiedad <xref:System.Runtime.Serialization.DataMemberAttribute.IsRequired%2A> de un miembro de datos (`IsRequired` es true cuando `minOccurs` es 1).</span><span class="sxs-lookup"><span data-stu-id="219df-244">Maps to the <xref:System.Runtime.Serialization.DataMemberAttribute.IsRequired%2A> property of a data member (`IsRequired` is true when `minOccurs` is 1).</span></span>|  
|`nillable`|<span data-ttu-id="219df-245">Afecta a la asignación de tipo.</span><span class="sxs-lookup"><span data-stu-id="219df-245">Affects type mapping.</span></span> <span data-ttu-id="219df-246">Vea Asignación de tipo/primitivo.</span><span class="sxs-lookup"><span data-stu-id="219df-246">See Type/primitive mapping.</span></span>|  
  
### <a name="xselement-with-maxoccurs1-within-an-xssequence-collections"></a><span data-ttu-id="219df-247">\<xs: element > con maxOccurs > 1 dentro de un \<xs: sequence > (colecciones)</span><span class="sxs-lookup"><span data-stu-id="219df-247">\<xs:element> with maxOccurs>1 within an \<xs:sequence> (Collections)</span></span>  
  
-   <span data-ttu-id="219df-248">Asigna a un <xref:System.Runtime.Serialization.CollectionDataContractAttribute>.</span><span class="sxs-lookup"><span data-stu-id="219df-248">Maps to a <xref:System.Runtime.Serialization.CollectionDataContractAttribute>.</span></span>  
  
-   <span data-ttu-id="219df-249">En tipos de colección, solo se permite un xs:element dentro de un xs:sequence.</span><span class="sxs-lookup"><span data-stu-id="219df-249">In collection types, only one xs:element is allowed within an xs:sequence.</span></span>  
  
 <span data-ttu-id="219df-250">Las colecciones pueden ser de los siguientes tipos:</span><span class="sxs-lookup"><span data-stu-id="219df-250">Collections can be of the following types:</span></span>  
  
-   <span data-ttu-id="219df-251">Colecciones normales (por ejemplo, matrices).</span><span class="sxs-lookup"><span data-stu-id="219df-251">Regular collections (for example, arrays).</span></span>  
  
-   <span data-ttu-id="219df-252">Colecciones de diccionarios (asignan un valor a otro; por ejemplo, un <xref:System.Collections.Hashtable>).</span><span class="sxs-lookup"><span data-stu-id="219df-252">Dictionary collections (mapping one value to another; for example, a <xref:System.Collections.Hashtable>).</span></span>  
  
-   <span data-ttu-id="219df-253">La única diferencia entre un diccionario y una matriz de un tipo de par clave-valor está en el modelo de programación generado.</span><span class="sxs-lookup"><span data-stu-id="219df-253">The only difference between a dictionary and an array of a key/value pair type is in the generated programming model.</span></span> <span data-ttu-id="219df-254">Hay un mecanismo de anotación de esquema que se puede utilizar para indicar que un tipo determinado es una colección de diccionarios.</span><span class="sxs-lookup"><span data-stu-id="219df-254">There is a schema annotation mechanism that can be used to indicate that a given type is a dictionary collection.</span></span>  
  
 <span data-ttu-id="219df-255">Las reglas para los atributos `ref`, `block`, `default`, `fixed`, `form`e `id` son las mismas que para el caso de que no se trate de una colección.</span><span class="sxs-lookup"><span data-stu-id="219df-255">The rules for the `ref`, `block`, `default`, `fixed`, `form`, and `id` attributes are the same as for the non-collection case.</span></span> <span data-ttu-id="219df-256">Entre otros atributos se incluyen los de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="219df-256">Other attributes include those in the following table.</span></span>  
  
|<span data-ttu-id="219df-257">Atributo</span><span class="sxs-lookup"><span data-stu-id="219df-257">Attribute</span></span>|<span data-ttu-id="219df-258">Schema</span><span class="sxs-lookup"><span data-stu-id="219df-258">Schema</span></span>|  
|---------------|------------|  
|`name`|<span data-ttu-id="219df-259">Admitido, asigna a la propiedad <xref:System.Runtime.Serialization.CollectionDataContractAttribute.ItemName%2A> en el atributo `CollectionDataContractAttribute` .</span><span class="sxs-lookup"><span data-stu-id="219df-259">Supported, maps to the <xref:System.Runtime.Serialization.CollectionDataContractAttribute.ItemName%2A> property in the `CollectionDataContractAttribute` attribute.</span></span>|  
|`type`|<span data-ttu-id="219df-260">Admitido, asigna al tipo almacenado en la colección.</span><span class="sxs-lookup"><span data-stu-id="219df-260">Supported, maps to the type stored in the collection.</span></span>|  
|`maxOccurs`|<span data-ttu-id="219df-261">Mayor que 1 o "ilimitado".</span><span class="sxs-lookup"><span data-stu-id="219df-261">Greater than 1 or "unbounded".</span></span> <span data-ttu-id="219df-262">El esquema de DC debería utilizar "ilimitado."</span><span class="sxs-lookup"><span data-stu-id="219df-262">The DC schema should use "unbounded".</span></span>|  
|`minOccurs`|<span data-ttu-id="219df-263">ignorado.</span><span class="sxs-lookup"><span data-stu-id="219df-263">Ignored.</span></span>|  
|`nillable`|<span data-ttu-id="219df-264">Afecta a la asignación de tipo.</span><span class="sxs-lookup"><span data-stu-id="219df-264">Affects type mapping.</span></span> <span data-ttu-id="219df-265">Este atributo se omite para las colecciones de diccionarios.</span><span class="sxs-lookup"><span data-stu-id="219df-265">This attribute is ignored for dictionary collections.</span></span>|  
  
### <a name="xselement-within-an-xsschema-global-element-declaration"></a><span data-ttu-id="219df-266">\<xs: element > dentro de un \<xs: schema > declaración de elemento Global</span><span class="sxs-lookup"><span data-stu-id="219df-266">\<xs:element> within an \<xs:schema> Global Element Declaration</span></span>  
  
-   <span data-ttu-id="219df-267">Una declaración de elemento global (GED) que tiene el mismo nombre y espacio de nombres que un tipo en esquema o que define un tipo anónimo dentro de sí mismo, se dice que está asociado al tipo.</span><span class="sxs-lookup"><span data-stu-id="219df-267">A Global Element Declaration (GED) that has the same name and namespace as a type in schema, or that defines an anonymous type inside itself, is said to be associated with the type.</span></span>  
  
-   <span data-ttu-id="219df-268">Exportación del esquema: las GED asociadas se generan para cada tipo generado, tanto simple como complejo.</span><span class="sxs-lookup"><span data-stu-id="219df-268">Schema export: associated GEDs are generated for every generated type, both simple and complex.</span></span>  
  
-   <span data-ttu-id="219df-269">Deserialización/serialización: las GED asociadas se utilizan como elementos raíz para el tipo.</span><span class="sxs-lookup"><span data-stu-id="219df-269">Deserialization/serialization: associated GEDs are used as root elements for the type.</span></span>  
  
-   <span data-ttu-id="219df-270">Importación del esquema: las GED asociadas no se requieren y se omiten si siguen las reglas siguientes (a menos que definan tipos).</span><span class="sxs-lookup"><span data-stu-id="219df-270">Schema import: associated GEDs are not required and are ignored if they follow the following rules (unless they define types).</span></span>  
  
|<span data-ttu-id="219df-271">Atributo</span><span class="sxs-lookup"><span data-stu-id="219df-271">Attribute</span></span>|<span data-ttu-id="219df-272">Schema</span><span class="sxs-lookup"><span data-stu-id="219df-272">Schema</span></span>|  
|---------------|------------|  
|`abstract`|<span data-ttu-id="219df-273">Debe ser false para GED asociadas.</span><span class="sxs-lookup"><span data-stu-id="219df-273">Must be false for associated GEDs.</span></span>|  
|`block`|<span data-ttu-id="219df-274">Se prohíbe en GED asociadas.</span><span class="sxs-lookup"><span data-stu-id="219df-274">Forbidden in associated GEDs.</span></span>|  
|`default`|<span data-ttu-id="219df-275">Se prohíbe en GED asociadas.</span><span class="sxs-lookup"><span data-stu-id="219df-275">Forbidden in associated GEDs.</span></span>|  
|`final`|<span data-ttu-id="219df-276">Debe ser false para GED asociadas.</span><span class="sxs-lookup"><span data-stu-id="219df-276">Must be false for associated GEDs.</span></span>|  
|`fixed`|<span data-ttu-id="219df-277">Se prohíbe en GED asociadas.</span><span class="sxs-lookup"><span data-stu-id="219df-277">Forbidden in associated GEDs.</span></span>|  
|`id`|<span data-ttu-id="219df-278">ignorado.</span><span class="sxs-lookup"><span data-stu-id="219df-278">Ignored.</span></span>|  
|`name`|<span data-ttu-id="219df-279">Se admite.</span><span class="sxs-lookup"><span data-stu-id="219df-279">Supported.</span></span> <span data-ttu-id="219df-280">Vea la definición de GED asociadas.</span><span class="sxs-lookup"><span data-stu-id="219df-280">See the definition of associated GEDs.</span></span>|  
|`nillable`|<span data-ttu-id="219df-281">Debe ser true para las GED asociadas.</span><span class="sxs-lookup"><span data-stu-id="219df-281">Must be true for associated GEDs.</span></span>|  
|`substitutionGroup`|<span data-ttu-id="219df-282">Se prohíbe en GED asociadas.</span><span class="sxs-lookup"><span data-stu-id="219df-282">Forbidden in associated GEDs.</span></span>|  
|`type`|<span data-ttu-id="219df-283">Admitido y debe coincidir con el tipo asociado para las GED asociadas (a menos que el elemento contenga un tipo anónimo).</span><span class="sxs-lookup"><span data-stu-id="219df-283">Supported, and must match the associated type for associated GEDs (unless the element contains an anonymous type).</span></span>|  
  
### <a name="xselement-contents"></a><span data-ttu-id="219df-284">\<xs: element >: contenido</span><span class="sxs-lookup"><span data-stu-id="219df-284">\<xs:element>: contents</span></span>  
  
|<span data-ttu-id="219df-285">Contenido</span><span class="sxs-lookup"><span data-stu-id="219df-285">Contents</span></span>|<span data-ttu-id="219df-286">Schema</span><span class="sxs-lookup"><span data-stu-id="219df-286">Schema</span></span>|  
|--------------|------------|  
|`simpleType`|<span data-ttu-id="219df-287">Admitido.\*</span><span class="sxs-lookup"><span data-stu-id="219df-287">Supported.\*</span></span>|  
|`complexType`|<span data-ttu-id="219df-288">Admitido.\*</span><span class="sxs-lookup"><span data-stu-id="219df-288">Supported.\*</span></span>|  
|`unique`|<span data-ttu-id="219df-289">ignorado.</span><span class="sxs-lookup"><span data-stu-id="219df-289">Ignored.</span></span>|  
|`key`|<span data-ttu-id="219df-290">ignorado.</span><span class="sxs-lookup"><span data-stu-id="219df-290">Ignored.</span></span>|  
|`keyref`|<span data-ttu-id="219df-291">ignorado.</span><span class="sxs-lookup"><span data-stu-id="219df-291">Ignored.</span></span>|  
|<span data-ttu-id="219df-292">(en blanco)</span><span class="sxs-lookup"><span data-stu-id="219df-292">(blank)</span></span>|<span data-ttu-id="219df-293">Se admite.</span><span class="sxs-lookup"><span data-stu-id="219df-293">Supported.</span></span>|  
  
 <span data-ttu-id="219df-294">\* Cuando se usa el `simpleType` y `complexType,` asignación para tipos anónimos es el mismo que los tipos no anónimos, salvo que no hay ningún contrato de datos anónimos, por lo que se crea un contrato de datos con nombre, con un nombre generado derivado del nombre de elemento.</span><span class="sxs-lookup"><span data-stu-id="219df-294">\* When using the `simpleType` and `complexType,` mapping for anonymous types is the same as for non-anonymous types, except that there is no anonymous data contracts, and so a named data contract is created, with a generated name derived from the element name.</span></span> <span data-ttu-id="219df-295">Las reglas para los tipos anónimos están en la lista siguiente:</span><span class="sxs-lookup"><span data-stu-id="219df-295">The rules for anonymous types are in the following list:</span></span>  
  
-   <span data-ttu-id="219df-296">Detalle de implementación de WCF: Si el `xs:element` nombre no contiene puntos, el tipo anónimo asigna a un tipo interno del tipo de contrato de datos externo.</span><span class="sxs-lookup"><span data-stu-id="219df-296">WCF implementation detail: If the `xs:element` name does not contain periods, the anonymous type maps to an inner type of the outer data contract type.</span></span> <span data-ttu-id="219df-297">Si el nombre contiene puntos, el tipo de contrato de datos resultante es independiente (no un tipo interno).</span><span class="sxs-lookup"><span data-stu-id="219df-297">If the name contains periods, the resulting data contract type is independent (not an inner type).</span></span>  
  
-   <span data-ttu-id="219df-298">El nombre de contrato de datos generado del tipo interno es el nombre de contrato de datos del tipo exterior seguido por un punto, el nombre del elemento, y la cadena “Type”.</span><span class="sxs-lookup"><span data-stu-id="219df-298">The generated data contract name of the inner type is the data contract name of the outer type followed by a period, the name of the element, and the string "Type".</span></span>  
  
-   <span data-ttu-id="219df-299">Si un contrato de datos con este tipo de nombre ya existe, el nombre se hace único anexando "1", "2", "3", y así sucesivamente, hasta que se cree un nombre único.</span><span class="sxs-lookup"><span data-stu-id="219df-299">If a data contract with such a name already exists, the name is made unique by appending "1", "2", "3", and so on until a unique name is created.</span></span>  
  
## <a name="simple-types---xssimpletype"></a><span data-ttu-id="219df-300">Tipos simples: \<xs: simpleType ></span><span class="sxs-lookup"><span data-stu-id="219df-300">Simple Types - \<xs:simpleType></span></span>  
  
### <a name="xssimpletype-attributes"></a><span data-ttu-id="219df-301">\<xs:simpleType>: attributes</span><span class="sxs-lookup"><span data-stu-id="219df-301">\<xs:simpleType>: attributes</span></span>  
  
|<span data-ttu-id="219df-302">Atributo</span><span class="sxs-lookup"><span data-stu-id="219df-302">Attribute</span></span>|<span data-ttu-id="219df-303">Schema</span><span class="sxs-lookup"><span data-stu-id="219df-303">Schema</span></span>|  
|---------------|------------|  
|`final`|<span data-ttu-id="219df-304">ignorado.</span><span class="sxs-lookup"><span data-stu-id="219df-304">Ignored.</span></span>|  
|`id`|<span data-ttu-id="219df-305">ignorado.</span><span class="sxs-lookup"><span data-stu-id="219df-305">Ignored.</span></span>|  
|`name`|<span data-ttu-id="219df-306">Admitido, asigna al nombre de contrato de datos.</span><span class="sxs-lookup"><span data-stu-id="219df-306">Supported, maps to the data contract name.</span></span>|  
  
### <a name="xssimpletype-contents"></a><span data-ttu-id="219df-307">\<xs:simpleType>: contents</span><span class="sxs-lookup"><span data-stu-id="219df-307">\<xs:simpleType>: contents</span></span>  
  
|<span data-ttu-id="219df-308">Contenido</span><span class="sxs-lookup"><span data-stu-id="219df-308">Contents</span></span>|<span data-ttu-id="219df-309">Schema</span><span class="sxs-lookup"><span data-stu-id="219df-309">Schema</span></span>|  
|--------------|------------|  
|`restriction`|<span data-ttu-id="219df-310">Se admite.</span><span class="sxs-lookup"><span data-stu-id="219df-310">Supported.</span></span> <span data-ttu-id="219df-311">Asigna a contratos de datos de enumeración.</span><span class="sxs-lookup"><span data-stu-id="219df-311">Maps to enumeration data contracts.</span></span> <span data-ttu-id="219df-312">Este atributo se omite si no coincide con el patrón de enumeración.</span><span class="sxs-lookup"><span data-stu-id="219df-312">This attribute is ignored if it does not match the enumeration pattern.</span></span> <span data-ttu-id="219df-313">Vea la sección de restricciones de `xs:simpleType` .</span><span class="sxs-lookup"><span data-stu-id="219df-313">See the `xs:simpleType` restrictions section.</span></span>|  
|`list`|<span data-ttu-id="219df-314">Se admite.</span><span class="sxs-lookup"><span data-stu-id="219df-314">Supported.</span></span> <span data-ttu-id="219df-315">Asigna a contratos de datos de enumeración de marcas.</span><span class="sxs-lookup"><span data-stu-id="219df-315">Maps to flag enumeration data contracts.</span></span> <span data-ttu-id="219df-316">Vea la sección de listas de `xs:simpleType` .</span><span class="sxs-lookup"><span data-stu-id="219df-316">See the `xs:simpleType` lists section.</span></span>|  
|`union`|<span data-ttu-id="219df-317">no autorizado.</span><span class="sxs-lookup"><span data-stu-id="219df-317">Forbidden.</span></span>|  
  
### <a name="xsrestriction"></a><span data-ttu-id="219df-318">\<xs:restriction></span><span class="sxs-lookup"><span data-stu-id="219df-318">\<xs:restriction></span></span>  
  
-   <span data-ttu-id="219df-319">Las restricciones de tipos complejos solo se admiten para base = "`xs:anyType`".</span><span class="sxs-lookup"><span data-stu-id="219df-319">Complex type restrictions are supported only for base="`xs:anyType`".</span></span>  
  
-   <span data-ttu-id="219df-320">Las restricciones de tipos simples de `xs:string` que no tienen facetas de restricciones que no sean `xs:enumeration` están asignadas a contratos de datos de enumeración.</span><span class="sxs-lookup"><span data-stu-id="219df-320">Simple type restrictions of `xs:string` that do not have any restriction facets other than `xs:enumeration` are mapped to enumeration data contracts.</span></span>  
  
-   <span data-ttu-id="219df-321">El resto de restricciones de tipos simples se asignan a los tipos que restringen.</span><span class="sxs-lookup"><span data-stu-id="219df-321">All other simple type restrictions are mapped to the types they restrict.</span></span> <span data-ttu-id="219df-322">Por ejemplo, una restricción de `xs:int` se asigna a un entero, como hace `xs:int` .</span><span class="sxs-lookup"><span data-stu-id="219df-322">For example, a restriction of `xs:int` maps to an integer, just as `xs:int` itself does.</span></span> <span data-ttu-id="219df-323">Para obtener más información sobre la asignación de tipo primitivo, vea asignación de tipo/primitivo.</span><span class="sxs-lookup"><span data-stu-id="219df-323">For more information about primitive type mapping, see Type/primitive mapping.</span></span>  
  
### <a name="xsrestriction-attributes"></a><span data-ttu-id="219df-324">\<xs:restriction>: attributes</span><span class="sxs-lookup"><span data-stu-id="219df-324">\<xs:restriction>: attributes</span></span>  
  
|<span data-ttu-id="219df-325">Atributo</span><span class="sxs-lookup"><span data-stu-id="219df-325">Attribute</span></span>|<span data-ttu-id="219df-326">Schema</span><span class="sxs-lookup"><span data-stu-id="219df-326">Schema</span></span>|  
|---------------|------------|  
|`base`|<span data-ttu-id="219df-327">Debe ser un tipo simple admitido o `xs:anyType`.</span><span class="sxs-lookup"><span data-stu-id="219df-327">Must be a supported simple type or `xs:anyType`.</span></span>|  
|`id`|<span data-ttu-id="219df-328">ignorado.</span><span class="sxs-lookup"><span data-stu-id="219df-328">Ignored.</span></span>|  
  
### <a name="xsrestriction-for-all-other-cases-contents"></a><span data-ttu-id="219df-329">\<xs: restriction > para todos los demás casos: contenido</span><span class="sxs-lookup"><span data-stu-id="219df-329">\<xs:restriction> for all other cases: contents</span></span>  
  
|<span data-ttu-id="219df-330">Contenido</span><span class="sxs-lookup"><span data-stu-id="219df-330">Contents</span></span>|<span data-ttu-id="219df-331">Schema</span><span class="sxs-lookup"><span data-stu-id="219df-331">Schema</span></span>|  
|--------------|------------|  
|`simpleType`|<span data-ttu-id="219df-332">Si está presente, se debe derivar de un tipo primitivo admitido.</span><span class="sxs-lookup"><span data-stu-id="219df-332">If present, must be derived from a supported primitive type.</span></span>|  
|`minExclusive`|<span data-ttu-id="219df-333">ignorado.</span><span class="sxs-lookup"><span data-stu-id="219df-333">Ignored.</span></span>|  
|`minInclusive`|<span data-ttu-id="219df-334">ignorado.</span><span class="sxs-lookup"><span data-stu-id="219df-334">Ignored.</span></span>|  
|`maxExclusive`|<span data-ttu-id="219df-335">ignorado.</span><span class="sxs-lookup"><span data-stu-id="219df-335">Ignored.</span></span>|  
|`maxInclusive`|<span data-ttu-id="219df-336">ignorado.</span><span class="sxs-lookup"><span data-stu-id="219df-336">Ignored.</span></span>|  
|`totalDigits`|<span data-ttu-id="219df-337">ignorado.</span><span class="sxs-lookup"><span data-stu-id="219df-337">Ignored.</span></span>|  
|`fractionDigits`|<span data-ttu-id="219df-338">ignorado.</span><span class="sxs-lookup"><span data-stu-id="219df-338">Ignored.</span></span>|  
|`length`|<span data-ttu-id="219df-339">ignorado.</span><span class="sxs-lookup"><span data-stu-id="219df-339">Ignored.</span></span>|  
|`minLength`|<span data-ttu-id="219df-340">ignorado.</span><span class="sxs-lookup"><span data-stu-id="219df-340">Ignored.</span></span>|  
|`maxLength`|<span data-ttu-id="219df-341">ignorado.</span><span class="sxs-lookup"><span data-stu-id="219df-341">Ignored.</span></span>|  
|`enumeration`|<span data-ttu-id="219df-342">ignorado.</span><span class="sxs-lookup"><span data-stu-id="219df-342">Ignored.</span></span>|  
|`whiteSpace`|<span data-ttu-id="219df-343">ignorado.</span><span class="sxs-lookup"><span data-stu-id="219df-343">Ignored.</span></span>|  
|`pattern`|<span data-ttu-id="219df-344">ignorado.</span><span class="sxs-lookup"><span data-stu-id="219df-344">Ignored.</span></span>|  
|<span data-ttu-id="219df-345">(en blanco)</span><span class="sxs-lookup"><span data-stu-id="219df-345">(blank)</span></span>|<span data-ttu-id="219df-346">Se admite.</span><span class="sxs-lookup"><span data-stu-id="219df-346">Supported.</span></span>|  
  
## <a name="enumeration"></a><span data-ttu-id="219df-347">Enumeración</span><span class="sxs-lookup"><span data-stu-id="219df-347">Enumeration</span></span>  
  
### <a name="xsrestriction-for-enumerations-attributes"></a><span data-ttu-id="219df-348">\<xs: restriction > para enumeraciones: atributos</span><span class="sxs-lookup"><span data-stu-id="219df-348">\<xs:restriction> for enumerations: attributes</span></span>  
  
|<span data-ttu-id="219df-349">Atributo</span><span class="sxs-lookup"><span data-stu-id="219df-349">Attribute</span></span>|<span data-ttu-id="219df-350">Schema</span><span class="sxs-lookup"><span data-stu-id="219df-350">Schema</span></span>|  
|---------------|------------|  
|`base`|<span data-ttu-id="219df-351">Si está presente, debe ser `xs:string`.</span><span class="sxs-lookup"><span data-stu-id="219df-351">If present, must be `xs:string`.</span></span>|  
|`id`|<span data-ttu-id="219df-352">ignorado.</span><span class="sxs-lookup"><span data-stu-id="219df-352">Ignored.</span></span>|  
  
### <a name="xsrestriction-for-enumerations-contents"></a><span data-ttu-id="219df-353">\<xs: restriction > para enumeraciones: contenido</span><span class="sxs-lookup"><span data-stu-id="219df-353">\<xs:restriction> for enumerations: contents</span></span>  
  
|<span data-ttu-id="219df-354">Contenido</span><span class="sxs-lookup"><span data-stu-id="219df-354">Contents</span></span>|<span data-ttu-id="219df-355">Schema</span><span class="sxs-lookup"><span data-stu-id="219df-355">Schema</span></span>|  
|--------------|------------|  
|`simpleType`|<span data-ttu-id="219df-356">Si está presente, debe ser una restricción de enumeración admitida por el contrato de datos (esta sección).</span><span class="sxs-lookup"><span data-stu-id="219df-356">If present, must be an enumeration restriction supported by the data contract (this section).</span></span>|  
|`minExclusive`|<span data-ttu-id="219df-357">ignorado.</span><span class="sxs-lookup"><span data-stu-id="219df-357">Ignored.</span></span>|  
|`minInclusive`|<span data-ttu-id="219df-358">ignorado.</span><span class="sxs-lookup"><span data-stu-id="219df-358">Ignored.</span></span>|  
|`maxExclusive`|<span data-ttu-id="219df-359">ignorado.</span><span class="sxs-lookup"><span data-stu-id="219df-359">Ignored.</span></span>|  
|`maxInclusive`|<span data-ttu-id="219df-360">ignorado.</span><span class="sxs-lookup"><span data-stu-id="219df-360">Ignored.</span></span>|  
|`totalDigits`|<span data-ttu-id="219df-361">ignorado.</span><span class="sxs-lookup"><span data-stu-id="219df-361">Ignored.</span></span>|  
|`fractionDigits`|<span data-ttu-id="219df-362">ignorado.</span><span class="sxs-lookup"><span data-stu-id="219df-362">Ignored.</span></span>|  
|`length`|<span data-ttu-id="219df-363">no autorizado.</span><span class="sxs-lookup"><span data-stu-id="219df-363">Forbidden.</span></span>|  
|`minLength`|<span data-ttu-id="219df-364">no autorizado.</span><span class="sxs-lookup"><span data-stu-id="219df-364">Forbidden.</span></span>|  
|`maxLength`|<span data-ttu-id="219df-365">no autorizado.</span><span class="sxs-lookup"><span data-stu-id="219df-365">Forbidden.</span></span>|  
|`enumeration`|<span data-ttu-id="219df-366">Se admite.</span><span class="sxs-lookup"><span data-stu-id="219df-366">Supported.</span></span> <span data-ttu-id="219df-367">Se omite el "id" de enumeración y "value" se asigna al nombre del valor en el contrato de datos de enumeración.</span><span class="sxs-lookup"><span data-stu-id="219df-367">Enumeration "id" is ignored, and "value" maps to the value name in the enumeration data contract.</span></span>|  
|`whiteSpace`|<span data-ttu-id="219df-368">no autorizado.</span><span class="sxs-lookup"><span data-stu-id="219df-368">Forbidden.</span></span>|  
|`pattern`|<span data-ttu-id="219df-369">no autorizado.</span><span class="sxs-lookup"><span data-stu-id="219df-369">Forbidden.</span></span>|  
|<span data-ttu-id="219df-370">(vacío)</span><span class="sxs-lookup"><span data-stu-id="219df-370">(empty)</span></span>|<span data-ttu-id="219df-371">Compatible; se asigna a un tipo de enumeración vacío.</span><span class="sxs-lookup"><span data-stu-id="219df-371">Supported, maps to empty enumeration type.</span></span>|  
  
 <span data-ttu-id="219df-372">En el siguiente código se muestra una clase de enumeración de C#.</span><span class="sxs-lookup"><span data-stu-id="219df-372">The following code shows a C# enumeration class.</span></span>  
  
```csharp  
public enum MyEnum  
{  
  first = 3,  
  second = 4,  
  third =5  
}  
```  
  
 <span data-ttu-id="219df-373">Esta clase se asigna al esquema siguiente mediante el `DataContractSerializer`.</span><span class="sxs-lookup"><span data-stu-id="219df-373">This class maps to the following schema by the `DataContractSerializer`.</span></span> <span data-ttu-id="219df-374">Si los valores de la enumeración se inician en 1, no se generan bloques `xs:annotation` .</span><span class="sxs-lookup"><span data-stu-id="219df-374">If enumeration values start from 1, `xs:annotation` blocks are not generated.</span></span>  
  
```xml  
<xs:simpleType name="MyEnum">  
<xs:restriction base="xs:string">  
 <xs:enumeration value="first">  
  <xs:annotation>  
   <xs:appinfo>  
    <EnumerationValue   
     xmlns="http://schemas.microsoft.com/2003/10/Serialization/">  
     3  
    </EnumerationValue>  
   </xs:appinfo>  
  </xs:annotation>  
 </xs:enumeration>  
 <xs:enumeration value="second">  
  <xs:annotation>  
   <xs:appinfo>  
    <EnumerationValue   
     xmlns="http://schemas.microsoft.com/2003/10/Serialization/">  
     4  
    </EnumerationValue>  
   </xs:appinfo>  
  </xs:annotation>  
 </xs:enumeration>  
</xs:restriction>  
</xs:simpleType>  
```  
  
### <a name="xslist"></a><span data-ttu-id="219df-375">\<xs:list></span><span class="sxs-lookup"><span data-stu-id="219df-375">\<xs:list></span></span>  
 <span data-ttu-id="219df-376">El`DataContractSerializer` asigna tipos de enumeración marcados con `System.FlagsAttribute` a `xs:list` derivado de `xs:string`.</span><span class="sxs-lookup"><span data-stu-id="219df-376">`DataContractSerializer` maps enumeration types marked with `System.FlagsAttribute` to `xs:list` derived from `xs:string`.</span></span> <span data-ttu-id="219df-377">No se admite ninguna otra variación de `xs:list` .</span><span class="sxs-lookup"><span data-stu-id="219df-377">No other `xs:list` variations are supported.</span></span>  
  
### <a name="xslist-attributes"></a><span data-ttu-id="219df-378">\<xs:list>: attributes</span><span class="sxs-lookup"><span data-stu-id="219df-378">\<xs:list>: attributes</span></span>  
  
|<span data-ttu-id="219df-379">Atributo</span><span class="sxs-lookup"><span data-stu-id="219df-379">Attribute</span></span>|<span data-ttu-id="219df-380">Schema</span><span class="sxs-lookup"><span data-stu-id="219df-380">Schema</span></span>|  
|---------------|------------|  
|`itemType`|<span data-ttu-id="219df-381">no autorizado.</span><span class="sxs-lookup"><span data-stu-id="219df-381">Forbidden.</span></span>|  
|`id`|<span data-ttu-id="219df-382">ignorado.</span><span class="sxs-lookup"><span data-stu-id="219df-382">Ignored.</span></span>|  
  
### <a name="xslist-contents"></a><span data-ttu-id="219df-383">\<xs:list>: contents</span><span class="sxs-lookup"><span data-stu-id="219df-383">\<xs:list>: contents</span></span>  
  
|<span data-ttu-id="219df-384">Contenido</span><span class="sxs-lookup"><span data-stu-id="219df-384">Contents</span></span>|<span data-ttu-id="219df-385">Schema</span><span class="sxs-lookup"><span data-stu-id="219df-385">Schema</span></span>|  
|--------------|------------|  
|`simpleType`|<span data-ttu-id="219df-386">Debe ser la restricción de `xs:string` utilizando la faceta `xs:enumeration` .</span><span class="sxs-lookup"><span data-stu-id="219df-386">Must be restriction from `xs:string` using `xs:enumeration` facet.</span></span>|  
  
 <span data-ttu-id="219df-387">Si el valor de enumeración no sigue una progresión de potencia 2 (valor predeterminado para marcas), el valor se almacena en `xs:annotation/xs:appInfo/ser:EnumerationValue` .</span><span class="sxs-lookup"><span data-stu-id="219df-387">If enumeration value does not follow a power of 2 progression (default for Flags), the value is stored in the `xs:annotation/xs:appInfo/ser:EnumerationValue` element.</span></span>  
  
 <span data-ttu-id="219df-388">Por ejemplo, el código siguiente marca un tipo de enumeración.</span><span class="sxs-lookup"><span data-stu-id="219df-388">For example, the following code flags an enumeration type.</span></span>  
  
```csharp  
[Flags]  
public enum AuthFlags  
{    
  AuthAnonymous = 1,  
  AuthBasic = 2,  
  AuthNTLM = 4,  
  AuthMD5 = 16,  
  AuthWindowsLiveID = 64,  
}  
```  
  
 <span data-ttu-id="219df-389">Este tipo asigna al esquema siguiente.</span><span class="sxs-lookup"><span data-stu-id="219df-389">This type maps to the following schema.</span></span>  
  
```xml  
<xs:simpleType name="AuthFlags">  
    <xs:list>  
      <xs:simpleType>  
        <xs:restriction base="xs:string">  
          <xs:enumeration value="AuthAnonymous" />  
          <xs:enumeration value="AuthBasic" />  
          <xs:enumeration value="AuthNTLM" />  
          <xs:enumeration value="AuthMD5">  
            <xs:annotation>  
              <xs:appinfo>  
                <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Se  
rialization/">16</EnumerationValue>  
              </xs:appinfo>  
            </xs:annotation>  
          </xs:enumeration>  
          <xs:enumeration value="AuthWindowsLiveID">  
            <xs:annotation>  
              <xs:appinfo>  
                <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Se  
rialization/">64</EnumerationValue>  
              </xs:appinfo>  
            </xs:annotation>  
          </xs:enumeration>  
        </xs:restriction>  
      </xs:simpleType>  
    </xs:list>  
  </xs:simpleType>  
```  
  
## <a name="inheritance"></a><span data-ttu-id="219df-390">Herencia</span><span class="sxs-lookup"><span data-stu-id="219df-390">Inheritance</span></span>  
  
### <a name="general-rules"></a><span data-ttu-id="219df-391">Reglas Generales</span><span class="sxs-lookup"><span data-stu-id="219df-391">General rules</span></span>  
 <span data-ttu-id="219df-392">Un contrato de datos puede heredar de otro contrato de datos.</span><span class="sxs-lookup"><span data-stu-id="219df-392">A data contract can inherit from another data contract.</span></span> <span data-ttu-id="219df-393">Tales contratos de datos asignan a una base y son derivados por tipos de extensión mediante la construcción de squema XML `<xs:extension>` .</span><span class="sxs-lookup"><span data-stu-id="219df-393">Such data contracts map to a base and are derived by extension types using the `<xs:extension>` XML Schema construct.</span></span>  
  
 <span data-ttu-id="219df-394">Un contrato de datos no puede heredar de un contrato de datos de colección.</span><span class="sxs-lookup"><span data-stu-id="219df-394">A data contract cannot inherit from a collection data contract.</span></span>  
  
 <span data-ttu-id="219df-395">Por ejemplo, el código siguiente es un contrato de datos.</span><span class="sxs-lookup"><span data-stu-id="219df-395">For example, the following code is a data contract.</span></span>  
  
```csharp  
[DataContract]  
public class Person  
{  
  [DataMember]  
  public string Name;  
}  
[DataContract]  
public class Employee : Person   
{      
  [DataMember]  
  public int ID;  
}  
```  
  
 <span data-ttu-id="219df-396">Este contrato de datos asigna a la declaración de tipos de esquema XML siguiente.</span><span class="sxs-lookup"><span data-stu-id="219df-396">This data contract maps to the following XML Schema type declaration.</span></span>  
  
```xml  
<xs:complexType name="Employee">  
 <xs:complexContent mixed="false">  
  <xs:extension base="tns:Person">  
   <xs:sequence>  
    <xs:element minOccurs="0" name="ID" type="xs:int"/>  
   </xs:sequence>  
  </xs:extension>  
 </xs:complexContent>  
</xs:complexType>  
<xs:complexType name="Person">  
 <xs:sequence>  
  <xs:element minOccurs="0" name="Name"   
    nillable="true" type="xs:string"/>  
 </xs:sequence>  
</xs:complexType>  
```  
  
### <a name="xscomplexcontent-attributes"></a><span data-ttu-id="219df-397">\<xs: complexContent >: atributos</span><span class="sxs-lookup"><span data-stu-id="219df-397">\<xs:complexContent>: attributes</span></span>  
  
|<span data-ttu-id="219df-398">Atributo</span><span class="sxs-lookup"><span data-stu-id="219df-398">Attribute</span></span>|<span data-ttu-id="219df-399">Schema</span><span class="sxs-lookup"><span data-stu-id="219df-399">Schema</span></span>|  
|---------------|------------|  
|`id`|<span data-ttu-id="219df-400">ignorado.</span><span class="sxs-lookup"><span data-stu-id="219df-400">Ignored.</span></span>|  
|`mixed`|<span data-ttu-id="219df-401">Debe ser false.</span><span class="sxs-lookup"><span data-stu-id="219df-401">Must be false.</span></span>|  
  
### <a name="xscomplexcontent-contents"></a><span data-ttu-id="219df-402">\<xs: complexContent >: contenido</span><span class="sxs-lookup"><span data-stu-id="219df-402">\<xs:complexContent>: contents</span></span>  
  
|<span data-ttu-id="219df-403">Contenido</span><span class="sxs-lookup"><span data-stu-id="219df-403">Contents</span></span>|<span data-ttu-id="219df-404">Schema</span><span class="sxs-lookup"><span data-stu-id="219df-404">Schema</span></span>|  
|--------------|------------|  
|`restriction`|<span data-ttu-id="219df-405">Prohibido, excepto cuando base = "`xs:anyType`".</span><span class="sxs-lookup"><span data-stu-id="219df-405">Forbidden, except when base="`xs:anyType`".</span></span> <span data-ttu-id="219df-406">Lo último es equivalente a colocar directamente el contenido de `xs:restriction` bajo el contenedor de `xs:complexContent`.</span><span class="sxs-lookup"><span data-stu-id="219df-406">The latter is equivalent to placing the content of the `xs:restriction` directly under the container of the `xs:complexContent`.</span></span>|  
|`extension`|<span data-ttu-id="219df-407">Se admite.</span><span class="sxs-lookup"><span data-stu-id="219df-407">Supported.</span></span> <span data-ttu-id="219df-408">Asigna a la herencia del contrato de datos.</span><span class="sxs-lookup"><span data-stu-id="219df-408">Maps to data contract inheritance.</span></span>|  
  
### <a name="xsextension-in-xscomplexcontent-attributes"></a><span data-ttu-id="219df-409">\<xs: extension > en \<xs: complexContent >: atributos</span><span class="sxs-lookup"><span data-stu-id="219df-409">\<xs:extension> in \<xs:complexContent>: attributes</span></span>  
  
|<span data-ttu-id="219df-410">Atributo</span><span class="sxs-lookup"><span data-stu-id="219df-410">Attribute</span></span>|<span data-ttu-id="219df-411">Schema</span><span class="sxs-lookup"><span data-stu-id="219df-411">Schema</span></span>|  
|---------------|------------|  
|`id`|<span data-ttu-id="219df-412">ignorado.</span><span class="sxs-lookup"><span data-stu-id="219df-412">Ignored.</span></span>|  
|`base`|<span data-ttu-id="219df-413">Se admite.</span><span class="sxs-lookup"><span data-stu-id="219df-413">Supported.</span></span> <span data-ttu-id="219df-414">Asigna al tipo de contrato de datos base desde el que este tipo hereda.</span><span class="sxs-lookup"><span data-stu-id="219df-414">Maps to the base data contract type that this type inherits from.</span></span>|  
  
### <a name="xsextension-in-xscomplexcontent-contents"></a><span data-ttu-id="219df-415">\<xs: extension > en \<xs: complexContent >: contenido</span><span class="sxs-lookup"><span data-stu-id="219df-415">\<xs:extension> in \<xs:complexContent>: contents</span></span>  
 <span data-ttu-id="219df-416">Las reglas son la mismas que para el contenido `<xs:complexType>` .</span><span class="sxs-lookup"><span data-stu-id="219df-416">The rules are the same as for `<xs:complexType>` contents.</span></span>  
  
 <span data-ttu-id="219df-417">Si se proporciona un `<xs:sequence>` , sus elementos de miembro asignan a los miembros de datos adicionales que se encuentran en el contrato de datos derivado.</span><span class="sxs-lookup"><span data-stu-id="219df-417">If an `<xs:sequence>` is provided, its member elements map to additional data members that are present in the derived data contract.</span></span>  
  
 <span data-ttu-id="219df-418">Si un tipo derivado contiene un elemento con el mismo nombre que un elemento en un tipo base, la declaración de elementos duplicados asigna a un miembro de datos con un nombre que se genera para que sea único.</span><span class="sxs-lookup"><span data-stu-id="219df-418">If a derived type contains an element with the same name as an element in a base type, the duplicate element declaration maps to a data member with a name that is generated to be unique.</span></span> <span data-ttu-id="219df-419">Los números enteros positivos se suman al nombre del miembro de datos ("member1", "member2", etc.) hasta que se encuentre un nombre único.</span><span class="sxs-lookup"><span data-stu-id="219df-419">Positive integer numbers are added to the data member name ("member1", "member2", and so on) until a unique name is found.</span></span> <span data-ttu-id="219df-420">De manera inversa:</span><span class="sxs-lookup"><span data-stu-id="219df-420">Conversely:</span></span>  
  
-   <span data-ttu-id="219df-421">Si un contrato de datos derivado tiene un miembro de datos con el mismo nombre y tipo que un miembro de datos en un contrato de datos base, `DataContractSerializer` genera este elemento correspondiente en el tipo derivado.</span><span class="sxs-lookup"><span data-stu-id="219df-421">If a derived data contract has a data member with the same name and type as a data member in a base data contract, `DataContractSerializer` generates this corresponding element in the derived type.</span></span>  
  
-   <span data-ttu-id="219df-422">Si un contrato de datos derivado tiene un miembro de datos con el mismo nombre que un miembro de datos en un contrato de datos base pero un tipo diferente, el `DataContractSerializer` importa un esquema con un elemento del tipo `xs:anyType` en las declaraciones de tipos base y de tipos derivados.</span><span class="sxs-lookup"><span data-stu-id="219df-422">If a derived data contract has a data member with the same name as a data member in a base data contract but a different type, the `DataContractSerializer` imports a schema with an element of the type `xs:anyType` in both base type and derived type declarations.</span></span> <span data-ttu-id="219df-423">El nombre de tipo original se conserva en `xs:annotations/xs:appInfo/ser:ActualType/@Name`.</span><span class="sxs-lookup"><span data-stu-id="219df-423">The original type name is preserved in `xs:annotations/xs:appInfo/ser:ActualType/@Name`.</span></span>  
  
 <span data-ttu-id="219df-424">Ambas variaciones pueden conducir a un esquema con un modelo de contenido ambiguo, que depende del orden de los miembros de datos respectivos.</span><span class="sxs-lookup"><span data-stu-id="219df-424">Both variations may lead to a schema with an ambiguous content model, which depends on the order of the respective data members.</span></span>  
  
## <a name="typeprimitive-mapping"></a><span data-ttu-id="219df-425">Asignación de tipo/primitivo.</span><span class="sxs-lookup"><span data-stu-id="219df-425">Type/primitive mapping</span></span>  
 <span data-ttu-id="219df-426">El `DataContractSerializer` utiliza la asignación siguiente para los tipos primitivos del esquema XML.</span><span class="sxs-lookup"><span data-stu-id="219df-426">The `DataContractSerializer` uses the following mapping for XML Schema primitive types.</span></span>  
  
|<span data-ttu-id="219df-427">Tipo XSD</span><span class="sxs-lookup"><span data-stu-id="219df-427">XSD type</span></span>|<span data-ttu-id="219df-428">Tipo de .NET</span><span class="sxs-lookup"><span data-stu-id="219df-428">.NET type</span></span>|  
|--------------|---------------|  
|`anyType`|<span data-ttu-id="219df-429"><xref:System.Object>.</span><span class="sxs-lookup"><span data-stu-id="219df-429"><xref:System.Object>.</span></span>|  
|`anySimpleType`|<span data-ttu-id="219df-430"><xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="219df-430"><xref:System.String>.</span></span>|  
|`duration`|<span data-ttu-id="219df-431"><xref:System.TimeSpan>.</span><span class="sxs-lookup"><span data-stu-id="219df-431"><xref:System.TimeSpan>.</span></span>|  
|`dateTime`|<span data-ttu-id="219df-432"><xref:System.DateTime>.</span><span class="sxs-lookup"><span data-stu-id="219df-432"><xref:System.DateTime>.</span></span>|  
|`dateTimeOffset`|<span data-ttu-id="219df-433"><xref:System.DateTime> y <xref:System.TimeSpan> para el desplazamiento.</span><span class="sxs-lookup"><span data-stu-id="219df-433"><xref:System.DateTime> and <xref:System.TimeSpan> for the offset.</span></span> <span data-ttu-id="219df-434">Vea abajo Serialización de DateTimeOffset.</span><span class="sxs-lookup"><span data-stu-id="219df-434">See DateTimeOffset Serialization below.</span></span>|  
|`time`|<span data-ttu-id="219df-435"><xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="219df-435"><xref:System.String>.</span></span>|  
|`date`|<span data-ttu-id="219df-436"><xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="219df-436"><xref:System.String>.</span></span>|  
|`gYearMonth`|<span data-ttu-id="219df-437"><xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="219df-437"><xref:System.String>.</span></span>|  
|`gYear`|<span data-ttu-id="219df-438"><xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="219df-438"><xref:System.String>.</span></span>|  
|`gMonthDay`|<span data-ttu-id="219df-439"><xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="219df-439"><xref:System.String>.</span></span>|  
|`gDay`|<span data-ttu-id="219df-440"><xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="219df-440"><xref:System.String>.</span></span>|  
|`gMonth`|<span data-ttu-id="219df-441"><xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="219df-441"><xref:System.String>.</span></span>|  
|`boolean`|<xref:System.Boolean>|  
|`base64Binary`|<span data-ttu-id="219df-442">Matriz de tipo<xref:System.Byte> .</span><span class="sxs-lookup"><span data-stu-id="219df-442"><xref:System.Byte> array.</span></span>|  
|`hexBinary`|<span data-ttu-id="219df-443"><xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="219df-443"><xref:System.String>.</span></span>|  
|`float`|<span data-ttu-id="219df-444"><xref:System.Single>.</span><span class="sxs-lookup"><span data-stu-id="219df-444"><xref:System.Single>.</span></span>|  
|`double`|<span data-ttu-id="219df-445"><xref:System.Double>.</span><span class="sxs-lookup"><span data-stu-id="219df-445"><xref:System.Double>.</span></span>|  
|`anyURI`|<span data-ttu-id="219df-446"><xref:System.Uri>.</span><span class="sxs-lookup"><span data-stu-id="219df-446"><xref:System.Uri>.</span></span>|  
|`QName`|<span data-ttu-id="219df-447"><xref:System.Xml.XmlQualifiedName>.</span><span class="sxs-lookup"><span data-stu-id="219df-447"><xref:System.Xml.XmlQualifiedName>.</span></span>|  
|`string`|<span data-ttu-id="219df-448"><xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="219df-448"><xref:System.String>.</span></span>|  
|`normalizedString`|<span data-ttu-id="219df-449"><xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="219df-449"><xref:System.String>.</span></span>|  
|`token`|<span data-ttu-id="219df-450"><xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="219df-450"><xref:System.String>.</span></span>|  
|`language`|<span data-ttu-id="219df-451"><xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="219df-451"><xref:System.String>.</span></span>|  
|`Name`|<span data-ttu-id="219df-452"><xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="219df-452"><xref:System.String>.</span></span>|  
|`NCName`|<span data-ttu-id="219df-453"><xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="219df-453"><xref:System.String>.</span></span>|  
|`ID`|<span data-ttu-id="219df-454"><xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="219df-454"><xref:System.String>.</span></span>|  
|`IDREF`|<span data-ttu-id="219df-455"><xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="219df-455"><xref:System.String>.</span></span>|  
|`IDREFS`|<span data-ttu-id="219df-456"><xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="219df-456"><xref:System.String>.</span></span>|  
|`ENTITY`|<span data-ttu-id="219df-457"><xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="219df-457"><xref:System.String>.</span></span>|  
|`ENTITIES`|<span data-ttu-id="219df-458"><xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="219df-458"><xref:System.String>.</span></span>|  
|`NMTOKEN`|<span data-ttu-id="219df-459"><xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="219df-459"><xref:System.String>.</span></span>|  
|`NMTOKENS`|<span data-ttu-id="219df-460"><xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="219df-460"><xref:System.String>.</span></span>|  
|`decimal`|<span data-ttu-id="219df-461"><xref:System.Decimal>.</span><span class="sxs-lookup"><span data-stu-id="219df-461"><xref:System.Decimal>.</span></span>|  
|`integer`|<span data-ttu-id="219df-462"><xref:System.Int64>.</span><span class="sxs-lookup"><span data-stu-id="219df-462"><xref:System.Int64>.</span></span>|  
|`nonPositiveInteger`|<span data-ttu-id="219df-463"><xref:System.Int64>.</span><span class="sxs-lookup"><span data-stu-id="219df-463"><xref:System.Int64>.</span></span>|  
|`negativeInteger`|<span data-ttu-id="219df-464"><xref:System.Int64>.</span><span class="sxs-lookup"><span data-stu-id="219df-464"><xref:System.Int64>.</span></span>|  
|`long`|<span data-ttu-id="219df-465"><xref:System.Int64>.</span><span class="sxs-lookup"><span data-stu-id="219df-465"><xref:System.Int64>.</span></span>|  
|`int`|<span data-ttu-id="219df-466"><xref:System.Int32>.</span><span class="sxs-lookup"><span data-stu-id="219df-466"><xref:System.Int32>.</span></span>|  
|`short`|<span data-ttu-id="219df-467"><xref:System.Int16>.</span><span class="sxs-lookup"><span data-stu-id="219df-467"><xref:System.Int16>.</span></span>|  
|`Byte`|<span data-ttu-id="219df-468"><xref:System.SByte>.</span><span class="sxs-lookup"><span data-stu-id="219df-468"><xref:System.SByte>.</span></span>|  
|`nonNegativeInteger`|<span data-ttu-id="219df-469"><xref:System.Int64>.</span><span class="sxs-lookup"><span data-stu-id="219df-469"><xref:System.Int64>.</span></span>|  
|`unsignedLong`|<span data-ttu-id="219df-470"><xref:System.UInt64>.</span><span class="sxs-lookup"><span data-stu-id="219df-470"><xref:System.UInt64>.</span></span>|  
|`unsignedInt`|<span data-ttu-id="219df-471"><xref:System.UInt32>.</span><span class="sxs-lookup"><span data-stu-id="219df-471"><xref:System.UInt32>.</span></span>|  
|`unsignedShort`|<span data-ttu-id="219df-472"><xref:System.UInt16>.</span><span class="sxs-lookup"><span data-stu-id="219df-472"><xref:System.UInt16>.</span></span>|  
|`unsignedByte`|<span data-ttu-id="219df-473"><xref:System.Byte>.</span><span class="sxs-lookup"><span data-stu-id="219df-473"><xref:System.Byte>.</span></span>|  
|`positiveInteger`|<span data-ttu-id="219df-474"><xref:System.Int64>.</span><span class="sxs-lookup"><span data-stu-id="219df-474"><xref:System.Int64>.</span></span>|  
  
## <a name="iserializable-types-mapping"></a><span data-ttu-id="219df-475">Asignación de tipos ISerializable</span><span class="sxs-lookup"><span data-stu-id="219df-475">ISerializable types mapping</span></span>  
 <span data-ttu-id="219df-476">En la versión 1.0 de [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 1.0, <xref:System.Runtime.Serialization.ISerializable> se introdujo como un mecanismo general para serializar objetos para proporcionar persistencia o transferencia de datos.</span><span class="sxs-lookup"><span data-stu-id="219df-476">In [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] version 1.0, <xref:System.Runtime.Serialization.ISerializable> was introduced as a general mechanism to serialize objects for persistence or data transfer.</span></span> <span data-ttu-id="219df-477">Hay muchos tipos de [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] que implementan `ISerializable` y que pueden pasarse entre aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="219df-477">There are many [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] types that implement `ISerializable` and that can be passed between applications.</span></span> <span data-ttu-id="219df-478"><xref:System.Runtime.Serialization.DataContractSerializer> proporciona de manera natural compatibilidad para las clases `ISerializable` .</span><span class="sxs-lookup"><span data-stu-id="219df-478"><xref:System.Runtime.Serialization.DataContractSerializer> naturally provides support for `ISerializable` classes.</span></span> <span data-ttu-id="219df-479">`DataContractSerializer` asigna tipos de esquema de implementación de `ISerializable` que solo difieren en cuanto al QName (nombre completo) del tipo y son colecciones de propiedades.</span><span class="sxs-lookup"><span data-stu-id="219df-479">The `DataContractSerializer` maps `ISerializable` implementation schema types that differ only by the QName (qualified name) of the type and are effectively property collections.</span></span> <span data-ttu-id="219df-480">Por ejemplo, el `DataContractSerializer` asigna <xref:System.Exception> al tipo XSD siguiente en el `http://schemas.datacontract.org/2004/07/System` espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="219df-480">For example, the `DataContractSerializer` maps <xref:System.Exception> to the following XSD type in the `http://schemas.datacontract.org/2004/07/System` namespace.</span></span>  
  
```xml  
<xs:complexType name="Exception">  
 <xs:sequence>  
  <xs:any minOccurs="0" maxOccurs="unbounded"   
      namespace="##local" processContents="skip"/>  
 </xs:sequence>  
 <xs:attribute ref="ser:FactoryType"/>  
</xs:complexType>  
```  
  
 <span data-ttu-id="219df-481">El atributo opcional `ser:FactoryType` opcional declarado en el esquema de serialización de contrato de datos hace referencia a una clase de generador que puede deserializar el tipo.</span><span class="sxs-lookup"><span data-stu-id="219df-481">The optional attribute `ser:FactoryType` declared in the Data Contract Serialization schema references a factory class that can deserialize the type.</span></span> <span data-ttu-id="219df-482">La clase de generador debe formar parte de la colección de tipos conocidos de la instancia de `DataContractSerializer` que se está usando.</span><span class="sxs-lookup"><span data-stu-id="219df-482">The factory class must be part of the known types collection of the `DataContractSerializer` instance being used.</span></span> <span data-ttu-id="219df-483">Para obtener más información sobre los tipos conocidos, consulte [Data Contract Known Types](../../../../docs/framework/wcf/feature-details/data-contract-known-types.md).</span><span class="sxs-lookup"><span data-stu-id="219df-483">For more information about known types, see [Data Contract Known Types](../../../../docs/framework/wcf/feature-details/data-contract-known-types.md).</span></span>  
  
## <a name="datacontract-serialization-schema"></a><span data-ttu-id="219df-484">Esquema de serialización de DataContract</span><span class="sxs-lookup"><span data-stu-id="219df-484">DataContract Serialization Schema</span></span>  
 <span data-ttu-id="219df-485">Varios esquemas exportados por los tipos de uso, elementos y atributos del `DataContractSerializer` , desde un espacio de nombres de serialización de contrato de datos especial:</span><span class="sxs-lookup"><span data-stu-id="219df-485">A number of schemas exported by the `DataContractSerializer` use types, elements, and attributes from a special Data Contract Serialization namespace:</span></span>  
  
 `http://schemas.microsoft.com/2003/10/Serialization`
  
 <span data-ttu-id="219df-486">A continuación, se muestra una declaración de esquema de serialización de contrato de datos completa.</span><span class="sxs-lookup"><span data-stu-id="219df-486">The following is a complete Data Contract Serialization schema declaration.</span></span>  
  
```xml  
<xs:schema attributeFormDefault="qualified"          
   elementFormDefault="qualified"        
   targetNamespace =   
    "http://schemas.microsoft.com/2003/10/Serialization/"   
   xmlns:xs="http://www.w3.org/2001/XMLSchema"        
   xmlns:tns="http://schemas.microsoft.com/2003/10/Serialization/">  
  
 <!-- Top-level elements for primitive types. -->  
 <xs:element name="anyType" nillable="true" type="xs:anyType"/>  
 <xs:element name="anyURI" nillable="true" type="xs:anyURI"/>  
 <xs:element name="base64Binary"  
       nillable="true" type="xs:base64Binary"/>  
 <xs:element name="boolean" nillable="true" type="xs:boolean"/>  
 <xs:element name="byte" nillable="true" type="xs:byte"/>  
 <xs:element name="dateTime" nillable="true" type="xs:dateTime"/>  
 <xs:element name="decimal" nillable="true" type="xs:decimal"/>  
 <xs:element name="double" nillable="true" type="xs:double"/>  
 <xs:element name="float" nillable="true" type="xs:float"/>  
 <xs:element name="int" nillable="true" type="xs:int"/>  
 <xs:element name="long" nillable="true" type="xs:long"/>  
 <xs:element name="QName" nillable="true" type="xs:QName"/>  
 <xs:element name="short" nillable="true" type="xs:short"/>  
 <xs:element name="string" nillable="true" type="xs:string"/>  
 <xs:element name="unsignedByte"  
       nillable="true" type="xs:unsignedByte"/>  
 <xs:element name="unsignedInt"  
       nillable="true" type="xs:unsignedInt"/>  
 <xs:element name="unsignedLong"  
       nillable="true" type="xs:unsignedLong"/>  
 <xs:element name="unsignedShort"  
       nillable="true" type="xs:unsignedShort"/>  
  
 <!-- Primitive types introduced for certain .NET simple types. -->  
 <xs:element name="char" nillable="true" type="tns:char"/>  
 <xs:simpleType name="char">  
  <xs:restriction base="xs:int"/>  
 </xs:simpleType>  
  
 <!-- xs:duration is restricted to an ordered value space,  
    to map to System.TimeSpan -->  
 <xs:element name="duration" nillable="true" type="tns:duration"/>  
 <xs:simpleType name="duration">  
  <xs:restriction base="xs:duration">  
   <xs:pattern   
     value="\-?P(\d*D)?(T(\d*H)?(\d*M)?(\d*(\.\d*)?S)?)?"/>  
   <xs:minInclusive value="-P10675199DT2H48M5.4775808S"/>  
   <xs:maxInclusive value="P10675199DT2H48M5.4775807S"/>  
  </xs:restriction>  
 </xs:simpleType>  
  
 <xs:element name="guid" nillable="true" type="tns:guid"/>  
 <xs:simpleType name="guid">  
  <xs:restriction base="xs:string">  
   <xs:pattern value="[\da-fA-F]{8}-[\da-fA-F]{4}-[\da-fA-F]{4}-[\da-fA-F]{4}-[\da-fA-F]{12}"/>  
  </xs:restriction>  
 </xs:simpleType>  
  
 <!-- This is used for schemas exported from ISerializable type. -->  
 <xs:attribute name="FactoryType" type="xs:QName"/>  
</xs:schema>  
```  
  
 <span data-ttu-id="219df-487">Se debería tener en cuenta lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="219df-487">The following should be noted:</span></span>  
  
-   <span data-ttu-id="219df-488">`ser:char` se introduce para representar caracteres Unicode de tipo <xref:System.Char>.</span><span class="sxs-lookup"><span data-stu-id="219df-488">`ser:char` is introduced to represent Unicode characters of type <xref:System.Char>.</span></span>  
  
-   <span data-ttu-id="219df-489">El `valuespace` de `xs:duration` se reduce a un conjunto ordenado para que pueda asignarse a un <xref:System.TimeSpan>.</span><span class="sxs-lookup"><span data-stu-id="219df-489">The `valuespace` of `xs:duration` is reduced to an ordered set so that it can be mapped to a <xref:System.TimeSpan>.</span></span>  
  
-   <span data-ttu-id="219df-490">`FactoryType` se utiliza en esquemas exportados a partir de tipos que se derivan de <xref:System.Runtime.Serialization.ISerializable>.</span><span class="sxs-lookup"><span data-stu-id="219df-490">`FactoryType` is used in schemas exported from types that are derived from <xref:System.Runtime.Serialization.ISerializable>.</span></span>  
  
## <a name="importing-non-datacontract-schemas"></a><span data-ttu-id="219df-491">Importación de esquemas no DataContract</span><span class="sxs-lookup"><span data-stu-id="219df-491">Importing non-DataContract schemas</span></span>  
 <span data-ttu-id="219df-492">`DataContractSerializer` tiene la opción `ImportXmlTypes` para permitir la importación de esquemas que no cumplen el perfil XSD `DataContractSerializer` (vea la propiedad <xref:System.Runtime.Serialization.XsdDataContractImporter.Options%2A> ).</span><span class="sxs-lookup"><span data-stu-id="219df-492">`DataContractSerializer` has the `ImportXmlTypes` option to allow import of schemas that do not conform to the `DataContractSerializer` XSD profile (see the <xref:System.Runtime.Serialization.XsdDataContractImporter.Options%2A> property).</span></span> <span data-ttu-id="219df-493">Establecer esta opción en `true` habilita la aceptación de tipos de esquema no conformes y la asignación de ellos a la implementación siguiente, <xref:System.Xml.Serialization.IXmlSerializable> ajuste de una matriz de <xref:System.Xml.XmlNode> (solo difiere el nombre de la clase).</span><span class="sxs-lookup"><span data-stu-id="219df-493">Setting this option to `true` enables acceptance of non-conforming schema types and mapping them to the following implementation, <xref:System.Xml.Serialization.IXmlSerializable> wrapping an array of <xref:System.Xml.XmlNode> (only the class name differs).</span></span>  
  
```csharp  
[GeneratedCodeAttribute("System.Runtime.Serialization", "3.0.0.0")]  
[System.Xml.Serialization.XmlSchemaProviderAttribute("ExportSchema")]  
[System.Xml.Serialization.XmlRootAttribute(IsNullable=false)]  
public partial class Person : object, IXmlSerializable  
{    
  private XmlNode[] nodesField;    
  private static XmlQualifiedName typeName =   
new XmlQualifiedName("Person","http://Microsoft.ServiceModel.Samples");    
  public XmlNode[] Nodes  
  {  
    get {return this.nodesField;}  
    set {this.nodesField = value;}  
  }    
  public void ReadXml(XmlReader reader)  
  {  
    this.nodesField = XmlSerializableServices.ReadNodes(reader);  
  }    
  public void WriteXml(XmlWriter writer)  
  {  
    XmlSerializableServices.WriteNodes(writer, this.Nodes);  
  }    
  public System.Xml.Schema.XmlSchema GetSchema()  
  {  
    return null;  
  }    
  public static XmlQualifiedName ExportSchema(XmlSchemaSet schemas)  
  {  
    XmlSerializableServices.AddDefaultSchema(schemas, typeName);  
    return typeName;  
  }  
}  
```  
  
## <a name="datetimeoffset-serialization"></a><span data-ttu-id="219df-494">Serialización de DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="219df-494">DateTimeOffset Serialization</span></span>  
 <span data-ttu-id="219df-495"><xref:System.DateTimeOffset> no se trata como un tipo primitivo.</span><span class="sxs-lookup"><span data-stu-id="219df-495">The <xref:System.DateTimeOffset> is not treated as a primitive type.</span></span> <span data-ttu-id="219df-496">En su lugar, se serializa como un elemento complejo con dos partes.</span><span class="sxs-lookup"><span data-stu-id="219df-496">Instead, it is serialized as a complex element with two parts.</span></span> <span data-ttu-id="219df-497">La primera parte representa la fecha y hora, y la segunda parte representa el desplazamiento de la fecha y hora.</span><span class="sxs-lookup"><span data-stu-id="219df-497">The first part represents the date time, and the second part represents the offset from the date time.</span></span> <span data-ttu-id="219df-498">En el siguiente código se muestra un ejemplo de un valor DateTimeOffset serializado.</span><span class="sxs-lookup"><span data-stu-id="219df-498">An example of a serialized DateTimeOffset value is shown in the following code.</span></span>  
  
```xml  
<OffSet xmlns:a="http://schemas.datacontract.org/2004/07/System">  
  <DateTime i:type="b:dateTime" xmlns=""   
    xmlns:b="http://www.w3.org/2001/XMLSchema">2008-08-28T08:00:00    
  </DateTime>   
  <OffsetMinutes i:type="b:short" xmlns=""   
   xmlns:b="http://www.w3.org/2001/XMLSchema">-480  
   </OffsetMinutes>   
</OffSet>  
```  
  
 <span data-ttu-id="219df-499">El esquema es de la siguiente manera.</span><span class="sxs-lookup"><span data-stu-id="219df-499">The schema is as follows.</span></span>  
  
```xml  
<xs:schema targetNamespace="http://schemas.datacontract.org/2004/07/System">  
   <xs:complexType name="DateTimeOffset">  
      <xs:sequence minOccurs="1" maxOccurs="1">  
         <xs:element name="DateTime" type="xs:dateTime"  
         minOccurs="1" maxOccurs="1" />  
         <xs:element name="OffsetMinutes" type="xs:short"  
         minOccurs="1" maxOccurs="1" />  
      </xs:sequence>  
   </xs:complexType>  
</xs:schema>  
```  
  
## <a name="see-also"></a><span data-ttu-id="219df-500">Vea también</span><span class="sxs-lookup"><span data-stu-id="219df-500">See also</span></span>

- <xref:System.Runtime.Serialization.DataContractSerializer>
- <xref:System.Runtime.Serialization.DataContractAttribute>
- <xref:System.Runtime.Serialization.DataMemberAttribute>
- <xref:System.Runtime.Serialization.XsdDataContractImporter>
- [<span data-ttu-id="219df-501">Utilización de contratos de datos</span><span class="sxs-lookup"><span data-stu-id="219df-501">Using Data Contracts</span></span>](../../../../docs/framework/wcf/feature-details/using-data-contracts.md)
