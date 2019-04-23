---
title: <UseRandomizedStringHashAlgorithm> (Elemento)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- UseRandomizedStringHashAlgorithm element
- <UseRandomizedStringHashAlgorithm> element
ms.assetid: c08125d6-56cc-4b23-b482-813ff85dc630
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2a51b9fb485da605effbad0e81b8baf5e05e382a
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59087799"
---
# <a name="userandomizedstringhashalgorithm-element"></a><span data-ttu-id="4612b-102">\<UseRandomizedStringHashAlgorithm > elemento</span><span class="sxs-lookup"><span data-stu-id="4612b-102">\<UseRandomizedStringHashAlgorithm> Element</span></span>
<span data-ttu-id="4612b-103">Determina si common language runtime calcula los códigos hash para cadenas en una por cada dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="4612b-103">Determines whether the common language runtime calculates hash codes for strings on a per application domain basis.</span></span>  
  
 <span data-ttu-id="4612b-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="4612b-104">\<configuration></span></span>  
<span data-ttu-id="4612b-105">\<runtime></span><span class="sxs-lookup"><span data-stu-id="4612b-105">\<runtime></span></span>  
<span data-ttu-id="4612b-106">\<UseRandomizedStringHashAlgorithm></span><span class="sxs-lookup"><span data-stu-id="4612b-106">\<UseRandomizedStringHashAlgorithm></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4612b-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4612b-107">Syntax</span></span>  
  
