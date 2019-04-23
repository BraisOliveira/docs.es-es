---
title: Ngen.exe (Generador de imágenes nativas)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Native Image Generator
- images [.NET Framework], native
- side-by-side execution, native images
- assemblies [.NET Framework], native image
- Ngen.exe
- native image generation
- native image cache
- publisher policy applied for native images
- invalid images
- BypassNGenAttribute
- System.Runtime.BypassNGenAttribute
ms.assetid: 44bf97aa-a9a4-4eba-9a0d-cfaa6fc53a66
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e425394df0d04ffbb4cde41c83a9efe3c5b4abe0
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59481267"
---
# <a name="ngenexe-native-image-generator"></a><span data-ttu-id="e7d11-102">Ngen.exe (Generador de imágenes nativas)</span><span class="sxs-lookup"><span data-stu-id="e7d11-102">Ngen.exe (Native Image Generator)</span></span>

<span data-ttu-id="e7d11-103">El Generador de imágenes nativas (Ngen.exe) es una herramienta que mejora el rendimiento de las aplicaciones administradas.</span><span class="sxs-lookup"><span data-stu-id="e7d11-103">The Native Image Generator (Ngen.exe) is a tool that improves the performance of managed applications.</span></span> <span data-ttu-id="e7d11-104">Ngen.exe crea imágenes nativas, que son archivos que contienen código máquina compilado específicamente para un procesador, e instala estas imágenes en la memoria caché de imágenes nativas del equipo local.</span><span class="sxs-lookup"><span data-stu-id="e7d11-104">Ngen.exe creates native images, which are files containing compiled processor-specific machine code, and installs them into the native image cache on the local computer.</span></span> <span data-ttu-id="e7d11-105">El runtime puede usar imágenes nativas de la memoria caché en lugar de usar el compilador Just-In-Time (JIT) para compilar el ensamblado original.</span><span class="sxs-lookup"><span data-stu-id="e7d11-105">The runtime can use native images from the cache instead of using the just-in-time (JIT) compiler to compile the original assembly.</span></span>

<span data-ttu-id="e7d11-106">Cambios en Ngen.exe en [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="e7d11-106">Changes to Ngen.exe in the [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)]:</span></span>

- <span data-ttu-id="e7d11-107">Ahora, Ngen.exe compila los ensamblados con plena confianza y ya no se evalúa la directiva de seguridad de acceso del código (CAS).</span><span class="sxs-lookup"><span data-stu-id="e7d11-107">Ngen.exe now compiles assemblies with full trust, and code access security (CAS) policy is no longer evaluated.</span></span>

- <span data-ttu-id="e7d11-108">Las imágenes nativas que se generan con Ngen.exe ya no se pueden cargar en las aplicaciones que se están ejecutando con confianza parcial.</span><span class="sxs-lookup"><span data-stu-id="e7d11-108">Native images that are generated with Ngen.exe can no longer be loaded into applications that are running in partial trust.</span></span>

<span data-ttu-id="e7d11-109">Cambios en Ngen.exe en la versión 2.0 de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="e7d11-109">Changes to Ngen.exe in the .NET Framework version 2.0:</span></span>

- <span data-ttu-id="e7d11-110">Al instalar un ensamblado, también se instalan sus dependencias, lo que simplifica la sintaxis de Ngen.exe.</span><span class="sxs-lookup"><span data-stu-id="e7d11-110">Installing an assembly also installs its dependencies, simplifying the syntax of Ngen.exe.</span></span>

- <span data-ttu-id="e7d11-111">Ahora, las imágenes nativas se pueden compartir en los dominios de aplicación.</span><span class="sxs-lookup"><span data-stu-id="e7d11-111">Native images can now be shared across application domains.</span></span>

- <span data-ttu-id="e7d11-112">Una nueva acción, `update`, vuelve a crear las imágenes invalidadas.</span><span class="sxs-lookup"><span data-stu-id="e7d11-112">A new action, `update`, re-creates images that have been invalidated.</span></span>

- <span data-ttu-id="e7d11-113">Se pueden aplazar las acciones para que las ejecute un servicio que use el tiempo de inactividad del equipo para generar e instalar las imágenes.</span><span class="sxs-lookup"><span data-stu-id="e7d11-113">Actions can be deferred for execution by a service that uses idle time on the computer to generate and install images.</span></span>

- <span data-ttu-id="e7d11-114">Se han eliminado algunas de las causas que provocan la invalidación de imágenes.</span><span class="sxs-lookup"><span data-stu-id="e7d11-114">Some causes of image invalidation have been eliminated.</span></span>

