---
title: <gcAllowVeryLargeObjects> (Elemento)
ms.date: 03/30/2017
helpviewer_keywords:
- gcAllowVeryLargeObjects element
- <gcAllowVeryLargeObjects> element
ms.assetid: 5c7ea24a-39ac-4e5f-83b7-b9f9a1b556ab
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c6db26d250de191559fdae0479aca9f41c147502
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/21/2019
ms.locfileid: "69663708"
---
# <a name="gcallowverylargeobjects-element"></a><span data-ttu-id="afd36-102">\<gcAllowVeryLargeObjects >, elemento</span><span class="sxs-lookup"><span data-stu-id="afd36-102">\<gcAllowVeryLargeObjects> Element</span></span>
<span data-ttu-id="afd36-103">En plataformas de 64 bits, habilita matrices con un tamaño total superior a 2 gigabytes (GB).</span><span class="sxs-lookup"><span data-stu-id="afd36-103">On 64-bit platforms, enables arrays that are greater than 2 gigabytes (GB) in total size.</span></span>  
  
 <span data-ttu-id="afd36-104">\<Elemento Configuration ></span><span class="sxs-lookup"><span data-stu-id="afd36-104">\<configuration> Element</span></span>  
<span data-ttu-id="afd36-105">\<Elemento > en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="afd36-105">\<runtime> Element</span></span>  
<span data-ttu-id="afd36-106">\<gcAllowVeryLargeObjects >, elemento</span><span class="sxs-lookup"><span data-stu-id="afd36-106">\<gcAllowVeryLargeObjects> Element</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="afd36-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="afd36-107">Syntax</span></span>  
  
```xml  
<gcAllowVeryLargeObjects    
   enabled="true|false" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="afd36-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="afd36-108">Attributes and Elements</span></span>  
 <span data-ttu-id="afd36-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="afd36-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="afd36-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="afd36-110">Attributes</span></span>  
  
|<span data-ttu-id="afd36-111">Atributo</span><span class="sxs-lookup"><span data-stu-id="afd36-111">Attribute</span></span>|<span data-ttu-id="afd36-112">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="afd36-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="afd36-113">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="afd36-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="afd36-114">Especifica si las matrices con un tamaño total superior a 2 GB se habilitan en plataformas de 64 bits.</span><span class="sxs-lookup"><span data-stu-id="afd36-114">Specifies whether arrays that are greater than 2 GB in total size are enabled on 64-bit platforms.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="afd36-115">Atributo enabled</span><span class="sxs-lookup"><span data-stu-id="afd36-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="afd36-116">Valor</span><span class="sxs-lookup"><span data-stu-id="afd36-116">Value</span></span>|<span data-ttu-id="afd36-117">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="afd36-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="afd36-118">Las matrices con un tamaño total superior a 2 GB no están habilitadas.</span><span class="sxs-lookup"><span data-stu-id="afd36-118">Arrays greater than 2 GB in total size are not enabled.</span></span> <span data-ttu-id="afd36-119">Este es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="afd36-119">This is the default.</span></span>|  
|`true`|<span data-ttu-id="afd36-120">Las matrices con un tamaño total superior a 2 GB se habilitan en plataformas de 64 bits.</span><span class="sxs-lookup"><span data-stu-id="afd36-120">Arrays greater than 2 GB in total size are enabled on 64-bit platforms.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="afd36-121">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="afd36-121">Child Elements</span></span>  
 <span data-ttu-id="afd36-122">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="afd36-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="afd36-123">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="afd36-123">Parent Elements</span></span>  
  
|<span data-ttu-id="afd36-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="afd36-124">Element</span></span>|<span data-ttu-id="afd36-125">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="afd36-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="afd36-126">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="afd36-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="afd36-127">Contiene información sobre las opciones de inicialización del motor en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="afd36-127">Contains information about runtime initialization options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="afd36-128">Comentarios</span><span class="sxs-lookup"><span data-stu-id="afd36-128">Remarks</span></span>  
 <span data-ttu-id="afd36-129">El uso de este elemento en el archivo de configuración de la aplicación permite utilizar matrices con un tamaño superior a 2 GB, pero no cambia otros límites de tamaño de objetos o matrices:</span><span class="sxs-lookup"><span data-stu-id="afd36-129">Using this element in your application configuration file enables arrays that are larger than 2 GB in size, but does not change other limits on object size or array size:</span></span>  
  
- <span data-ttu-id="afd36-130">El número máximo de elementos de una matriz es <xref:System.UInt32.MaxValue?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="afd36-130">The maximum number of elements in an array is <xref:System.UInt32.MaxValue?displayProperty=nameWithType>.</span></span>  
  
- <span data-ttu-id="afd36-131">El índice máximo de cualquier dimensión única es 2.147.483.591 (0x7FFFFFC7) para matrices de bytes y matrices de estructuras de un solo byte, y 2.146.435.071 (0X7FEFFFFF) para otros tipos.</span><span class="sxs-lookup"><span data-stu-id="afd36-131">The maximum index in any single dimension is 2,147,483,591 (0x7FFFFFC7) for byte arrays and arrays of single-byte structures, and 2,146,435,071 (0X7FEFFFFF) for other types.</span></span>  
  
- <span data-ttu-id="afd36-132">El tamaño máximo de las cadenas y otros objetos que no sean de matriz no varía.</span><span class="sxs-lookup"><span data-stu-id="afd36-132">The maximum size for strings and other non-array objects is unchanged.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="afd36-133">Antes de habilitar esta característica, asegúrese de que la aplicación no incluye código no seguro que supone que todas las matrices tienen un tamaño inferior a 2 GB.</span><span class="sxs-lookup"><span data-stu-id="afd36-133">Before enabling this feature, ensure that your application does not include unsafe code that assumes that all arrays are smaller than 2 GB in size.</span></span> <span data-ttu-id="afd36-134">Por ejemplo, el código no seguro que usa matrices como búferes puede ser susceptible a saturaciones de búfer si se escribe basándose en la suposición de que las matrices no superarán los 2 GB de tamaño.</span><span class="sxs-lookup"><span data-stu-id="afd36-134">For example, unsafe code that uses arrays as buffers might be susceptible to buffer overruns if it is written on the assumption that arrays will not exceed 2 GB.</span></span>  
  
## <a name="example"></a><span data-ttu-id="afd36-135">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="afd36-135">Example</span></span>  
 <span data-ttu-id="afd36-136">En el ejemplo siguiente se muestra cómo habilitar esta característica para una aplicación.</span><span class="sxs-lookup"><span data-stu-id="afd36-136">The following example shows how to enable this feature for an application.</span></span>  
  
```xml  
<configuration>  
  <runtime>  
    <gcAllowVeryLargeObjects enabled="true" />  
  </runtime>  
</configuration>  
```  
  
## <a name="supported-in"></a><span data-ttu-id="afd36-137">Compatible con</span><span class="sxs-lookup"><span data-stu-id="afd36-137">Supported in</span></span>

<span data-ttu-id="afd36-138">.NET Framework 4,5 y versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="afd36-138">.NET Framework 4.5 and later versions</span></span>

## <a name="see-also"></a><span data-ttu-id="afd36-139">Vea también</span><span class="sxs-lookup"><span data-stu-id="afd36-139">See also</span></span>

- [<span data-ttu-id="afd36-140">Esquema de la configuración de Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="afd36-140">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="afd36-141">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="afd36-141">Configuration File Schema</span></span>](../index.md)
