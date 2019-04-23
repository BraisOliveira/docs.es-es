---
title: Elemento <authenticationModules> (configuración de red)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#authenticationModules
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/authenticationModules
helpviewer_keywords:
- authenticationModules element
- <authenticationModules> element
ms.assetid: 10fcfaad-82ef-4692-871a-0aec9dfbe75e
ms.openlocfilehash: 8878bcbdf8b3613677231db3e91a6d71dfa10bae
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59143343"
---
# <a name="authenticationmodules-element-network-settings"></a><span data-ttu-id="32d6f-102">\<authenticationModules > elemento (configuración de red)</span><span class="sxs-lookup"><span data-stu-id="32d6f-102">\<authenticationModules> Element (Network Settings)</span></span>
<span data-ttu-id="32d6f-103">Especifica los módulos que se usa para autenticar las solicitudes de red.</span><span class="sxs-lookup"><span data-stu-id="32d6f-103">Specifies modules used to authenticate network requests.</span></span>  
  
 <span data-ttu-id="32d6f-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="32d6f-104">\<configuration></span></span>  
<span data-ttu-id="32d6f-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="32d6f-105">\<system.net></span></span>  
<span data-ttu-id="32d6f-106">\<authenticationModules></span><span class="sxs-lookup"><span data-stu-id="32d6f-106">\<authenticationModules></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="32d6f-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="32d6f-107">Syntax</span></span>  
  
```xml  
<authenticationModules>   
</authenticationModules>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="32d6f-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="32d6f-108">Attributes and Elements</span></span>  
 <span data-ttu-id="32d6f-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="32d6f-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="32d6f-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="32d6f-110">Attributes</span></span>  
 <span data-ttu-id="32d6f-111">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="32d6f-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="32d6f-112">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="32d6f-112">Child Elements</span></span>  
  
|<span data-ttu-id="32d6f-113">**Element**</span><span class="sxs-lookup"><span data-stu-id="32d6f-113">**Element**</span></span>|<span data-ttu-id="32d6f-114">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="32d6f-114">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="32d6f-115">add</span><span class="sxs-lookup"><span data-stu-id="32d6f-115">add</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/add-element-for-authenticationmodules-network-settings.md)|<span data-ttu-id="32d6f-116">Agrega un módulo de autenticación a la aplicación.</span><span class="sxs-lookup"><span data-stu-id="32d6f-116">Adds an authentication module to the application.</span></span>|  
|[<span data-ttu-id="32d6f-117">clear</span><span class="sxs-lookup"><span data-stu-id="32d6f-117">clear</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/clear-element-for-authenticationmodules-network-settings.md)|<span data-ttu-id="32d6f-118">Borra todos los módulos de autenticación de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="32d6f-118">Clears all authentication modules from the application.</span></span>|  
|[<span data-ttu-id="32d6f-119">remove</span><span class="sxs-lookup"><span data-stu-id="32d6f-119">remove</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/remove-element-for-authenticationmodules-network-settings.md)|<span data-ttu-id="32d6f-120">Quita un módulo de autenticación de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="32d6f-120">Removes an authentication module from the application.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="32d6f-121">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="32d6f-121">Parent Elements</span></span>  
  
|<span data-ttu-id="32d6f-122">**Element**</span><span class="sxs-lookup"><span data-stu-id="32d6f-122">**Element**</span></span>|<span data-ttu-id="32d6f-123">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="32d6f-123">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="32d6f-124">system.net</span><span class="sxs-lookup"><span data-stu-id="32d6f-124">system.net</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/system-net-element-network-settings.md)|<span data-ttu-id="32d6f-125">Contiene valores que especifican cómo se conecta .NET Framework a la red.</span><span class="sxs-lookup"><span data-stu-id="32d6f-125">Contains settings that specify how the .NET Framework connects to the network.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="32d6f-126">Comentarios</span><span class="sxs-lookup"><span data-stu-id="32d6f-126">Remarks</span></span>  
 <span data-ttu-id="32d6f-127">El `authenticationModule` elemento especifica los módulos de autenticación que realizan el proceso de autenticación con un servidor.</span><span class="sxs-lookup"><span data-stu-id="32d6f-127">The `authenticationModule` element specifies the authentication modules that conduct the authentication process with a server.</span></span> <span data-ttu-id="32d6f-128">Un módulo de autenticación debe implementar la <xref:System.Net.IAuthenticationModule> interfaz.</span><span class="sxs-lookup"><span data-stu-id="32d6f-128">An authentication module must implement the <xref:System.Net.IAuthenticationModule> interface.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="32d6f-129">Archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="32d6f-129">Configuration Files</span></span>  
 <span data-ttu-id="32d6f-130">Este elemento se puede usar en el archivo de configuración de la aplicación o en el archivo de configuración del equipo (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="32d6f-130">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="32d6f-131">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="32d6f-131">Example</span></span>  
 <span data-ttu-id="32d6f-132">El ejemplo siguiente habilita un módulo de autenticación.</span><span class="sxs-lookup"><span data-stu-id="32d6f-132">The following example enables an authentication module.</span></span> <span data-ttu-id="32d6f-133">Debe reemplazar los valores de versión y PublicKeyToken con los valores correctos para el módulo especificado.</span><span class="sxs-lookup"><span data-stu-id="32d6f-133">You should replace the values for Version and PublicKeyToken with the correct values for the specified module.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <authenticationModules>  
      <add type="System.Net.DigestClient, System, Version=2.0.3600.0,  
                 Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
    </authenticationModules>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="32d6f-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="32d6f-134">See also</span></span>

- <xref:System.Net.IAuthenticationModule>
- <xref:System.Net.AuthenticationManager>
- [<span data-ttu-id="32d6f-135">Esquema de la configuración de red</span><span class="sxs-lookup"><span data-stu-id="32d6f-135">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
