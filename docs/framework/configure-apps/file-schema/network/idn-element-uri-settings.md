---
title: <idn> Elemento (configuración de Uri)
ms.date: 03/30/2017
ms.assetid: 16c8e869-1791-4cf5-9244-3d3c738f60ec
ms.openlocfilehash: 3940f30f2ef90a77560a82edc909071f0ee8e130
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59129407"
---
# <a name="idn-element-uri-settings"></a><span data-ttu-id="9b66b-102">\<IDN > elemento (configuración de Uri)</span><span class="sxs-lookup"><span data-stu-id="9b66b-102">\<idn> Element (Uri Settings)</span></span>
<span data-ttu-id="9b66b-103">Especifica si el análisis de nombres de dominio internacionalizados (IDN) se aplican a un nombre de dominio.</span><span class="sxs-lookup"><span data-stu-id="9b66b-103">Specifies if Internationalized Domain Name (IDN) parsing is applied to a domain name.</span></span>  
  
## <a name="schema-hierarchy"></a><span data-ttu-id="9b66b-104">Jerarquía del esquema</span><span class="sxs-lookup"><span data-stu-id="9b66b-104">Schema Hierarchy</span></span>  
 [<span data-ttu-id="9b66b-105">\<Configuración > elemento</span><span class="sxs-lookup"><span data-stu-id="9b66b-105">\<configuration> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)  
  
 [<span data-ttu-id="9b66b-106">\<URI > elemento (configuración de Uri)</span><span class="sxs-lookup"><span data-stu-id="9b66b-106">\<Uri> Element (Uri Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/uri-element-uri-settings.md)  
  
 [<span data-ttu-id="9b66b-107">\<idn></span><span class="sxs-lookup"><span data-stu-id="9b66b-107">\<idn></span></span>](../../../../../docs/framework/configure-apps/file-schema/network/idn-element-uri-settings.md)  
  
## <a name="syntax"></a><span data-ttu-id="9b66b-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9b66b-108">Syntax</span></span>  
  
```xml  
<idn  
  enabled="All|AllExceptIntranet|None"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9b66b-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="9b66b-109">Attributes and Elements</span></span>  
 <span data-ttu-id="9b66b-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="9b66b-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9b66b-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="9b66b-111">Attributes</span></span>  
  
|**<span data-ttu-id="9b66b-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="9b66b-112">Element</span></span>**|**<span data-ttu-id="9b66b-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="9b66b-113">Description</span></span>**|  
|-----------------|---------------------|  
|`enabled`|<span data-ttu-id="9b66b-114">Especifica que si se aplican el análisis de nombres de dominio internacionalizados (IDN) para un nombre de dominio, el valor predeterminado es none.</span><span class="sxs-lookup"><span data-stu-id="9b66b-114">Specifies if Internationalized Domain Name (IDN) parsing is applied to a domain name The default value is none.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9b66b-115">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="9b66b-115">Child Elements</span></span>  
 <span data-ttu-id="9b66b-116">Ninguna</span><span class="sxs-lookup"><span data-stu-id="9b66b-116">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="9b66b-117">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="9b66b-117">Parent Elements</span></span>  
  
|**<span data-ttu-id="9b66b-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="9b66b-118">Element</span></span>**|**<span data-ttu-id="9b66b-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="9b66b-119">Description</span></span>**|  
|-----------------|---------------------|  
|[<span data-ttu-id="9b66b-120">uri</span><span class="sxs-lookup"><span data-stu-id="9b66b-120">uri</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/uri-element-uri-settings.md)|<span data-ttu-id="9b66b-121">Contiene valores que especifican cómo .NET Framework controla las direcciones web expresadas mediante identificadores uniformes de recursos (URI).</span><span class="sxs-lookup"><span data-stu-id="9b66b-121">Contains settings that specify how the .NET Framework handles web addresses expressed using uniform resource identifiers (URIs).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9b66b-122">Comentarios</span><span class="sxs-lookup"><span data-stu-id="9b66b-122">Remarks</span></span>  
 <span data-ttu-id="9b66b-123">Existente <xref:System.Uri> se ha ampliado la clase en .NET Framework 3.5.</span><span class="sxs-lookup"><span data-stu-id="9b66b-123">The existing <xref:System.Uri> class has been extended in .NET Framework 3.5.</span></span> <span data-ttu-id="9b66b-124">3.0 SP1 y 2.0 SP1 con compatibilidad para los identificadores de recursos internacionales (IRI) y los nombres de dominio internacionalizados (IDN).</span><span class="sxs-lookup"><span data-stu-id="9b66b-124">3.0 SP1, and 2.0 SP1 with support for International Resource Identifiers (IRI) and Internationalized Domain Names (IDN).</span></span> <span data-ttu-id="9b66b-125">Los usuarios actuales no verán ningún cambio respecto al comportamiento de .NET Framework 2.0, a menos que habiliten específicamente IRI e IDN admite.</span><span class="sxs-lookup"><span data-stu-id="9b66b-125">Current users will not see any change from the .NET Framework 2.0 behavior unless they specifically enable IRI and IDN support.</span></span> <span data-ttu-id="9b66b-126">Esto garantiza la compatibilidad de las aplicaciones con versiones anteriores de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="9b66b-126">This ensures application compatibility with prior versions of the .NET Framework.</span></span>  
  
 <span data-ttu-id="9b66b-127">Para habilitar la compatibilidad con IRI, se requieren los siguientes dos cambios:</span><span class="sxs-lookup"><span data-stu-id="9b66b-127">To enable support for IRI, the following two changes are required:</span></span>  
  
1.  <span data-ttu-id="9b66b-128">Agregue la siguiente línea al archivo machine.config en el directorio de .NET Framework 2.0</span><span class="sxs-lookup"><span data-stu-id="9b66b-128">Add the following line to the machine.config file under the .NET Framework 2.0 directory</span></span>  
  
    ```xml  
    <section name="uri" type="System.Configuration.UriSection, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
    ```  
  
2.  <span data-ttu-id="9b66b-129">Especifique si desea analizar el nombre de dominio internacionalizado (IDN) aplicado en el nombre de dominio y si debe aplicarse las reglas de análisis de IRI.</span><span class="sxs-lookup"><span data-stu-id="9b66b-129">Specify whether you want Internationalized Domain Name (IDN) parsing applied to the domain name and whether IRI parsing rules should be applied.</span></span> <span data-ttu-id="9b66b-130">Esto puede hacerse en el archivo machine.config o app.config.</span><span class="sxs-lookup"><span data-stu-id="9b66b-130">This can be done in the machine.config or in the app.config file.</span></span>  
  
 <span data-ttu-id="9b66b-131">Hay tres valores posibles para IDN dependiendo de los servidores DNS que se usan:</span><span class="sxs-lookup"><span data-stu-id="9b66b-131">There are three possible values for IDN depending on the DNS servers that are used:</span></span>  
  
-   <span data-ttu-id="9b66b-132">IDN habilitado = All</span><span class="sxs-lookup"><span data-stu-id="9b66b-132">idn enabled = All</span></span>  
  
     <span data-ttu-id="9b66b-133">Este valor convierte cualquier nombre de dominio Unicode a su equivalente Punycode (nombres IDN).</span><span class="sxs-lookup"><span data-stu-id="9b66b-133">This value will convert any Unicode domain names to their Punycode equivalents (IDN names).</span></span>  
  
-   <span data-ttu-id="9b66b-134">IDN habilitado = AllExceptIntranet</span><span class="sxs-lookup"><span data-stu-id="9b66b-134">idn enabled = AllExceptIntranet</span></span>  
  
     <span data-ttu-id="9b66b-135">Este valor convertirá todos los nombres de dominio Unicode no en la Intranet local para que utilicen sus equivalentes Punycode (nombres IDN).</span><span class="sxs-lookup"><span data-stu-id="9b66b-135">This value will convert all Unicode domain names not on the local Intranet to use the Punycode equivalents (IDN names).</span></span> <span data-ttu-id="9b66b-136">En este caso para controlar los nombres internacionales en la Intranet local, los servidores DNS que se usan para la Intranet deben admitir la resolución de nombre de Unicode.</span><span class="sxs-lookup"><span data-stu-id="9b66b-136">In this case to handle international names on the local Intranet, the DNS servers that are used for the Intranet should support Unicode name resolution.</span></span>  
  
-   <span data-ttu-id="9b66b-137">IDN habilitado = ninguno</span><span class="sxs-lookup"><span data-stu-id="9b66b-137">idn enabled = None</span></span>  
  
     <span data-ttu-id="9b66b-138">Este valor no convierte cualquier nombre de dominio Unicode para que se use Punycode.</span><span class="sxs-lookup"><span data-stu-id="9b66b-138">This value will not convert any Unicode domain names to use Punycode.</span></span> <span data-ttu-id="9b66b-139">Este es el valor predeterminado que es coherente con el comportamiento de .NET Framework 2.0.</span><span class="sxs-lookup"><span data-stu-id="9b66b-139">This is the default value which is consistent with the .NET Framework 2.0 behaviour.</span></span>  
  
 <span data-ttu-id="9b66b-140">La activación de IDN convertirá todas la etiquetas Unicode de un nombre de dominio en sus equivalentes de Punycode.</span><span class="sxs-lookup"><span data-stu-id="9b66b-140">Enabling IDN will convert all Unicode labels in a domain name to their Punycode equivalents.</span></span> <span data-ttu-id="9b66b-141">Los nombres de Punycode solo contienen caracteres ASCII y siempre empiezan con el prefijo xn--.</span><span class="sxs-lookup"><span data-stu-id="9b66b-141">Punycode names contain only ASCII characters and always start with the xn-- prefix.</span></span> <span data-ttu-id="9b66b-142">De este modo, se admiten los servidores DNS existentes en Internet, ya que la mayoría de los servidores DNS solo admite caracteres ASCII (vea RFC 3940).</span><span class="sxs-lookup"><span data-stu-id="9b66b-142">The reason for this is to support existing DNS servers on the Internet, since most DNS servers only support ASCII characters (see RFC 3940).</span></span>  
  
### <a name="configuration-files"></a><span data-ttu-id="9b66b-143">Archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="9b66b-143">Configuration Files</span></span>  
 <span data-ttu-id="9b66b-144">Este elemento se puede usar en el archivo de configuración de la aplicación o en el archivo de configuración del equipo (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="9b66b-144">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="9b66b-145">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="9b66b-145">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="9b66b-146">Descripción</span><span class="sxs-lookup"><span data-stu-id="9b66b-146">Description</span></span>  
 <span data-ttu-id="9b66b-147">El ejemplo siguiente muestra una configuración utilizada por el <xref:System.Uri> clase para admitir el análisis de IRI y nombres de IDN.</span><span class="sxs-lookup"><span data-stu-id="9b66b-147">The following example shows a configuration used by the <xref:System.Uri> class to support IRI parsing and IDN names.</span></span>  
  
### <a name="code"></a><span data-ttu-id="9b66b-148">Código</span><span class="sxs-lookup"><span data-stu-id="9b66b-148">Code</span></span>  
  
```xml  
<configuration>  
  <uri>  
    <idn enabled="All" />  
    <iriParsing enabled="true" />  
  </uri>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="9b66b-149">Vea también</span><span class="sxs-lookup"><span data-stu-id="9b66b-149">See also</span></span>

- <xref:System.Configuration.IdnElement?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection?displayProperty=nameWithType>
- [<span data-ttu-id="9b66b-150">Esquema de la configuración de red</span><span class="sxs-lookup"><span data-stu-id="9b66b-150">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
