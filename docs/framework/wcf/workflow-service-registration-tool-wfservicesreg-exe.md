---
title: Herramienta de registro de servicio de flujo de trabajo (WFServicesReg.exe)
ms.date: 03/30/2017
ms.assetid: 9e92c87b-99c5-4e8d-9d53-7944cc2b47d3
ms.openlocfilehash: 0a9cd5039c085f82f5507c93ebe0855cc620825d
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69916821"
---
# <a name="workflow-service-registration-tool-wfservicesregexe"></a><span data-ttu-id="690ec-102">Herramienta de registro de servicio de flujo de trabajo (WFServicesReg.exe)</span><span class="sxs-lookup"><span data-stu-id="690ec-102">WorkFlow Service Registration Tool (WFServicesReg.exe)</span></span>
<span data-ttu-id="690ec-103">El registro de servicio de flujo de trabajo (WFServicesReg.exe) es una herramienta independiente que puede utilizarse para agregar, quitar o reparar los elementos de configuración de los servicios de Windows Workflow Foundation (WF).</span><span class="sxs-lookup"><span data-stu-id="690ec-103">Workflow Services Registration tool (WFServicesReg.exe) is a stand-alone tool that can be used to add, remove, or repair the configuration elements for Windows Workflow Foundation (WF) services.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="690ec-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="690ec-104">Syntax</span></span>  
  
```  
WFServicesReg.exe [-c | -r | -v | -m | -i]  
```  
  
## <a name="remarks"></a><span data-ttu-id="690ec-105">Comentarios</span><span class="sxs-lookup"><span data-stu-id="690ec-105">Remarks</span></span>  
 <span data-ttu-id="690ec-106">La herramienta se encuentra en la ubicación de instalación [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)], concretamente, en %windir%\Microsoft.NET\Framework\v3.5 o, en el caso de equipos de 64 bits, en %windir%\Microsoft.NET\Framework64\v3.5.</span><span class="sxs-lookup"><span data-stu-id="690ec-106">The tool can be found at the [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)] installation location, specifically, %windir%\Microsoft.NET\Framework\v3.5, or at %windir%\Microsoft.NET\Framework64\v3.5 in 64-bit machines.</span></span>  
  
 <span data-ttu-id="690ec-107">Las tablas siguientes describen las opciones que pueden utilizarse con la herramienta de registro de servicio de flujo de trabajo (WFServicesReg.exe).</span><span class="sxs-lookup"><span data-stu-id="690ec-107">The following tables describe the options that can be used with the Workflow Services Registration tool (WFServicesReg.exe).</span></span>  
  
|<span data-ttu-id="690ec-108">Opción</span><span class="sxs-lookup"><span data-stu-id="690ec-108">Option</span></span>|<span data-ttu-id="690ec-109">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="690ec-109">Description</span></span>|  
|------------|-----------------|  
|`/c`|<span data-ttu-id="690ec-110">Configura los servicios de flujo de trabajo de Windows.</span><span class="sxs-lookup"><span data-stu-id="690ec-110">Configures Windows Workflow Services.</span></span> <span data-ttu-id="690ec-111">Se utiliza en escenarios de instalación y reparación.</span><span class="sxs-lookup"><span data-stu-id="690ec-111">Used in install and repair scenarios.</span></span>|  
|`/r`|<span data-ttu-id="690ec-112">Quita la configuración de los servicios de flujo de trabajo de Windows.</span><span class="sxs-lookup"><span data-stu-id="690ec-112">Removes Windows Workflow Services Configuration.</span></span>|  
|`/v`|<span data-ttu-id="690ec-113">Imprime información detallada (para configuración o eliminación).</span><span class="sxs-lookup"><span data-stu-id="690ec-113">Print verbose information (for either configuration or removal).</span></span>|  
|`/m`|<span data-ttu-id="690ec-114">Habilita el formato de registro de MSI.</span><span class="sxs-lookup"><span data-stu-id="690ec-114">Enables MSI logging format.</span></span>|  
|`/i`|<span data-ttu-id="690ec-115">Minimiza la ventana cuando se ejecuta la aplicación.</span><span class="sxs-lookup"><span data-stu-id="690ec-115">Minimizes the window when the application runs.</span></span>|  
  
