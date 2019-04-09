---
title: <connectionManagement> Elemento (configuración de red)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/connectionManagement
- http://schemas.microsoft.com/.NetConfiguration/v2.0#connectionManagement
helpviewer_keywords:
- <connectionManagement> element
- connectionManagement element
ms.assetid: bedccaab-12a2-4511-8f67-e961f249aec6
ms.openlocfilehash: 4412fe30bfb8dcb3d7576df18cb2a472463d935c
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59125190"
---
# <a name="connectionmanagement-element-network-settings"></a><span data-ttu-id="2b1f5-102">\<connectionManagement > elemento (configuración de red)</span><span class="sxs-lookup"><span data-stu-id="2b1f5-102">\<connectionManagement> Element (Network Settings)</span></span>
<span data-ttu-id="2b1f5-103">Especifica el número máximo de conexiones a un host de red.</span><span class="sxs-lookup"><span data-stu-id="2b1f5-103">Specifies the maximum number of connections to a network host.</span></span>  
  
 <span data-ttu-id="2b1f5-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="2b1f5-104">\<configuration></span></span>  
<span data-ttu-id="2b1f5-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="2b1f5-105">\<system.net></span></span>  
<span data-ttu-id="2b1f5-106">\<connectionManagement></span><span class="sxs-lookup"><span data-stu-id="2b1f5-106">\<connectionManagement></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2b1f5-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2b1f5-107">Syntax</span></span>  
  
```xml  
<connectionManagement>   
</connectionManagement>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2b1f5-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="2b1f5-108">Attributes and Elements</span></span>  
 <span data-ttu-id="2b1f5-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="2b1f5-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2b1f5-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="2b1f5-110">Attributes</span></span>  
 <span data-ttu-id="2b1f5-111">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="2b1f5-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="2b1f5-112">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="2b1f5-112">Child Elements</span></span>  
  
|**<span data-ttu-id="2b1f5-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="2b1f5-113">Element</span></span>**|**<span data-ttu-id="2b1f5-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="2b1f5-114">Description</span></span>**|  
|-----------------|---------------------|  
|[<span data-ttu-id="2b1f5-115">agregar</span><span class="sxs-lookup"><span data-stu-id="2b1f5-115">add</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/add-element-for-connectionmanagement-network-settings.md)|<span data-ttu-id="2b1f5-116">Agrega una dirección IP o nombre DNS a la lista de administración de conexión.</span><span class="sxs-lookup"><span data-stu-id="2b1f5-116">Adds an IP address or DNS name to the connection management list.</span></span>|  
|[<span data-ttu-id="2b1f5-117">desactivada</span><span class="sxs-lookup"><span data-stu-id="2b1f5-117">clear</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/clear-element-for-connectionmanagement-network-settings.md)|<span data-ttu-id="2b1f5-118">Borra la lista de administración de conexiones.</span><span class="sxs-lookup"><span data-stu-id="2b1f5-118">Clears the connection management list.</span></span>|  
|[<span data-ttu-id="2b1f5-119">remove</span><span class="sxs-lookup"><span data-stu-id="2b1f5-119">remove</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/remove-element-for-connectionmanagement-network-settings.md)|<span data-ttu-id="2b1f5-120">Quita una dirección IP o nombre DNS de la lista de administración de conexiones.</span><span class="sxs-lookup"><span data-stu-id="2b1f5-120">Removes an IP address or DNS name from the connection management list.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="2b1f5-121">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="2b1f5-121">Parent Elements</span></span>  
  
|**<span data-ttu-id="2b1f5-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="2b1f5-122">Element</span></span>**|**<span data-ttu-id="2b1f5-123">Descripción</span><span class="sxs-lookup"><span data-stu-id="2b1f5-123">Description</span></span>**|  
|-----------------|---------------------|  
|[<span data-ttu-id="2b1f5-124">system.net</span><span class="sxs-lookup"><span data-stu-id="2b1f5-124">system.net</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/system-net-element-network-settings.md)|<span data-ttu-id="2b1f5-125">Contiene valores que especifican cómo se conecta .NET Framework a la red.</span><span class="sxs-lookup"><span data-stu-id="2b1f5-125">Contains settings that specify how the .NET Framework connects to the network.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2b1f5-126">Comentarios</span><span class="sxs-lookup"><span data-stu-id="2b1f5-126">Remarks</span></span>  
 <span data-ttu-id="2b1f5-127">El `connectionManagement` elemento define el número máximo de conexiones en un servidor o grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="2b1f5-127">The `connectionManagement` element defines the maximum number of connections to a server or group of servers.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="2b1f5-128">Archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="2b1f5-128">Configuration Files</span></span>  
 <span data-ttu-id="2b1f5-129">Este elemento se puede usar en el archivo de configuración de la aplicación o en el archivo de configuración del equipo (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="2b1f5-129">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="2b1f5-130">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="2b1f5-130">Example</span></span>  
 <span data-ttu-id="2b1f5-131">En el ejemplo siguiente se configura una aplicación para usar cuatro conexiones al servidor `www.contoso.com` y dos conexiones con todos los demás servidores.</span><span class="sxs-lookup"><span data-stu-id="2b1f5-131">The following example configures an application to use four connections to the server `www.contoso.com` and two connections to all other servers.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <connectionManagement>  
      <add address = "http://www.contoso.com" maxconnection = "4" />  
      <add address = "*" maxconnection = "2" />  
    </connectionManagement>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="2b1f5-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="2b1f5-132">See also</span></span>

- <xref:System.Net.ServicePoint>
- <xref:System.Net.ServicePointManager>
- [<span data-ttu-id="2b1f5-133">Esquema de la configuración de red</span><span class="sxs-lookup"><span data-stu-id="2b1f5-133">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
