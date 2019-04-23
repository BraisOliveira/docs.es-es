---
title: <enforceFIPSPolicy> (Elemento)
ms.date: 03/30/2017
helpviewer_keywords:
- enforceFIPSPolicy element
- FIPS
- <enforceFIPSPolicy> element
- Federal Information Processing Standards (FIPS)
ms.assetid: c35509c4-35cf-43c0-bb47-75e4208aa24e
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b1aa958e15449949a1b7ca740198fff71295b2ad
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59114838"
---
# <a name="enforcefipspolicy-element"></a><span data-ttu-id="f3f74-102">\<enforceFIPSPolicy > elemento</span><span class="sxs-lookup"><span data-stu-id="f3f74-102">\<enforceFIPSPolicy> Element</span></span>
<span data-ttu-id="f3f74-103">Especifica si se debe exigir un requisito de configuración del equipo que indique que los algoritmos criptográficos deben cumplir con los Estándares federales de procesamiento de la información (FIPS).</span><span class="sxs-lookup"><span data-stu-id="f3f74-103">Specifies whether to enforce a computer configuration requirement that cryptographic algorithms must comply with the Federal Information Processing Standards (FIPS).</span></span>  
  
 <span data-ttu-id="f3f74-104">\<Configuración > elemento</span><span class="sxs-lookup"><span data-stu-id="f3f74-104">\<configuration> Element</span></span>  
<span data-ttu-id="f3f74-105">\<en tiempo de ejecución > elemento</span><span class="sxs-lookup"><span data-stu-id="f3f74-105">\<runtime> Element</span></span>  
<span data-ttu-id="f3f74-106">\<enforceFIPSPolicy > elemento</span><span class="sxs-lookup"><span data-stu-id="f3f74-106">\<enforceFIPSPolicy> Element</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f3f74-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f3f74-107">Syntax</span></span>  
  
