---
title: <schemeSettings> Elemento (configuración de Uri)
ms.date: 03/30/2017
ms.assetid: 0ae45c6e-8c4c-4c0d-8b9f-a93824648890
ms.openlocfilehash: 8dc505d8a9de4e8939372af61b23652551c36530
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59094241"
---
# <a name="schemesettings-element-uri-settings"></a><span data-ttu-id="f1ce6-102">\<schemeSettings > elemento (configuración de Uri)</span><span class="sxs-lookup"><span data-stu-id="f1ce6-102">\<schemeSettings> Element (Uri Settings)</span></span>
<span data-ttu-id="f1ce6-103">Especifica cómo se analizará un <xref:System.Uri> para esquemas concretos.</span><span class="sxs-lookup"><span data-stu-id="f1ce6-103">Specifies how a <xref:System.Uri> will be parsed for specific schemes.</span></span>  
  
 <span data-ttu-id="f1ce6-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="f1ce6-104">\<configuration></span></span>  
<span data-ttu-id="f1ce6-105">\<uri></span><span class="sxs-lookup"><span data-stu-id="f1ce6-105">\<uri></span></span>  
<span data-ttu-id="f1ce6-106">\<schemeSettings></span><span class="sxs-lookup"><span data-stu-id="f1ce6-106">\<schemeSettings></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f1ce6-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f1ce6-107">Syntax</span></span>  
  