## <a name="registration"></a><span data-ttu-id="690ec-116">Registro</span><span class="sxs-lookup"><span data-stu-id="690ec-116">Registration</span></span>  
 <span data-ttu-id="690ec-117">La herramienta inspecciona el archivo Web.config y registra lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="690ec-117">The tool inspects the Web.config file and registers the following:</span></span>  
  
- <span data-ttu-id="690ec-118">Ensamblados de referencia [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="690ec-118">[!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)] reference assemblies.</span></span>  
  
- <span data-ttu-id="690ec-119">Proveedor de compilación para archivos .xoml.</span><span class="sxs-lookup"><span data-stu-id="690ec-119">A build provider for .xoml files.</span></span>  
  
- <span data-ttu-id="690ec-120">Controladores HTTP para archivos .xoml y .rules.</span><span class="sxs-lookup"><span data-stu-id="690ec-120">HTTP handlers for .xoml and .rules files.</span></span>  
  
 <span data-ttu-id="690ec-121">La herramienta inspecciona el archivo Machine.config y registra las siguientes extensiones:</span><span class="sxs-lookup"><span data-stu-id="690ec-121">The tool inspects the Machine.config file and registers the following extensions:</span></span>  
  
- <span data-ttu-id="690ec-122">behaviorExtensions</span><span class="sxs-lookup"><span data-stu-id="690ec-122">behaviorExtensions</span></span>  
  
- <span data-ttu-id="690ec-123">bindingElementExtensions</span><span class="sxs-lookup"><span data-stu-id="690ec-123">bindingElementExtensions</span></span>  
  
- <span data-ttu-id="690ec-124">bindingExtensions</span><span class="sxs-lookup"><span data-stu-id="690ec-124">bindingExtensions</span></span>  
  
 <span data-ttu-id="690ec-125">La herramienta también registra los siguientes importadores de metadatos de cliente:</span><span class="sxs-lookup"><span data-stu-id="690ec-125">The tool also registers the following client metadata importers:</span></span>  
  
- <span data-ttu-id="690ec-126">policyImporters</span><span class="sxs-lookup"><span data-stu-id="690ec-126">policyImporters</span></span>  
  
