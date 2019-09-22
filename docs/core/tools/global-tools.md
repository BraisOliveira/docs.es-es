---
title: Herramientas globales de .NET Core
description: Información general sobre las herramientas globales de .NET Core y los comandos de CLI de .NET Core que hay disponibles para ellas.
author: KathleenDollard
ms.date: 05/29/2018
ms.custom: seodec18
ms.openlocfilehash: 01c1463ceddcd64e5bab05b95a5ae4a91b6da838
ms.sourcegitcommit: a4b10e1f2a8bb4e8ff902630855474a0c4f1b37a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/19/2019
ms.locfileid: "71117459"
---
# <a name="net-core-global-tools-overview"></a><span data-ttu-id="04b9f-103">Información general sobre las herramientas globales de .NET Core</span><span class="sxs-lookup"><span data-stu-id="04b9f-103">.NET Core Global Tools overview</span></span>

[!INCLUDE [topic-appliesto-net-core-21plus.md](../../../includes/topic-appliesto-net-core-21plus.md)]

<span data-ttu-id="04b9f-104">Una herramienta global de .NET Core es un paquete especial de NuGet que contiene una aplicación de consola.</span><span class="sxs-lookup"><span data-stu-id="04b9f-104">A .NET Core Global Tool is a special NuGet package that contains a console application.</span></span> <span data-ttu-id="04b9f-105">Las herramientas globales se pueden instalar en una ubicación predeterminada del equipo incluida en la variable de entorno PATH, o bien en una ubicación personalizada.</span><span class="sxs-lookup"><span data-stu-id="04b9f-105">A Global Tool can be installed on your machine on a default location that is included in the PATH environment variable or on a custom location.</span></span>

<span data-ttu-id="04b9f-106">Si quiere usar una herramienta global de .NET Core:</span><span class="sxs-lookup"><span data-stu-id="04b9f-106">If you want to use a .NET Core Global Tool:</span></span>

* <span data-ttu-id="04b9f-107">Busque información sobre la herramienta (normalmente un sitio web o página de GitHub).</span><span class="sxs-lookup"><span data-stu-id="04b9f-107">Find information about the tool (usually a website or GitHub page).</span></span>
* <span data-ttu-id="04b9f-108">Compruebe el autor y las estadísticas en la página principal de la fuente (normalmente NuGet.org).</span><span class="sxs-lookup"><span data-stu-id="04b9f-108">Check the author and statistics in the home for the feed (usually NuGet.org).</span></span>
* <span data-ttu-id="04b9f-109">Instale la herramienta.</span><span class="sxs-lookup"><span data-stu-id="04b9f-109">Install the tool.</span></span>
* <span data-ttu-id="04b9f-110">Llame a la herramienta.</span><span class="sxs-lookup"><span data-stu-id="04b9f-110">Call the tool.</span></span>
* <span data-ttu-id="04b9f-111">Actualice la herramienta.</span><span class="sxs-lookup"><span data-stu-id="04b9f-111">Update the tool.</span></span>
* <span data-ttu-id="04b9f-112">Desinstale la herramienta.</span><span class="sxs-lookup"><span data-stu-id="04b9f-112">Uninstall the tool.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="04b9f-113">Las herramientas globales de .NET Core aparecen en su ruta de acceso y se ejecutan con plena confianza.</span><span class="sxs-lookup"><span data-stu-id="04b9f-113">.NET Core Global Tools appear on your path and run in full trust.</span></span> <span data-ttu-id="04b9f-114">No instale herramientas globales de .NET Core a menos que confíe en el autor.</span><span class="sxs-lookup"><span data-stu-id="04b9f-114">Do not install .NET Core Global Tools unless you trust the author.</span></span>

## <a name="find-a-net-core-global-tool"></a><span data-ttu-id="04b9f-115">Buscar una herramienta global de .NET Core</span><span class="sxs-lookup"><span data-stu-id="04b9f-115">Find a .NET Core Global Tool</span></span>

