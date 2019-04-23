---
title: Comando dotnet
description: El comando dotnet pack crea paquetes de NuGet para el proyecto de .NET Core.
ms.date: 12/04/2018
ms.openlocfilehash: 8faa99bf35d9802b16f951082b20644d45a939c7
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/17/2019
ms.locfileid: "59672131"
---
# <a name="dotnet-pack"></a><span data-ttu-id="7af08-103">dotnet pack</span><span class="sxs-lookup"><span data-stu-id="7af08-103">dotnet pack</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="7af08-104">nombre</span><span class="sxs-lookup"><span data-stu-id="7af08-104">Name</span></span>

<span data-ttu-id="7af08-105">`dotnet pack`: empaqueta el código en un paquete de NuGet.</span><span class="sxs-lookup"><span data-stu-id="7af08-105">`dotnet pack` - Packs the code into a NuGet package.</span></span>

## <a name="synopsis"></a><span data-ttu-id="7af08-106">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="7af08-106">Synopsis</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="7af08-107">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="7af08-107">.NET Core 2.x</span></span>](#tab/netcore2x)

```
dotnet pack [<PROJECT>] [-c|--configuration] [--force] [--include-source] [--include-symbols] [--no-build] [--no-dependencies]
    [--no-restore] [-o|--output] [--runtime] [-s|--serviceable] [-v|--verbosity] [--version-suffix]
dotnet pack [-h|--help]
```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="7af08-108">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="7af08-108">.NET Core 1.x</span></span>](#tab/netcore1x)

```
dotnet pack [<PROJECT>] [-c|--configuration] [--include-source] [--include-symbols] [--no-build] [-o|--output]
    [-s|--serviceable] [-v|--verbosity] [--version-suffix]
dotnet pack [-h|--help]
```

---

## <a name="description"></a><span data-ttu-id="7af08-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="7af08-109">Description</span></span>

<span data-ttu-id="7af08-110">El comando `dotnet pack` compila el proyecto y crea paquetes de NuGet.</span><span class="sxs-lookup"><span data-stu-id="7af08-110">The `dotnet pack` command builds the project and creates NuGet packages.</span></span> <span data-ttu-id="7af08-111">El resultado de este comando es un paquete de NuGet.</span><span class="sxs-lookup"><span data-stu-id="7af08-111">The result of this command is a NuGet package.</span></span> <span data-ttu-id="7af08-112">Si la opción `--include-symbols` está presente, se crea otro paquete que contiene los símbolos de depuración.</span><span class="sxs-lookup"><span data-stu-id="7af08-112">If the `--include-symbols` option is present, another package containing the debug symbols is created.</span></span>

<span data-ttu-id="7af08-113">Las dependencias de NuGet del proyecto empaquetado se agregan al archivo *.nuspec*, por lo que se pueden resolver adecuadamente cuando se instala el paquete.</span><span class="sxs-lookup"><span data-stu-id="7af08-113">NuGet dependencies of the packed project are added to the *.nuspec* file, so they're properly resolved when the package is installed.</span></span> <span data-ttu-id="7af08-114">Las referencias de proyecto a proyecto no se empaquetan dentro del proyecto.</span><span class="sxs-lookup"><span data-stu-id="7af08-114">Project-to-project references aren't packaged inside the project.</span></span> <span data-ttu-id="7af08-115">Actualmente, debe disponer de un paquete por proyecto si tiene dependencias de proyecto a proyecto.</span><span class="sxs-lookup"><span data-stu-id="7af08-115">Currently, you must have a package per project if you have project-to-project dependencies.</span></span>

<span data-ttu-id="7af08-116">De forma predeterminada, `dotnet pack` compila primero el proyecto.</span><span class="sxs-lookup"><span data-stu-id="7af08-116">By default, `dotnet pack` builds the project first.</span></span> <span data-ttu-id="7af08-117">Si desea evitar este comportamiento, pase la opción `--no-build`.</span><span class="sxs-lookup"><span data-stu-id="7af08-117">If you wish to avoid this behavior, pass the `--no-build` option.</span></span> <span data-ttu-id="7af08-118">Esta opción a menudo resulta útil en escenarios de compilación de integración continua (CI) donde se conoce el código que se compiló anteriormente.</span><span class="sxs-lookup"><span data-stu-id="7af08-118">This option is often useful in Continuous Integration (CI) build scenarios where you know the code was previously built.</span></span>

<span data-ttu-id="7af08-119">Puede proporcionar propiedades de MSBuild en el comando `dotnet pack` para el proceso de empaquetado.</span><span class="sxs-lookup"><span data-stu-id="7af08-119">You can provide MSBuild properties to the `dotnet pack` command for the packing process.</span></span> <span data-ttu-id="7af08-120">Para obtener más información, vea [Propiedades de metadatos de NuGet](csproj.md#nuget-metadata-properties) y la [Referencia de la línea de comandos de MSBuild](/visualstudio/msbuild/msbuild-command-line-reference).</span><span class="sxs-lookup"><span data-stu-id="7af08-120">For more information, see [NuGet metadata properties](csproj.md#nuget-metadata-properties) and the [MSBuild Command-Line Reference](/visualstudio/msbuild/msbuild-command-line-reference).</span></span> <span data-ttu-id="7af08-121">La sección [Ejemplos](#examples) muestra cómo utilizar el modificador -p de MSBuild en un par de escenarios diferentes.</span><span class="sxs-lookup"><span data-stu-id="7af08-121">The [Examples](#examples) section shows how to use the MSBuild -p switch for a couple of different scenarios.</span></span>

[!INCLUDE[dotnet restore note + options](~/includes/dotnet-restore-note-options.md)]

## <a name="arguments"></a><span data-ttu-id="7af08-122">Argumentos</span><span class="sxs-lookup"><span data-stu-id="7af08-122">Arguments</span></span>

* **`PROJECT`**

  <span data-ttu-id="7af08-123">El proyecto para empaquetar.</span><span class="sxs-lookup"><span data-stu-id="7af08-123">The project to pack.</span></span> <span data-ttu-id="7af08-124">O bien una ruta de acceso a un [archivo csproj](csproj.md) o a un directorio.</span><span class="sxs-lookup"><span data-stu-id="7af08-124">It's either a path to a [csproj file](csproj.md) or to a directory.</span></span> <span data-ttu-id="7af08-125">Si no se especifica, se toma como predeterminado el directorio actual.</span><span class="sxs-lookup"><span data-stu-id="7af08-125">If not specified, it defaults to the current directory.</span></span>

## <a name="options"></a><span data-ttu-id="7af08-126">Opciones</span><span class="sxs-lookup"><span data-stu-id="7af08-126">Options</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="7af08-127">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="7af08-127">.NET Core 2.x</span></span>](#tab/netcore2x)

* **`-c|--configuration {Debug|Release}`**

  <span data-ttu-id="7af08-128">Define la configuración de compilación.</span><span class="sxs-lookup"><span data-stu-id="7af08-128">Defines the build configuration.</span></span> <span data-ttu-id="7af08-129">El valor predeterminado es `Debug`.</span><span class="sxs-lookup"><span data-stu-id="7af08-129">The default value is `Debug`.</span></span>

* **`--force`**

  <span data-ttu-id="7af08-130">Fuerza la resolución de todas las dependencias, incluso si la última restauración se realizó correctamente.</span><span class="sxs-lookup"><span data-stu-id="7af08-130">Forces all dependencies to be resolved even if the last restore was successful.</span></span> <span data-ttu-id="7af08-131">Especificar esta marca es lo mismo que eliminar el archivo *project.assets.json*.</span><span class="sxs-lookup"><span data-stu-id="7af08-131">Specifying this flag is the same as deleting the *project.assets.json* file.</span></span>

* **`-h|--help`**

  <span data-ttu-id="7af08-132">Imprime una corta ayuda para el comando.</span><span class="sxs-lookup"><span data-stu-id="7af08-132">Prints out a short help for the command.</span></span>

* **`--include-source`**

  <span data-ttu-id="7af08-133">Incluye los archivos de origen en el paquete de NuGet.</span><span class="sxs-lookup"><span data-stu-id="7af08-133">Includes the source files in the NuGet package.</span></span> <span data-ttu-id="7af08-134">Los archivos de origen se incluyen en la carpeta `src` dentro de `nupkg`.</span><span class="sxs-lookup"><span data-stu-id="7af08-134">The sources files are included in the `src` folder within the `nupkg`.</span></span>

* **`--include-symbols`**

  <span data-ttu-id="7af08-135">Genera símbolos `nupkg`.</span><span class="sxs-lookup"><span data-stu-id="7af08-135">Generates the symbols `nupkg`.</span></span>

* **`--no-build`**

  <span data-ttu-id="7af08-136">No compila el proyecto antes de empaquetarlo.</span><span class="sxs-lookup"><span data-stu-id="7af08-136">Doesn't build the project before packing.</span></span> <span data-ttu-id="7af08-137">También establece la marca `--no-restore` de forma implícita.</span><span class="sxs-lookup"><span data-stu-id="7af08-137">It also implicitly sets the `--no-restore` flag.</span></span>

* **`--no-dependencies`**

  <span data-ttu-id="7af08-138">Omite las referencias de proyecto a proyecto y solo restaura el proyecto raíz.</span><span class="sxs-lookup"><span data-stu-id="7af08-138">Ignores project-to-project references and only restores the root project.</span></span>

* **`--no-restore`**

  <span data-ttu-id="7af08-139">No ejecuta una restauración implícita al ejecutar el comando.</span><span class="sxs-lookup"><span data-stu-id="7af08-139">Doesn't execute an implicit restore when running the command.</span></span>

* **`-o|--output <OUTPUT_DIRECTORY>`**

  <span data-ttu-id="7af08-140">Coloca los paquetes compilados en el directorio especificado.</span><span class="sxs-lookup"><span data-stu-id="7af08-140">Places the built packages in the directory specified.</span></span>

* **`--runtime <RUNTIME_IDENTIFIER>`**

  <span data-ttu-id="7af08-141">Especifica el tiempo de ejecución de destino para el que restaurar los paquetes.</span><span class="sxs-lookup"><span data-stu-id="7af08-141">Specifies the target runtime to restore packages for.</span></span> <span data-ttu-id="7af08-142">Para obtener una lista de identificadores de tiempo de ejecución (RID), consulte el [catálogo de RID](../rid-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="7af08-142">For a list of Runtime Identifiers (RIDs), see the [RID catalog](../rid-catalog.md).</span></span>

* **`-s|--serviceable`**

  <span data-ttu-id="7af08-143">Establece la marca de servicio en el paquete.</span><span class="sxs-lookup"><span data-stu-id="7af08-143">Sets the serviceable flag in the package.</span></span> <span data-ttu-id="7af08-144">Para más información, consulte [.NET Blog: .NET 4.5.1 Supports Microsoft Security Updates for .NET NuGet Libraries](https://aka.ms/nupkgservicing) (Blog de .NET: .NET 4.5.1 admite actualizaciones de seguridad de Microsoft para bibliotecas NuGet de .NET).</span><span class="sxs-lookup"><span data-stu-id="7af08-144">For more information, see [.NET Blog: .NET 4.5.1 Supports Microsoft Security Updates for .NET NuGet Libraries](https://aka.ms/nupkgservicing).</span></span>

* **`--version-suffix <VERSION_SUFFIX>`**

  <span data-ttu-id="7af08-145">Define el valor de la propiedad de `$(VersionSuffix)` en el proyecto.</span><span class="sxs-lookup"><span data-stu-id="7af08-145">Defines the value for the `$(VersionSuffix)` MSBuild property in the project.</span></span>

* **`-v|--verbosity <LEVEL>`**

  <span data-ttu-id="7af08-146">Establece el nivel de detalle del comando.</span><span class="sxs-lookup"><span data-stu-id="7af08-146">Sets the verbosity level of the command.</span></span> <span data-ttu-id="7af08-147">Los valores permitidos son `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` y `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="7af08-147">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

> [!NOTE]
> <span data-ttu-id="7af08-148">Los proyectos web no están empaquetados de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="7af08-148">Web projects aren't packable by default.</span></span> <span data-ttu-id="7af08-149">Para invalidar el comportamiento predeterminado, agregue la siguiente propiedad a su archivo *.csproj*:</span><span class="sxs-lookup"><span data-stu-id="7af08-149">To override the default behavior, add the following property to your *.csproj* file:</span></span>
>
> ```xml
> <PropertyGroup>
>    <IsPackable>true</IsPackable>
> </PropertyGroup>
> ```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="7af08-150">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="7af08-150">.NET Core 1.x</span></span>](#tab/netcore1x)

* **`-c|--configuration {Debug|Release}`**

  <span data-ttu-id="7af08-151">Define la configuración de compilación.</span><span class="sxs-lookup"><span data-stu-id="7af08-151">Defines the build configuration.</span></span> <span data-ttu-id="7af08-152">El valor predeterminado es `Debug`.</span><span class="sxs-lookup"><span data-stu-id="7af08-152">The default value is `Debug`.</span></span>

* **`-h|--help`**

  <span data-ttu-id="7af08-153">Imprime una corta ayuda para el comando.</span><span class="sxs-lookup"><span data-stu-id="7af08-153">Prints out a short help for the command.</span></span>

* **`--include-source`**

  <span data-ttu-id="7af08-154">Incluye los archivos de origen en el paquete de NuGet.</span><span class="sxs-lookup"><span data-stu-id="7af08-154">Includes the source files in the NuGet package.</span></span> <span data-ttu-id="7af08-155">Los archivos de origen se incluyen en la carpeta `src` dentro de `nupkg`.</span><span class="sxs-lookup"><span data-stu-id="7af08-155">The sources files are included in the `src` folder within the `nupkg`.</span></span>

* **`--include-symbols`**

  <span data-ttu-id="7af08-156">Genera símbolos `nupkg`.</span><span class="sxs-lookup"><span data-stu-id="7af08-156">Generates the symbols `nupkg`.</span></span>

* **`--no-build`**

  <span data-ttu-id="7af08-157">No compila el proyecto antes de empaquetarlo.</span><span class="sxs-lookup"><span data-stu-id="7af08-157">Doesn't build the project before packing.</span></span>

* **`-o|--output <OUTPUT_DIRECTORY>`**

  <span data-ttu-id="7af08-158">Coloca los paquetes compilados en el directorio especificado.</span><span class="sxs-lookup"><span data-stu-id="7af08-158">Places the built packages in the directory specified.</span></span>

* **`-s|--serviceable`**

  <span data-ttu-id="7af08-159">Establece la marca de servicio en el paquete.</span><span class="sxs-lookup"><span data-stu-id="7af08-159">Sets the serviceable flag in the package.</span></span> <span data-ttu-id="7af08-160">Para más información, consulte [.NET Blog: .NET 4.5.1 Supports Microsoft Security Updates for .NET NuGet Libraries](https://aka.ms/nupkgservicing) (Blog de .NET: .NET 4.5.1 admite actualizaciones de seguridad de Microsoft para bibliotecas NuGet de .NET).</span><span class="sxs-lookup"><span data-stu-id="7af08-160">For more information, see [.NET Blog: .NET 4.5.1 Supports Microsoft Security Updates for .NET NuGet Libraries](https://aka.ms/nupkgservicing).</span></span>

* **`--version-suffix <VERSION_SUFFIX>`**

  <span data-ttu-id="7af08-161">Define el valor de la propiedad de `$(VersionSuffix)` en el proyecto.</span><span class="sxs-lookup"><span data-stu-id="7af08-161">Defines the value for the `$(VersionSuffix)` MSBuild property in the project.</span></span>

* **`-v|--verbosity <LEVEL>`**

  <span data-ttu-id="7af08-162">Establece el nivel de detalle del comando.</span><span class="sxs-lookup"><span data-stu-id="7af08-162">Sets the verbosity level of the command.</span></span> <span data-ttu-id="7af08-163">Los valores permitidos son `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` y `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="7af08-163">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

---

## <a name="examples"></a><span data-ttu-id="7af08-164">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="7af08-164">Examples</span></span>

* <span data-ttu-id="7af08-165">Empaquetado del proyecto en el directorio actual:</span><span class="sxs-lookup"><span data-stu-id="7af08-165">Pack the project in the current directory:</span></span>

  ```console
  dotnet pack
  ```

* <span data-ttu-id="7af08-166">Empaquetar el proyecto `app1`:</span><span class="sxs-lookup"><span data-stu-id="7af08-166">Pack the `app1` project:</span></span>

  ```console
  dotnet pack ~/projects/app1/project.csproj
  ```

* <span data-ttu-id="7af08-167">Empaquetar el proyecto en el directorio actual y colocar los paquetes resultantes en la carpeta `nupkgs`:</span><span class="sxs-lookup"><span data-stu-id="7af08-167">Pack the project in the current directory and place the resulting packages into the `nupkgs` folder:</span></span>

  ```console
  dotnet pack --output nupkgs
  ```

* <span data-ttu-id="7af08-168">Empaquetar el proyecto en el directorio actual en la carpeta `nupkgs` y omitir del paso de compilación:</span><span class="sxs-lookup"><span data-stu-id="7af08-168">Pack the project in the current directory into the `nupkgs` folder and skip the build step:</span></span>

  ```console
  dotnet pack --no-build --output nupkgs
  ```

* <span data-ttu-id="7af08-169">Con el sufijo de la versión del proyecto configurado como `<VersionSuffix>$(VersionSuffix)</VersionSuffix>` en el archivo *.csproj*, empaquetar el proyecto actual y actualizar la versión del paquete resultante con el sufijo dado:</span><span class="sxs-lookup"><span data-stu-id="7af08-169">With the project's version suffix configured as `<VersionSuffix>$(VersionSuffix)</VersionSuffix>` in the *.csproj* file, pack the current project and update the resulting package version with the given suffix:</span></span>

  ```console
  dotnet pack --version-suffix "ci-1234"
  ```

* <span data-ttu-id="7af08-170">Establecer la versión del paquete en `2.1.0` con la propiedad de MSBuild `PackageVersion`:</span><span class="sxs-lookup"><span data-stu-id="7af08-170">Set the package version to `2.1.0` with the `PackageVersion` MSBuild property:</span></span>

  ```console
  dotnet pack -p:PackageVersion=2.1.0
  ```

* <span data-ttu-id="7af08-171">Empaquete el proyecto para un determinado [marco de destino](../../standard/frameworks.md):</span><span class="sxs-lookup"><span data-stu-id="7af08-171">Pack the project for a specific [target framework](../../standard/frameworks.md):</span></span>

  ```console
  dotnet pack -p:TargetFrameworks=net45
  ```

* <span data-ttu-id="7af08-172">Empaquete el proyecto y use un tiempo de ejecución específico (Windows 10) para la operación de restauración (SDK de .NET Core 2.0 y versiones superiores):</span><span class="sxs-lookup"><span data-stu-id="7af08-172">Pack the project and use a specific runtime (Windows 10) for the restore operation (.NET Core SDK 2.0 and later versions):</span></span>

  ```console
  dotnet pack --runtime win10-x64
  ```

* <span data-ttu-id="7af08-173">Empaquete el proyecto mediante un [archivo .nuspec](https://docs.microsoft.com/nuget/reference/msbuild-targets#packing-using-a-nuspec):</span><span class="sxs-lookup"><span data-stu-id="7af08-173">Pack the project using a [.nuspec file](https://docs.microsoft.com/nuget/reference/msbuild-targets#packing-using-a-nuspec):</span></span>

  ```console
  dotnet pack ~/projects/app1/project.csproj /p:NuspecFile=~/projects/app1/project.nuspec /p:NuspecBasePath=~/projects/app1/nuget
  ```
