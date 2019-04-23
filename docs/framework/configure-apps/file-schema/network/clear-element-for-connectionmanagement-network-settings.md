---
title: Elemento <clear> para connectionManagement (configuración de red)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/connectionManagement/clear
- http://schemas.microsoft.com/.NetConfiguration/v2.0#clear
helpviewer_keywords:
- <clear> element, connectionManagement
- connectionManagement, clear element
- clear element, connectionManagement
- <connectionManagement>, clear element
ms.assetid: fb259282-84c4-4dc4-a226-78d904a6edc3
ms.openlocfilehash: 733c70b0575de7e2635afaab58ad48591f035fc0
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59125000"
---
# <a name="clear-element-for-connectionmanagement-network-settings"></a><span data-ttu-id="6ad91-102">\<Borrar > elemento para connectionManagement (configuración de red)</span><span class="sxs-lookup"><span data-stu-id="6ad91-102">\<clear> Element for connectionManagement (Network Settings)</span></span>
<span data-ttu-id="6ad91-103">Borra la lista de administración de conexiones.</span><span class="sxs-lookup"><span data-stu-id="6ad91-103">Clears the connection management list.</span></span>  
  
 <span data-ttu-id="6ad91-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="6ad91-104">\<configuration></span></span>  
<span data-ttu-id="6ad91-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="6ad91-105">\<system.net></span></span>  
<span data-ttu-id="6ad91-106">\<connectionManagement></span><span class="sxs-lookup"><span data-stu-id="6ad91-106">\<connectionManagement></span></span>  
<span data-ttu-id="6ad91-107">\<clear></span><span class="sxs-lookup"><span data-stu-id="6ad91-107">\<clear></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6ad91-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6ad91-108">Syntax</span></span>  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6ad91-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="6ad91-109">Attributes and Elements</span></span>  
 <span data-ttu-id="6ad91-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="6ad91-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6ad91-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="6ad91-111">Attributes</span></span>  
 <span data-ttu-id="6ad91-112">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="6ad91-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="6ad91-113">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="6ad91-113">Child Elements</span></span>  
 <span data-ttu-id="6ad91-114">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="6ad91-114">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="6ad91-115">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="6ad91-115">Parent Elements</span></span>  
  
|<span data-ttu-id="6ad91-116">**Element**</span><span class="sxs-lookup"><span data-stu-id="6ad91-116">**Element**</span></span>|<span data-ttu-id="6ad91-117">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="6ad91-117">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="6ad91-118">connectionManagement</span><span class="sxs-lookup"><span data-stu-id="6ad91-118">connectionManagement</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/connectionmanagement-element-network-settings.md)|<span data-ttu-id="6ad91-119">Especifica el número máximo de conexiones a un host de red.</span><span class="sxs-lookup"><span data-stu-id="6ad91-119">Specifies the maximum number of connections to a network host.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6ad91-120">Comentarios</span><span class="sxs-lookup"><span data-stu-id="6ad91-120">Remarks</span></span>  
 <span data-ttu-id="6ad91-121">El `clear` elemento borra todas las entradas de la lista de administración de conexiones.</span><span class="sxs-lookup"><span data-stu-id="6ad91-121">The `clear` element clears all entries from the connection management list.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="6ad91-122">Archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="6ad91-122">Configuration Files</span></span>  
 <span data-ttu-id="6ad91-123">Este elemento se puede usar en el archivo de configuración de la aplicación o en el archivo de configuración del equipo (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="6ad91-123">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="6ad91-124">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="6ad91-124">Example</span></span>  
 <span data-ttu-id="6ad91-125">El siguiente ejemplo se borra la lista de administración de conexión y, a continuación, agrega nuevas entradas para el servidor `www.contoso.com` y todos los demás hosts de red.</span><span class="sxs-lookup"><span data-stu-id="6ad91-125">The following example clears the connection management list and then adds new connection management entries for the server `www.contoso.com` and all other network hosts.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <connectionManagement>  
      <clear/>  
      <add address = "http://www.contoso.com" maxconnection = "4" />  
      <add address = "*" maxconnection = "2" />  
    </connectionManagement>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="6ad91-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="6ad91-126">See also</span></span>

- <xref:System.Net.ServicePoint>
- <xref:System.Net.ServicePointManager>
- [<span data-ttu-id="6ad91-127">Esquema de la configuración de red</span><span class="sxs-lookup"><span data-stu-id="6ad91-127">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
