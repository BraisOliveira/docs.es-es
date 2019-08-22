---
title: Elemento <remove> para authenticationModules (configuración de red)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/authenticationModules/remove
- http://schemas.microsoft.com/.NetConfiguration/v2.0#remove
helpviewer_keywords:
- remove element, authenticationModules
- <authenticationModules>, remove element
- <remove> element, authenticationModules
- authenticationModules, remove element
ms.assetid: abf79949-b05c-465a-b51c-bbeda9a74173
ms.openlocfilehash: 7f923ce73760fa42a2c435d346f9d1097a5ed82f
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/21/2019
ms.locfileid: "69664050"
---
# <a name="remove-element-for-authenticationmodules-network-settings"></a><span data-ttu-id="91f18-102">\<quitar > elemento para authenticationModules (configuración de red)</span><span class="sxs-lookup"><span data-stu-id="91f18-102">\<remove> Element for authenticationModules (Network Settings)</span></span>
<span data-ttu-id="91f18-103">Quita un módulo de autenticación de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="91f18-103">Removes an authentication module from the application.</span></span>  
  
 <span data-ttu-id="91f18-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="91f18-104">\<configuration></span></span>  
<span data-ttu-id="91f18-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="91f18-105">\<system.net></span></span>  
<span data-ttu-id="91f18-106">\<authenticationModules></span><span class="sxs-lookup"><span data-stu-id="91f18-106">\<authenticationModules></span></span>  
<span data-ttu-id="91f18-107">\<remove></span><span class="sxs-lookup"><span data-stu-id="91f18-107">\<remove></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="91f18-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="91f18-108">Syntax</span></span>  
  
```xml  
<remove   
   type="authentication module name"   
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="91f18-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="91f18-109">Attributes and Elements</span></span>  
 <span data-ttu-id="91f18-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="91f18-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="91f18-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="91f18-111">Attributes</span></span>  
  
|<span data-ttu-id="91f18-112">**Attribute**</span><span class="sxs-lookup"><span data-stu-id="91f18-112">**Attribute**</span></span>|<span data-ttu-id="91f18-113">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="91f18-113">**Description**</span></span>|  
|-------------------|---------------------|  
|<span data-ttu-id="91f18-114">**type**</span><span class="sxs-lookup"><span data-stu-id="91f18-114">**type**</span></span>|<span data-ttu-id="91f18-115">Nombre del módulo de autenticación que se va a quitar.</span><span class="sxs-lookup"><span data-stu-id="91f18-115">The name of the authentication module to remove.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="91f18-116">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="91f18-116">Child Elements</span></span>  
 <span data-ttu-id="91f18-117">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="91f18-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="91f18-118">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="91f18-118">Parent Elements</span></span>  
  
|<span data-ttu-id="91f18-119">**Element**</span><span class="sxs-lookup"><span data-stu-id="91f18-119">**Element**</span></span>|<span data-ttu-id="91f18-120">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="91f18-120">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="91f18-121">authenticationModules</span><span class="sxs-lookup"><span data-stu-id="91f18-121">authenticationModules</span></span>](authenticationmodules-element-network-settings.md)|<span data-ttu-id="91f18-122">Especifica los módulos que se usan para autenticar las solicitudes de red.</span><span class="sxs-lookup"><span data-stu-id="91f18-122">Specifies modules used to authenticate network requests.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="91f18-123">Comentarios</span><span class="sxs-lookup"><span data-stu-id="91f18-123">Remarks</span></span>  
 <span data-ttu-id="91f18-124">El `remove` elemento quita los módulos de autenticación que se definieron anteriormente en el archivo de configuración o en un nivel superior en la jerarquía de configuración.</span><span class="sxs-lookup"><span data-stu-id="91f18-124">The `remove` element removes authentication modules that were defined earlier in the configuration file or at a higher level in the configuration hierarchy.</span></span>  
  
 <span data-ttu-id="91f18-125">El valor del `type` atributo debe ser un nombre de clase válido.</span><span class="sxs-lookup"><span data-stu-id="91f18-125">The value for the `type` attribute should be a valid class name.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="91f18-126">Archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="91f18-126">Configuration Files</span></span>  
 <span data-ttu-id="91f18-127">Este elemento se puede usar en el archivo de configuración de la aplicación o en el archivo de configuración del equipo (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="91f18-127">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="91f18-128">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="91f18-128">Example</span></span>  
 <span data-ttu-id="91f18-129">En el ejemplo siguiente se quita un módulo de autenticación.</span><span class="sxs-lookup"><span data-stu-id="91f18-129">The following example removes an authentication module.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <authenticationModules>  
      <remove type="System.Net.NtlmClient" />  
    </authenticationModules>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="91f18-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="91f18-130">See also</span></span>

- <xref:System.Net.IAuthenticationModule>
- <xref:System.Net.AuthenticationManager>
- [<span data-ttu-id="91f18-131">Esquema de la configuración de red</span><span class="sxs-lookup"><span data-stu-id="91f18-131">Network Settings Schema</span></span>](index.md)