<span data-ttu-id="04b9f-116">Actualmente, no hay una característica que permita buscar herramientas globales en la interfaz de línea de comandos (CLI) de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="04b9f-116">Currently, there isn't a Global Tool search feature in the .NET Core Command-line Interface (CLI).</span></span>

<span data-ttu-id="04b9f-117">Aunque estas herramientas se pueden encontrar en [NuGet](https://www.nuget.org),</span><span class="sxs-lookup"><span data-stu-id="04b9f-117">You can find .NET Core Global Tools on [NuGet](https://www.nuget.org).</span></span> <span data-ttu-id="04b9f-118">NuGet todavía no permite buscar de manera específica herramientas globales de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="04b9f-118">However, NuGet doesn't yet allow you to search specifically for .NET Core Global Tools.</span></span>

<span data-ttu-id="04b9f-119">Es posible que encuentre recomendaciones sobre herramientas en entradas de blog o en el repositorio de GitHub [natemcmaster/dotnet-tools](https://github.com/natemcmaster/dotnet-tools).</span><span class="sxs-lookup"><span data-stu-id="04b9f-119">You may also find tool recommendations in blog posts or in the [natemcmaster/dotnet-tools](https://github.com/natemcmaster/dotnet-tools) GitHub repository.</span></span>

<span data-ttu-id="04b9f-120">Asimismo, puede ver el código fuente de las herramientas globales creado por el equipo de ASP.NET en el repositorio de GitHub [aspnet/DotNetTools](https://github.com/aspnet/DotNetTools/).</span><span class="sxs-lookup"><span data-stu-id="04b9f-120">You can also see the source code for the Global Tools created by the ASP.NET team at the [aspnet/DotNetTools](https://github.com/aspnet/DotNetTools/) GitHub repository.</span></span>

## <a name="check-the-author-and-statistics"></a><span data-ttu-id="04b9f-121">Comprobar el autor y las estadísticas</span><span class="sxs-lookup"><span data-stu-id="04b9f-121">Check the author and statistics</span></span>

<span data-ttu-id="04b9f-122">Dado que herramientas globales de .NET Core se ejecutan con plena confianza y generalmente se instalan en su ruta de acceso, pueden ser muy eficaces.</span><span class="sxs-lookup"><span data-stu-id="04b9f-122">Since .NET Core Global Tools run in full trust and are generally installed on your path, they can be very powerful.</span></span> <span data-ttu-id="04b9f-123">No descargue herramientas de personas en las que no confíe.</span><span class="sxs-lookup"><span data-stu-id="04b9f-123">Don't download tools from people you don't trust.</span></span>

<span data-ttu-id="04b9f-124">Si la herramienta está hospedada en NuGet, busque la herramienta para comprobar el autor y las estadísticas.</span><span class="sxs-lookup"><span data-stu-id="04b9f-124">If the tool is hosted on NuGet, you can check the author and statistics by searching for the tool.</span></span>

## <a name="install-a-global-tool"></a><span data-ttu-id="04b9f-125">Instalar una herramienta global</span><span class="sxs-lookup"><span data-stu-id="04b9f-125">Install a Global Tool</span></span>

<span data-ttu-id="04b9f-126">Para instalar una herramienta global, use el comando de CLI de .NET Core [dotnet tool install](dotnet-tool-install.md).</span><span class="sxs-lookup"><span data-stu-id="04b9f-126">To install a Global Tool, you use the [dotnet tool install](dotnet-tool-install.md) .NET Core CLI command.</span></span> <span data-ttu-id="04b9f-127">En el ejemplo siguiente se muestra cómo instalar una herramienta global en la ubicación predeterminada:</span><span class="sxs-lookup"><span data-stu-id="04b9f-127">The following example shows how to install a Global Tool in the default location:</span></span>

```dotnetcli
dotnet tool install -g dotnetsay
```

<span data-ttu-id="04b9f-128">Si no se puede instalar la herramienta, se muestran mensajes de error.</span><span class="sxs-lookup"><span data-stu-id="04b9f-128">If the tool can't be installed, error messages are displayed.</span></span> <span data-ttu-id="04b9f-129">Verifique que se comprueban las fuentes que esperaba.</span><span class="sxs-lookup"><span data-stu-id="04b9f-129">Check that the feeds you expected are being checked.</span></span>

<span data-ttu-id="04b9f-130">Si está intentando instalar una versión preliminar o una versión específica de la herramienta, puede especificar el número de versión con el formato siguiente:</span><span class="sxs-lookup"><span data-stu-id="04b9f-130">If you're trying to install a pre-release version or a specific version of the tool, you can specify the version number using the following format:</span></span>

```dotnetcli
dotnet tool install -g <package-name> --version <version-number>
```

<span data-ttu-id="04b9f-131">Si la instalación es correcta, se muestra un mensaje similar al siguiente con el comando que se usa para llamar a la herramienta y la versión instalada:</span><span class="sxs-lookup"><span data-stu-id="04b9f-131">If installation is successful, a message is displayed showing the command used to call the tool and the version installed, similar to the following example:</span></span>

```output
You can invoke the tool using the following command: dotnetsay
Tool 'dotnetsay' (version '2.0.0') was successfully installed.
```

<span data-ttu-id="04b9f-132">Las herramientas globales pueden instalarse en el directorio predeterminado o en una ubicación específica.</span><span class="sxs-lookup"><span data-stu-id="04b9f-132">Global Tools can be installed in the default directory or in a specific location.</span></span> <span data-ttu-id="04b9f-133">Los directorios predeterminados son:</span><span class="sxs-lookup"><span data-stu-id="04b9f-133">The default directories are:</span></span>

| <span data-ttu-id="04b9f-134">SO</span><span class="sxs-lookup"><span data-stu-id="04b9f-134">OS</span></span>          | <span data-ttu-id="04b9f-135">Ruta de acceso</span><span class="sxs-lookup"><span data-stu-id="04b9f-135">Path</span></span>                          |
|-------------|-------------------------------|
| <span data-ttu-id="04b9f-136">Linux/macOS</span><span class="sxs-lookup"><span data-stu-id="04b9f-136">Linux/macOS</span></span> | `$HOME/.dotnet/tools`         |
| <span data-ttu-id="04b9f-137">Windows</span><span class="sxs-lookup"><span data-stu-id="04b9f-137">Windows</span></span>     | `%USERPROFILE%\.dotnet\tools` |

<span data-ttu-id="04b9f-138">Estas ubicaciones se agregan a la ruta de acceso del usuario cuando se ejecuta el SDK por primera vez, permitiendo así llamar directamente a las herramientas globales allí instaladas.</span><span class="sxs-lookup"><span data-stu-id="04b9f-138">These locations are added to the user's path when the SDK is first run, so Global Tools installed there can be called directly.</span></span>

<span data-ttu-id="04b9f-139">Tenga en cuenta que las herramientas globales son específicas del usuario, no de la máquina.</span><span class="sxs-lookup"><span data-stu-id="04b9f-139">Note that the Global Tools are user-specific, not machine global.</span></span> <span data-ttu-id="04b9f-140">Específica del usuario significa que no se puede instalar una herramienta global que está disponible para todos los usuarios de la máquina.</span><span class="sxs-lookup"><span data-stu-id="04b9f-140">Being user-specific means you cannot install a Global Tool that is available to all users of the machine.</span></span> <span data-ttu-id="04b9f-141">La herramienta solo está disponible para cada perfil de usuario en el que se instaló la herramienta.</span><span class="sxs-lookup"><span data-stu-id="04b9f-141">The tool is only available for each user profile where the tool was installed.</span></span>

<span data-ttu-id="04b9f-142">Las herramientas globales también pueden instalarse en un directorio específico.</span><span class="sxs-lookup"><span data-stu-id="04b9f-142">Global Tools can also be installed in a specific directory.</span></span> <span data-ttu-id="04b9f-143">Cuando se instalan en un directorio específico, el usuario debe incluir el directorio en la ruta de acceso a fin de asegurarse de que el comando está disponible. Hay dos maneras de hacerlo: llamar al comando con el directorio especificado, o llamar a la herramienta desde el directorio especificado.</span><span class="sxs-lookup"><span data-stu-id="04b9f-143">When installed in a specific directory, the user must ensure the command is available, by including that directory in the path, by calling the command with the directory specified, or calling the tool from within the specified directory.</span></span>
<span data-ttu-id="04b9f-144">En este caso, la CLI de .NET Core no agrega esta ubicación automáticamente a la variable de entorno PATH.</span><span class="sxs-lookup"><span data-stu-id="04b9f-144">In this case, the .NET Core CLI doesn't add this location automatically to the PATH environment variable.</span></span>

## <a name="use-the-tool"></a><span data-ttu-id="04b9f-145">Usar la herramienta</span><span class="sxs-lookup"><span data-stu-id="04b9f-145">Use the tool</span></span>

<span data-ttu-id="04b9f-146">Una vez que la herramienta se ha instalado, puede llamarla mediante su comando.</span><span class="sxs-lookup"><span data-stu-id="04b9f-146">Once the tool is installed, you can call it by using its command.</span></span> <span data-ttu-id="04b9f-147">Tenga en cuenta que el comando podría no ser el mismo que el nombre del paquete.</span><span class="sxs-lookup"><span data-stu-id="04b9f-147">Note that the command may not be the same as the package name.</span></span>

<span data-ttu-id="04b9f-148">Si el comando es `dotnetsay`, llame a la herramienta con:</span><span class="sxs-lookup"><span data-stu-id="04b9f-148">If the command is `dotnetsay`, you call it with:</span></span>

```console
dotnetsay
```

<span data-ttu-id="04b9f-149">Si la intención del autor era mostrar la herramienta ante una petición de `dotnet`, puede haberla escrito de manera que se llame como `dotnet <command>`, por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="04b9f-149">If the tool author wanted the tool to appear in the context of the `dotnet` prompt, they may have written it in a way that you call it as `dotnet <command>`, such as:</span></span>

```dotnetcli
dotnet doc
```

<span data-ttu-id="04b9f-150">Para ver las herramientas que están incluidas en un paquete de herramienta global instalado, enumere los paquetes instalados con el comando [dotnet tool list](dotnet-tool-list.md).</span><span class="sxs-lookup"><span data-stu-id="04b9f-150">You can find which tools are included in an installed Global Tool package by listing the installed packages using the [dotnet tool list](dotnet-tool-list.md) command.</span></span>

<span data-ttu-id="04b9f-151">También puede buscar las instrucciones de uso en el sitio web de la herramienta o escribir uno de los siguientes comandos:</span><span class="sxs-lookup"><span data-stu-id="04b9f-151">You can also look for usage instructions at the tool's website or by typing one of the following commands:</span></span>

```console
<command> --help
dotnet <command> --help
```

### <a name="what-could-go-wrong"></a><span data-ttu-id="04b9f-152">Cosas que pueden fallar</span><span class="sxs-lookup"><span data-stu-id="04b9f-152">What could go wrong</span></span>

<span data-ttu-id="04b9f-153">Las herramientas globales son [aplicaciones que dependen del marco](../deploying/index.md#framework-dependent-deployments-fdd), lo que significa que se basan en un runtime de .NET Core instalado en el equipo.</span><span class="sxs-lookup"><span data-stu-id="04b9f-153">Global Tools are [framework-dependent applications](../deploying/index.md#framework-dependent-deployments-fdd), which means they rely on a .NET Core runtime installed on your machine.</span></span> <span data-ttu-id="04b9f-154">Si no se encuentra el runtime esperado, se siguen las reglas normales de puesta al día de runtime de .NET Core:</span><span class="sxs-lookup"><span data-stu-id="04b9f-154">If the expected runtime is not found, they follow normal .NET Core runtime roll-forward rules such as:</span></span>

* <span data-ttu-id="04b9f-155">Una aplicación avanza a la versión de revisión más alta de las versiones principal y secundaria especificadas.</span><span class="sxs-lookup"><span data-stu-id="04b9f-155">An application rolls forward to the highest patch release of the specified major and minor version.</span></span>
* <span data-ttu-id="04b9f-156">Si no hay ningún runtime que coincida con un número de versión principal y secundaria, se usa la siguiente versión secundaria más alta.</span><span class="sxs-lookup"><span data-stu-id="04b9f-156">If there is no matching runtime with a matching major and minor version number, the next higher minor version is used.</span></span>
* <span data-ttu-id="04b9f-157">Esta puesta al día no se produce entre versiones preliminares del runtime ni entre versiones preliminares y versiones de lanzamiento.</span><span class="sxs-lookup"><span data-stu-id="04b9f-157">Roll forward doesn't occur between preview versions of the runtime or between preview versions and release versions.</span></span> <span data-ttu-id="04b9f-158">En consecuencia, las herramientas globales creadas con versiones preliminares deben ser recompiladas por el autor y posteriormente reinstaladas.</span><span class="sxs-lookup"><span data-stu-id="04b9f-158">Thus, Global Tools created using preview versions must be rebuilt and republished by the author and reinstalled.</span></span>
* <span data-ttu-id="04b9f-159">Pueden producirse otros problemas con las herramientas globales creadas en .NET Core 2.1, versión preliminar 1.</span><span class="sxs-lookup"><span data-stu-id="04b9f-159">Additional issues can occur with Global Tools created in .NET Core 2.1 Preview 1.</span></span> <span data-ttu-id="04b9f-160">Para obtener más información, consulte [.NET Core 2.1 Preview 2 Known Issues](https://github.com/dotnet/core/blob/master/release-notes/2.1/Preview/2.1.0-preview2-known-issues.md) (Problemas conocidos de .NET Core 2.1, versión preliminar 2).</span><span class="sxs-lookup"><span data-stu-id="04b9f-160">For more information, see [.NET Core 2.1 Preview 2 Known Issues](https://github.com/dotnet/core/blob/master/release-notes/2.1/Preview/2.1.0-preview2-known-issues.md).</span></span>

<span data-ttu-id="04b9f-161">Si una aplicación no encuentra el runtime apropiado, no se puede ejecutar y notifica un error.</span><span class="sxs-lookup"><span data-stu-id="04b9f-161">If an application cannot find an appropriate runtime, it fails to run and reports an error.</span></span>

<span data-ttu-id="04b9f-162">Otro problema que puede ocurrir es que una herramienta global que se creó durante una versión preliminar anterior no funcione con los runtime de .NET Core instalados actualmente.</span><span class="sxs-lookup"><span data-stu-id="04b9f-162">Another issue that might happen is that a Global Tool that was created during an earlier preview may not run with your currently installed .NET Core runtimes.</span></span> <span data-ttu-id="04b9f-163">Puede usar el comando siguiente para ver los runtime que están instalados en su equipo:</span><span class="sxs-lookup"><span data-stu-id="04b9f-163">You can see which runtimes are installed on your machine using the following command:</span></span>

```dotnetcli
dotnet --list-runtimes
```

<span data-ttu-id="04b9f-164">Póngase en contacto con el autor de la herramienta global y vea si puede volver a compilar y publicar en NuGet el paquete de la herramienta con un número de versión actualizada.</span><span class="sxs-lookup"><span data-stu-id="04b9f-164">Contact the author of the Global Tool and see if they can recompile and republish their tool package to NuGet with an updated version number.</span></span> <span data-ttu-id="04b9f-165">Una vez que hayan actualizado el paquete en NuGet, puede actualizar su copia.</span><span class="sxs-lookup"><span data-stu-id="04b9f-165">Once they have updated the package on NuGet, you can update your copy.</span></span>

<span data-ttu-id="04b9f-166">La primera vez que se usa, la CLI de .NET Core intenta agregar las ubicaciones predeterminadas a la variable de entorno PATH.</span><span class="sxs-lookup"><span data-stu-id="04b9f-166">The .NET Core CLI tries to add the default locations to the PATH environment variable on its first usage.</span></span> <span data-ttu-id="04b9f-167">Pero hay un par de escenarios en los que la ubicación podría no agregarse automáticamente a PATH:</span><span class="sxs-lookup"><span data-stu-id="04b9f-167">However, there are a couple of scenarios where the location might not be added to PATH automatically, such as:</span></span>

* <span data-ttu-id="04b9f-168">Si ha establecido la variable de entorno `DOTNET_SKIP_FIRST_TIME_EXPERIENCE`.</span><span class="sxs-lookup"><span data-stu-id="04b9f-168">If you've set the `DOTNET_SKIP_FIRST_TIME_EXPERIENCE` environment variable.</span></span>
* <span data-ttu-id="04b9f-169">En macOS, si ha instalado el SDK de .NET Core usando archivos *.tar.gz* en lugar de *.pkg*.</span><span class="sxs-lookup"><span data-stu-id="04b9f-169">On macOS, if you've installed the .NET Core SDK using *.tar.gz* files and not *.pkg*.</span></span>
* <span data-ttu-id="04b9f-170">En Linux, debe editar el archivo de entorno de shell para configurar PATH.</span><span class="sxs-lookup"><span data-stu-id="04b9f-170">On Linux, you need to edit the shell environment file to configure the PATH.</span></span>

## <a name="other-cli-commands"></a><span data-ttu-id="04b9f-171">Otros comandos de la CLI</span><span class="sxs-lookup"><span data-stu-id="04b9f-171">Other CLI commands</span></span>

<span data-ttu-id="04b9f-172">El SDK de .NET Core contiene otros comandos que pueden usarse con las herramientas globales de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="04b9f-172">The .NET Core SDK contains other commands that support .NET Core Global Tools.</span></span> <span data-ttu-id="04b9f-173">Utilice cualquiera de los comandos de `dotnet tool` combinado con las opciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="04b9f-173">Use any of the `dotnet tool` commands with one of the following options:</span></span>

* <span data-ttu-id="04b9f-174">`--global` o `-g` especifica que el comando es aplicable a las herramientas globales de todos los usuarios.</span><span class="sxs-lookup"><span data-stu-id="04b9f-174">`--global` or `-g` specifies that the command is applicable to user-wide Global Tools.</span></span>
* <span data-ttu-id="04b9f-175">`--tool-path` especifica una ubicación personalizada para las herramientas globales.</span><span class="sxs-lookup"><span data-stu-id="04b9f-175">`--tool-path` specifies a custom location for Global Tools.</span></span>

<span data-ttu-id="04b9f-176">Para saber qué comandos están disponibles con las herramientas globales:</span><span class="sxs-lookup"><span data-stu-id="04b9f-176">To find out which commands are available for Global Tools:</span></span>

```dotnetcli
dotnet tool --help
```

<span data-ttu-id="04b9f-177">La actualización de una herramienta global implica desinstalarla y reinstalarla con la versión estable más reciente.</span><span class="sxs-lookup"><span data-stu-id="04b9f-177">Updating a Global Tool involves uninstalling and reinstalling it with the latest stable version.</span></span> <span data-ttu-id="04b9f-178">Para actualizar una herramienta global, utilice el comando [dotnet tool update](dotnet-tool-update.md):</span><span class="sxs-lookup"><span data-stu-id="04b9f-178">To update a Global Tool, use the [dotnet tool update](dotnet-tool-update.md) command:</span></span>

```dotnetcli
dotnet tool update -g <packagename>
```

<span data-ttu-id="04b9f-179">Para quitar una herramienta global con [dotnet tool uninstall](dotnet-tool-uninstall.md):</span><span class="sxs-lookup"><span data-stu-id="04b9f-179">Remove a Global Tool using the [dotnet tool uninstall](dotnet-tool-uninstall.md):</span></span>

```dotnetcli
dotnet tool uninstall -g <packagename>
```

<span data-ttu-id="04b9f-180">Para mostrar todas las herramientas globales instaladas actualmente en el equipo, junto con su versión y los comandos, use el comando [dotnet tool list](dotnet-tool-list.md):</span><span class="sxs-lookup"><span data-stu-id="04b9f-180">To display all of the Global Tools currently installed on the machine, along with their version and commands, use the [dotnet tool list](dotnet-tool-list.md) command:</span></span>

```dotnetcli
dotnet tool list -g
```
