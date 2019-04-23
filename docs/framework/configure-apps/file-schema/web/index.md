---
title: Esquema de configuración web
ms.date: 03/30/2017
helpviewer_keywords:
- Web.config configuration file [ASP.NET]
- ASP.NET configuration system, Web settings schema
- schema Web settings
- Web settings, schema [ASP.NET]
- configuration files [ASP.NET]
- configuration schema [.NET Framework], Web settings
ms.assetid: ae1ac356-267d-4753-8d7a-7a04eb45a9be
ms.openlocfilehash: 1f0241b65c915dd5703ceea97dd5b07f88832003
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59113066"
---
# <a name="web-settings-schema"></a><span data-ttu-id="0b23a-102">Esquema de configuración web</span><span class="sxs-lookup"><span data-stu-id="0b23a-102">Web Settings Schema</span></span>
<span data-ttu-id="0b23a-103">La configuración web especifica la configuración de la CPU y de ASP.NET de nivel de ejecución que se aplica al comportamiento de todo el proceso administrado por el nivel de hospedaje de ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="0b23a-103">Web settings specify CPU and execution-level ASP.NET settings that apply to process-wide behavior managed by the ASP.NET hosting layer.</span></span> <span data-ttu-id="0b23a-104">Esta configuración difiere de la del tipo de dominio de la aplicación que se especifica en el archivo Web.config de una aplicación ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="0b23a-104">These settings differ from application domain-type settings that are specified in the Web.config file of an ASP.NET application.</span></span>  
  
 <span data-ttu-id="0b23a-105">La configuración web se incluye en los archivos Aspnet.config, que se encuentran en las carpetas de instalación de las versiones de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="0b23a-105">Web settings are contained in Aspnet.config files, which are located in the installation folders for versions of the .NET Framework.</span></span> <span data-ttu-id="0b23a-106">Por ejemplo, el archivo Aspnet.config para [!INCLUDE[dnprdnext](../../../../../includes/dnprdnext-md.md)] está en la carpeta siguiente:</span><span class="sxs-lookup"><span data-stu-id="0b23a-106">For example, the Aspnet.config file for [!INCLUDE[dnprdnext](../../../../../includes/dnprdnext-md.md)] is in the following folder:</span></span>  
  
 `C:\Windows\Microsoft.NET\Framework\v2.0.50727\`  
  
 <span data-ttu-id="0b23a-107">La configuración web no se usa en otros archivos de configuración, como el archivo machine.config, el archivo raíz Web.config o los archivos Web.config de nivel de aplicación.</span><span class="sxs-lookup"><span data-stu-id="0b23a-107">Web settings are not used in any other configuration files such as the machine.config file, the root Web.config, or application-level Web.config files.</span></span>  
  
 [<span data-ttu-id="0b23a-108">Elemento \<configuration></span><span class="sxs-lookup"><span data-stu-id="0b23a-108">\<configuration> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)  
  
 [<span data-ttu-id="0b23a-109">Elemento \<system.web> (configuración web)</span><span class="sxs-lookup"><span data-stu-id="0b23a-109">\<system.web> Element (Web Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/web/system-web-element-web-settings.md)  
  
 [<span data-ttu-id="0b23a-110">Elemento \<applicationPool> (configuración web)</span><span class="sxs-lookup"><span data-stu-id="0b23a-110">\<applicationPool> Element (Web Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/web/applicationpool-element-web-settings.md)  
  
|<span data-ttu-id="0b23a-111">Elemento</span><span class="sxs-lookup"><span data-stu-id="0b23a-111">Element</span></span>|<span data-ttu-id="0b23a-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="0b23a-112">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0b23a-113">\<system.web></span><span class="sxs-lookup"><span data-stu-id="0b23a-113">\<system.web></span></span>](../../../../../docs/framework/configure-apps/file-schema/web/system-web-element-web-settings.md)|<span data-ttu-id="0b23a-114">Contiene información usada por el nivel de hospedaje de ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="0b23a-114">Contains information that the ASP.NET hosting layer uses.</span></span>|  
|[<span data-ttu-id="0b23a-115">\<applicationPool></span><span class="sxs-lookup"><span data-stu-id="0b23a-115">\<applicationPool></span></span>](../../../../../docs/framework/configure-apps/file-schema/web/applicationpool-element-web-settings.md)|<span data-ttu-id="0b23a-116">Especifica la configuración de la CPU y de ASP.NET de nivel de ejecución que se aplica al comportamiento de todo el proceso, administrado por el nivel de hospedaje de ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="0b23a-116">Specifies CPU and execution-level ASP.NET settings that apply to process-wide behavior managed by the ASP.NET hosting layer.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="0b23a-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="0b23a-117">See also</span></span>

- [<span data-ttu-id="0b23a-118">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="0b23a-118">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
