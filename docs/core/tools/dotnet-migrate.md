---
title: Comando dotnet migrate
description: El comando dotnet migrate migra un proyecto y todas sus dependencias.
ms.date: 06/26/2019
ms.openlocfilehash: 3304f666d15d9188cdae76a401747d91791f817f
ms.sourcegitcommit: b5c59eaaf8bf48ef3ec259f228cb328d6d4c0ceb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/03/2019
ms.locfileid: "67539399"
---
# <a name="dotnet-migrate"></a><span data-ttu-id="03962-103">dotnet migrate</span><span class="sxs-lookup"><span data-stu-id="03962-103">dotnet migrate</span></span>

<span data-ttu-id="03962-104">**Este tema se aplica a: ✓** SDK de .NET Core 1.x y versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="03962-104">**This topic applies to: ✓** .NET Core 1.x SDK and later versions</span></span>

<!-- todo: uncomment when all CLI commands are reviewed
[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]
-->

## <a name="name"></a><span data-ttu-id="03962-105">nombre</span><span class="sxs-lookup"><span data-stu-id="03962-105">Name</span></span>

<span data-ttu-id="03962-106">`dotnet migrate`: migra un proyecto .NET Core de la versión preliminar 2 a un proyecto del estilo de SDK de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="03962-106">`dotnet migrate` - Migrates a Preview 2 .NET Core project to a .NET Core SDK-style project.</span></span>

> [!NOTE]
> <span data-ttu-id="03962-107">`dotnet migrate` se quitará del SDK de .NET Core 3.0 en la próxima publicación de versión preliminar.</span><span class="sxs-lookup"><span data-stu-id="03962-107">`dotnet migrate` will be removed from the .NET Core 3.0 SDK in the next preview release.</span></span>

## <a name="synopsis"></a><span data-ttu-id="03962-108">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="03962-108">Synopsis</span></span>

```
dotnet migrate [<SOLUTION_FILE|PROJECT_DIR>] [--format-report-file-json] [-r|--report-file] [-s|--skip-project-references] [--skip-backup] [-t|--template-file] [-v|--sdk-package-version] [-x|--xproj-file]
dotnet migrate [-h|--help]
```

## <a name="description"></a><span data-ttu-id="03962-109">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="03962-109">Description</span></span>

<span data-ttu-id="03962-110">Con el comando `dotnet migrate` se migra un proyecto válido basado en *project.json* de la versión preliminar 2 a un proyecto válido *csproj* del estilo de SDK de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="03962-110">The `dotnet migrate` command migrates a valid Preview 2 *project.json*-based project to a valid .NET Core SDK-style *csproj* project.</span></span>

<span data-ttu-id="03962-111">De forma predeterminada, el comando migra el proyecto raíz y todas las referencias de proyecto que contiene.</span><span class="sxs-lookup"><span data-stu-id="03962-111">By default, the command migrates the root project and any project references that the root project contains.</span></span> <span data-ttu-id="03962-112">Este comportamiento se deshabilita mediante la opción `--skip-project-references` en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="03962-112">This behavior is disabled using the `--skip-project-references` option at runtime.</span></span>

<span data-ttu-id="03962-113">La migración se puede realizar en los recursos siguientes:</span><span class="sxs-lookup"><span data-stu-id="03962-113">Migration can be performed on the following assets:</span></span>

* <span data-ttu-id="03962-114">Un único proyecto mediante la especificación del archivo *project.json* que quiere migrar.</span><span class="sxs-lookup"><span data-stu-id="03962-114">A single project by specifying the *project.json* file to migrate.</span></span>
* <span data-ttu-id="03962-115">Todos los directorios especificados en el archivo *global.json* pasando una ruta al archivo *global.json*.</span><span class="sxs-lookup"><span data-stu-id="03962-115">All of the directories specified in the *global.json* file by passing in a path to the *global.json* file.</span></span>
* <span data-ttu-id="03962-116">Un archivo *solution.sln*, donde se migran los proyectos a los que se hace referencia en la solución.</span><span class="sxs-lookup"><span data-stu-id="03962-116">A *solution.sln* file, where it migrates the projects referenced in the solution.</span></span>
* <span data-ttu-id="03962-117">Todos los subdirectorios del directorio dado de manera recursiva.</span><span class="sxs-lookup"><span data-stu-id="03962-117">On all subdirectories of the given directory recursively.</span></span>

