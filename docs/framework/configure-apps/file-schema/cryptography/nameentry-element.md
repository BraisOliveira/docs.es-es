---
title: <nameEntry> (Elemento)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#nameEntry
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/mscorlib/cryptographySettings/cryptoNameMapping/nameEntry
helpviewer_keywords:
- <nameEntry> element
- nameEntry element
ms.assetid: 7d7535e9-4b4a-4b8c-82e2-e40dff5a7821
ms.openlocfilehash: 97521ba9073820beeea62f5fc7cab480b5422fb0
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61705186"
---
# <a name="nameentry-element"></a><span data-ttu-id="73b7b-102">\<nameEntry > elemento</span><span class="sxs-lookup"><span data-stu-id="73b7b-102">\<nameEntry> Element</span></span>
<span data-ttu-id="73b7b-103">Asigna un nombre de clase a un nombre de algoritmo descriptivo, que permite que una clase tenga varios nombres descriptivos.</span><span class="sxs-lookup"><span data-stu-id="73b7b-103">Maps a class name to a friendly algorithm name, which allows one class to have many friendly names.</span></span>  
  
 <span data-ttu-id="73b7b-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="73b7b-104">\<configuration></span></span>  
<span data-ttu-id="73b7b-105">\<mscorlib></span><span class="sxs-lookup"><span data-stu-id="73b7b-105">\<mscorlib></span></span>  
<span data-ttu-id="73b7b-106">\<cryptographySettings></span><span class="sxs-lookup"><span data-stu-id="73b7b-106">\<cryptographySettings></span></span>  
<span data-ttu-id="73b7b-107">\<cryptoNameMapping></span><span class="sxs-lookup"><span data-stu-id="73b7b-107">\<cryptoNameMapping></span></span>  
<span data-ttu-id="73b7b-108">\<nameEntry></span><span class="sxs-lookup"><span data-stu-id="73b7b-108">\<nameEntry></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="73b7b-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="73b7b-109">Syntax</span></span>  
  
