---
title: Storeadm.exe (herramienta de almacenamiento aislado)
ms.date: 03/30/2017
helpviewer_keywords:
- Storeadm.exe
- listing stores for current user
- Isolated Storage tool
- stores, current user
- removing stores
ms.assetid: b81202b8-d91d-4b23-9c53-4a112f74a44a
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 13640e508dafe28b53f4254656afe744b90a2eb2
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57491482"
---
# <a name="storeadmexe-isolated-storage-tool"></a><span data-ttu-id="d8e51-102">Storeadm.exe (herramienta de almacenamiento aislado)</span><span class="sxs-lookup"><span data-stu-id="d8e51-102">Storeadm.exe (Isolated Storage Tool)</span></span>
<span data-ttu-id="d8e51-103">La herramienta de almacenamiento aislado incluye o quita todos los almacenes existentes del usuario actual.</span><span class="sxs-lookup"><span data-stu-id="d8e51-103">The Isolated Storage tool lists or removes all existing stores for the current user.</span></span>  
  
 <span data-ttu-id="d8e51-104">Esta herramienta se instala automáticamente con Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="d8e51-104">This tool is automatically installed with Visual Studio.</span></span> <span data-ttu-id="d8e51-105">Para ejecutar la herramienta, use Símbolo del sistema para desarrolladores de Visual Studio (o Símbolo del sistema de Visual Studio en Windows 7).</span><span class="sxs-lookup"><span data-stu-id="d8e51-105">To run the tool, use the Developer Command Prompt for Visual Studio (or the Visual Studio Command Prompt in Windows 7).</span></span> <span data-ttu-id="d8e51-106">Para más información, consulte [Símbolos del sistema](../../../docs/framework/tools/developer-command-prompt-for-vs.md).</span><span class="sxs-lookup"><span data-stu-id="d8e51-106">For more information, see [Command Prompts](../../../docs/framework/tools/developer-command-prompt-for-vs.md).</span></span>  
  
 <span data-ttu-id="d8e51-107">En el símbolo del sistema, escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="d8e51-107">At the command prompt, type the following:</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d8e51-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d8e51-108">Syntax</span></span>  
  
```  
storeadm [/list][/machine][/remove][/roaming][/quiet]  
```  
  
## <a name="parameters"></a><span data-ttu-id="d8e51-109">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d8e51-109">Parameters</span></span>  
  
|<span data-ttu-id="d8e51-110">Opción</span><span class="sxs-lookup"><span data-stu-id="d8e51-110">Option</span></span>|<span data-ttu-id="d8e51-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="d8e51-111">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="d8e51-112">**/h**[**elp**]</span><span class="sxs-lookup"><span data-stu-id="d8e51-112">**/h**[**elp**]</span></span>|<span data-ttu-id="d8e51-113">Muestra las opciones y la sintaxis de los comandos para la herramienta.</span><span class="sxs-lookup"><span data-stu-id="d8e51-113">Displays command syntax and options for the tool.</span></span>|  
|<span data-ttu-id="d8e51-114">**/list**</span><span class="sxs-lookup"><span data-stu-id="d8e51-114">**/list**</span></span>|<span data-ttu-id="d8e51-115">Muestra todos los almacenes existentes del usuario actual.</span><span class="sxs-lookup"><span data-stu-id="d8e51-115">Displays all existing stores for the current user.</span></span> <span data-ttu-id="d8e51-116">Entre estos se incluyen los almacenes de todas las aplicaciones o ensamblados ejecutados por este usuario.</span><span class="sxs-lookup"><span data-stu-id="d8e51-116">This includes the stores for all applications or assemblies executed by this user.</span></span>|  
|<span data-ttu-id="d8e51-117">**/machine**</span><span class="sxs-lookup"><span data-stu-id="d8e51-117">**/machine**</span></span>|<span data-ttu-id="d8e51-118">Selecciona el almacén del equipo.</span><span class="sxs-lookup"><span data-stu-id="d8e51-118">Selects the machine store.</span></span> <span data-ttu-id="d8e51-119">Use esta opción con las opciones **/list** o **/remove** para especificar que la acción se debe aplicar al almacén del equipo.</span><span class="sxs-lookup"><span data-stu-id="d8e51-119">Use this option with the **/list** or **/remove** option to specify that the action should apply to the machine store.</span></span><br /><br /> <span data-ttu-id="d8e51-120">Se trata de una novedad de la versión 2.0 de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="d8e51-120">New in the .NET Framework 2.0</span></span>|  
|<span data-ttu-id="d8e51-121">**/quiet**</span><span class="sxs-lookup"><span data-stu-id="d8e51-121">**/quiet**</span></span>|<span data-ttu-id="d8e51-122">Especifica el modo silencioso; suprime los resultados que contienen información mostrándose únicamente mensajes de error.</span><span class="sxs-lookup"><span data-stu-id="d8e51-122">Specifies quiet mode; suppresses informational output so that only error messages appear.</span></span>|  
|<span data-ttu-id="d8e51-123">**/remove**</span><span class="sxs-lookup"><span data-stu-id="d8e51-123">**/remove**</span></span>|<span data-ttu-id="d8e51-124">Quita de forma permanente todos los almacenes existentes del usuario actual.</span><span class="sxs-lookup"><span data-stu-id="d8e51-124">Permanently removes all existing stores for the current user.</span></span>|  
|<span data-ttu-id="d8e51-125">**/roaming**</span><span class="sxs-lookup"><span data-stu-id="d8e51-125">**/roaming**</span></span>|<span data-ttu-id="d8e51-126">Selecciona el almacén móvil.</span><span class="sxs-lookup"><span data-stu-id="d8e51-126">Selects the roaming store.</span></span> <span data-ttu-id="d8e51-127">Use esta opción con las opciones **/list** o **/remove** para especificar que la acción se debe aplicar al almacén móvil.</span><span class="sxs-lookup"><span data-stu-id="d8e51-127">Use this option with the **/list** or **/remove** options to specify that the action should apply to the roaming store.</span></span>|  
|<span data-ttu-id="d8e51-128">**/?**</span><span class="sxs-lookup"><span data-stu-id="d8e51-128">**/?**</span></span>|<span data-ttu-id="d8e51-129">Muestra las opciones y la sintaxis de los comandos para la herramienta.</span><span class="sxs-lookup"><span data-stu-id="d8e51-129">Displays command syntax and options for the tool.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d8e51-130">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d8e51-130">Remarks</span></span>  
 <span data-ttu-id="d8e51-131">La ejecución de Storeadm.exe desde la línea de comandos sin especificar ninguna opción muestra la sintaxis y las opciones para la herramienta.</span><span class="sxs-lookup"><span data-stu-id="d8e51-131">Running Storeadm.exe from the command line without specifying any options displays the syntax and options for the tool.</span></span>  
  
 <span data-ttu-id="d8e51-132">Las opciones **/list** y **/remove** se usan normalmente de una en una, pero si se especifican dos o más opciones, se ejecutarán en el orden en que aparezcan en la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="d8e51-132">The **/list** and **/remove** options are typically used one at a time; however, if two or more options are specified they will be performed in the order in which they appear on the command line.</span></span>  
  
 <span data-ttu-id="d8e51-133">Las aplicaciones tienen la opción de guardar los datos en uno de los dos siguientes almacenes de usuario o en el almacén del equipo:</span><span class="sxs-lookup"><span data-stu-id="d8e51-133">Applications have a choice of saving to one of two stores for a user or to the machine store:</span></span>  
  