```xml  
<enforceFIPSPolicy enabled="true|false" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f3f74-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="f3f74-108">Attributes and Elements</span></span>  
 <span data-ttu-id="f3f74-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="f3f74-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f3f74-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="f3f74-110">Attributes</span></span>  
  
|<span data-ttu-id="f3f74-111">Atributo</span><span class="sxs-lookup"><span data-stu-id="f3f74-111">Attribute</span></span>|<span data-ttu-id="f3f74-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="f3f74-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="f3f74-113">enabled</span><span class="sxs-lookup"><span data-stu-id="f3f74-113">enabled</span></span>|<span data-ttu-id="f3f74-114">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="f3f74-114">Required attribute.</span></span><br /><br /> <span data-ttu-id="f3f74-115">Especifica si se habilita el cumplimiento de un requisito de configuración del equipo que los algoritmos criptográficos deben ser compatibles con FIPS.</span><span class="sxs-lookup"><span data-stu-id="f3f74-115">Specifies whether to enable the enforcement of a computer configuration requirement that cryptographic algorithms must be compliant with FIPS.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="f3f74-116">Atributo enabled</span><span class="sxs-lookup"><span data-stu-id="f3f74-116">enabled Attribute</span></span>  
  
|<span data-ttu-id="f3f74-117">Valor</span><span class="sxs-lookup"><span data-stu-id="f3f74-117">Value</span></span>|<span data-ttu-id="f3f74-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="f3f74-118">Description</span></span>|  
|-----------|-----------------|  
|`true`|<span data-ttu-id="f3f74-119">Si el equipo está configurado para requerir que los algoritmos criptográficos sea compatible con FIPS, se aplicará este requisito.</span><span class="sxs-lookup"><span data-stu-id="f3f74-119">If your computer is configured to require cryptographic algorithms to be FIPS compliant, that requirement is enforced.</span></span> <span data-ttu-id="f3f74-120">Si una clase implementa un algoritmo que no es compatible con FIPS, los constructores o `Create` métodos de esa clase producen excepciones cuando se ejecutan en ese equipo.</span><span class="sxs-lookup"><span data-stu-id="f3f74-120">If a class implements an algorithm that is not compliant with FIPS, the constructors or `Create` methods for that class throw exceptions when they are run on that computer.</span></span> <span data-ttu-id="f3f74-121">Este es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="f3f74-121">This is the default.</span></span>|  
|`false`|<span data-ttu-id="f3f74-122">Los algoritmos criptográficos utilizados por la aplicación no tienen que ser compatible con FIPS, independientemente de la configuración del equipo.</span><span class="sxs-lookup"><span data-stu-id="f3f74-122">Cryptographic algorithms that are used by the application are not required to be compliant with FIPS, regardless of computer configuration.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f3f74-123">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="f3f74-123">Child Elements</span></span>  
 <span data-ttu-id="f3f74-124">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="f3f74-124">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f3f74-125">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="f3f74-125">Parent Elements</span></span>  
  
|<span data-ttu-id="f3f74-126">Elemento</span><span class="sxs-lookup"><span data-stu-id="f3f74-126">Element</span></span>|<span data-ttu-id="f3f74-127">Descripción</span><span class="sxs-lookup"><span data-stu-id="f3f74-127">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="f3f74-128">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="f3f74-128">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="f3f74-129">Contiene información del enlace del ensamblado y de la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="f3f74-129">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f3f74-130">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f3f74-130">Remarks</span></span>  
 <span data-ttu-id="f3f74-131">A partir de .NET Framework 2.0, la creación de clases que implementan algoritmos criptográficos se controla mediante la configuración del equipo.</span><span class="sxs-lookup"><span data-stu-id="f3f74-131">Starting with the .NET Framework 2.0, the creation of classes that implement cryptographic algorithms is controlled by the configuration of the computer.</span></span> <span data-ttu-id="f3f74-132">Si el equipo está configurado para requerir algoritmos para ser compatible con FIPS, y una clase implementa un algoritmo que no es compatible con FIPS, cualquier intento de crear una instancia de esa clase produce una excepción.</span><span class="sxs-lookup"><span data-stu-id="f3f74-132">If the computer is configured to require algorithms to be compliant with FIPS, and a class implements an algorithm that is not compliant with FIPS, any attempt to create an instance of that class throws an exception.</span></span> <span data-ttu-id="f3f74-133">Constructores de producen una <xref:System.InvalidOperationException> excepción, y `Create` métodos inician una <xref:System.Reflection.TargetInvocationException> excepción con un interior <xref:System.InvalidOperationException> excepción.</span><span class="sxs-lookup"><span data-stu-id="f3f74-133">Constructors throw an <xref:System.InvalidOperationException> exception, and `Create` methods throw a <xref:System.Reflection.TargetInvocationException> exception with an inner <xref:System.InvalidOperationException> exception.</span></span>  
  
 <span data-ttu-id="f3f74-134">Si la aplicación se ejecuta en equipos cuya configuración exigir el cumplimiento de FIPS y la aplicación utiliza un algoritmo que no es compatible con FIPS, puede usar este elemento en el archivo de configuración para evitar que common language runtime (CLR) de exigir el cumplimiento de FIPS.</span><span class="sxs-lookup"><span data-stu-id="f3f74-134">If your application runs on computers whose configurations require compliance with FIPS, and your application uses an algorithm that is not compliant with FIPS, you can use this element in your configuration file to prevent the common language runtime (CLR) from enforcing FIPS compliance.</span></span> <span data-ttu-id="f3f74-135">Este elemento se introdujo en la [!INCLUDE[net_v20SP1_long](../../../../../includes/net-v20sp1-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f3f74-135">This element was introduced in the [!INCLUDE[net_v20SP1_long](../../../../../includes/net-v20sp1-long-md.md)].</span></span>  
  
## <a name="example"></a><span data-ttu-id="f3f74-136">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f3f74-136">Example</span></span>  
 <span data-ttu-id="f3f74-137">El ejemplo siguiente muestra cómo evitar que el CLR exigir el cumplimiento de FIPS.</span><span class="sxs-lookup"><span data-stu-id="f3f74-137">The following example shows how to prevent the CLR from enforcing FIPS compliance.</span></span>  
  
```xml  
<configuration>  
    <runtime>  
        <enforceFIPSPolicy enabled="false"/>  
    </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="f3f74-138">Vea también</span><span class="sxs-lookup"><span data-stu-id="f3f74-138">See also</span></span>

- [<span data-ttu-id="f3f74-139">Esquema de la configuración de Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="f3f74-139">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [<span data-ttu-id="f3f74-140">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="f3f74-140">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
- [<span data-ttu-id="f3f74-141">Modelo de criptografía</span><span class="sxs-lookup"><span data-stu-id="f3f74-141">Cryptography Model</span></span>](../../../../../docs/standard/security/cryptography-model.md)