```xml  
<nameEntry name="friendly name" Class="class name" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="73b7b-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="73b7b-110">Attributes and Elements</span></span>  
 <span data-ttu-id="73b7b-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="73b7b-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="73b7b-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="73b7b-112">Attributes</span></span>  
  
|<span data-ttu-id="73b7b-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="73b7b-113">Attribute</span></span>|<span data-ttu-id="73b7b-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="73b7b-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="73b7b-115">**name**</span><span class="sxs-lookup"><span data-stu-id="73b7b-115">**name**</span></span>|<span data-ttu-id="73b7b-116">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="73b7b-116">Required attribute.</span></span><br /><br /> <span data-ttu-id="73b7b-117">Especifica el nombre descriptivo del algoritmo que implementa la clase de criptografía.</span><span class="sxs-lookup"><span data-stu-id="73b7b-117">Specifies the friendly name of the algorithm that the cryptography class implements.</span></span>|  
|<span data-ttu-id="73b7b-118">**class**</span><span class="sxs-lookup"><span data-stu-id="73b7b-118">**class**</span></span>|<span data-ttu-id="73b7b-119">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="73b7b-119">Required attribute.</span></span><br /><br /> <span data-ttu-id="73b7b-120">Especifica el valor de la **nombre** atributo en el [ \<cryptoClass >](../../../../../docs/framework/configure-apps/file-schema/cryptography/cryptoclass-element.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="73b7b-120">Specifies the value for the **name** attribute in the [\<cryptoClass>](../../../../../docs/framework/configure-apps/file-schema/cryptography/cryptoclass-element.md) element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="73b7b-121">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="73b7b-121">Child Elements</span></span>  
 <span data-ttu-id="73b7b-122">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="73b7b-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="73b7b-123">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="73b7b-123">Parent Elements</span></span>  
  
|<span data-ttu-id="73b7b-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="73b7b-124">Element</span></span>|<span data-ttu-id="73b7b-125">Descripción</span><span class="sxs-lookup"><span data-stu-id="73b7b-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="73b7b-126">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="73b7b-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.web`|<span data-ttu-id="73b7b-127">Especifica el elemento raíz de la sección de configuración de ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="73b7b-127">Specifies the root element for the ASP.NET configuration section.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="73b7b-128">Comentarios</span><span class="sxs-lookup"><span data-stu-id="73b7b-128">Remarks</span></span>  
 <span data-ttu-id="73b7b-129">El **nombre** atributo puede ser el nombre de una de las clases abstractas se encuentra en la <xref:System.Security.Cryptography> espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="73b7b-129">The **name** attribute can be the name of one of the abstract classes found in the <xref:System.Security.Cryptography> namespace.</span></span> <span data-ttu-id="73b7b-130">Cuando se llama a la **crear** método en una clase abstracta de criptografía, el nombre de la clase abstracta se pasa a la <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A> método.</span><span class="sxs-lookup"><span data-stu-id="73b7b-130">When you call the **Create** method on an abstract cryptography class, the abstract class name is passed to the <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A> method.</span></span> <span data-ttu-id="73b7b-131">**CreateFromName** devuelve una instancia del tipo indicado por la **clase** atributo.</span><span class="sxs-lookup"><span data-stu-id="73b7b-131">**CreateFromName** returns an instance of the type indicated by the **class** attribute.</span></span> <span data-ttu-id="73b7b-132">Si el **nombre** atributo es un nombre corto, como RSA, se puede utilizar ese nombre al llamar a la **CreateFromName** método.</span><span class="sxs-lookup"><span data-stu-id="73b7b-132">If the **name** attribute is a short name, such as RSA, you can use that name when calling the **CreateFromName** method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="73b7b-133">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="73b7b-133">Example</span></span>  
 <span data-ttu-id="73b7b-134">El ejemplo siguiente muestra cómo usar el  **\<nameEntry >** elemento para hacer referencia a una clase de criptografía y configurar el tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="73b7b-134">The following example shows how to use the **\<nameEntry>** element to reference a cryptography class and to configure the runtime.</span></span> <span data-ttu-id="73b7b-135">A continuación, puede pasar la cadena "RSA" a la <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> método y el uso la <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> método devuelva un `MyCryptoRSAClass` objeto.</span><span class="sxs-lookup"><span data-stu-id="73b7b-135">You can then pass the string "RSA" to the <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> method and use the <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> method to return a `MyCryptoRSAClass` object.</span></span>  
  
```xml  
<configuration>  
   <mscorlib>  
      <cryptographySettings>  
         <cryptoNameMapping>  
            <cryptoClasses>  
               <cryptoClass   MyCryptoRSA="MyCryptoRSAClass, MyAssembly  
                  Culture=neutral, PublicKeyToken=a5d015c7d5a0b012,  
                  Version=1.0.0.0"/>  
            </cryptoClasses>  
            <nameEntry name="RSA" class="MyCryptoRSA"/>  
            <nameEntry name="System.Security.Cryptography.AsymmetricAlgorithm"  
                       class="MyCryptoRSA"/>  
         </cryptoNameMapping>  
      </cryptographySettings>  
   </mscorlib>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="73b7b-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="73b7b-136">See also</span></span>

- [<span data-ttu-id="73b7b-137">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="73b7b-137">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
- [<span data-ttu-id="73b7b-138">Esquema de la configuración de criptografía</span><span class="sxs-lookup"><span data-stu-id="73b7b-138">Cryptography Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/cryptography/index.md)
- [<span data-ttu-id="73b7b-139">Cryptographic Services</span><span class="sxs-lookup"><span data-stu-id="73b7b-139">Cryptographic Services</span></span>](../../../../../docs/standard/security/cryptographic-services.md)
- [<span data-ttu-id="73b7b-140">Configurar clases de criptografía</span><span class="sxs-lookup"><span data-stu-id="73b7b-140">Configuring Cryptography Classes</span></span>](../../../../../docs/framework/configure-apps/configure-cryptography-classes.md)