<span data-ttu-id="03962-118">El comando `dotnet migrate` mantiene el archivo *project.json* migrado dentro de un directorio `backup`, que se crea en caso de que no exista.</span><span class="sxs-lookup"><span data-stu-id="03962-118">The `dotnet migrate` command keeps the migrated *project.json* file inside a `backup` directory, which it creates if the directory doesn't exist.</span></span> <span data-ttu-id="03962-119">Este comportamiento se invalida con la opción `--skip-backup`.</span><span class="sxs-lookup"><span data-stu-id="03962-119">This behavior is overridden using the `--skip-backup` option.</span></span>

<span data-ttu-id="03962-120">De forma predeterminada, la operación de migración genera el estado del proceso de migración a la salida estándar (STDOUT).</span><span class="sxs-lookup"><span data-stu-id="03962-120">By default, the migration operation outputs the state of the migration process to standard output (STDOUT).</span></span> <span data-ttu-id="03962-121">Si usa la opción `--report-file <REPORT_FILE>`, la salida se guarda en el archivo especificado.</span><span class="sxs-lookup"><span data-stu-id="03962-121">If you use the `--report-file <REPORT_FILE>` option, the output is saved to the file specify.</span></span>

<span data-ttu-id="03962-122">El comando `dotnet migrate` solo admite proyectos válidos basados en *project.json* de la versión preliminar 2.</span><span class="sxs-lookup"><span data-stu-id="03962-122">The `dotnet migrate` command only supports valid Preview 2 *project.json*-based projects.</span></span> <span data-ttu-id="03962-123">Esto significa que no se puede usar para migrar DNX o los proyectos basados en *project.json* de la versión preliminar 1 directamente a proyectos de MSBuild/csproj.</span><span class="sxs-lookup"><span data-stu-id="03962-123">This means that you cannot use it to migrate DNX or Preview 1 *project.json*-based projects directly to MSBuild/csproj projects.</span></span> <span data-ttu-id="03962-124">Primero debe migrar manualmente el proyecto a un proyecto basado en *project.json* de la versión preliminar 2 y luego usar el comando `dotnet migrate` para migrar el proyecto.</span><span class="sxs-lookup"><span data-stu-id="03962-124">You first need to manually migrate the project to a Preview 2 *project.json*-based project and then use the `dotnet migrate` command to migrate the project.</span></span>

## <a name="arguments"></a><span data-ttu-id="03962-125">Argumentos</span><span class="sxs-lookup"><span data-stu-id="03962-125">Arguments</span></span>

`PROJECT_JSON/GLOBAL_JSON/SOLUTION_FILE/PROJECT_DIR`

<span data-ttu-id="03962-126">La ruta de acceso a uno de los siguientes elementos:</span><span class="sxs-lookup"><span data-stu-id="03962-126">The path to one of the following:</span></span>

* <span data-ttu-id="03962-127">Un archivo *project.json* para migrar.</span><span class="sxs-lookup"><span data-stu-id="03962-127">a *project.json* file to migrate.</span></span>
* <span data-ttu-id="03962-128">Un archivo *global.json*: se migran las carpetas especificadas en *global.json*.</span><span class="sxs-lookup"><span data-stu-id="03962-128">a *global.json* file: the folders specified in *global.json* are migrated.</span></span>
* <span data-ttu-id="03962-129">Un archivo *solution.sln*: se migran los proyectos a los que se hace referencia en la solución.</span><span class="sxs-lookup"><span data-stu-id="03962-129">a *solution.sln* file: the projects referenced in the solution are migrated.</span></span>
* <span data-ttu-id="03962-130">Un directorio para migrar: se buscan de forma recursiva los archivos *project.json* que se van a migrar dentro del directorio especificado.</span><span class="sxs-lookup"><span data-stu-id="03962-130">a directory to migrate: recursively searches for *project.json* files to migrate inside the specified directory.</span></span>

<span data-ttu-id="03962-131">Si no se especifica nada, se toma como valor predeterminado el directorio actual.</span><span class="sxs-lookup"><span data-stu-id="03962-131">Defaults to current directory if nothing is specified.</span></span>

## <a name="options"></a><span data-ttu-id="03962-132">Opciones</span><span class="sxs-lookup"><span data-stu-id="03962-132">Options</span></span>