```xml  
<UseRandomizedStringHashAlgorithm   
   enabled=0|1 />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4612b-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="4612b-108">Attributes and Elements</span></span>  
 <span data-ttu-id="4612b-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="4612b-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4612b-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="4612b-110">Attributes</span></span>  
  
|<span data-ttu-id="4612b-111">Atributo</span><span class="sxs-lookup"><span data-stu-id="4612b-111">Attribute</span></span>|<span data-ttu-id="4612b-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="4612b-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="4612b-113">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="4612b-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="4612b-114">Especifica si se calculan los códigos hash para cadenas en una por cada dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="4612b-114">Specifies whether hash codes for strings are calculated on a per application domain basis.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="4612b-115">Atributo enabled</span><span class="sxs-lookup"><span data-stu-id="4612b-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="4612b-116">Valor</span><span class="sxs-lookup"><span data-stu-id="4612b-116">Value</span></span>|<span data-ttu-id="4612b-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="4612b-117">Description</span></span>|  
|-----------|-----------------|  
|`0`|<span data-ttu-id="4612b-118">Common language runtime no calcula los códigos hash para cadenas en una por cada dominio de aplicación; se usa un solo algoritmo para calcular los códigos hash de cadena.</span><span class="sxs-lookup"><span data-stu-id="4612b-118">The common language runtime does not compute hash codes for strings on a per application domain basis; a single algorithm is used to calculate string hash codes.</span></span> <span data-ttu-id="4612b-119">Este es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="4612b-119">This is the default.</span></span>|  
|`1`|<span data-ttu-id="4612b-120">Common language runtime calcula los códigos hash para cadenas en una por cada dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="4612b-120">The common language runtime computes hash codes for strings on a per application domain basis.</span></span> <span data-ttu-id="4612b-121">Las cadenas idénticas en distintos dominios de aplicación y en distintos procesos tendrán distintos códigos hash.</span><span class="sxs-lookup"><span data-stu-id="4612b-121">Identical strings in different application domains and in different processes will have different hash codes.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4612b-122">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="4612b-122">Child Elements</span></span>  
 <span data-ttu-id="4612b-123">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="4612b-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="4612b-124">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="4612b-124">Parent Elements</span></span>  
  
|<span data-ttu-id="4612b-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="4612b-125">Element</span></span>|<span data-ttu-id="4612b-126">Descripción</span><span class="sxs-lookup"><span data-stu-id="4612b-126">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="4612b-127">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="4612b-127">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="4612b-128">Contiene información sobre las opciones de inicialización del motor en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="4612b-128">Contains information about runtime initialization options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4612b-129">Comentarios</span><span class="sxs-lookup"><span data-stu-id="4612b-129">Remarks</span></span>  
 <span data-ttu-id="4612b-130">De forma predeterminada, el <xref:System.StringComparer> clase y el <xref:System.String.GetHashCode%2A?displayProperty=nameWithType> método usa un solo algoritmo hash que genera un código hash coherente entre dominios de aplicación.</span><span class="sxs-lookup"><span data-stu-id="4612b-130">By default, the <xref:System.StringComparer> class and the <xref:System.String.GetHashCode%2A?displayProperty=nameWithType> method use a single hashing algorithm that produces a consistent hash code across application domains.</span></span> <span data-ttu-id="4612b-131">Esto es equivalente a establecer el `enabled` atributo de la `<UseRandomizedStringHashAlgorithm>` elemento `0`.</span><span class="sxs-lookup"><span data-stu-id="4612b-131">This is equivalent to setting the `enabled` attribute of the `<UseRandomizedStringHashAlgorithm>` element to `0`.</span></span> <span data-ttu-id="4612b-132">Este es el algoritmo hash utilizado en el [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4612b-132">This is the hashing algorithm used in the [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)].</span></span>  
  
 <span data-ttu-id="4612b-133">El <xref:System.StringComparer> clase y el <xref:System.String.GetHashCode%2A?displayProperty=nameWithType> método también puede usar un algoritmo hash diferente que calcula códigos hash en una por cada dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="4612b-133">The <xref:System.StringComparer> class and the <xref:System.String.GetHashCode%2A?displayProperty=nameWithType> method can also use a different hashing algorithm that computes hash codes on a per application domain basis.</span></span> <span data-ttu-id="4612b-134">Como resultado, los códigos hash para cadenas equivalentes variarán entre dominios de aplicación.</span><span class="sxs-lookup"><span data-stu-id="4612b-134">As a result, hash codes for equivalent strings will differ across application domains.</span></span> <span data-ttu-id="4612b-135">Se trata de una característica opcional; para aprovechar las ventajas de la misma, debe establecer el `enabled` atributo de la `<UseRandomizedStringHashAlgorithm>` elemento `1`.</span><span class="sxs-lookup"><span data-stu-id="4612b-135">This is an opt-in feature; to take advantage of it, you must set the `enabled` attribute of the `<UseRandomizedStringHashAlgorithm>` element to `1`.</span></span>  
  
 <span data-ttu-id="4612b-136">La búsqueda de cadenas en una tabla hash suele ser una operación o (1).</span><span class="sxs-lookup"><span data-stu-id="4612b-136">The string lookup in a hash table is typically an O(1) operation.</span></span> <span data-ttu-id="4612b-137">Sin embargo, cuando se produce un gran número de colisiones, la búsqueda puede convertirse en una O (n<sup>2</sup>) operación.</span><span class="sxs-lookup"><span data-stu-id="4612b-137">However, when a large number of collisions occur, the lookup can become an O(n<sup>2</sup>) operation.</span></span> <span data-ttu-id="4612b-138">Puede usar el `<UseRandomizedStringHashAlgorithm>` elemento de configuración para generar un algoritmo hash aleatorio por dominio de aplicación, lo que a su vez limita el número de conflictos potenciales, especialmente cuando las claves desde el que se calculan los códigos hash se basan en la entrada de datos los usuarios.</span><span class="sxs-lookup"><span data-stu-id="4612b-138">You can use the `<UseRandomizedStringHashAlgorithm>` configuration element to generate a random hashing algorithm per application domain, which in turn limits the number of potential collisions, particularly when the keys from which the hash codes are calculated are based on data input by users.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4612b-139">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="4612b-139">Example</span></span>  
 <span data-ttu-id="4612b-140">En el ejemplo siguiente se define un `DisplayString` clase que incluya una constante de cadena privada, `s`, cuyo valor es "Es una cadena".</span><span class="sxs-lookup"><span data-stu-id="4612b-140">The following example defines a `DisplayString` class that includes a private string constant, `s`, whose value is "This is a string."</span></span> <span data-ttu-id="4612b-141">También incluye un `ShowStringHashCode` método que muestra el valor de cadena y su código hash junto con el nombre del dominio de aplicación en el que se ejecuta el método.</span><span class="sxs-lookup"><span data-stu-id="4612b-141">It also includes a `ShowStringHashCode` method that displays the string value and its hash code along with the name of the application domain in which the method is executing.</span></span>  
  
 [!code-csharp[System.String.GetHashCode#2](../../../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.String.GetHashCode/CS/perdomain.cs#2)]
 [!code-vb[System.String.GetHashCode#2](../../../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.String.GetHashCode/VB/perdomain.vb#2)]  
  
 <span data-ttu-id="4612b-142">Al ejecutar el ejemplo sin proporcionar un archivo de configuración, muestra un resultado similar al siguiente.</span><span class="sxs-lookup"><span data-stu-id="4612b-142">When you run the example without supplying a configuration file, it displays output similar to the following.</span></span> <span data-ttu-id="4612b-143">Tenga en cuenta que los códigos hash de la cadena son idénticos en los dos dominios de aplicación.</span><span class="sxs-lookup"><span data-stu-id="4612b-143">Note that the hash codes for the string are identical in the two application domains.</span></span>  
  
```  
String 'This is a string.' in domain 'PerDomain.exe': 941BCEAC  
String 'This is a string.' in domain 'NewDomain': 941BCEAC  
```  
  
 <span data-ttu-id="4612b-144">Sin embargo, si agrega el siguiente archivo de configuración al directorio del ejemplo y, a continuación, ejecute el ejemplo, los códigos hash para la misma cadena diferirán por dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="4612b-144">However, if you add the following configuration file to the example's directory and then run the example, the hash codes for the same string will differ by application domain.</span></span>  
  
```xml  
<?xml version ="1.0"?>  
<configuration>  
   <runtime>  
      <UseRandomizedStringHashAlgorithm enabled="1" />  
   </runtime>  
</configuration>  
```  
  
 <span data-ttu-id="4612b-145">Cuando el archivo de configuración está presente, el ejemplo muestra el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="4612b-145">When the configuration file is present, the example displays the following output:</span></span>  
  
```  
String 'This is a string.' in domain 'PerDomain.exe': 5435776D  
String 'This is a string.' in domain 'NewDomain': 75CC8236  
```  
  
## <a name="see-also"></a><span data-ttu-id="4612b-146">Vea también</span><span class="sxs-lookup"><span data-stu-id="4612b-146">See also</span></span>

- <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType>
- <xref:System.String.GetHashCode%2A?displayProperty=nameWithType>
- <xref:System.Object.GetHashCode%2A?displayProperty=nameWithType>