- <span data-ttu-id="690ec-127">wsdlImporters</span><span class="sxs-lookup"><span data-stu-id="690ec-127">wsdlImporters</span></span>  
  
 <span data-ttu-id="690ec-128">La herramienta también registra los controladores y las asignaciones de secuencias de comandos de .xoml y .rules en la metabase de IIS.</span><span class="sxs-lookup"><span data-stu-id="690ec-128">The tool also registers .xoml and .rules scriptmaps and handlers in the IIS metabase.</span></span>  
  
 <span data-ttu-id="690ec-129">En [!INCLUDE[ws2003](../../../includes/ws2003-md.md)] las [!INCLUDE[wxp](../../../includes/wxp-md.md)] máquinas y (IIS 5,1 e IIS 6,0), se registra un conjunto de asignaciones de scripts. xoml y. rules.</span><span class="sxs-lookup"><span data-stu-id="690ec-129">On [!INCLUDE[ws2003](../../../includes/ws2003-md.md)] and [!INCLUDE[wxp](../../../includes/wxp-md.md)] machines (IIS 5.1 and IIS 6.0), one set of .xoml and .rules scriptmaps are registered.</span></span>  
  
 <span data-ttu-id="690ec-130">En equipos de 64 bits, la herramienta registra asignaciones de secuencias de comandos en el modo WOW si el modificador `Enable32BitAppOnWin64` está habilitado, o asignaciones de secuencias de comandos nativas de 64 bits si el modificador `Enable32BitAppOnWin64` está deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="690ec-130">On 64-bit machines, the tool registers WOW mode scriptmaps if the `Enable32BitAppOnWin64` switch is enabled, or native 64-bit scriptmaps if the `Enable32BitAppOnWin64` switch is disabled.</span></span>  
  
 <span data-ttu-id="690ec-131">En [!INCLUDE[wv](../../../includes/wv-md.md)] y Windows Server 2008 (IIS 7,0 y versiones posteriores), se registran dos conjuntos de controladores. xoml y. rules: uno para el modo integrado y otro para el modo clásico.</span><span class="sxs-lookup"><span data-stu-id="690ec-131">On [!INCLUDE[wv](../../../includes/wv-md.md)] and Windows Server 2008 (IIS 7.0 and above) machines, two sets of .xoml and .rules handlers are registered: one for Integrated mode and one for Classic mode.</span></span>  
  
 <span data-ttu-id="690ec-132">En equipos de 64 bits, se registran tres conjuntos de controladores (independientemente del estado del modificador `Enable32BitAppOnWin64`): uno para el modo integrado, otro para el modo clásico de WOW y el tercero para el modo clásico de 64 bits nativo.</span><span class="sxs-lookup"><span data-stu-id="690ec-132">On 64-bit machines, three sets of handlers are registered (regardless of the state of the `Enable32BitAppOnWin64` switch): one for Integrated mode, one for WOW Classic mode and one for native 64-bit Classic mode.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="690ec-133">A diferencia de ServiceModelReg.exe, WFServicesReg.exe no permite agregar, quitar o reparar asignaciones de secuencias de comandos o controladores de un sitio web determinado.</span><span class="sxs-lookup"><span data-stu-id="690ec-133">Unlike ServiceModelreg.exe, WFServicesReg.exe does not allow adding, removing, or repairing scriptmaps or handlers for a particular Web site.</span></span> <span data-ttu-id="690ec-134">Para encontrar una solución a este problema, vea la sección "Reparar asignaciones de secuencias de comandos".</span><span class="sxs-lookup"><span data-stu-id="690ec-134">For a workaround to this issue, see the "Repairing the Scriptmaps" section.</span></span>  
  
## <a name="usage-scenarios"></a><span data-ttu-id="690ec-135">Escenarios de uso</span><span class="sxs-lookup"><span data-stu-id="690ec-135">Usage Scenarios</span></span>  
  
### <a name="installing-iis-after-net-framework-35-is-installed"></a><span data-ttu-id="690ec-136">Instalar IIS una vez instalado .NET Framework 3.5</span><span class="sxs-lookup"><span data-stu-id="690ec-136">Installing IIS after .NET Framework 3.5 is installed</span></span>  
 <span data-ttu-id="690ec-137">En un equipo [!INCLUDE[ws2003](../../../includes/ws2003-md.md)], se instala [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)] antes que IIS.</span><span class="sxs-lookup"><span data-stu-id="690ec-137">On a [!INCLUDE[ws2003](../../../includes/ws2003-md.md)] machine, [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)] is installed prior to IIS installation.</span></span> <span data-ttu-id="690ec-138">Debido a la falta de disponibilidad de la metabase de IIS, [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)] se instala correctamente sin instalar las asignaciones de secuencias de comandos de .xoml y .rules.</span><span class="sxs-lookup"><span data-stu-id="690ec-138">Due to the unavailability of the IIS metabase, installation of [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)] succeeds without installing .xoml and .rules scriptmaps.</span></span>  
  
 <span data-ttu-id="690ec-139">Una vez instalado IIS, puede utilizar la herramienta WFServicesReg.exe con el modificador `/c` para instalar estas asignaciones de secuencias de comandos concretas.</span><span class="sxs-lookup"><span data-stu-id="690ec-139">After IIS is installed, you can use the WFServicesReg.exe tool with the `/c` switch to install these specific scriptmaps.</span></span>  
  
### <a name="repairing-the-scriptmaps"></a><span data-ttu-id="690ec-140">Reparar asignaciones de secuencias de comandos</span><span class="sxs-lookup"><span data-stu-id="690ec-140">Repairing the Scriptmaps</span></span>  
  
