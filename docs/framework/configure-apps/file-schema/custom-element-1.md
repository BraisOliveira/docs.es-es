---
title: Elemento personalizado para SingleTagSectionHandler
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/sectionName
helpviewer_keywords:
- custom element
ms.assetid: e62056c6-b351-40eb-afc0-cc13fc44e45e
author: rpetrusha
ms.author: mairaw
ms.openlocfilehash: ad98617cd4e88d1650f67136536b7dd5994233a4
ms.sourcegitcommit: 621a5f6df00152006160987395b93b5b55f7ffcd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/29/2019
ms.locfileid: "66301151"
---
# <a name="custom-element-for-singletagsectionhandler"></a><span data-ttu-id="c96ed-102">Elemento personalizado para SingleTagSectionHandler</span><span class="sxs-lookup"><span data-stu-id="c96ed-102">Custom element for SingleTagSectionHandler</span></span>

<span data-ttu-id="c96ed-103">Define la configuración en una sección de configuración personalizada que se define mediante un \<sección > elemento y se usa el <xref:System.Configuration.SingleTagSectionHandler> clase.</span><span class="sxs-lookup"><span data-stu-id="c96ed-103">Defines settings in a custom configuration section that is defined by a \<section> element and uses the <xref:System.Configuration.SingleTagSectionHandler> class.</span></span>

<span data-ttu-id="c96ed-104">[ **\<configuration>** ](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="c96ed-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span></span>  
<span data-ttu-id="c96ed-105">&nbsp;&nbsp; *\<sectionName>*</span><span class="sxs-lookup"><span data-stu-id="c96ed-105">&nbsp;&nbsp;*\<sectionName>*</span></span>

## <a name="syntax"></a><span data-ttu-id="c96ed-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c96ed-106">Syntax</span></span>

```xml
<sectionName key="value" key2="value2" ... />
```

## <a name="attributes"></a><span data-ttu-id="c96ed-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="c96ed-107">Attributes</span></span>

<span data-ttu-id="c96ed-108">Atributos y valores de atributo son definidos por el usuario.</span><span class="sxs-lookup"><span data-stu-id="c96ed-108">Attributes and attribute values are user defined.</span></span>

## <a name="parent-element"></a><span data-ttu-id="c96ed-109">Elemento primario</span><span class="sxs-lookup"><span data-stu-id="c96ed-109">Parent element</span></span>

|     | <span data-ttu-id="c96ed-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="c96ed-110">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="c96ed-111"> *\*\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="c96ed-111">**\<configuration>**</span></span>](~/docs/framework/configure-apps/file-schema/configuration-element.md) | <span data-ttu-id="c96ed-112">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="c96ed-112">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="c96ed-113">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="c96ed-113">Child elements</span></span>

<span data-ttu-id="c96ed-114">Ninguna</span><span class="sxs-lookup"><span data-stu-id="c96ed-114">None</span></span>

## <a name="remarks"></a><span data-ttu-id="c96ed-115">Comentarios</span><span class="sxs-lookup"><span data-stu-id="c96ed-115">Remarks</span></span>

<span data-ttu-id="c96ed-116">El  **\<sectionName >** trata de un elemento personalizado definido por una [  **\<sección >** ](~/docs/framework/configure-apps/file-schema/section-element.md) etiquetar en el [  **\<configSections >** ](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="c96ed-116">The **\<sectionName>** element is a custom element defined by a [**\<section>**](~/docs/framework/configure-apps/file-schema/section-element.md) tag in the [**\<configSections>**](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md) element.</span></span> <span data-ttu-id="c96ed-117">Devuelve el sistema de configuración un <xref:System.Collections.IDictionary> objeto cuando se llama a <xref:System.Configuration.Configuration.GetSection(System.String)?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="c96ed-117">The configuration system returns a <xref:System.Collections.IDictionary> object when you call <xref:System.Configuration.Configuration.GetSection(System.String)?displayProperty=nameWithType>.</span></span>

## <a name="example"></a><span data-ttu-id="c96ed-118">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c96ed-118">Example</span></span>

<span data-ttu-id="c96ed-119">En el ejemplo siguiente se declara un elemento personalizado llamado  **\<sampleSection >** que contiene los valores leídos por la <xref:System.Configuration.SingleTagSectionHandler> clase:</span><span class="sxs-lookup"><span data-stu-id="c96ed-119">The following example declares a custom element called **\<sampleSection>** that contains settings read by the <xref:System.Configuration.SingleTagSectionHandler> class:</span></span>

```xml
<configuration>
  <configSections>
    <section name="sampleSection" 
             type="System.Configuration.SingleTagSectionHandler" />
  </configSections>
  <sampleSection setting1="Value1" 
                 setting2="value two" 
                 setting3="third value" />
</configuration>
```

## <a name="configuration-file"></a><span data-ttu-id="c96ed-120">Archivo de configuración</span><span class="sxs-lookup"><span data-stu-id="c96ed-120">Configuration file</span></span>

<span data-ttu-id="c96ed-121">Este elemento se puede usar en el archivo de configuración de aplicación, archivo de configuración del equipo (*Machine.config*), y *Web.config* archivos que no están en el nivel de directorio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="c96ed-121">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="c96ed-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="c96ed-122">See also</span></span>

- [<span data-ttu-id="c96ed-123">Esquema de archivo de configuración de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="c96ed-123">Configuration file schema for the .NET Framework</span></span>](~/docs/framework/configure-apps/file-schema/index.md)