-   <span data-ttu-id="d8e51-134">El almacén local, que está situado en una ubicación donde se anula la posibilidad de movilidad (en Windows 2000 y posterior), aunque la movilidad de datos de usuario esté habilitada para el usuario.</span><span class="sxs-lookup"><span data-stu-id="d8e51-134">The local store exists in a location that is guaranteed not to roam (on Windows 2000 and later) even if user data roaming is enabled for the user.</span></span>  
  
-   <span data-ttu-id="d8e51-135">El almacén móvil, que se encuentra en una ubicación con posibilidad de movilidad, pero esta acción solo es posible si la movilidad está habilitada para el usuario mediante la administración de Windows NT.</span><span class="sxs-lookup"><span data-stu-id="d8e51-135">The roaming store exists in a location that is able to roam, but can only do so if roaming is enabled for the user via Windows NT administration.</span></span>  
  
-   <span data-ttu-id="d8e51-136">El almacén del equipo, que es común a todos los usuarios del equipo y se almacena bajo un directorio común en dicho equipo.</span><span class="sxs-lookup"><span data-stu-id="d8e51-136">The machine store is common to all users on a machine and is stored under a common directory on that machine.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="d8e51-137">El almacén del equipo es una novedad de la versión 2.0 de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="d8e51-137">The machine store is new in the .NET Framework version 2.0.</span></span>  
  
 <span data-ttu-id="d8e51-138">Si la movilidad está habilitada realmente para el usuario, no afecta a la administración de Storeadm.exe.</span><span class="sxs-lookup"><span data-stu-id="d8e51-138">Whether roaming is actually enabled for the user does not affect the administration of Storeadm.exe.</span></span> <span data-ttu-id="d8e51-139">Si la herramienta se ejecuta sin ninguna opción, todas las acciones se aplican al almacén local.</span><span class="sxs-lookup"><span data-stu-id="d8e51-139">Running the tool without any options applies all actions to the local store.</span></span> <span data-ttu-id="d8e51-140">Si la herramienta se ejecuta con la opción **/roaming**, todas las acciones se aplican al almacén que tiene posibilidad de movilidad.</span><span class="sxs-lookup"><span data-stu-id="d8e51-140">Running the tool with the **/roaming** option applies all actions to the store that is able to roam.</span></span> <span data-ttu-id="d8e51-141">Si la herramienta se ejecuta con la opción **/machine**, todas las acciones se aplican al almacén del equipo.</span><span class="sxs-lookup"><span data-stu-id="d8e51-141">Running the tool with the **/machine** option applies all actions to the machine store.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d8e51-142">Vea también</span><span class="sxs-lookup"><span data-stu-id="d8e51-142">See also</span></span>
- [<span data-ttu-id="d8e51-143">Herramientas</span><span class="sxs-lookup"><span data-stu-id="d8e51-143">Tools</span></span>](../../../docs/framework/tools/index.md)
- [<span data-ttu-id="d8e51-144">Almacenamiento aislado</span><span class="sxs-lookup"><span data-stu-id="d8e51-144">Isolated Storage</span></span>](../../../docs/standard/io/isolated-storage.md)
- [<span data-ttu-id="d8e51-145">Símbolos del sistema</span><span class="sxs-lookup"><span data-stu-id="d8e51-145">Command Prompts</span></span>](../../../docs/framework/tools/developer-command-prompt-for-vs.md)