```xml  
<schemeSettings>   
</schemeSettings>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f1ce6-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="f1ce6-108">Attributes and Elements</span></span>  
 <span data-ttu-id="f1ce6-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="f1ce6-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f1ce6-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="f1ce6-110">Attributes</span></span>  
 <span data-ttu-id="f1ce6-111">Ninguna</span><span class="sxs-lookup"><span data-stu-id="f1ce6-111">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="f1ce6-112">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="f1ce6-112">Child Elements</span></span>  
  
|**<span data-ttu-id="f1ce6-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="f1ce6-113">Element</span></span>**|**<span data-ttu-id="f1ce6-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="f1ce6-114">Description</span></span>**|  
|-----------------|---------------------|  
|[<span data-ttu-id="f1ce6-115">agregar</span><span class="sxs-lookup"><span data-stu-id="f1ce6-115">add</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/add-element-for-schemesettings-uri-settings.md)|<span data-ttu-id="f1ce6-116">Agrega un valor de esquema para un nombre de esquema.</span><span class="sxs-lookup"><span data-stu-id="f1ce6-116">Adds a scheme setting for a scheme name.</span></span>|  
|[<span data-ttu-id="f1ce6-117">desactivada</span><span class="sxs-lookup"><span data-stu-id="f1ce6-117">clear</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/clear-element-for-schemesettings-uri-settings.md)|<span data-ttu-id="f1ce6-118">Borra todos los valores de esquema existente.</span><span class="sxs-lookup"><span data-stu-id="f1ce6-118">Clears all existing scheme settings.</span></span>|  
|[<span data-ttu-id="f1ce6-119">remove</span><span class="sxs-lookup"><span data-stu-id="f1ce6-119">remove</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/remove-element-for-schemesettings-uri-settings.md)|<span data-ttu-id="f1ce6-120">Quita un valor de esquema para un nombre de esquema.</span><span class="sxs-lookup"><span data-stu-id="f1ce6-120">Removes a scheme setting for a scheme name.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="f1ce6-121">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="f1ce6-121">Parent Elements</span></span>  
  
|**<span data-ttu-id="f1ce6-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="f1ce6-122">Element</span></span>**|**<span data-ttu-id="f1ce6-123">Descripción</span><span class="sxs-lookup"><span data-stu-id="f1ce6-123">Description</span></span>**|  
|-----------------|---------------------|  
|[<span data-ttu-id="f1ce6-124">uri</span><span class="sxs-lookup"><span data-stu-id="f1ce6-124">uri</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/uri-element-uri-settings.md)|<span data-ttu-id="f1ce6-125">Contiene valores que especifican cómo .NET Framework controla las direcciones web expresadas mediante identificadores uniformes de recursos (URI).</span><span class="sxs-lookup"><span data-stu-id="f1ce6-125">Contains settings that specify how the .NET Framework handles web addresses expressed using uniform resource identifiers (URIs).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f1ce6-126">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f1ce6-126">Remarks</span></span>  
 <span data-ttu-id="f1ce6-127">De forma predeterminada, el <xref:System.Uri?displayProperty=nameWithType> delimitadores de ruta de acceso de codificación de porcentaje de anular los caracteres de escape de clase antes de ejecutar la compresión de la ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="f1ce6-127">By default, the <xref:System.Uri?displayProperty=nameWithType> class un-escapes percent encoded path delimiters before executing path compression.</span></span> <span data-ttu-id="f1ce6-128">Esto se implementó como un mecanismo de seguridad frente a ataques similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="f1ce6-128">This was implemented as a security mechanism against attacks like the following:</span></span>  
  
 `http://www.contoso.com/..%2F..%2F/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="f1ce6-129">Si este URI se pasa a los módulos no se controla por ciento correctamente los caracteres codificados, podría dar como resultado el siguiente comando que se está ejecutando el servidor:</span><span class="sxs-lookup"><span data-stu-id="f1ce6-129">If this URI gets passed down to modules not handling percent encoded characters correctly, it could result in the following command being executed by the server:</span></span>  
  
 `c:\Windows\System32\cmd.exe /c dir c:\`  
  
 <span data-ttu-id="f1ce6-130">Por este motivo, <xref:System.Uri?displayProperty=nameWithType> delimitadores de ruta de acceso de primera anular los caracteres de escape de clase y, a continuación, aplica la compresión de la ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="f1ce6-130">For this reason, <xref:System.Uri?displayProperty=nameWithType> class first un-escapes path delimiters and then applies path compression.</span></span> <span data-ttu-id="f1ce6-131">El resultado de pasar la dirección URL malintencionada anterior a <xref:System.Uri?displayProperty=nameWithType> clase constructor produce el siguiente URI:</span><span class="sxs-lookup"><span data-stu-id="f1ce6-131">The result of passing the malicious URL above to <xref:System.Uri?displayProperty=nameWithType> class constructor results in the following URI:</span></span>  
  
 `http://www.microsoft.com/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="f1ce6-132">Este comportamiento predeterminado puede modificarse para no escape de un porcentaje de ruta de acceso codificada delimitadores de mediante la opción de configuración schemeSettings para un esquema específico.</span><span class="sxs-lookup"><span data-stu-id="f1ce6-132">This default behavior can be modified to not un-escape percent encoded path delimiters using the schemeSettings configuration option for a specific scheme.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="f1ce6-133">Archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="f1ce6-133">Configuration Files</span></span>  
 <span data-ttu-id="f1ce6-134">Este elemento se puede usar en el archivo de configuración de la aplicación o en el archivo de configuración del equipo (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="f1ce6-134">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="f1ce6-135">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f1ce6-135">Example</span></span>  
 <span data-ttu-id="f1ce6-136">El ejemplo siguiente muestra una configuración utilizada por el <xref:System.Uri> clase para admitir los delimitadores de ruta de acceso codificados con porcentaje para el esquema http.</span><span class="sxs-lookup"><span data-stu-id="f1ce6-136">The following example shows a configuration used by the <xref:System.Uri> class to support not escaping percent-encoded path delimiters for the http scheme.</span></span>  
  
```xml  
<configuration>  
  <uri>  
    <schemeSettings>  
      <add name="http" genericUriParserOptions="DontUnescapePathDotsAndSlashes"/>  
    </schemeSettings>  
  </uri>  
</configuration>  
```  
  
## <a name="element-information"></a><span data-ttu-id="f1ce6-137">Información de elemento</span><span class="sxs-lookup"><span data-stu-id="f1ce6-137">Element Information</span></span>  
  
|||
|-|-|  
|<span data-ttu-id="f1ce6-138">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="f1ce6-138">Namespace</span></span>|<span data-ttu-id="f1ce6-139">Sistema</span><span class="sxs-lookup"><span data-stu-id="f1ce6-139">System</span></span>|  
|<span data-ttu-id="f1ce6-140">Nombre de esquema</span><span class="sxs-lookup"><span data-stu-id="f1ce6-140">Schema Name</span></span>||  
|<span data-ttu-id="f1ce6-141">Archivo de validación</span><span class="sxs-lookup"><span data-stu-id="f1ce6-141">Validation File</span></span>||  
|<span data-ttu-id="f1ce6-142">Puede estar vacío</span><span class="sxs-lookup"><span data-stu-id="f1ce6-142">Can be Empty</span></span>||  
  
## <a name="see-also"></a><span data-ttu-id="f1ce6-143">Vea también</span><span class="sxs-lookup"><span data-stu-id="f1ce6-143">See also</span></span>

- <xref:System.Configuration.SchemeSettingElement?displayProperty=nameWithType>
- <xref:System.Configuration.SchemeSettingElementCollection?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection.SchemeSettings%2A?displayProperty=nameWithType>
- <xref:System.GenericUriParserOptions?displayProperty=nameWithType>
- <xref:System.Uri?displayProperty=nameWithType>
- [<span data-ttu-id="f1ce6-144">Esquema de la configuración de red</span><span class="sxs-lookup"><span data-stu-id="f1ce6-144">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