#### <a name="scriptmap-deleted-under-web-sites-node"></a><span data-ttu-id="690ec-141">Asignación de secuencias de comandos eliminada en el nodo de sitios web</span><span class="sxs-lookup"><span data-stu-id="690ec-141">Scriptmap deleted under Web Sites node</span></span>  
 <span data-ttu-id="690ec-142">En un equipo [!INCLUDE[ws2003](../../../includes/ws2003-md.md)], los archivos .xoml o .rules se eliminaron accidentalmente del nodo de sitios web.</span><span class="sxs-lookup"><span data-stu-id="690ec-142">On a [!INCLUDE[ws2003](../../../includes/ws2003-md.md)] machine, .xoml or .rules is accidentally deleted from the Web Sites node.</span></span> <span data-ttu-id="690ec-143">Esto puede repararse ejecutando la herramienta WFServicesReg.exe con el modificador `/c`.</span><span class="sxs-lookup"><span data-stu-id="690ec-143">This can be repaired by running the WFServicesReg.exe tool with the `/c` switch.</span></span>  
  
#### <a name="scriptmap-deleted-under-a-particular-web-site"></a><span data-ttu-id="690ec-144">Asignación de secuencias de comandos eliminada en un sitio web determinado</span><span class="sxs-lookup"><span data-stu-id="690ec-144">Scriptmap deleted under a particular Web site</span></span>  
 <span data-ttu-id="690ec-145">En un equipo [!INCLUDE[ws2003](../../../includes/ws2003-md.md)], .los archivos xoml o .rules se eliminaron accidentalmente de un sitio web determinado (por ejemplo, el sitio web predeterminado), en lugar de eliminarse del nodo de sitios web.</span><span class="sxs-lookup"><span data-stu-id="690ec-145">On a [!INCLUDE[ws2003](../../../includes/ws2003-md.md)] machine, .xoml or .rules is accidentally deleted from a particular Web site (for example, the Default Web Site) rather than from the Web Sites node.</span></span>  
  
 <span data-ttu-id="690ec-146">Para reparar los controladores eliminados de un sitio Web determinado, debe ejecutar "WFServicesReg. exe/r" para quitar los controladores de todos los sitios web y, a continuación, ejecutar "WFServicesReg. exe/c" para crear los controladores adecuados para todos los sitios Web.</span><span class="sxs-lookup"><span data-stu-id="690ec-146">To repair deleted handlers for a particular Web site, you should run "WFServicesReg.exe /r" to remove handlers from all Web sites, then run "WFServicesReg.exe /c" to create the appropriate handlers for all Web sites.</span></span>  
  
### <a name="configuring-handlers-after-switching-iis-mode"></a><span data-ttu-id="690ec-147">Configurar los controladores después de cambiar al modo de IIS</span><span class="sxs-lookup"><span data-stu-id="690ec-147">Configuring handlers after switching IIS mode</span></span>  
 <span data-ttu-id="690ec-148">Cuando IIS está en modo de configuración compartido y se instala [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)], la metabase de IIS se configura en una ubicación compartida.</span><span class="sxs-lookup"><span data-stu-id="690ec-148">When IIS is in shared configuration mode and [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)] is installed, the IIS metabase is configured under a shared location.</span></span> <span data-ttu-id="690ec-149">Si pasa IIS al modo de configuración no compartido, la metabase local no contendrá los controladores necesarios.</span><span class="sxs-lookup"><span data-stu-id="690ec-149">If you switch IIS to non-shared configuration mode, the local metabase will not contain the required handlers.</span></span> <span data-ttu-id="690ec-150">Para configurar la metabase local correctamente, puede importar la metabase compartida a local o ejecutar "WFServicesReg. exe/c", que configura la metabase local.</span><span class="sxs-lookup"><span data-stu-id="690ec-150">To configure the local metabase properly, you can either import the shared metabase to local, or run "WFServicesReg.exe /c", which configures the local metabase.</span></span>