<span data-ttu-id="e7d11-115">En Windows 8, consulte [Tarea de imagen nativa](#native-image-task).</span><span class="sxs-lookup"><span data-stu-id="e7d11-115">On Windows 8, see [Native Image Task](#native-image-task).</span></span>

<span data-ttu-id="e7d11-116">Para información adicional sobre el uso de Ngen.exe y el servicio de imágenes nativas, consulte [Servicio de imágenes nativas](#native-image-service).</span><span class="sxs-lookup"><span data-stu-id="e7d11-116">For additional information on using Ngen.exe and the native image service, see [Native Image Service](#native-image-service).</span></span>

> [!NOTE]
> <span data-ttu-id="e7d11-117">Puede encontrar información sobre la sintaxis de Ngen.exe para las versiones 1.0 y 1.1 de .NET Framework en [Sintaxis heredada del generador de imágenes nativas (Ngen.exe)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms165073(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="e7d11-117">Ngen.exe syntax for versions 1.0 and 1.1 of the .NET Framework can be found in [Native Image Generator (Ngen.exe) Legacy Syntax](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms165073(v=vs.100)).</span></span>

<span data-ttu-id="e7d11-118">Esta herramienta se instala automáticamente con Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="e7d11-118">This tool is automatically installed with Visual Studio.</span></span> <span data-ttu-id="e7d11-119">Para ejecutar la herramienta, use Símbolo del sistema para desarrolladores de Visual Studio (o Símbolo del sistema de Visual Studio en Windows 7).</span><span class="sxs-lookup"><span data-stu-id="e7d11-119">To run the tool, use the Developer Command Prompt for Visual Studio (or the Visual Studio Command Prompt in Windows 7).</span></span> <span data-ttu-id="e7d11-120">Para más información, consulte [Símbolos del sistema](../../../docs/framework/tools/developer-command-prompt-for-vs.md).</span><span class="sxs-lookup"><span data-stu-id="e7d11-120">For more information, see [Command Prompts](../../../docs/framework/tools/developer-command-prompt-for-vs.md).</span></span>

<span data-ttu-id="e7d11-121">En el símbolo del sistema, escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="e7d11-121">At the command prompt, type the following:</span></span>

## <a name="syntax"></a><span data-ttu-id="e7d11-122">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e7d11-122">Syntax</span></span>

```
ngen action [options]
```

```
ngen /? | /help
```

## <a name="actions"></a><span data-ttu-id="e7d11-123">Acciones</span><span class="sxs-lookup"><span data-stu-id="e7d11-123">Actions</span></span>

<span data-ttu-id="e7d11-124">En la tabla siguiente se muestra la sintaxis de cada acción (`action`).</span><span class="sxs-lookup"><span data-stu-id="e7d11-124">The following table shows the syntax of each `action`.</span></span> <span data-ttu-id="e7d11-125">Para ver descripciones de los distintos elementos de una `action`, consulte las tablas [Argumentos](#ArgumentTable), [Niveles de prioridad](#PriorityTable), [Escenarios](#ScenarioTable) y [Configuración](#ConfigTable).</span><span class="sxs-lookup"><span data-stu-id="e7d11-125">For descriptions of the individual parts of an `action`, see the [Arguments](#ArgumentTable), [Priority Levels](#PriorityTable), [Scenarios](#ScenarioTable), and [Config](#ConfigTable) tables.</span></span> <span data-ttu-id="e7d11-126">En la tabla [Opciones](#OptionTable) se describe el parámetro `options` y los modificadores de ayuda.</span><span class="sxs-lookup"><span data-stu-id="e7d11-126">The [Options](#OptionTable) table describes the `options` and the help switches.</span></span>

|<span data-ttu-id="e7d11-127">Acción</span><span class="sxs-lookup"><span data-stu-id="e7d11-127">Action</span></span>|<span data-ttu-id="e7d11-128">Descripción</span><span class="sxs-lookup"><span data-stu-id="e7d11-128">Description</span></span>|
|------------|-----------------|
|<span data-ttu-id="e7d11-129">`install` [`assemblyName` &#124; `assemblyPath`] [`scenarios`] [`config`] [`/queue`[`:`{`1`&#124;`2`&#124;`3`}]]</span><span class="sxs-lookup"><span data-stu-id="e7d11-129">`install` [`assemblyName` &#124; `assemblyPath`] [`scenarios`] [`config`] [`/queue`[`:`{`1`&#124;`2`&#124;`3`}]]</span></span>|<span data-ttu-id="e7d11-130">Genera imágenes nativas para un ensamblado y sus dependencias e instala las imágenes en la memoria caché de imágenes nativas.</span><span class="sxs-lookup"><span data-stu-id="e7d11-130">Generate native images for an assembly and its dependencies and install the images in the native image cache.</span></span><br /><br /> <span data-ttu-id="e7d11-131">Si se especifica `/queue`, la acción se pone en la cola del servicio de imágenes nativas.</span><span class="sxs-lookup"><span data-stu-id="e7d11-131">If `/queue` is specified, the action is queued for the native image service.</span></span> <span data-ttu-id="e7d11-132">La prioridad predeterminada es 3.</span><span class="sxs-lookup"><span data-stu-id="e7d11-132">The default priority is 3.</span></span> <span data-ttu-id="e7d11-133">Consulte la tabla [Niveles de prioridad](#PriorityTable).</span><span class="sxs-lookup"><span data-stu-id="e7d11-133">See the [Priority Levels](#PriorityTable) table.</span></span>|
|<span data-ttu-id="e7d11-134">`uninstall` [`assemblyName` &#124; `assemblyPath`] [`scenarios`] [`config`]</span><span class="sxs-lookup"><span data-stu-id="e7d11-134">`uninstall` [`assemblyName` &#124; `assemblyPath`] [`scenarios`] [`config`]</span></span>|<span data-ttu-id="e7d11-135">Elimina las imágenes nativas de un ensamblado y sus dependencias de la memoria caché de imágenes nativas.</span><span class="sxs-lookup"><span data-stu-id="e7d11-135">Delete the native images of an assembly and its dependencies from the native image cache.</span></span><br /><br /> <span data-ttu-id="e7d11-136">Para desinstalar una imagen y sus dependencias, use los mismos argumentos de la línea de comandos que usó para instalar la imagen.</span><span class="sxs-lookup"><span data-stu-id="e7d11-136">To uninstall a single image and its dependencies, use the same command-line arguments that were used to install the image.</span></span> <span data-ttu-id="e7d11-137">**Nota:**  A partir de [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], ya no se admite la acción `uninstall` \*.</span><span class="sxs-lookup"><span data-stu-id="e7d11-137">**Note:**  Starting with the [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], the action `uninstall` \* is no longer supported.</span></span>|
|<span data-ttu-id="e7d11-138">`update` [`/queue`]</span><span class="sxs-lookup"><span data-stu-id="e7d11-138">`update` [`/queue`]</span></span>|<span data-ttu-id="e7d11-139">Actualiza las imágenes nativas que han dejado de ser válidas.</span><span class="sxs-lookup"><span data-stu-id="e7d11-139">Update native images that have become invalid.</span></span><br /><br /> <span data-ttu-id="e7d11-140">Si se especifica `/queue`, las actualizaciones se ponen en la cola del servicio de imágenes nativas.</span><span class="sxs-lookup"><span data-stu-id="e7d11-140">If `/queue` is specified, the updates are queued for the native image service.</span></span> <span data-ttu-id="e7d11-141">Las actualizaciones siempre se programan con una prioridad de 3, por lo que se ejecutan cuando el equipo se encuentra inactivo.</span><span class="sxs-lookup"><span data-stu-id="e7d11-141">Updates are always scheduled at priority 3, so they run when the computer is idle.</span></span>|
|<span data-ttu-id="e7d11-142">`display` [`assemblyName` &#124; `assemblyPath`]</span><span class="sxs-lookup"><span data-stu-id="e7d11-142">`display` [`assemblyName` &#124; `assemblyPath`]</span></span>|<span data-ttu-id="e7d11-143">Muestra el estado de las imágenes nativas para un ensamblado y sus dependencias.</span><span class="sxs-lookup"><span data-stu-id="e7d11-143">Display the state of the native images for an assembly and its dependencies.</span></span><br /><br /> <span data-ttu-id="e7d11-144">Si no se proporciona ningún argumento, se muestra todo el contenido de la memoria caché de imágenes nativas.</span><span class="sxs-lookup"><span data-stu-id="e7d11-144">If no argument is supplied, everything in the native image cache is displayed.</span></span>|
|<span data-ttu-id="e7d11-145">`executeQueuedItems` [<code>1&#124;2&#124;3</code>]</span><span class="sxs-lookup"><span data-stu-id="e7d11-145">`executeQueuedItems` [<code>1&#124;2&#124;3</code>]</span></span><br /><br /> <span data-ttu-id="e7d11-146">o bien</span><span class="sxs-lookup"><span data-stu-id="e7d11-146">-or-</span></span><br /><br /> <span data-ttu-id="e7d11-147">`eqi` [1&#124;2&#124;3]</span><span class="sxs-lookup"><span data-stu-id="e7d11-147">`eqi` [1&#124;2&#124;3]</span></span>|<span data-ttu-id="e7d11-148">Ejecuta los trabajos de compilación en cola.</span><span class="sxs-lookup"><span data-stu-id="e7d11-148">Execute queued compilation jobs.</span></span><br /><br /> <span data-ttu-id="e7d11-149">Si se especifica una prioridad, se ejecutan los trabajos de compilación con una prioridad mayor o igual a la especificada.</span><span class="sxs-lookup"><span data-stu-id="e7d11-149">If a priority is specified, compilation jobs with greater or equal priority are executed.</span></span> <span data-ttu-id="e7d11-150">Si no se especifica ninguna prioridad, se ejecutan todos los trabajos de compilación en cola.</span><span class="sxs-lookup"><span data-stu-id="e7d11-150">If no priority is specified, all queued compilation jobs are executed.</span></span>|
|<span data-ttu-id="e7d11-151">`queue` {`pause` &#124; `continue` &#124; `status`}</span><span class="sxs-lookup"><span data-stu-id="e7d11-151">`queue` {`pause` &#124; `continue` &#124; `status`}</span></span>|<span data-ttu-id="e7d11-152">Pausa el servicio de imágenes nativas, permite la reanudación del servicio en pausa o consulta el estado del servicio.</span><span class="sxs-lookup"><span data-stu-id="e7d11-152">Pause the native image service, allow the paused service to continue, or query the status of the service.</span></span>|

<a name="ArgumentTable"></a>

## <a name="arguments"></a><span data-ttu-id="e7d11-153">Argumentos</span><span class="sxs-lookup"><span data-stu-id="e7d11-153">Arguments</span></span>

|<span data-ttu-id="e7d11-154">Argumento</span><span class="sxs-lookup"><span data-stu-id="e7d11-154">Argument</span></span>|<span data-ttu-id="e7d11-155">Descripción</span><span class="sxs-lookup"><span data-stu-id="e7d11-155">Description</span></span>|
|--------------|-----------------|
|`assemblyName`|<span data-ttu-id="e7d11-156">El nombre para mostrar completo del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="e7d11-156">The full display name of the assembly.</span></span> <span data-ttu-id="e7d11-157">Por ejemplo: `"myAssembly, Version=2.0.0.0, Culture=neutral, PublicKeyToken=0038abc9deabfle5"`.</span><span class="sxs-lookup"><span data-stu-id="e7d11-157">For example, `"myAssembly, Version=2.0.0.0, Culture=neutral, PublicKeyToken=0038abc9deabfle5"`.</span></span> <span data-ttu-id="e7d11-158">**Nota:**  Puede proporcionar un nombre de ensamblado parcial, como `myAssembly`, para las acciones `display` y `uninstall`.</span><span class="sxs-lookup"><span data-stu-id="e7d11-158">**Note:**  You can supply a partial assembly name, such as `myAssembly`, for the `display` and `uninstall` actions.</span></span> <br /><br /> <span data-ttu-id="e7d11-159">Solo se puede especificar un ensamblado por cada línea de comandos de Ngen.exe.</span><span class="sxs-lookup"><span data-stu-id="e7d11-159">Only one assembly can be specified per Ngen.exe command line.</span></span>|
|`assemblyPath`|<span data-ttu-id="e7d11-160">La ruta de acceso explícita del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="e7d11-160">The explicit path of the assembly.</span></span> <span data-ttu-id="e7d11-161">Se puede especificar una ruta de acceso completa o relativa.</span><span class="sxs-lookup"><span data-stu-id="e7d11-161">You can specify a full or relative path.</span></span><br /><br /> <span data-ttu-id="e7d11-162">Si se especifica un nombre de archivo sin una ruta de acceso, el ensamblado deberá estar ubicado en el directorio actual.</span><span class="sxs-lookup"><span data-stu-id="e7d11-162">If you specify a file name without a path, the assembly must be located in the current directory.</span></span><br /><br /> <span data-ttu-id="e7d11-163">Solo se puede especificar un ensamblado por cada línea de comandos de Ngen.exe.</span><span class="sxs-lookup"><span data-stu-id="e7d11-163">Only one assembly can be specified per Ngen.exe command line.</span></span>|

<a name="PriorityTable"></a>

## <a name="priority-levels"></a><span data-ttu-id="e7d11-164">Niveles de prioridad</span><span class="sxs-lookup"><span data-stu-id="e7d11-164">Priority Levels</span></span>

|<span data-ttu-id="e7d11-165">Prioridad</span><span class="sxs-lookup"><span data-stu-id="e7d11-165">Priority</span></span>|<span data-ttu-id="e7d11-166">Descripción</span><span class="sxs-lookup"><span data-stu-id="e7d11-166">Description</span></span>|
|--------------|-----------------|
|`1`|<span data-ttu-id="e7d11-167">Las imágenes nativas se generan e instalan de forma inmediata, sin esperar al tiempo de inactividad.</span><span class="sxs-lookup"><span data-stu-id="e7d11-167">Native images are generated and installed immediately, without waiting for idle time.</span></span>|
|`2`|<span data-ttu-id="e7d11-168">Las imágenes nativas se generan e instalan sin esperar al tiempo de inactividad, pero después de que se hayan completado todas las acciones de prioridad 1 (y sus dependencias).</span><span class="sxs-lookup"><span data-stu-id="e7d11-168">Native images are generated and installed without waiting for idle time, but after all priority 1 actions (and their dependencies) have completed.</span></span>|
|`3`|<span data-ttu-id="e7d11-169">Las imágenes nativas se instalan cuando el servicio de imágenes nativas detecta que el equipo se encuentra inactivo.</span><span class="sxs-lookup"><span data-stu-id="e7d11-169">Native images are installed when the native image service detects that the computer is idle.</span></span> <span data-ttu-id="e7d11-170">Consulte [Servicio de imágenes nativas](#native-image-service).</span><span class="sxs-lookup"><span data-stu-id="e7d11-170">See [Native Image Service](#native-image-service).</span></span>|

<a name="ScenarioTable"></a>

## <a name="scenarios"></a><span data-ttu-id="e7d11-171">Escenarios</span><span class="sxs-lookup"><span data-stu-id="e7d11-171">Scenarios</span></span>

|<span data-ttu-id="e7d11-172">Escenario</span><span class="sxs-lookup"><span data-stu-id="e7d11-172">Scenario</span></span>|<span data-ttu-id="e7d11-173">Descripción</span><span class="sxs-lookup"><span data-stu-id="e7d11-173">Description</span></span>|
|--------------|-----------------|
|`/Debug`|<span data-ttu-id="e7d11-174">Genera imágenes nativas que pueden usarse con un depurador.</span><span class="sxs-lookup"><span data-stu-id="e7d11-174">Generate native images that can be used under a debugger.</span></span>|
|`/Profile`|<span data-ttu-id="e7d11-175">Genera imágenes nativas que pueden usarse con un generador de perfiles.</span><span class="sxs-lookup"><span data-stu-id="e7d11-175">Generate native images that can be used under a profiler.</span></span>|
|`/NoDependencies`|<span data-ttu-id="e7d11-176">Genera el número mínimo de imágenes nativas requerido por las opciones de escenario especificadas.</span><span class="sxs-lookup"><span data-stu-id="e7d11-176">Generate the minimum number of native images required by the specified scenario options.</span></span>|

<a name="ConfigTable"></a>

## <a name="config"></a><span data-ttu-id="e7d11-177">Configuración</span><span class="sxs-lookup"><span data-stu-id="e7d11-177">Config</span></span>

|<span data-ttu-id="e7d11-178">Configuración</span><span class="sxs-lookup"><span data-stu-id="e7d11-178">Configuration</span></span>|<span data-ttu-id="e7d11-179">Descripción</span><span class="sxs-lookup"><span data-stu-id="e7d11-179">Description</span></span>|
|-------------------|-----------------|
|<span data-ttu-id="e7d11-180">`/ExeConfig:` `exePath`</span><span class="sxs-lookup"><span data-stu-id="e7d11-180">`/ExeConfig:` `exePath`</span></span>|<span data-ttu-id="e7d11-181">Usa la configuración del ensamblado ejecutable especificado.</span><span class="sxs-lookup"><span data-stu-id="e7d11-181">Use the configuration of the specified executable assembly.</span></span><br /><br /> <span data-ttu-id="e7d11-182">Ngen.exe tiene que tomar las mismas decisiones que el cargador al enlazarse a las dependencias.</span><span class="sxs-lookup"><span data-stu-id="e7d11-182">Ngen.exe needs to make the same decisions as the loader when binding to dependencies.</span></span> <span data-ttu-id="e7d11-183">Cuando se carga un componente compartido en tiempo de ejecución usando el método <xref:System.Reflection.Assembly.Load%2A>, el archivo de configuración de la aplicación determina las dependencias que se cargan para el componente compartido como, por ejemplo, la versión que se carga de una dependencia.</span><span class="sxs-lookup"><span data-stu-id="e7d11-183">When a shared component is loaded at run time, using the <xref:System.Reflection.Assembly.Load%2A> method, the application's configuration file determines the dependencies that are loaded for the shared component — for example, the version of a dependency that is loaded.</span></span> <span data-ttu-id="e7d11-184">El modificador `/ExeConfig` proporciona a Ngen.exe orientación sobre las dependencias que se cargarán en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="e7d11-184">The `/ExeConfig` switch gives Ngen.exe guidance on which dependencies would be loaded at run time.</span></span>|
|<span data-ttu-id="e7d11-185">`/AppBase:` `directoryPath`</span><span class="sxs-lookup"><span data-stu-id="e7d11-185">`/AppBase:` `directoryPath`</span></span>|<span data-ttu-id="e7d11-186">Al buscar dependencias, usa el directorio especificado como base de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="e7d11-186">When locating dependencies, use the specified directory as the application base.</span></span>|

<a name="OptionTable"></a>

## <a name="options"></a><span data-ttu-id="e7d11-187">Opciones</span><span class="sxs-lookup"><span data-stu-id="e7d11-187">Options</span></span>

|<span data-ttu-id="e7d11-188">Opción</span><span class="sxs-lookup"><span data-stu-id="e7d11-188">Option</span></span>|<span data-ttu-id="e7d11-189">Descripción</span><span class="sxs-lookup"><span data-stu-id="e7d11-189">Description</span></span>|
|------------|-----------------|
|`/nologo`|<span data-ttu-id="e7d11-190">Suprime la presentación de la pancarta de inicio de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="e7d11-190">Suppress the Microsoft startup banner display.</span></span>|
|`/silent`|<span data-ttu-id="e7d11-191">Suprime la presentación de mensajes de operaciones correctas.</span><span class="sxs-lookup"><span data-stu-id="e7d11-191">Suppress the display of success messages.</span></span>|
|`/verbose`|<span data-ttu-id="e7d11-192">Muestra información detallada para la depuración.</span><span class="sxs-lookup"><span data-stu-id="e7d11-192">Display detailed information for debugging.</span></span> <span data-ttu-id="e7d11-193">**Nota:**  Debido a las limitaciones de los sistemas operativos, esta opción no muestra tanta información adicional en Windows 98 y Windows Millennium Edition.</span><span class="sxs-lookup"><span data-stu-id="e7d11-193">**Note:**  Due to operating system limitations, this option does not display as much additional information on Windows 98 and Windows Millennium Edition.</span></span>|
|<span data-ttu-id="e7d11-194">`/help`, `/?`</span><span class="sxs-lookup"><span data-stu-id="e7d11-194">`/help`, `/?`</span></span>|<span data-ttu-id="e7d11-195">Muestra las opciones y la sintaxis de los comandos de la versión actual.</span><span class="sxs-lookup"><span data-stu-id="e7d11-195">Display command syntax and options for the current release.</span></span>|

## <a name="remarks"></a><span data-ttu-id="e7d11-196">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e7d11-196">Remarks</span></span>

<span data-ttu-id="e7d11-197">Para ejecutar Ngen.exe, es necesario disponer de privilegios administrativos.</span><span class="sxs-lookup"><span data-stu-id="e7d11-197">To run Ngen.exe, you must have administrative privileges.</span></span>

> [!CAUTION]
> <span data-ttu-id="e7d11-198">No ejecute Ngen.exe en ensamblados que no son de plena confianza.</span><span class="sxs-lookup"><span data-stu-id="e7d11-198">Do not run Ngen.exe on assemblies that are not fully trusted.</span></span> <span data-ttu-id="e7d11-199">A partir de [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], Ngen.exe compila los ensamblados con plena confianza y ya no se evalúa la directiva de seguridad de acceso del código (CAS).</span><span class="sxs-lookup"><span data-stu-id="e7d11-199">Starting with the [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], Ngen.exe compiles assemblies with full trust, and code access security (CAS) policy is no longer evaluated.</span></span>

<span data-ttu-id="e7d11-200">A partir de [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)], las imágenes nativas que se generan con Ngen.exe ya no se pueden cargar en las aplicaciones que se están ejecutando con confianza parcial.</span><span class="sxs-lookup"><span data-stu-id="e7d11-200">Starting with the [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)], the native images that are generated with Ngen.exe can no longer be loaded into applications that are running in partial trust.</span></span> <span data-ttu-id="e7d11-201">En su lugar, se invoca el compilador Just-In-Time (JIT).</span><span class="sxs-lookup"><span data-stu-id="e7d11-201">Instead, the just-in-time (JIT) compiler is invoked.</span></span>

<span data-ttu-id="e7d11-202">Ngen.exe genera imágenes nativas para el ensamblado que el argumento `assemblyname` especifica para la acción `install` y todas sus dependencias.</span><span class="sxs-lookup"><span data-stu-id="e7d11-202">Ngen.exe generates native images for the assembly specified by the `assemblyname` argument to the `install` action and all its dependencies.</span></span> <span data-ttu-id="e7d11-203">Las dependencias se determinan a partir de las referencias del manifiesto del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="e7d11-203">Dependencies are determined from references in the assembly manifest.</span></span> <span data-ttu-id="e7d11-204">El único escenario en el que es necesario instalar una dependencia por separado es aquel donde la aplicación carga la dependencia usando la reflexión, por ejemplo, llamando al método <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="e7d11-204">The only scenario in which you need to install a dependency separately is when the application loads it using reflection, for example by calling the <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType> method.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e7d11-205">No use el método <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=nameWithType> con imágenes nativas.</span><span class="sxs-lookup"><span data-stu-id="e7d11-205">Do not use the <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=nameWithType> method with native images.</span></span> <span data-ttu-id="e7d11-206">Una imagen cargada con este método no la podrán usar otros ensamblados en el contexto de ejecución.</span><span class="sxs-lookup"><span data-stu-id="e7d11-206">An image loaded with this method cannot be used by other assemblies in the execution context.</span></span>

<span data-ttu-id="e7d11-207">Ngen.exe mantiene un recuento de las dependencias.</span><span class="sxs-lookup"><span data-stu-id="e7d11-207">Ngen.exe maintains a count on dependencies.</span></span> <span data-ttu-id="e7d11-208">Por ejemplo, suponga que `MyAssembly.exe` y `YourAssembly.exe` están instalados en la memoria caché de imágenes nativas y que ambos tienen referencias a `OurDependency.dll`.</span><span class="sxs-lookup"><span data-stu-id="e7d11-208">For example, suppose `MyAssembly.exe` and `YourAssembly.exe` are both installed in the native image cache, and both have references to `OurDependency.dll`.</span></span> <span data-ttu-id="e7d11-209">Si se desinstala `MyAssembly.exe`, no se desinstala `OurDependency.dll`.</span><span class="sxs-lookup"><span data-stu-id="e7d11-209">If `MyAssembly.exe` is uninstalled, `OurDependency.dll` is not uninstalled.</span></span> <span data-ttu-id="e7d11-210">Solo se quita cuando también se desinstala `YourAssembly.exe`.</span><span class="sxs-lookup"><span data-stu-id="e7d11-210">It is only removed when `YourAssembly.exe` is also uninstalled.</span></span>

<span data-ttu-id="e7d11-211">Si va a generar una imagen nativa para un ensamblado en la caché global de ensamblados, especifique su nombre para mostrar.</span><span class="sxs-lookup"><span data-stu-id="e7d11-211">If you are generating a native image for an assembly in the global assembly cache, specify its display name.</span></span> <span data-ttu-id="e7d11-212">Vea <xref:System.Reflection.Assembly.FullName%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="e7d11-212">See <xref:System.Reflection.Assembly.FullName%2A?displayProperty=nameWithType>.</span></span>

<span data-ttu-id="e7d11-213">Las imágenes nativas generadas por Ngen.exe se pueden compartir en los dominios de aplicación.</span><span class="sxs-lookup"><span data-stu-id="e7d11-213">The native images that Ngen.exe generates can be shared across application domains.</span></span> <span data-ttu-id="e7d11-214">Esto significa que Ngen.exe puede usarse en escenarios de aplicación que requieren el uso compartido de los ensamblados entre los dominios de aplicación.</span><span class="sxs-lookup"><span data-stu-id="e7d11-214">This means you can use Ngen.exe in application scenarios that require assemblies to be shared across application domains.</span></span> <span data-ttu-id="e7d11-215">Para especificar una neutralidad de dominios:</span><span class="sxs-lookup"><span data-stu-id="e7d11-215">To specify domain neutrality:</span></span>

- <span data-ttu-id="e7d11-216">Aplique el atributo <xref:System.LoaderOptimizationAttribute> a la aplicación.</span><span class="sxs-lookup"><span data-stu-id="e7d11-216">Apply the <xref:System.LoaderOptimizationAttribute> attribute to your application.</span></span>

- <span data-ttu-id="e7d11-217">Establezca la propiedad <xref:System.AppDomainSetup.LoaderOptimization%2A?displayProperty=nameWithType> al crear la información de instalación de un nuevo dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="e7d11-217">Set the <xref:System.AppDomainSetup.LoaderOptimization%2A?displayProperty=nameWithType> property when you create setup information for a new application domain.</span></span>

<span data-ttu-id="e7d11-218">Use siempre código con dominio neutro al cargar el mismo ensamblado en varios dominios de aplicación.</span><span class="sxs-lookup"><span data-stu-id="e7d11-218">Always use domain-neutral code when loading the same assembly into multiple application domains.</span></span> <span data-ttu-id="e7d11-219">Si una imagen nativa se carga en un dominio de aplicación no compartido después de haberse cargado en un dominio compartido, no se podrá usar.</span><span class="sxs-lookup"><span data-stu-id="e7d11-219">If a native image is loaded into a nonshared application domain after having been loaded into a shared domain, it cannot be used.</span></span>

> [!NOTE]
> <span data-ttu-id="e7d11-220">No se puede descargar código con dominio neutro y el rendimiento puede resultar algo más lento, especialmente al obtener acceso a miembros estáticos.</span><span class="sxs-lookup"><span data-stu-id="e7d11-220">Domain-neutral code cannot be unloaded, and performance may be slightly slower, particularly when accessing static members.</span></span>

<span data-ttu-id="e7d11-221">En esta sección Comentarios:</span><span class="sxs-lookup"><span data-stu-id="e7d11-221">In this Remarks section:</span></span>

- [<span data-ttu-id="e7d11-222">Generación de imágenes para distintos escenarios</span><span class="sxs-lookup"><span data-stu-id="e7d11-222">Generating images for different scenarios</span></span>](#Scenarios)

- [<span data-ttu-id="e7d11-223">Determinación de cuándo se deben usar imágenes nativas</span><span class="sxs-lookup"><span data-stu-id="e7d11-223">Determining when to Use native images</span></span>](#WhenToUse)

  - [<span data-ttu-id="e7d11-224">Uso de memoria mejorado</span><span class="sxs-lookup"><span data-stu-id="e7d11-224">Improved memory use</span></span>](#Memory)

  - [<span data-ttu-id="e7d11-225">Inicio de aplicación más rápido</span><span class="sxs-lookup"><span data-stu-id="e7d11-225">Faster application startup</span></span>](#Startup)

  - [<span data-ttu-id="e7d11-226">Resumen de las consideraciones de uso</span><span class="sxs-lookup"><span data-stu-id="e7d11-226">Summary of usage considerations</span></span>](#UsageSummary)

- [<span data-ttu-id="e7d11-227">Importancia de las direcciones base de los ensamblados</span><span class="sxs-lookup"><span data-stu-id="e7d11-227">Importance of assembly base addresses</span></span>](#BaseAddresses)

- [<span data-ttu-id="e7d11-228">Enlace fuerte</span><span class="sxs-lookup"><span data-stu-id="e7d11-228">Hard binding</span></span>](#HardBinding)

  - [<span data-ttu-id="e7d11-229">Especificación de una sugerencia de enlace para una dependencia</span><span class="sxs-lookup"><span data-stu-id="e7d11-229">Specifying a binding hint for a dependency</span></span>](#DependencyHint)

  - [<span data-ttu-id="e7d11-230">Especificación de una sugerencia de enlace predeterminado para un ensamblado</span><span class="sxs-lookup"><span data-stu-id="e7d11-230">Specifying a default binding hint for an assembly</span></span>](#AssemblyHint)

- [<span data-ttu-id="e7d11-231">Procesamiento diferido</span><span class="sxs-lookup"><span data-stu-id="e7d11-231">Deferred processing</span></span>](#Deferred)

- [<span data-ttu-id="e7d11-232">Imágenes nativas y compilación JIT</span><span class="sxs-lookup"><span data-stu-id="e7d11-232">Native images and JIT compilation</span></span>](#JITCompilation)

  - [<span data-ttu-id="e7d11-233">Imágenes no válidas</span><span class="sxs-lookup"><span data-stu-id="e7d11-233">Invalid images</span></span>](#InvalidImages)

- [<span data-ttu-id="e7d11-234">Solución de problemas</span><span class="sxs-lookup"><span data-stu-id="e7d11-234">Troubleshooting</span></span>](#Troubleshooting)

  - [<span data-ttu-id="e7d11-235">Visor de registro de enlaces de ensamblados</span><span class="sxs-lookup"><span data-stu-id="e7d11-235">Assembly Binding Log Viewer</span></span>](#Fusion)

  - [<span data-ttu-id="e7d11-236">Asistente para la depuración administrada JITCompilationStart</span><span class="sxs-lookup"><span data-stu-id="e7d11-236">The JITCompilationStart managed debugging assistant</span></span>](#MDA)

  - [<span data-ttu-id="e7d11-237">Exclusión de la generación de imágenes nativas</span><span class="sxs-lookup"><span data-stu-id="e7d11-237">Opting out of native image generation</span></span>](#OptOut)

<a name="Scenarios"></a>

## <a name="generating-images-for-----different-scenarios"></a><span data-ttu-id="e7d11-238">Generación de imágenes para distintos escenarios</span><span class="sxs-lookup"><span data-stu-id="e7d11-238">Generating images for     different scenarios</span></span>

<span data-ttu-id="e7d11-239">Una vez generada la imagen nativa de un ensamblado, el runtime intenta localizar y usar automáticamente la imagen nativa cada vez que se ejecuta el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="e7d11-239">After you have generated a native image for an assembly, the runtime automatically attempts to locate and use this native   image each time it runs the assembly.</span></span> <span data-ttu-id="e7d11-240">Se pueden generar varias imágenes, en función de los escenarios de uso.</span><span class="sxs-lookup"><span data-stu-id="e7d11-240">Multiple images can be generated, depending on usage scenarios.</span></span>

<span data-ttu-id="e7d11-241">Por ejemplo, si ejecuta un ensamblado en un escenario de depuración o de generación de perfiles, el runtime buscará una imagen nativa generada con las opciones `/Debug` o `/Profile`.</span><span class="sxs-lookup"><span data-stu-id="e7d11-241">For example, if you run an assembly in a debugging or profiling scenario, the runtime looks for a native image that was generated with the `/Debug` or `/Profile` options.</span></span> <span data-ttu-id="e7d11-242">Si no encuentra una imagen nativa coincidente, el runtime usa la compilación JIT estándar.</span><span class="sxs-lookup"><span data-stu-id="e7d11-242">If it is unable to find a matching native image, the runtime reverts to standard JIT compilation.</span></span> <span data-ttu-id="e7d11-243">La única forma de depurar imágenes nativas es mediante la creación de una imagen nativa con la opción `/Debug`.</span><span class="sxs-lookup"><span data-stu-id="e7d11-243">The only way to debug native images is to create a native image with the `/Debug` option.</span></span>

<span data-ttu-id="e7d11-244">La acción `uninstall` también reconoce los escenarios, por lo que se pueden desinstalar todos los escenarios o solo los escenarios seleccionados.</span><span class="sxs-lookup"><span data-stu-id="e7d11-244">The `uninstall` action also recognize scenarios, so you can uninstall all scenarios or only selected scenarios.</span></span>

<a name="WhenToUse"></a>

## <a name="determining-when-to-use-native-images"></a><span data-ttu-id="e7d11-245">Determinación de cuándo se deben usar imágenes nativas</span><span class="sxs-lookup"><span data-stu-id="e7d11-245">Determining when to Use native images</span></span>

<span data-ttu-id="e7d11-246">Las imágenes nativas pueden ofrecer mejoras de rendimiento en dos áreas: uso de memoria mejorado y tiempo de inicio reducido.</span><span class="sxs-lookup"><span data-stu-id="e7d11-246">Native images can provide performance improvements in two areas: improved memory use and reduced startup time.</span></span>

> [!NOTE]
> <span data-ttu-id="e7d11-247">El rendimiento de las imágenes nativas depende de una serie de factores que dificultan el análisis, como los patrones de acceso a código y a datos, el número de llamadas realizadas a través de los límites de los módulos y el número de dependencias que ya se han cargado en otras aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="e7d11-247">Performance of native images depends on a number of factors that make analysis difficult, such as code and data access patterns, how many calls are made across module boundaries, and how many dependencies have already been loaded by other applications.</span></span> <span data-ttu-id="e7d11-248">La única forma de determinar si las imágenes nativas benefician a la aplicación es mediante la realización de mediciones del rendimiento meticulosas en los escenarios de implementación clave.</span><span class="sxs-lookup"><span data-stu-id="e7d11-248">The only way to determine whether native images benefit your application is by careful performance measurements in your key deployment scenarios.</span></span>

<a name="Memory"></a>

### <a name="improved-memory-use"></a><span data-ttu-id="e7d11-249">Uso de memoria mejorado</span><span class="sxs-lookup"><span data-stu-id="e7d11-249">Improved memory use</span></span>

<span data-ttu-id="e7d11-250">Las imágenes nativas pueden mejorar significativamente el uso de memoria cuando el código se comparte entre los procesos.</span><span class="sxs-lookup"><span data-stu-id="e7d11-250">Native images can significantly improve memory use when code is shared between processes.</span></span> <span data-ttu-id="e7d11-251">Las imágenes nativas son archivos PE de Windows, de modo que una única copia de un archivo .dll pueden compartirla varios procesos; en cambio, el código nativo generado por el compilador JIT se almacena en la memoria privada y no se puede compartir.</span><span class="sxs-lookup"><span data-stu-id="e7d11-251">Native images are Windows PE files, so a single copy of a .dll file can be shared by multiple processes; by contrast, native code produced by the JIT compiler is stored in private memory and cannot be shared.</span></span>

<span data-ttu-id="e7d11-252">Las aplicaciones que se ejecutan en Terminal Services también pueden beneficiarse de las páginas de código compartido.</span><span class="sxs-lookup"><span data-stu-id="e7d11-252">Applications that are run under terminal services can also benefit from shared code pages.</span></span>

<span data-ttu-id="e7d11-253">Además, al no cargar el compilador JIT, se reserva una cantidad de memoria fija para cada instancia de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="e7d11-253">In addition, not loading the JIT compiler saves a fixed amount of memory for each application instance.</span></span>

<a name="Startup"></a>

### <a name="faster-application-startup"></a><span data-ttu-id="e7d11-254">Inicio de aplicación más rápido</span><span class="sxs-lookup"><span data-stu-id="e7d11-254">Faster application startup</span></span>

<span data-ttu-id="e7d11-255">Precompilar los ensamblados con Ngen.exe puede reducir el tiempo de inicio de algunas aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="e7d11-255">Precompiling assemblies with Ngen.exe can improve the startup time for some applications.</span></span> <span data-ttu-id="e7d11-256">En general, pueden obtenerse mejoras cuando las aplicaciones comparten ensamblados de componentes porque, una vez iniciada la primera aplicación, los componentes compartidos ya estarán cargados para las siguientes aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="e7d11-256">In general, gains can be made when applications share component assemblies because after the first application has been started the shared components are already loaded for subsequent applications.</span></span> <span data-ttu-id="e7d11-257">Un inicio en frío, en el que todos los ensamblados de una aplicación deben cargarse desde el disco duro, no se beneficia tanto de las imágenes nativas porque predomina el tiempo de acceso al disco duro.</span><span class="sxs-lookup"><span data-stu-id="e7d11-257">Cold startup, in which all the assemblies in an application must be loaded from the hard disk, does not benefit as much from native images because the hard disk access time predominates.</span></span>

<span data-ttu-id="e7d11-258">El enlace fuerte puede afectar al tiempo de inicio, ya que todas las imágenes con enlaces fuertes al ensamblado de aplicación principal deben cargarse al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="e7d11-258">Hard binding can affect startup time, because all images that are hard bound to the main application assembly must be loaded at the same time.</span></span>

> [!NOTE]
> <span data-ttu-id="e7d11-259">Antes de [!INCLUDE[net_v35SP1_long](../../../includes/net-v35sp1-long-md.md)], debía poner componentes con nombre seguro en la caché global de ensamblados porque el cargador efectúa una validación adicional de los ensamblados con nombre seguro que no se encuentran en la caché global de ensamblados, lo que anula cualquier mejora del tiempo de inicio obtenida gracias al uso de imágenes nativas.</span><span class="sxs-lookup"><span data-stu-id="e7d11-259">Before the [!INCLUDE[net_v35SP1_long](../../../includes/net-v35sp1-long-md.md)], you should put shared, strong-named components in the global assembly cache, because the loader performs extra validation on strong-named assemblies that are not in the global assembly cache, effectively eliminating any improvement in startup time gained by using native images.</span></span> <span data-ttu-id="e7d11-260">Las optimizaciones introducidas en [!INCLUDE[net_v35SP1_short](../../../includes/net-v35sp1-short-md.md)] quitaron la validación adicional.</span><span class="sxs-lookup"><span data-stu-id="e7d11-260">Optimizations that were introduced in the [!INCLUDE[net_v35SP1_short](../../../includes/net-v35sp1-short-md.md)] removed the extra validation.</span></span>

<a name="UsageSummary"></a>

### <a name="summary-of-usage-considerations"></a><span data-ttu-id="e7d11-261">Resumen de las consideraciones de uso</span><span class="sxs-lookup"><span data-stu-id="e7d11-261">Summary of usage considerations</span></span>

<span data-ttu-id="e7d11-262">Las siguientes consideraciones generales y consideraciones sobre la aplicación pueden ayudarle a decidir si merece la pena asumir el esfuerzo de evaluar las imágenes nativas de la aplicación:</span><span class="sxs-lookup"><span data-stu-id="e7d11-262">The following general considerations and application considerations may assist you in deciding whether to undertake the effort of evaluating native images for your application:</span></span>

- <span data-ttu-id="e7d11-263">Las imágenes nativas se cargan más rápido que MSIL, ya que eliminan la necesidad de ejecutar muchas actividades en el inicio, como la compilación JIT y la comprobación de la seguridad de tipos.</span><span class="sxs-lookup"><span data-stu-id="e7d11-263">Native images load faster than MSIL because they eliminate the need for many startup activities, such as JIT compilation and type-safety verification.</span></span>

- <span data-ttu-id="e7d11-264">Las imágenes nativas requieren un espacio de trabajo inicial más pequeño, ya que el compilador JIT no es necesario.</span><span class="sxs-lookup"><span data-stu-id="e7d11-264">Native images require a smaller initial working set because there is no need for the JIT compiler.</span></span>

- <span data-ttu-id="e7d11-265">Las imágenes nativas permiten un uso compartido del código entre los procesos.</span><span class="sxs-lookup"><span data-stu-id="e7d11-265">Native images enable code sharing between processes.</span></span>

- <span data-ttu-id="e7d11-266">Las imágenes nativas requieren más espacio en el disco duro que los ensamblados MSIL y pueden tardar bastante tiempo en generarse.</span><span class="sxs-lookup"><span data-stu-id="e7d11-266">Native images require more hard disk space than MSIL assemblies and may require considerable time to generate.</span></span>

- <span data-ttu-id="e7d11-267">Las imágenes nativas necesitan mantenimiento.</span><span class="sxs-lookup"><span data-stu-id="e7d11-267">Native images must be maintained.</span></span>

  - <span data-ttu-id="e7d11-268">Cuando se realiza el mantenimiento del ensamblado original o de una de sus dependencias, es necesario volver a generar las imágenes.</span><span class="sxs-lookup"><span data-stu-id="e7d11-268">Images need to be regenerated when the original assembly or one of its dependencies is serviced.</span></span>

  - <span data-ttu-id="e7d11-269">Un solo ensamblado puede necesitar varias imágenes nativas para su uso en aplicaciones o escenarios diferentes.</span><span class="sxs-lookup"><span data-stu-id="e7d11-269">A single assembly may need multiple native images for use in different applications or different scenarios.</span></span> <span data-ttu-id="e7d11-270">Por ejemplo, la información de configuración de dos aplicaciones podría producir distintas decisiones de enlace para el mismo ensamblado dependiente.</span><span class="sxs-lookup"><span data-stu-id="e7d11-270">For example, the configuration information in two applications might result in different binding decisions for the same dependent assembly.</span></span>

  - <span data-ttu-id="e7d11-271">La generación de imágenes nativas solo la puede llevar a cabo un administrador; es decir, deberá realizarse desde una cuenta de Windows del grupo de administradores.</span><span class="sxs-lookup"><span data-stu-id="e7d11-271">Native images must be generated by an administrator; that is, from a Windows account in the Administrators group.</span></span>

<span data-ttu-id="e7d11-272">Además de estas consideraciones generales, hay que tener en cuenta la naturaleza de la aplicación a la hora de determinar si las imágenes nativas pueden suponer una mejora en el rendimiento:</span><span class="sxs-lookup"><span data-stu-id="e7d11-272">In addition to these general considerations, the nature of your application must be considered when determining whether native images might provide a performance benefit:</span></span>

- <span data-ttu-id="e7d11-273">Si la aplicación se ejecuta en un entorno que usa muchos componentes compartidos, las imágenes nativas permiten un uso compartido de los componentes por parte de varios procesos.</span><span class="sxs-lookup"><span data-stu-id="e7d11-273">If your application runs in an environment that uses many shared components, native images allow the components to be shared by multiple processes.</span></span>

- <span data-ttu-id="e7d11-274">Si la aplicación usa varios dominios de aplicación, las imágenes nativas permiten un uso compartido de las páginas de códigos entre los distintos dominios.</span><span class="sxs-lookup"><span data-stu-id="e7d11-274">If your application uses multiple application domains, native images allow code pages to be shared across domains.</span></span>

    > [!NOTE]
    > <span data-ttu-id="e7d11-275">En las versiones 1.0 y 1.1 de .NET Framework, los dominios de aplicación no pueden compartir las imágenes nativas.</span><span class="sxs-lookup"><span data-stu-id="e7d11-275">In the .NET Framework versions 1.0 and 1.1, native images cannot be shared across application domains.</span></span> <span data-ttu-id="e7d11-276">Este no es el caso en la versión 2.0 o posterior.</span><span class="sxs-lookup"><span data-stu-id="e7d11-276">This is not the case in version 2.0 or later.</span></span>

- <span data-ttu-id="e7d11-277">Si la aplicación va a ejecutarse en Terminal Server, las imágenes nativas permiten un uso compartido de las páginas de código.</span><span class="sxs-lookup"><span data-stu-id="e7d11-277">If your application will be run under Terminal Server, native images allow sharing of code pages.</span></span>

- <span data-ttu-id="e7d11-278">En general, las aplicaciones de gran tamaño se benefician de la compilación de imágenes nativas.</span><span class="sxs-lookup"><span data-stu-id="e7d11-278">Large applications generally benefit from compilation to native images.</span></span> <span data-ttu-id="e7d11-279">En cambio, las aplicaciones pequeñas no suelen beneficiarse.</span><span class="sxs-lookup"><span data-stu-id="e7d11-279">Small applications generally do not benefit.</span></span>

- <span data-ttu-id="e7d11-280">En las aplicaciones de ejecución prolongada, la compilación JIT en tiempo de ejecución ofrece un rendimiento ligeramente superior al de las imágenes nativas.</span><span class="sxs-lookup"><span data-stu-id="e7d11-280">For long-running applications, run-time JIT compilation performs slightly better than native images.</span></span> <span data-ttu-id="e7d11-281">(El enlace fuerte puede mitigar hasta cierto punto esta diferencia de rendimiento).</span><span class="sxs-lookup"><span data-stu-id="e7d11-281">(Hard binding can mitigate this performance difference to some degree.)</span></span>

<a name="BaseAddresses"></a>

## <a name="importance-of-assembly-base-addresses"></a><span data-ttu-id="e7d11-282">Importancia de las direcciones base de los ensamblados</span><span class="sxs-lookup"><span data-stu-id="e7d11-282">Importance of assembly base addresses</span></span>

<span data-ttu-id="e7d11-283">Dado que las imágenes nativas son archivos PE de Windows, están sujetas a las mismas cuestiones de cambio de ubicación que otros archivos ejecutables.</span><span class="sxs-lookup"><span data-stu-id="e7d11-283">Because native images are Windows PE files, they are subject to the same rebasing issues as other executable files.</span></span> <span data-ttu-id="e7d11-284">La repercusión que las reubicaciones tienen en el rendimiento es aún mayor si se usan enlaces fuertes.</span><span class="sxs-lookup"><span data-stu-id="e7d11-284">The performance cost of relocation is even more pronounced if hard binding is employed.</span></span>

<span data-ttu-id="e7d11-285">Para establecer la dirección base de una imagen nativa, use la opción adecuada del compilador para establecer la dirección base del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="e7d11-285">To set the base address for a native image, use the appropriate option of your compiler to set the base address for the assembly.</span></span> <span data-ttu-id="e7d11-286">Ngen.exe usa esta dirección base para la imagen nativa.</span><span class="sxs-lookup"><span data-stu-id="e7d11-286">Ngen.exe uses this base address for the native image.</span></span>

> [!NOTE]
> <span data-ttu-id="e7d11-287">Las imágenes nativas son de mayor tamaño que los ensamblados administrados a partir de los que se crean.</span><span class="sxs-lookup"><span data-stu-id="e7d11-287">Native images are larger than the managed assemblies from which they were created.</span></span> <span data-ttu-id="e7d11-288">Las direcciones base deben calcularse para permitir estos tamaños mayores.</span><span class="sxs-lookup"><span data-stu-id="e7d11-288">Base addresses must be calculated to allow for these larger sizes.</span></span>

<span data-ttu-id="e7d11-289">Para ver la dirección base preferida de una imagen nativa, puede usar una herramienta como dumpbin.exe.</span><span class="sxs-lookup"><span data-stu-id="e7d11-289">You can use a tool such as dumpbin.exe to view the preferred base address of a native image.</span></span>

<a name="HardBinding"></a>

## <a name="hard-binding"></a><span data-ttu-id="e7d11-290">Enlace fuerte</span><span class="sxs-lookup"><span data-stu-id="e7d11-290">Hard binding</span></span>

<span data-ttu-id="e7d11-291">El enlace fuerte aumenta el rendimiento y reduce el tamaño del espacio de trabajo de las imágenes nativas.</span><span class="sxs-lookup"><span data-stu-id="e7d11-291">Hard binding increases throughput and reduces working set size for native images.</span></span> <span data-ttu-id="e7d11-292">El inconveniente del enlace fuerte es que todas las imágenes con enlaces fuertes a un ensamblado deben cargarse al cargar el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="e7d11-292">The disadvantage of hard binding is that all the images that are hard bound to an assembly must be loaded when the assembly is loaded.</span></span> <span data-ttu-id="e7d11-293">Esto puede aumentar significativamente el tiempo de inicio de una aplicación de gran tamaño.</span><span class="sxs-lookup"><span data-stu-id="e7d11-293">This can significantly increase startup time for a large application.</span></span>

<span data-ttu-id="e7d11-294">El enlace fuerte es adecuado para las dependencias que se cargan en todos los escenarios de la aplicación en los que el rendimiento es un factor crítico.</span><span class="sxs-lookup"><span data-stu-id="e7d11-294">Hard binding is appropriate for dependencies that are loaded in all your application's performance-critical scenarios.</span></span> <span data-ttu-id="e7d11-295">Al igual que con cualquier otro aspecto del uso de imágenes nativas, la realización de mediciones del rendimiento meticulosas constituye la única forma de determinar si el enlace fuerte mejora el rendimiento de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="e7d11-295">As with any aspect of native image use, careful performance measurements are the only way to determine whether hard binding improves your application's performance.</span></span>

<span data-ttu-id="e7d11-296">Los atributos <xref:System.Runtime.CompilerServices.DependencyAttribute> y <xref:System.Runtime.CompilerServices.DefaultDependencyAttribute> permiten suministrar sugerencias de enlace fuerte a Ngen.exe.</span><span class="sxs-lookup"><span data-stu-id="e7d11-296">The <xref:System.Runtime.CompilerServices.DependencyAttribute> and <xref:System.Runtime.CompilerServices.DefaultDependencyAttribute> attributes allow you to provide hard binding hints to Ngen.exe.</span></span>

> [!NOTE]
> <span data-ttu-id="e7d11-297">Estos atributos son sugerencias para Ngen.exe, no comandos.</span><span class="sxs-lookup"><span data-stu-id="e7d11-297">These attributes are hints to Ngen.exe, not commands.</span></span> <span data-ttu-id="e7d11-298">El uso de estos atributos no garantiza el enlace fuerte.</span><span class="sxs-lookup"><span data-stu-id="e7d11-298">Using them does not guarantee hard binding.</span></span> <span data-ttu-id="e7d11-299">El significado de estos atributos puede cambiar en futuras versiones.</span><span class="sxs-lookup"><span data-stu-id="e7d11-299">The meaning of these attributes may change in future releases.</span></span>

<a name="DependencyHint"></a>

### <a name="specifying-a-binding-hint-for-a-dependency"></a><span data-ttu-id="e7d11-300">Especificación de una sugerencia de enlace para una dependencia</span><span class="sxs-lookup"><span data-stu-id="e7d11-300">Specifying a binding hint for a dependency</span></span>

<span data-ttu-id="e7d11-301">Aplique <xref:System.Runtime.CompilerServices.DependencyAttribute> a un ensamblado para indicar la probabilidad de que se cargue una dependencia especificada.</span><span class="sxs-lookup"><span data-stu-id="e7d11-301">Apply the <xref:System.Runtime.CompilerServices.DependencyAttribute> to an assembly to indicate the likelihood that a specified dependency will be loaded.</span></span> <span data-ttu-id="e7d11-302"><xref:System.Runtime.CompilerServices.LoadHint.Always?displayProperty=nameWithType> indica que el enlace fuerte es adecuado, <xref:System.Runtime.CompilerServices.LoadHint.Default> indica que debe usarse el valor predeterminado de la dependencia y <xref:System.Runtime.CompilerServices.LoadHint.Sometimes> indica que el enlace fuerte no es adecuado.</span><span class="sxs-lookup"><span data-stu-id="e7d11-302"><xref:System.Runtime.CompilerServices.LoadHint.Always?displayProperty=nameWithType> indicates that hard binding is appropriate, <xref:System.Runtime.CompilerServices.LoadHint.Default> indicates that the default for the dependency should be used, and <xref:System.Runtime.CompilerServices.LoadHint.Sometimes> indicates that hard binding is not appropriate.</span></span>

<span data-ttu-id="e7d11-303">En el siguiente código se muestran los atributos de un ensamblado que tiene dos dependencias.</span><span class="sxs-lookup"><span data-stu-id="e7d11-303">The following code shows the attributes for an assembly that has two dependencies.</span></span> <span data-ttu-id="e7d11-304">La primera dependencia (Assembly1) es una candidata adecuada para el enlace fuerte, pero la segunda (Assembly2) no lo es.</span><span class="sxs-lookup"><span data-stu-id="e7d11-304">The first dependency (Assembly1) is an appropriate candidate for hard binding, and the second (Assembly2) is not.</span></span>

```vb
Imports System.Runtime.CompilerServices
<Assembly:DependencyAttribute("Assembly1", LoadHint.Always)>
<Assembly:DependencyAttribute("Assembly2", LoadHint.Sometimes)>
```

```csharp
using System.Runtime.CompilerServices;
[assembly:DependencyAttribute("Assembly1", LoadHint.Always)]
[assembly:DependencyAttribute("Assembly2", LoadHint.Sometimes)]
```

```cpp
using namespace System::Runtime::CompilerServices;
[assembly:DependencyAttribute("Assembly1", LoadHint.Always)];
[assembly:DependencyAttribute("Assembly2", LoadHint.Sometimes)];
```

<span data-ttu-id="e7d11-305">El nombre de ensamblado no incluye la extensión de nombre de archivo.</span><span class="sxs-lookup"><span data-stu-id="e7d11-305">The assembly name does not include the file name extension.</span></span> <span data-ttu-id="e7d11-306">Pueden usarse nombres para mostrar.</span><span class="sxs-lookup"><span data-stu-id="e7d11-306">Display names can be used.</span></span>

<a name="AssemblyHint"></a>

### <a name="specifying-a-default-binding-hint-for-an-assembly"></a><span data-ttu-id="e7d11-307">Especificación de una sugerencia de enlace predeterminado para un ensamblado</span><span class="sxs-lookup"><span data-stu-id="e7d11-307">Specifying a default binding hint for an assembly</span></span>

<span data-ttu-id="e7d11-308">Las sugerencias de enlace predeterminado solo son necesarias para los ensamblados que cualquier aplicación con una dependencia sobre los mismos vaya a usar inmediatamente y con frecuencia.</span><span class="sxs-lookup"><span data-stu-id="e7d11-308">Default binding hints are only needed for assemblies that will be used immediately and frequently by any application that has a dependency on them.</span></span> <span data-ttu-id="e7d11-309">Aplique el atributo <xref:System.Runtime.CompilerServices.DefaultDependencyAttribute> con <xref:System.Runtime.CompilerServices.LoadHint.Always?displayProperty=nameWithType> a dichos ensamblados para especificar que debe usarse un enlace fuerte.</span><span class="sxs-lookup"><span data-stu-id="e7d11-309">Apply the <xref:System.Runtime.CompilerServices.DefaultDependencyAttribute> with <xref:System.Runtime.CompilerServices.LoadHint.Always?displayProperty=nameWithType> to such assemblies to specify that hard binding should be used.</span></span>

> [!NOTE]
> <span data-ttu-id="e7d11-310">No hay ningún motivo para aplicar el atributo <xref:System.Runtime.CompilerServices.DefaultDependencyAttribute> a los ensamblados .dll que no pertenezcan a esta categoría, porque el hecho de aplicar el atributo con cualquier valor distinto de <xref:System.Runtime.CompilerServices.LoadHint.Always?displayProperty=nameWithType> produce el mismo efecto que no aplicar el atributo.</span><span class="sxs-lookup"><span data-stu-id="e7d11-310">There is no reason to apply <xref:System.Runtime.CompilerServices.DefaultDependencyAttribute> to .dll assemblies that do not fall into this category, because applying the attribute with any value other than <xref:System.Runtime.CompilerServices.LoadHint.Always?displayProperty=nameWithType> has the same effect as not applying the attribute at all.</span></span>

<span data-ttu-id="e7d11-311">Microsoft usa el atributo <xref:System.Runtime.CompilerServices.DefaultDependencyAttribute> para especificar que el enlace fuerte es el valor predeterminado para un pequeño número de ensamblados de .NET Framework, como mscorlib.dll.</span><span class="sxs-lookup"><span data-stu-id="e7d11-311">Microsoft uses the <xref:System.Runtime.CompilerServices.DefaultDependencyAttribute> to specify that hard binding is the default for a very small number of assemblies in the .NET Framework, such as mscorlib.dll.</span></span>

<a name="Deferred"></a>

## <a name="deferred-processing"></a><span data-ttu-id="e7d11-312">Procesamiento diferido</span><span class="sxs-lookup"><span data-stu-id="e7d11-312">Deferred processing</span></span>

<span data-ttu-id="e7d11-313">La generación de imágenes nativas para una aplicación de gran tamaño puede llevar bastante tiempo.</span><span class="sxs-lookup"><span data-stu-id="e7d11-313">Generation of native images for a very large application can take considerable time.</span></span> <span data-ttu-id="e7d11-314">Del mismo modo, los cambios realizados en un componente compartido o en la configuración del equipo pueden requerir la actualización de muchas imágenes nativas.</span><span class="sxs-lookup"><span data-stu-id="e7d11-314">Similarly, changes to a shared component or changes to computer settings might require many native images to be updated.</span></span> <span data-ttu-id="e7d11-315">Las acciones `install` y `update` disponen de una opción `/queue` que pone en cola la operación para su ejecución diferida por parte del servicio de imágenes nativas.</span><span class="sxs-lookup"><span data-stu-id="e7d11-315">The `install` and `update` actions have a `/queue` option that queues the operation for deferred execution by the native image service.</span></span> <span data-ttu-id="e7d11-316">Además, Ngen.exe dispone de las acciones `queue` y `executeQueuedItems`, que proporcionan algo de control sobre el servicio.</span><span class="sxs-lookup"><span data-stu-id="e7d11-316">In addition, Ngen.exe has `queue` and `executeQueuedItems` actions that provide some control over the service.</span></span> <span data-ttu-id="e7d11-317">Para más información, consulte [Servicio de imágenes nativas](#native-image-service).</span><span class="sxs-lookup"><span data-stu-id="e7d11-317">For more information, see [Native Image Service](#native-image-service).</span></span>

<a name="JITCompilation"></a>

## <a name="native-images-and-jit-compilation"></a><span data-ttu-id="e7d11-318">Imágenes nativas y compilación JIT</span><span class="sxs-lookup"><span data-stu-id="e7d11-318">Native images and JIT compilation</span></span>

<span data-ttu-id="e7d11-319">Si Ngen.exe encuentra en un ensamblado métodos que no puede generar, los excluye de la imagen nativa.</span><span class="sxs-lookup"><span data-stu-id="e7d11-319">If Ngen.exe encounters any methods in an assembly that it cannot generate, it excludes them from the native image.</span></span> <span data-ttu-id="e7d11-320">Cuando el runtime ejecuta el ensamblado, usa la compilación JIT para los métodos que no se han incluido en la imagen nativa.</span><span class="sxs-lookup"><span data-stu-id="e7d11-320">When the runtime executes this assembly, it reverts to JIT compilation for the methods that were not included in the native image.</span></span>

<span data-ttu-id="e7d11-321">Además, si se ha actualizado el ensamblado o la imagen se ha invalidado por cualquier motivo, no se usan imágenes nativas.</span><span class="sxs-lookup"><span data-stu-id="e7d11-321">In addition, native images are not used if the assembly has been upgraded, or if the image has been invalidated for any reason.</span></span>

<a name="InvalidImages"></a>

### <a name="invalid-images"></a><span data-ttu-id="e7d11-322">Imágenes no válidas</span><span class="sxs-lookup"><span data-stu-id="e7d11-322">Invalid images</span></span>

<span data-ttu-id="e7d11-323">Cuando se usa Ngen.exe para crear una imagen nativa de un ensamblado, el resultado depende de las opciones especificadas en la línea de comandos y de determinadas opciones de configuración del equipo.</span><span class="sxs-lookup"><span data-stu-id="e7d11-323">When you use Ngen.exe to create a native image of an assembly, the output depends upon the command-line options that you specify and certain settings on your computer.</span></span> <span data-ttu-id="e7d11-324">Entre estas opciones de configuración, se incluyen las siguientes:</span><span class="sxs-lookup"><span data-stu-id="e7d11-324">These settings include the following:</span></span>

- <span data-ttu-id="e7d11-325">La versión de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="e7d11-325">The version of the .NET Framework.</span></span>

- <span data-ttu-id="e7d11-326">La versión del sistema operativo, si se cambia de la familia Windows 9x a la familia Windows NT.</span><span class="sxs-lookup"><span data-stu-id="e7d11-326">The version of the operating system, if the change is from the Windows 9x family to the Windows NT family.</span></span>

- <span data-ttu-id="e7d11-327">La identidad exacta del ensamblado (la recompilación cambia la identidad).</span><span class="sxs-lookup"><span data-stu-id="e7d11-327">The exact identity of the assembly (recompilation changes identity).</span></span>

- <span data-ttu-id="e7d11-328">La identidad exacta de todos los ensamblados a los que hace referencia el ensamblado (la recompilación cambia la identidad).</span><span class="sxs-lookup"><span data-stu-id="e7d11-328">The exact identity of all assemblies that the assembly references (recompilation changes identity).</span></span>

- <span data-ttu-id="e7d11-329">Factores de seguridad.</span><span class="sxs-lookup"><span data-stu-id="e7d11-329">Security factors.</span></span>

<span data-ttu-id="e7d11-330">Ngen.exe registra esta información cuando genera una imagen nativa.</span><span class="sxs-lookup"><span data-stu-id="e7d11-330">Ngen.exe records this information when it generates a native image.</span></span> <span data-ttu-id="e7d11-331">Al ejecutar un ensamblado, el runtime busca la imagen nativa generada con las opciones y los valores de configuración que coinciden con el entorno actual del equipo.</span><span class="sxs-lookup"><span data-stu-id="e7d11-331">When you execute an assembly, the runtime looks for the native image generated with options and settings that match the computer's current environment.</span></span> <span data-ttu-id="e7d11-332">El runtime usa la compilación JIT del ensamblado si no encuentra una imagen nativa coincidente.</span><span class="sxs-lookup"><span data-stu-id="e7d11-332">The runtime reverts to JIT compilation of an assembly if it cannot find a matching native image.</span></span> <span data-ttu-id="e7d11-333">Si se realizan los siguientes cambios en la configuración y el entorno de un equipo, las imágenes nativas dejarán de ser válidas:</span><span class="sxs-lookup"><span data-stu-id="e7d11-333">The following changes to a computer's settings and environment cause native images to become invalid:</span></span>

- <span data-ttu-id="e7d11-334">La versión de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="e7d11-334">The version of the .NET Framework.</span></span>

     <span data-ttu-id="e7d11-335">Si se aplica una actualización a .NET Framework, todas las imágenes nativas que se hayan creado mediante Ngen.exe dejarán de ser válidas.</span><span class="sxs-lookup"><span data-stu-id="e7d11-335">If you apply an update to the .NET Framework, all native images that you have created using Ngen.exe become invalid.</span></span> <span data-ttu-id="e7d11-336">Por esta razón, todas las actualizaciones de .NET Framework ejecutan el comando `Ngen Update`, para garantizar que se vuelven a generar todas las imágenes nativas.</span><span class="sxs-lookup"><span data-stu-id="e7d11-336">For this reason, all updates of the .NET Framework execute the `Ngen Update` command, to ensure that all native images are regenerated.</span></span> <span data-ttu-id="e7d11-337">.NET Framework crea nuevas imágenes nativas de forma automática para las bibliotecas de .NET Framework que instala.</span><span class="sxs-lookup"><span data-stu-id="e7d11-337">The .NET Framework automatically creates new native images for the .NET Framework libraries that it installs.</span></span>

- <span data-ttu-id="e7d11-338">La versión del sistema operativo, si se cambia de la familia Windows 9x a la familia Windows NT.</span><span class="sxs-lookup"><span data-stu-id="e7d11-338">The version of the operating system, if the change is from the Windows 9x family to the Windows NT family.</span></span>

     <span data-ttu-id="e7d11-339">Por ejemplo, si la versión del sistema operativo que se ejecuta en un equipo cambia de Windows 98 a Windows XP, todas las imágenes nativas almacenadas en la memoria caché de imágenes nativas dejan de ser válidas.</span><span class="sxs-lookup"><span data-stu-id="e7d11-339">For example, if the version of the operating system running on a computer changes from Windows 98 to Windows XP, all native images stored in the native image cache become invalid.</span></span> <span data-ttu-id="e7d11-340">Sin embargo, si el sistema operativo cambia de Windows 2000 a Windows XP, las imágenes siguen siendo válidas.</span><span class="sxs-lookup"><span data-stu-id="e7d11-340">However, if the operating system changes from Windows 2000 to Windows XP, the images are not invalidated.</span></span>

- <span data-ttu-id="e7d11-341">La identidad exacta del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="e7d11-341">The exact identity of the assembly.</span></span>

     <span data-ttu-id="e7d11-342">Si vuelve a compilar un ensamblado, su imagen nativa correspondiente deja de ser válida.</span><span class="sxs-lookup"><span data-stu-id="e7d11-342">If you recompile an assembly, the assembly's corresponding native image becomes invalid.</span></span>

- <span data-ttu-id="e7d11-343">La identidad exacta de todos los ensamblados a los que hace referencia el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="e7d11-343">The exact identity of any assemblies the assembly references.</span></span>

     <span data-ttu-id="e7d11-344">Si actualiza un ensamblado administrado, todas las imágenes nativas que, directa o indirectamente, dependen de ese ensamblado dejan de ser válidas y deben volver a generarse.</span><span class="sxs-lookup"><span data-stu-id="e7d11-344">If you update a managed assembly, all native images that directly or indirectly depend on that assembly become invalid and need to be regenerated.</span></span> <span data-ttu-id="e7d11-345">Esto se aplica tanto a las referencias ordinarias como a las dependencias con enlaces fuertes.</span><span class="sxs-lookup"><span data-stu-id="e7d11-345">This includes both ordinary references and hard-bound dependencies.</span></span> <span data-ttu-id="e7d11-346">Cuando se aplica una actualización de software, el programa de instalación debe ejecutar un comando `Ngen Update` para garantizar que se vuelven a generar todas las imágenes nativas dependientes.</span><span class="sxs-lookup"><span data-stu-id="e7d11-346">Whenever a software update is applied, the installation program should execute an `Ngen Update` command to ensure that all dependent native images are regenerated.</span></span>

- <span data-ttu-id="e7d11-347">Factores de seguridad.</span><span class="sxs-lookup"><span data-stu-id="e7d11-347">Security factors.</span></span>

     <span data-ttu-id="e7d11-348">Si se modifica la directiva de seguridad del equipo para restringir los permisos previamente concedidos a un ensamblado, la imagen nativa compilada con anterioridad para dicho ensamblado puede dejar de ser válida.</span><span class="sxs-lookup"><span data-stu-id="e7d11-348">Changing machine security policy to restrict permissions previously granted to an assembly can cause a previously compiled native image for that assembly to become invalid.</span></span>

     <span data-ttu-id="e7d11-349">Para información detallada sobre cómo Common Language Runtime administra la seguridad de acceso del código y sobre cómo usar los permisos, consulte [Seguridad de acceso del código](../../../docs/framework/misc/code-access-security.md).</span><span class="sxs-lookup"><span data-stu-id="e7d11-349">For detailed information about how the common language runtime administers code access security and how to use permissions, see [Code Access Security](../../../docs/framework/misc/code-access-security.md).</span></span>

<a name="Troubleshooting"></a>

## <a name="troubleshooting"></a><span data-ttu-id="e7d11-350">Solución de problemas</span><span class="sxs-lookup"><span data-stu-id="e7d11-350">Troubleshooting</span></span>

<span data-ttu-id="e7d11-351">Los temas de solución de problemas siguientes permiten ver cuáles son las imágenes nativas que la aplicación usa y cuáles no puede usar, determinar cuándo el compilador JIT comienza a compilar un método y muestra cómo excluir la compilación de imágenes nativas de métodos específicos.</span><span class="sxs-lookup"><span data-stu-id="e7d11-351">The following troubleshooting topics allow you to see which native images are being used and which cannot be used by your application, to determine when the JIT compiler starts to compile a method, and shows how to opt out of native image compilation of specified methods.</span></span>

<a name="Fusion"></a>

### <a name="assembly-binding-log-viewer"></a><span data-ttu-id="e7d11-352">Visor de registro de enlaces de ensamblados</span><span class="sxs-lookup"><span data-stu-id="e7d11-352">Assembly Binding Log Viewer</span></span>

<span data-ttu-id="e7d11-353">Para confirmar que la aplicación está usando imágenes nativas, puede usar [Fuslogvw.exe (Visor de registro de enlaces de ensamblados)](../../../docs/framework/tools/fuslogvw-exe-assembly-binding-log-viewer.md).</span><span class="sxs-lookup"><span data-stu-id="e7d11-353">To confirm that native images are being used by your application, you can use the [Fuslogvw.exe (Assembly Binding Log Viewer)](../../../docs/framework/tools/fuslogvw-exe-assembly-binding-log-viewer.md).</span></span> <span data-ttu-id="e7d11-354">Seleccione **Imágenes nativas** en el cuadro **Categorías de registro** de la ventana del visor de registro de enlaces.</span><span class="sxs-lookup"><span data-stu-id="e7d11-354">Select **Native Images** in the **Log Categories** box on the binding log viewer window.</span></span> <span data-ttu-id="e7d11-355">Fuslogvw.exe proporciona información sobre el motivo por el que se ha rechazado una imagen nativa.</span><span class="sxs-lookup"><span data-stu-id="e7d11-355">Fuslogvw.exe provides information about why a native image was rejected.</span></span>

<a name="MDA"></a>

### <a name="the-jitcompilationstart-managed-debugging-assistant"></a><span data-ttu-id="e7d11-356">Asistente para la depuración administrada JITCompilationStart</span><span class="sxs-lookup"><span data-stu-id="e7d11-356">The JITCompilationStart managed debugging assistant</span></span>

<span data-ttu-id="e7d11-357">Puede usar el Asistente para la depuración administrada (MDA) [jitCompilationStart](../../../docs/framework/debug-trace-profile/jitcompilationstart-mda.md) para determinar el momento en el que el compilador JIT empieza a compilar una función.</span><span class="sxs-lookup"><span data-stu-id="e7d11-357">You can use the [jitCompilationStart](../../../docs/framework/debug-trace-profile/jitcompilationstart-mda.md) managed debugging assistant (MDA) to determine when the JIT compiler starts to compile a function.</span></span>

<a name="OptOut"></a>

### <a name="opting-out-of-native-image-generation"></a><span data-ttu-id="e7d11-358">Exclusión de la generación de imágenes nativas</span><span class="sxs-lookup"><span data-stu-id="e7d11-358">Opting out of native image generation</span></span>

<span data-ttu-id="e7d11-359">En algunos casos, NGen.exe puede tener problemas para generar una imagen nativa para un método específico, o bien es posible que prefiera que el método se compile en JIT en lugar de compilarlo en una imagen nativa.</span><span class="sxs-lookup"><span data-stu-id="e7d11-359">In some cases, NGen.exe may have difficulty generating a native image for a specific method, or you may prefer that the method be JIT compiled rather then compiled to a native image.</span></span> <span data-ttu-id="e7d11-360">En este caso, puede usar el atributo `System.Runtime.BypassNGenAttribute` para evitar que NGen.exe genere una imagen nativa para un método concreto.</span><span class="sxs-lookup"><span data-stu-id="e7d11-360">In this case, you can use the `System.Runtime.BypassNGenAttribute` attribute to prevent NGen.exe from generating a native image for a particular method.</span></span> <span data-ttu-id="e7d11-361">El atributo se debe aplicar individualmente a cada método cuyo código no desea que se incluya en la imagen nativa.</span><span class="sxs-lookup"><span data-stu-id="e7d11-361">The attribute must be applied individually to each method whose code you do not want to include in the native image.</span></span> <span data-ttu-id="e7d11-362">NGen.exe reconoce el atributo y no genera código en la imagen nativa para el método correspondiente.</span><span class="sxs-lookup"><span data-stu-id="e7d11-362">NGen.exe recognizes the attribute and does not generate code in the native image for the corresponding method.</span></span>

<span data-ttu-id="e7d11-363">Pero tenga en cuenta que `BypassNGenAttribute` no está definido como tipo en la biblioteca de clases .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="e7d11-363">Note, however, that `BypassNGenAttribute` is not defined as a type in the .NET Framework Class Library.</span></span> <span data-ttu-id="e7d11-364">Para usar el atributo en el código, primero debe definirlo de la manera siguiente:</span><span class="sxs-lookup"><span data-stu-id="e7d11-364">In order to consume the attribute in your code, you must first define it as follows:</span></span>

[!code-csharp[System.Runtime.BypassNGenAttribute#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/System.Runtime.BypassNGenAttribute/cs/Optout1.cs#1)]
[!code-vb[System.Runtime.BypassNGenAttribute#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/System.Runtime.BypassNGenAttribute/vb/Optout1.vb#1)]

<span data-ttu-id="e7d11-365">Luego puede aplicar el atributo a cada método.</span><span class="sxs-lookup"><span data-stu-id="e7d11-365">You can then apply the attribute on a per-method basis.</span></span> <span data-ttu-id="e7d11-366">En el ejemplo siguiente se indica al Generador de imágenes nativas que no debe generar una imagen nativa para el método `ExampleClass.ToJITCompile`.</span><span class="sxs-lookup"><span data-stu-id="e7d11-366">The following example instructs the Native Image Generator that it should not generate a native image for the `ExampleClass.ToJITCompile` method.</span></span>

[!code-csharp[System.Runtime.BypassNGenAttribute#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/System.Runtime.BypassNGenAttribute/cs/Optout1.cs#2)]
[!code-vb[System.Runtime.BypassNGenAttribute#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/System.Runtime.BypassNGenAttribute/vb/Optout1.vb#2)]

## <a name="examples"></a><span data-ttu-id="e7d11-367">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="e7d11-367">Examples</span></span>

<span data-ttu-id="e7d11-368">El siguiente comando genera una imagen nativa para `ClientApp.exe`, que se encuentra en el directorio actual, e instala la imagen en la memoria caché de imágenes nativas.</span><span class="sxs-lookup"><span data-stu-id="e7d11-368">The following command generates a native image for `ClientApp.exe`, located in the current directory, and installs the image in the native image cache.</span></span> <span data-ttu-id="e7d11-369">Si existe un archivo de configuración para el ensamblado, Ngen.exe usará dicho archivo.</span><span class="sxs-lookup"><span data-stu-id="e7d11-369">If a configuration file exists for the assembly, Ngen.exe uses it.</span></span> <span data-ttu-id="e7d11-370">Además, se generarán imágenes nativas para cualquier archivo .dll al que haga referencia `ClientApp.exe`.</span><span class="sxs-lookup"><span data-stu-id="e7d11-370">In addition, native images are generated for any .dll files that `ClientApp.exe` references.</span></span>

```
ngen install ClientApp.exe
```

<span data-ttu-id="e7d11-371">Una imagen instalada con Ngen.exe también recibe el nombre de raíz.</span><span class="sxs-lookup"><span data-stu-id="e7d11-371">An image installed with Ngen.exe is also called a root.</span></span> <span data-ttu-id="e7d11-372">Una raíz puede ser una aplicación o un componente compartido.</span><span class="sxs-lookup"><span data-stu-id="e7d11-372">A root can be an application or a shared component.</span></span>

<span data-ttu-id="e7d11-373">El siguiente comando genera una imagen nativa para `MyAssembly.exe` con la ruta de acceso especificada.</span><span class="sxs-lookup"><span data-stu-id="e7d11-373">The following command generates a native image for `MyAssembly.exe` with the specified path.</span></span>

```
ngen install c:\myfiles\MyAssembly.exe
```

<span data-ttu-id="e7d11-374">A la hora de buscar los ensamblados y sus dependencias, Ngen.exe usa la misma lógica de búsqueda que Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="e7d11-374">When locating assemblies and their dependencies, Ngen.exe uses the same probing logic used by the common language runtime.</span></span> <span data-ttu-id="e7d11-375">De forma predeterminada, el directorio que contiene `ClientApp.exe` se usa como directorio base de la aplicación y todas las búsquedas de ensamblados comienzan en este directorio.</span><span class="sxs-lookup"><span data-stu-id="e7d11-375">By default, the directory that contains `ClientApp.exe` is used as the application base directory, and all assembly probing begins in this directory.</span></span> <span data-ttu-id="e7d11-376">Se puede reemplazar este comportamiento mediante la opción `/AppBase`.</span><span class="sxs-lookup"><span data-stu-id="e7d11-376">You can override this behavior by using the `/AppBase` option.</span></span>

> [!NOTE]
> <span data-ttu-id="e7d11-377">Se trata de un cambio de comportamiento de Ngen.exe en las versiones 1.0 y 1.1 de .NET Framework, donde la base de la aplicación está establecida en el directorio actual.</span><span class="sxs-lookup"><span data-stu-id="e7d11-377">This is a change from Ngen.exe behavior in the .NET Framework versions 1.0 and 1.1, where the application base is set to the current directory.</span></span>

<span data-ttu-id="e7d11-378">Un ensamblado puede disponer de una dependencia sin referencia alguna; por ejemplo, si carga un archivo .dll mediante el método <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="e7d11-378">An assembly can have a dependency without a reference, for example if it loads a .dll file by using the <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="e7d11-379">Se puede crear una imagen nativa de este archivo .dll usando la información de configuración del ensamblado de aplicación, con la opción `/ExeConfig`.</span><span class="sxs-lookup"><span data-stu-id="e7d11-379">You can create a native image for such a .dll file by using configuration information for the application assembly, with the `/ExeConfig` option.</span></span> <span data-ttu-id="e7d11-380">El siguiente comando genera una imagen nativa de `MyLib.dll,` usando la información de configuración de `MyApp.exe`.</span><span class="sxs-lookup"><span data-stu-id="e7d11-380">The following command generates a native image for `MyLib.dll,` using the configuration information from `MyApp.exe`.</span></span>

```
ngen install c:\myfiles\MyLib.dll /ExeConfig:c:\myapps\MyApp.exe
```

<span data-ttu-id="e7d11-381">Los ensamblados instalados de esta manera no se quitan cuando se quita la aplicación.</span><span class="sxs-lookup"><span data-stu-id="e7d11-381">Assemblies installed in this way are not removed when the application is removed.</span></span>

<span data-ttu-id="e7d11-382">Para desinstalar una dependencia, use las mismas opciones de línea de comandos que se usaron para su instalación.</span><span class="sxs-lookup"><span data-stu-id="e7d11-382">To uninstall a dependency, use the same command-line options that were used to install it.</span></span> <span data-ttu-id="e7d11-383">El siguiente comando desinstala el archivo `MyLib.dll` del ejemplo anterior.</span><span class="sxs-lookup"><span data-stu-id="e7d11-383">The following command uninstalls the `MyLib.dll` from the previous example.</span></span>

```
ngen uninstall c:\myfiles\MyLib.dll /ExeConfig:c:\myapps\MyApp.exe
```

<span data-ttu-id="e7d11-384">Para crear una imagen nativa de un ensamblado en la caché global de ensamblados, use el nombre para mostrar del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="e7d11-384">To create a native image for an assembly in the global assembly cache, use the display name of the assembly.</span></span> <span data-ttu-id="e7d11-385">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="e7d11-385">For example:</span></span>

```
ngen install "ClientApp, Version=1.0.0.0, Culture=neutral,
  PublicKeyToken=3c7ba247adcd2081, processorArchitecture=MSIL"
```

<span data-ttu-id="e7d11-386">NGen.exe generará un conjunto independiente de imágenes para cada escenario que se instale.</span><span class="sxs-lookup"><span data-stu-id="e7d11-386">NGen.exe generates a separate set of images for each scenario you install.</span></span> <span data-ttu-id="e7d11-387">Por ejemplo, el siguiente comando instala un conjunto completo de imágenes nativas para el funcionamiento normal, otro conjunto completo para la depuración, y un tercer conjunto para la creación de perfiles:</span><span class="sxs-lookup"><span data-stu-id="e7d11-387">For example, the following commands install a complete set of native images for normal operation, another complete set for debugging, and a third for profiling:</span></span>

```
ngen install MyApp.exe
ngen install MyApp.exe /debug
ngen install MyApp.exe /profile
```

### <a name="displaying-the-native-image-cache"></a><span data-ttu-id="e7d11-388">Mostrar la memoria caché de imágenes nativas</span><span class="sxs-lookup"><span data-stu-id="e7d11-388">Displaying the Native Image Cache</span></span>

<span data-ttu-id="e7d11-389">Una vez instaladas en la memoria caché las imágenes nativas, se pueden mostrar mediante Ngen.exe.</span><span class="sxs-lookup"><span data-stu-id="e7d11-389">Once native images are installed in the cache, they can be displayed using Ngen.exe.</span></span> <span data-ttu-id="e7d11-390">El siguiente comando muestra todas las imágenes nativas que contiene la memoria caché de imágenes nativas.</span><span class="sxs-lookup"><span data-stu-id="e7d11-390">The following command displays all native images in the native image cache.</span></span>

```
ngen display
```

<span data-ttu-id="e7d11-391">La acción `display` muestra primero todos los ensamblados raíz, seguidos de una lista de todas las imágenes nativas del equipo.</span><span class="sxs-lookup"><span data-stu-id="e7d11-391">The `display` action lists all the root assemblies first, followed by a list of all the native images on the computer.</span></span>

<span data-ttu-id="e7d11-392">Use el nombre simple de un ensamblado para mostrar únicamente información de dicho ensamblado.</span><span class="sxs-lookup"><span data-stu-id="e7d11-392">Use the simple name of an assembly to display information only for that assembly.</span></span> <span data-ttu-id="e7d11-393">El siguiente comando muestra todas las imágenes nativas de la memoria caché de imágenes nativas que coinciden con el nombre parcial `MyAssembly`, sus dependencias y todas las raíces que tienen una dependencia en `MyAssembly`:</span><span class="sxs-lookup"><span data-stu-id="e7d11-393">The following command displays all native images in the native image cache that match the partial name `MyAssembly`, their dependencies, and all roots that have a dependency on `MyAssembly`:</span></span>

```
ngen display MyAssembly
```

<span data-ttu-id="e7d11-394">Conocer las raíces que dependen de un ensamblado de componente compartido resulta de gran utilidad para valorar el impacto de una acción `update` una vez actualizado el componente compartido.</span><span class="sxs-lookup"><span data-stu-id="e7d11-394">Knowing what roots depend on a shared component assembly is useful in gauging the impact of an `update` action after the shared component is upgraded.</span></span>

<span data-ttu-id="e7d11-395">Si especifica la extensión de archivo de un ensamblado, deberá especificar la ruta de acceso o ejecutar Ngen.exe desde el directorio que contiene el ensamblado:</span><span class="sxs-lookup"><span data-stu-id="e7d11-395">If you specify an assembly's file extension, you must either specify the path or execute Ngen.exe from the directory containing the assembly:</span></span>

```
ngen display c:\myApps\MyAssembly.exe
```

<span data-ttu-id="e7d11-396">El siguiente comando muestra todas las imágenes nativas de la memoria caché de imágenes nativas con el nombre `MyAssembly` y la versión 1.0.0.0.</span><span class="sxs-lookup"><span data-stu-id="e7d11-396">The following command displays all native images in the native image cache with the name `MyAssembly` and the version 1.0.0.0.</span></span>

```
ngen display "myAssembly, version=1.0.0.0"
```

### <a name="updating-images"></a><span data-ttu-id="e7d11-397">Actualizar imágenes</span><span class="sxs-lookup"><span data-stu-id="e7d11-397">Updating Images</span></span>

<span data-ttu-id="e7d11-398">Normalmente, las imágenes se actualizan tras la actualización de un componente compartido.</span><span class="sxs-lookup"><span data-stu-id="e7d11-398">Images are typically updated after a shared component has been upgraded.</span></span> <span data-ttu-id="e7d11-399">Para actualizar todas las imágenes nativas que hayan cambiado o cuyas dependencias hayan cambiado, use la acción `update` sin ningún argumento.</span><span class="sxs-lookup"><span data-stu-id="e7d11-399">To update all native images that have changed, or whose dependencies have changed, use the `update` action with no arguments.</span></span>

```
ngen update
```

<span data-ttu-id="e7d11-400">Actualizar todas las imágenes puede ser un proceso largo.</span><span class="sxs-lookup"><span data-stu-id="e7d11-400">Updating all images can be a lengthy process.</span></span> <span data-ttu-id="e7d11-401">La opción `/queue` pone en cola las actualizaciones para que las ejecute el servicio de imágenes nativas.</span><span class="sxs-lookup"><span data-stu-id="e7d11-401">You can queue the updates for execution by the native image service by using the `/queue` option.</span></span> <span data-ttu-id="e7d11-402">Para más información sobre la opción `/queue` y las prioridades de instalación, consulte [Servicio de imágenes nativas](#native-image-service).</span><span class="sxs-lookup"><span data-stu-id="e7d11-402">For more information on the `/queue` option and installation priorities, see [Native Image Service](#native-image-service).</span></span>

```
ngen update /queue
```

### <a name="uninstalling-images"></a><span data-ttu-id="e7d11-403">Desinstalar imágenes</span><span class="sxs-lookup"><span data-stu-id="e7d11-403">Uninstalling Images</span></span>

<span data-ttu-id="e7d11-404">Ngen.exe mantiene una lista de dependencias; de este modo, los componentes compartidos se quitan únicamente cuando se han quitado todos los ensamblados que dependen de ellos.</span><span class="sxs-lookup"><span data-stu-id="e7d11-404">Ngen.exe maintains a list of dependencies, so that shared components are removed only when all assemblies that depend on them have been removed.</span></span> <span data-ttu-id="e7d11-405">Además, si un componente compartido se ha instalado como raíz, no se quita.</span><span class="sxs-lookup"><span data-stu-id="e7d11-405">In addition, a shared component is not removed if it has been installed as a root.</span></span>

<span data-ttu-id="e7d11-406">El siguiente comando desinstala todos los escenarios de la raíz `ClientApp.exe`:</span><span class="sxs-lookup"><span data-stu-id="e7d11-406">The following command uninstalls all scenarios for the root `ClientApp.exe`:</span></span>

```
ngen uninstall ClientApp
```

<span data-ttu-id="e7d11-407">Se puede usar la acción `uninstall` para quitar escenarios concretos.</span><span class="sxs-lookup"><span data-stu-id="e7d11-407">The `uninstall` action can be used to remove specific scenarios.</span></span> <span data-ttu-id="e7d11-408">El siguiente comando desinstala todos los escenarios de depuración de `ClientApp.exe`:</span><span class="sxs-lookup"><span data-stu-id="e7d11-408">The following command uninstalls all debug scenarios for `ClientApp.exe`:</span></span>

```
ngen uninstall ClientApp /debug
```

> [!NOTE]
> <span data-ttu-id="e7d11-409">Cuando se desinstalan escenarios `/debug` no se desinstalan los escenarios que incluyen tanto `/profile` como `/debug.`</span><span class="sxs-lookup"><span data-stu-id="e7d11-409">Uninstalling `/debug` scenarios does not uninstall a scenario that includes both `/profile` and `/debug.`</span></span>

<span data-ttu-id="e7d11-410">El siguiente comando desinstala todos los escenarios de una versión concreta de `ClientApp.exe`:</span><span class="sxs-lookup"><span data-stu-id="e7d11-410">The following command uninstalls all scenarios for a specific version of `ClientApp.exe`:</span></span>

```
ngen uninstall "ClientApp, Version=1.0.0.0"
```

<span data-ttu-id="e7d11-411">Los siguientes comandos desinstalan todos los escenarios de `"ClientApp, Version=1.0.0.0, Culture=neutral, PublicKeyToken=3c7ba247adcd2081, processorArchitecture=MSIL",` o simplemente el escenario de depuración de dicho ensamblado:</span><span class="sxs-lookup"><span data-stu-id="e7d11-411">The following commands uninstall all scenarios for `"ClientApp, Version=1.0.0.0, Culture=neutral, PublicKeyToken=3c7ba247adcd2081, processorArchitecture=MSIL",` or just the debug scenario for that assembly:</span></span>

```
ngen uninstall "ClientApp, Version=1.0.0.0, Culture=neutral,
  PublicKeyToken=3c7ba247adcd2081, processorArchitecture=MSIL"
ngen uninstall "ClientApp, Version=1.0.0.0, Culture=neutral,
  PublicKeyToken=3c7ba247adcd2081, processorArchitecture=MSIL" /debug
```

<span data-ttu-id="e7d11-412">Al igual que ocurre con la acción `install`, cuando se suministra una extensión, es necesario ejecutar Ngen.exe desde el directorio que contiene el ensamblado o especificar una ruta de acceso completa.</span><span class="sxs-lookup"><span data-stu-id="e7d11-412">As with the `install` action, supplying an extension requires either executing Ngen.exe from the directory containing the assembly or specifying a full path.</span></span>

<span data-ttu-id="e7d11-413">Para ver ejemplos relacionados con el servicio de imágenes nativas, consulte [Servicio de imágenes nativas](#native-image-service).</span><span class="sxs-lookup"><span data-stu-id="e7d11-413">For examples relating to the native image service, see [Native Image Service](#native-image-service).</span></span>

## <a name="native-image-task"></a><span data-ttu-id="e7d11-414">Tarea de imagen nativa</span><span class="sxs-lookup"><span data-stu-id="e7d11-414">Native Image Task</span></span>

<span data-ttu-id="e7d11-415">La tarea de imagen nativa es una tarea de Windows que genera y mantiene imágenes nativas.</span><span class="sxs-lookup"><span data-stu-id="e7d11-415">The native image task is a Windows task that generates and maintains native images.</span></span> <span data-ttu-id="e7d11-416">La tarea de imagen nativa genera y recupera automáticamente imágenes nativas para los escenarios admitidos.</span><span class="sxs-lookup"><span data-stu-id="e7d11-416">The native image task generates and reclaims native images automatically for supported scenarios.</span></span> <span data-ttu-id="e7d11-417">También permite que los instaladores usen [Ngen.exe (Generador de imágenes nativas)](../../../docs/framework/tools/ngen-exe-native-image-generator.md) para aplazar la creación y la actualización de las imágenes nativas.</span><span class="sxs-lookup"><span data-stu-id="e7d11-417">It also enables installers to use [Ngen.exe (Native Image Generator)](../../../docs/framework/tools/ngen-exe-native-image-generator.md) to create and update native images at a deferred time.</span></span>

<span data-ttu-id="e7d11-418">La tarea de imagen nativa se registra una vez por cada arquitectura de CPU admitida en un equipo, para permitir la compilación de las aplicaciones que tienen como destino cada arquitectura:</span><span class="sxs-lookup"><span data-stu-id="e7d11-418">The native image task is registered once for each CPU architecture supported on a computer, to allow compilation for applications that target each architecture:</span></span>

|<span data-ttu-id="e7d11-419">Nombre de la tarea</span><span class="sxs-lookup"><span data-stu-id="e7d11-419">Task name</span></span>|<span data-ttu-id="e7d11-420">Equipo de 32 bits</span><span class="sxs-lookup"><span data-stu-id="e7d11-420">32-bit computer</span></span>|<span data-ttu-id="e7d11-421">Equipo de 64 bits</span><span class="sxs-lookup"><span data-stu-id="e7d11-421">64-bit computer</span></span>|
|---------------|----------------------|----------------------|
|<span data-ttu-id="e7d11-422">NET Framework NGEN v4.0.30319</span><span class="sxs-lookup"><span data-stu-id="e7d11-422">NET Framework NGEN v4.0.30319</span></span>|<span data-ttu-id="e7d11-423">Sí</span><span class="sxs-lookup"><span data-stu-id="e7d11-423">Yes</span></span>|<span data-ttu-id="e7d11-424">Sí</span><span class="sxs-lookup"><span data-stu-id="e7d11-424">Yes</span></span>|
|<span data-ttu-id="e7d11-425">NET Framework NGEN v4.0.30319 64</span><span class="sxs-lookup"><span data-stu-id="e7d11-425">NET Framework NGEN v4.0.30319 64</span></span>|<span data-ttu-id="e7d11-426">No</span><span class="sxs-lookup"><span data-stu-id="e7d11-426">No</span></span>|<span data-ttu-id="e7d11-427">Sí</span><span class="sxs-lookup"><span data-stu-id="e7d11-427">Yes</span></span>|

<span data-ttu-id="e7d11-428">La tarea de imagen nativa está disponible en .NET Framework 4.5 y las versiones posteriores, con Windows 8 o posterior.</span><span class="sxs-lookup"><span data-stu-id="e7d11-428">The native image task is available in the .NET Framework 4.5 and later versions, when running on Windows 8 or later.</span></span> <span data-ttu-id="e7d11-429">En las versiones anteriores de Windows, .NET Framework usa el [Servicio de imágenes nativas](#native-image-service).</span><span class="sxs-lookup"><span data-stu-id="e7d11-429">On earlier versions of Windows, the .NET Framework uses the [Native Image Service](#native-image-service).</span></span>

### <a name="task-lifetime"></a><span data-ttu-id="e7d11-430">Duración de la tarea</span><span class="sxs-lookup"><span data-stu-id="e7d11-430">Task Lifetime</span></span>

<span data-ttu-id="e7d11-431">En general, el Programador de tareas de Windows inicia la tarea de imagen nativa cada noche, cuando el equipo está inactivo.</span><span class="sxs-lookup"><span data-stu-id="e7d11-431">In general, the Windows Task Scheduler starts the native image task every night when the computer is idle.</span></span> <span data-ttu-id="e7d11-432">La tarea busca los trabajos aplazados puestos en cola por los instaladores de aplicaciones, las solicitudes aplazadas de actualización de imágenes nativas y las creaciones automáticas de imágenes.</span><span class="sxs-lookup"><span data-stu-id="e7d11-432">The task checks for any deferred work that is queued by application installers, any deferred native image update requests, and any automatic image creation.</span></span> <span data-ttu-id="e7d11-433">La tarea completa los elementos de trabajo pendientes y, después, se apaga.</span><span class="sxs-lookup"><span data-stu-id="e7d11-433">The task completes outstanding work items and then shuts down.</span></span> <span data-ttu-id="e7d11-434">Si el equipo deja de estar inactivo mientras se ejecuta la tarea, esta se detendrá.</span><span class="sxs-lookup"><span data-stu-id="e7d11-434">If the computer stops being idle while the task is running, the task stops.</span></span>

<span data-ttu-id="e7d11-435">También puede iniciar la tarea de imagen nativa manualmente con la interfaz de usuario del Programador de tareas o con llamadas manuales a NGen.exe.</span><span class="sxs-lookup"><span data-stu-id="e7d11-435">You can also start the native image task manually through the Task Scheduler UI or through manual calls to NGen.exe.</span></span> <span data-ttu-id="e7d11-436">Si la tarea se inicia con alguno de estos métodos, seguirá ejecutándose cuando el equipo ya no esté inactivo.</span><span class="sxs-lookup"><span data-stu-id="e7d11-436">If the task is started through either of these methods, it will continue running when the computer is no longer idle.</span></span> <span data-ttu-id="e7d11-437">Las imágenes creadas manualmente con NGen.exe tienen mayor prioridad, para que el comportamiento de los instaladores de aplicaciones sea predecible.</span><span class="sxs-lookup"><span data-stu-id="e7d11-437">Images created manually by using NGen.exe are prioritized to enable predictable behavior for application installers.</span></span>

## <a name="native-image-service"></a><span data-ttu-id="e7d11-438">Servicio de imágenes nativas</span><span class="sxs-lookup"><span data-stu-id="e7d11-438">Native Image Service</span></span>

<span data-ttu-id="e7d11-439">El servicio de imágenes nativas es un servicio de Windows que genera y mantiene imágenes nativas.</span><span class="sxs-lookup"><span data-stu-id="e7d11-439">The native image service is a Windows service that generates and maintains native images.</span></span> <span data-ttu-id="e7d11-440">El servicio de imágenes nativas permite al desarrollador aplazar la instalación y la actualización de imágenes nativas hasta los períodos en los que el equipo está inactivo.</span><span class="sxs-lookup"><span data-stu-id="e7d11-440">The native image service allows the developer to defer the installation and update of native images to periods when the computer is idle.</span></span>

<span data-ttu-id="e7d11-441">Normalmente, quien inicia el servicio de imágenes nativas es el programa de instalación (el instalador) de una aplicación o una actualización.</span><span class="sxs-lookup"><span data-stu-id="e7d11-441">Normally, the native image service is initiated by the installation program (installer) for an application or update.</span></span> <span data-ttu-id="e7d11-442">En el caso de las acciones de prioridad 3, el servicio se ejecuta durante el tiempo de inactividad del equipo.</span><span class="sxs-lookup"><span data-stu-id="e7d11-442">For priority 3 actions, the service executes during idle time on the computer.</span></span> <span data-ttu-id="e7d11-443">El servicio guarda su estado y es capaz de continuar a lo largo de varios reinicios si es necesario.</span><span class="sxs-lookup"><span data-stu-id="e7d11-443">The service saves its state and is capable of continuing through multiple reboots if necessary.</span></span> <span data-ttu-id="e7d11-444">Se pueden poner en cola varias compilaciones de imágenes.</span><span class="sxs-lookup"><span data-stu-id="e7d11-444">Multiple image compilations can be queued.</span></span>

<span data-ttu-id="e7d11-445">El servicio también interactúa con el comando Ngen.exe manual.</span><span class="sxs-lookup"><span data-stu-id="e7d11-445">The service also interacts with the manual Ngen.exe command.</span></span> <span data-ttu-id="e7d11-446">Los comandos manuales tienen prioridad sobre la actividad en segundo plano.</span><span class="sxs-lookup"><span data-stu-id="e7d11-446">Manual commands take precedence over background activity.</span></span>

> [!NOTE]
> <span data-ttu-id="e7d11-447">En Windows Vista, el nombre del servicio de imágenes nativas que se muestra es "Microsoft.NET Framework NGEN v2.0.50727_X86" o "Microsoft.NET Framework NGEN v2.0.50727_X64".</span><span class="sxs-lookup"><span data-stu-id="e7d11-447">On Windows Vista, the name displayed for the native image service is "Microsoft.NET Framework NGEN v2.0.50727_X86" or "Microsoft.NET Framework NGEN v2.0.50727_X64".</span></span> <span data-ttu-id="e7d11-448">En todas las versiones anteriores de Microsoft Windows, el nombre es "Servicio de optimización de tiempo de ejecución de .NET v2.0.50727_X86" o "Servicio de optimización de tiempo de ejecución de .NET v2.0.50727_X64".</span><span class="sxs-lookup"><span data-stu-id="e7d11-448">On all earlier versions of Microsoft Windows, the name is ".NET Runtime Optimization Service v2.0.50727_X86" or ".NET Runtime Optimization Service v2.0.50727_X64".</span></span>

### <a name="launching-deferred-operations"></a><span data-ttu-id="e7d11-449">Iniciar operaciones aplazadas</span><span class="sxs-lookup"><span data-stu-id="e7d11-449">Launching Deferred Operations</span></span>

<span data-ttu-id="e7d11-450">Antes de comenzar una instalación o una actualización, se recomienda pausar el servicio.</span><span class="sxs-lookup"><span data-stu-id="e7d11-450">Before beginning an installation or upgrade, pausing the service is recommended.</span></span> <span data-ttu-id="e7d11-451">Así, el servicio no se ejecutará mientras el instalador copia archivos o coloca ensamblados en la caché global de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="e7d11-451">This ensures that the service does not execute while the installer is copying files or putting assemblies in the global assembly cache.</span></span> <span data-ttu-id="e7d11-452">La siguiente línea de comandos de Ngen.exe pausa el servicio:</span><span class="sxs-lookup"><span data-stu-id="e7d11-452">The following Ngen.exe command line pauses the service:</span></span>

```
ngen queue pause
```

<span data-ttu-id="e7d11-453">Después de poner en cola todas las operaciones aplazadas, el siguiente comando permite reanudar el servicio:</span><span class="sxs-lookup"><span data-stu-id="e7d11-453">When all deferred operations have been queued, the following command allows the service to resume:</span></span>

```
ngen queue continue
```

<span data-ttu-id="e7d11-454">Para aplazar la generación de imágenes nativas al instalar una nueva aplicación o al actualizar un componente compartido, utilice la opción `/queue` con las acciones `install` o `update`.</span><span class="sxs-lookup"><span data-stu-id="e7d11-454">To defer native image generation when installing a new application or when updating a shared component, use the `/queue` option with the `install` or `update` actions.</span></span> <span data-ttu-id="e7d11-455">Las siguientes líneas de comandos de Ngen.exe instalan una imagen nativa de un componente compartido y realizan una actualización de todas las raíces a las que puede que afectaran:</span><span class="sxs-lookup"><span data-stu-id="e7d11-455">The following Ngen.exe command lines install a native image for a shared component and perform an update of all roots that may have been affected:</span></span>

```
ngen install MyComponent /queue
ngen update /queue
```

<span data-ttu-id="e7d11-456">La acción `update` vuelve a generar todas las imágenes nativas invalidadas, no solo las que utilizan `MyComponent`.</span><span class="sxs-lookup"><span data-stu-id="e7d11-456">The `update` action regenerates all native images that have been invalidated, not just those that use `MyComponent`.</span></span>

<span data-ttu-id="e7d11-457">Si la aplicación está formada por muchas raíces, puede controlar la prioridad de las acciones aplazadas.</span><span class="sxs-lookup"><span data-stu-id="e7d11-457">If your application consists of many roots, you can control the priority of the deferred actions.</span></span> <span data-ttu-id="e7d11-458">Los siguientes comandos ponen en cola la instalación de tres raíces.</span><span class="sxs-lookup"><span data-stu-id="e7d11-458">The following commands queue the installation of three roots.</span></span> <span data-ttu-id="e7d11-459">`Assembly1` se instala en primer lugar, sin esperar al tiempo de inactividad.</span><span class="sxs-lookup"><span data-stu-id="e7d11-459">`Assembly1` is installed first, without waiting for idle time.</span></span> <span data-ttu-id="e7d11-460">`Assembly2` también se instala sin esperar al tiempo de inactividad, pero una vez que finalizan todas las acciones de prioridad 1.</span><span class="sxs-lookup"><span data-stu-id="e7d11-460">`Assembly2` is also installed without waiting for idle time, but after all priority 1 actions have completed.</span></span> <span data-ttu-id="e7d11-461">`Assembly3` se instala cuando el servicio detecta que el equipo se encuentra inactivo.</span><span class="sxs-lookup"><span data-stu-id="e7d11-461">`Assembly3` is installed when the service detects that the computer is idle.</span></span>

```
ngen install Assembly1 /queue:1
ngen install Assembly2 /queue:2
ngen install Assembly3 /queue:3
```

<span data-ttu-id="e7d11-462">Puede forzar la ejecución sincrónica de las acciones en cola con la acción `executeQueuedItems`.</span><span class="sxs-lookup"><span data-stu-id="e7d11-462">You can force queued actions to occur synchronously by using the `executeQueuedItems` action.</span></span> <span data-ttu-id="e7d11-463">Si especifica la prioridad (opcional), esta acción afecta solo a las acciones en cola que tienen una prioridad igual o menor.</span><span class="sxs-lookup"><span data-stu-id="e7d11-463">If you supply the optional priority, this action affects only the queued actions that have equal or lower priority.</span></span> <span data-ttu-id="e7d11-464">La prioridad predeterminada es 3, por lo que el siguiente comando de Ngen.exe procesa todas las acciones en cola inmediatamente y no vuelve hasta que finalizan:</span><span class="sxs-lookup"><span data-stu-id="e7d11-464">The default priority is 3, so the following Ngen.exe command processes all queued actions immediately, and does not return until they are finished:</span></span>

```
ngen executeQueuedItems
```

<span data-ttu-id="e7d11-465">Los comandos sincrónicos son ejecutados por Ngen.exe y no utilizan el servicio de imágenes nativas.</span><span class="sxs-lookup"><span data-stu-id="e7d11-465">Synchronous commands are executed by Ngen.exe and do not use the native image service.</span></span> <span data-ttu-id="e7d11-466">Puede ejecutar acciones con Ngen.exe mientras se está ejecutando el servicio de imágenes nativas.</span><span class="sxs-lookup"><span data-stu-id="e7d11-466">You can execute actions using Ngen.exe while the native image service is running.</span></span>

### <a name="service-shutdown"></a><span data-ttu-id="e7d11-467">Apagado del servicio</span><span class="sxs-lookup"><span data-stu-id="e7d11-467">Service Shutdown</span></span>

<span data-ttu-id="e7d11-468">El servicio, después de iniciarse con la ejecución de un comando de Ngen.exe que incluye la opción `/queue`, se ejecuta en segundo plano hasta que se completan todas las acciones.</span><span class="sxs-lookup"><span data-stu-id="e7d11-468">After being initiated by the execution of an Ngen.exe command that includes the `/queue` option, the service runs in the background until all actions have been completed.</span></span> <span data-ttu-id="e7d11-469">El servicio guarda su estado para poder continuar a lo largo de varios reinicios si es necesario.</span><span class="sxs-lookup"><span data-stu-id="e7d11-469">The service saves its state so that it can continue through multiple reboots if necessary.</span></span> <span data-ttu-id="e7d11-470">Cuando el servicio detecta que no hay más acciones en cola, restablece su estado para no reiniciarse la próxima vez que se arranque el equipo y, luego, se apaga.</span><span class="sxs-lookup"><span data-stu-id="e7d11-470">When the service detects that there are no more actions queued, it resets its status so that it will not restart the next time the computer is booted, and then it shuts itself down.</span></span>

### <a name="service-interaction-with-clients"></a><span data-ttu-id="e7d11-471">Interacción del servicio con los clientes</span><span class="sxs-lookup"><span data-stu-id="e7d11-471">Service Interaction with Clients</span></span>

<span data-ttu-id="e7d11-472">En la versión 2.0 de .NET Framework, la única interacción con el servicio de imágenes nativas es a través de la herramienta de línea de comandos Ngen.exe.</span><span class="sxs-lookup"><span data-stu-id="e7d11-472">In the .NET Framework version 2.0, the only interaction with the native image service is through the command-line tool Ngen.exe.</span></span> <span data-ttu-id="e7d11-473">Utilice la herramienta de línea de comandos en los scripts de instalación para poner en cola las acciones del servicio de imágenes nativas e interactuar con el servicio.</span><span class="sxs-lookup"><span data-stu-id="e7d11-473">Use the command-line tool in installation scripts to queue actions for the native image service and to interact with the service.</span></span>

## <a name="see-also"></a><span data-ttu-id="e7d11-474">Vea también</span><span class="sxs-lookup"><span data-stu-id="e7d11-474">See also</span></span>

- [<span data-ttu-id="e7d11-475">Herramientas</span><span class="sxs-lookup"><span data-stu-id="e7d11-475">Tools</span></span>](../../../docs/framework/tools/index.md)
- [<span data-ttu-id="e7d11-476">Proceso de ejecución administrada</span><span class="sxs-lookup"><span data-stu-id="e7d11-476">Managed Execution Process</span></span>](../../../docs/standard/managed-execution-process.md)
- [<span data-ttu-id="e7d11-477">Cómo el motor en tiempo de ejecución ubica ensamblados</span><span class="sxs-lookup"><span data-stu-id="e7d11-477">How the Runtime Locates Assemblies</span></span>](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)
- [<span data-ttu-id="e7d11-478">Símbolos del sistema</span><span class="sxs-lookup"><span data-stu-id="e7d11-478">Command Prompts</span></span>](../../../docs/framework/tools/developer-command-prompt-for-vs.md)