`--format-report-file-json <REPORT_FILE>`

<span data-ttu-id="03962-133">Salida del archivo de informe de migración como JSON en lugar de mensajes de usuario.</span><span class="sxs-lookup"><span data-stu-id="03962-133">Output migration report file as JSON rather than user messages.</span></span>

`-h|--help`

<span data-ttu-id="03962-134">Imprime una corta ayuda para el comando.</span><span class="sxs-lookup"><span data-stu-id="03962-134">Prints out a short help for the command.</span></span>

`-r|--report-file <REPORT_FILE>`

<span data-ttu-id="03962-135">Salida del informe de migración a un archivo además de a la consola.</span><span class="sxs-lookup"><span data-stu-id="03962-135">Output migration report to a file in addition to the console.</span></span>

`-s|--skip-project-references [Debug|Release]`

<span data-ttu-id="03962-136">Omite la migración de referencias de proyecto.</span><span class="sxs-lookup"><span data-stu-id="03962-136">Skip migrating project references.</span></span> <span data-ttu-id="03962-137">De forma predeterminada, las referencias de proyecto se migran de forma recursiva.</span><span class="sxs-lookup"><span data-stu-id="03962-137">By default, project references are migrated recursively.</span></span>

`--skip-backup`

<span data-ttu-id="03962-138">Omite el traslado de *project.json*, *global.json* y *\*.xproj* a un directorio `backup` tras la realización correcta de la migración.</span><span class="sxs-lookup"><span data-stu-id="03962-138">Skip moving *project.json*, *global.json*, and *\*.xproj* to a `backup` directory after successful migration.</span></span>

`-t|--template-file <TEMPLATE_FILE>`

<span data-ttu-id="03962-139">Archivo csproj de plantilla que se utilizará para la migración.</span><span class="sxs-lookup"><span data-stu-id="03962-139">Template csproj file to use for migration.</span></span> <span data-ttu-id="03962-140">De forma predeterminada, se usa la misma plantilla que la descartada por `dotnet new console`.</span><span class="sxs-lookup"><span data-stu-id="03962-140">By default, the same template as the one dropped by `dotnet new console` is used.</span></span>

`-v|--sdk-package-version <VERSION>`

<span data-ttu-id="03962-141">La versión del paquete sdk a la que se hace referencia en la aplicación migrada.</span><span class="sxs-lookup"><span data-stu-id="03962-141">The version of the sdk package that's referenced in the migrated app.</span></span> <span data-ttu-id="03962-142">El valor predeterminado es la versión del SDK en `dotnet new`.</span><span class="sxs-lookup"><span data-stu-id="03962-142">The default is the version of the SDK in `dotnet new`.</span></span>

`-x|--xproj-file <FILE>`

<span data-ttu-id="03962-143">La ruta de acceso al archivo xproj que se usará.</span><span class="sxs-lookup"><span data-stu-id="03962-143">The path to the xproj file to use.</span></span> <span data-ttu-id="03962-144">Necesario cuando hay más de un archivo xproj en un directorio de proyecto.</span><span class="sxs-lookup"><span data-stu-id="03962-144">Required when there is more than one xproj in a project directory.</span></span>

## <a name="examples"></a><span data-ttu-id="03962-145">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="03962-145">Examples</span></span>

<span data-ttu-id="03962-146">Migrar un proyecto del directorio actual y todas sus dependencias de proyecto a proyecto:</span><span class="sxs-lookup"><span data-stu-id="03962-146">Migrate a project in the current directory and all of its project-to-project dependencies:</span></span>

`dotnet migrate`

<span data-ttu-id="03962-147">Migrar todos los proyectos que incluyen el archivo *global.json*:</span><span class="sxs-lookup"><span data-stu-id="03962-147">Migrate all projects that *global.json* file includes:</span></span>

`dotnet migrate path/to/global.json`

<span data-ttu-id="03962-148">Migrar solo el proyecto actual y ninguna dependencia de proyecto a proyecto (P2P).</span><span class="sxs-lookup"><span data-stu-id="03962-148">Migrate only the current project and no project-to-project (P2P) dependencies.</span></span> <span data-ttu-id="03962-149">Además, usar una versión específica de SDK:</span><span class="sxs-lookup"><span data-stu-id="03962-149">Also, use a specific SDK version:</span></span>

`dotnet migrate -s -v 1.0.0-preview4`
