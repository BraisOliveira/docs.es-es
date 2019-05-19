---
ms.openlocfilehash: 497ac09e5c9a10470d3ae1932d7e3dc114d121dd
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "65632016"
---
> [!NOTE]
> <span data-ttu-id="08872-101">A partir de .NET Core 2.0, no es necesario ejecutar [`dotnet restore`](~/docs/core/tools/dotnet-restore.md) porque se ejecuta implícitamente por todos los comandos, como `dotnet build` y `dotnet run`, que requieren que se produzca una restauración.</span><span class="sxs-lookup"><span data-stu-id="08872-101">Starting with .NET Core 2.0, you don't have to run [`dotnet restore`](~/docs/core/tools/dotnet-restore.md) because it's run implicitly by all commands, such as `dotnet build` and `dotnet run`, that require a restore to occur.</span></span> <span data-ttu-id="08872-102">Sigue siendo un comando válido en algunos escenarios donde tiene sentido realizar una restauración explícita, como las [compilaciones de integración continua en Azure DevOps Services](/azure/devops/build-release/apps/aspnet/build-aspnet-core) o en los sistemas de compilación que necesitan controlar explícitamente la hora a la que se produce la restauración.</span><span class="sxs-lookup"><span data-stu-id="08872-102">It's still a valid command in certain scenarios where doing an explicit restore makes sense, such as [continuous integration builds in Azure DevOps Services](/azure/devops/build-release/apps/aspnet/build-aspnet-core) or in build systems that need to explicitly control the time at which the restore occurs.</span></span>
>
> <span data-ttu-id="08872-103">Este comando también admite las opciones `dotnet restore` cuando se pasan con el formato largo (por ejemplo, `--source`).</span><span class="sxs-lookup"><span data-stu-id="08872-103">This command also supports the `dotnet restore` options when passed in the long form (for example, `--source`).</span></span> <span data-ttu-id="08872-104">No se admiten las opciones de formato corto, como `-s`.</span><span class="sxs-lookup"><span data-stu-id="08872-104">Short form options, such as `-s`, are not supported.</span></span>
