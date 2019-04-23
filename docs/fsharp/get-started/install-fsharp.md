---
title: InstalarF#
description: Obtenga información sobre cómo instalar F# basándose en su entorno.
ms.date: 08/28/2018
ms.openlocfilehash: 792c61c0522cd4d0c68a64572f2892ce33f71ea6
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59331980"
---
# <a name="install-f"></a><span data-ttu-id="a7e6a-103">Instalar F\#</span><span class="sxs-lookup"><span data-stu-id="a7e6a-103">Install F\#</span></span>

<span data-ttu-id="a7e6a-104">Puede instalar F# de varias maneras, dependiendo de su entorno.</span><span class="sxs-lookup"><span data-stu-id="a7e6a-104">You can install F# in multiple ways, depending on your environment.</span></span>

## <a name="install-f-with-visual-studio"></a><span data-ttu-id="a7e6a-105">Instalar F# con Visual Studio</span><span class="sxs-lookup"><span data-stu-id="a7e6a-105">Install F# with Visual Studio</span></span>

<span data-ttu-id="a7e6a-106">Si está descargando [Visual Studio](https://visualstudio.microsoft.com/vs/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link) por primera vez, instalará el instalador de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="a7e6a-106">If you're downloading [Visual Studio](https://visualstudio.microsoft.com/vs/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link) for the first time, it will first install the Visual Studio installer.</span></span> <span data-ttu-id="a7e6a-107">Instale el adecuado SKU de Visual Studio desde el instalador.</span><span class="sxs-lookup"><span data-stu-id="a7e6a-107">Install the appropriate SKU of Visual Studio from the installer.</span></span> <span data-ttu-id="a7e6a-108">Si ya tiene instalado, haga clic en **modificar**.</span><span class="sxs-lookup"><span data-stu-id="a7e6a-108">If you already have it installed, click **Modify**.</span></span>

<span data-ttu-id="a7e6a-109">A continuación verá una lista de las cargas de trabajo.</span><span class="sxs-lookup"><span data-stu-id="a7e6a-109">You'll next see a list of Workloads.</span></span> <span data-ttu-id="a7e6a-110">Seleccione **ASP.NET y desarrollo web** que instalará F# soporte de soporte técnico y .NET Core para proyectos de ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="a7e6a-110">Select **ASP.NET and web development** which will install F# support and .NET Core support for ASP.NET Core projects.</span></span>

<span data-ttu-id="a7e6a-111">A continuación, haga clic en **modificar** en el lado inferior derecho.</span><span class="sxs-lookup"><span data-stu-id="a7e6a-111">Next, click **Modify** in the lower right-hand side.</span></span>  <span data-ttu-id="a7e6a-112">Así instalará todo lo que ha seleccionado.</span><span class="sxs-lookup"><span data-stu-id="a7e6a-112">This will install everything you have selected.</span></span> <span data-ttu-id="a7e6a-113">A continuación, puede abrir Visual Studio 2017 con F# compatibilidad de idioma, haga clic en **iniciar**.</span><span class="sxs-lookup"><span data-stu-id="a7e6a-113">You can then open Visual Studio 2017 with F# language support by clicking **Launch**.</span></span>

## <a name="install-f-with-visual-studio-for-mac"></a><span data-ttu-id="a7e6a-114">Instalar F# con Visual Studio para Mac</span><span class="sxs-lookup"><span data-stu-id="a7e6a-114">Install F# with Visual Studio for Mac</span></span>

<span data-ttu-id="a7e6a-115">F#se instala de forma predeterminada en [Visual Studio para Mac](https://visualstudio.microsoft.com/vs/mac/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link), con independencia de la configuración elija.</span><span class="sxs-lookup"><span data-stu-id="a7e6a-115">F# is installed by default in [Visual Studio for Mac](https://visualstudio.microsoft.com/vs/mac/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link), no matter which configuration you choose.</span></span>

<span data-ttu-id="a7e6a-116">Una vez finalizada la instalación, elija "Iniciar Visual Studio".</span><span class="sxs-lookup"><span data-stu-id="a7e6a-116">After the install completes, choose "Start Visual Studio".</span></span> <span data-ttu-id="a7e6a-117">También puede iniciar a través de Finder de macOS.</span><span class="sxs-lookup"><span data-stu-id="a7e6a-117">You can also launch it through Finder on macOS.</span></span>

## <a name="install-f-with-visual-studio-code"></a><span data-ttu-id="a7e6a-118">Instalar F# con Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="a7e6a-118">Install F# with Visual Studio Code</span></span>

<span data-ttu-id="a7e6a-119">Debe tener [git instalado](https://git-scm.com/download) y está disponible en la ruta de acceso para hacer uso de plantillas de proyecto.</span><span class="sxs-lookup"><span data-stu-id="a7e6a-119">You must have [git installed](https://git-scm.com/download) and available on your PATH to make use of project templates.</span></span> <span data-ttu-id="a7e6a-120">Puede comprobar que está instalado correctamente escribiendo `git --version` en un símbolo del sistema y presione **ENTRAR**.</span><span class="sxs-lookup"><span data-stu-id="a7e6a-120">You can verify that it is installed correctly by typing `git --version` at a command prompt and pressing **Enter**.</span></span>

### <a name="macostabmacos"></a>[<span data-ttu-id="a7e6a-121">macOS</span><span class="sxs-lookup"><span data-stu-id="a7e6a-121">macOS</span></span>](#tab/macos)

<span data-ttu-id="a7e6a-122">[Mono](https://www.mono-project.com) se usa para [ F# interactivo](../tutorials/fsharp-interactive/index.md) admite.</span><span class="sxs-lookup"><span data-stu-id="a7e6a-122">[Mono](https://www.mono-project.com) is used for [F# Interactive](../tutorials/fsharp-interactive/index.md) support.</span></span> <span data-ttu-id="a7e6a-123">La manera más fácil para instalar Mono en macOS es a través de Homebrew.</span><span class="sxs-lookup"><span data-stu-id="a7e6a-123">The easiest way to install Mono on macOS is via Homebrew.</span></span> <span data-ttu-id="a7e6a-124">Basta con escribir lo siguiente en el terminal:</span><span class="sxs-lookup"><span data-stu-id="a7e6a-124">Simply type the following into your terminal:</span></span>

```console
brew install mono
```

<span data-ttu-id="a7e6a-125">Instale también la [SDK de .NET Core](https://www.microsoft.com/net/download).</span><span class="sxs-lookup"><span data-stu-id="a7e6a-125">Also install the [.NET Core SDK](https://www.microsoft.com/net/download).</span></span>

### <a name="linuxtablinux"></a>[<span data-ttu-id="a7e6a-126">Linux</span><span class="sxs-lookup"><span data-stu-id="a7e6a-126">Linux</span></span>](#tab/linux)

<span data-ttu-id="a7e6a-127">[Mono](https://www.mono-project.com) se usa para [ F# interactivo](../tutorials/fsharp-interactive/index.md) admite.</span><span class="sxs-lookup"><span data-stu-id="a7e6a-127">[Mono](https://www.mono-project.com) is used for [F# Interactive](../tutorials/fsharp-interactive/index.md) support.</span></span> <span data-ttu-id="a7e6a-128">Si se encuentra en Debian o Ubuntu, puede utilizar lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="a7e6a-128">If you're on Debian or Ubuntu, you can use the following:</span></span>

```console
sudo apt-get update
sudo apt-get install mono-complete fsharp
```

<span data-ttu-id="a7e6a-129">Instale también la [SDK de .NET Core](https://www.microsoft.com/net/download).</span><span class="sxs-lookup"><span data-stu-id="a7e6a-129">Also install the [.NET Core SDK](https://www.microsoft.com/net/download).</span></span>

### <a name="windowstabwindows"></a>[<span data-ttu-id="a7e6a-130">Windows</span><span class="sxs-lookup"><span data-stu-id="a7e6a-130">Windows</span></span>](#tab/windows)

<span data-ttu-id="a7e6a-131">Instalar [Visual Studio con F# admite](#install-f-with-visual-studio).</span><span class="sxs-lookup"><span data-stu-id="a7e6a-131">Install [Visual Studio with F# support](#install-f-with-visual-studio).</span></span> <span data-ttu-id="a7e6a-132">Esto instala todos los componentes necesarios para escribir, compilar y ejecutar F# código.</span><span class="sxs-lookup"><span data-stu-id="a7e6a-132">This installs all the necessary components to write, compile, and execute F# code.</span></span>

<span data-ttu-id="a7e6a-133">Instale también la [SDK de .NET Core](https://www.microsoft.com/net/download/).</span><span class="sxs-lookup"><span data-stu-id="a7e6a-133">Also install the [.NET Core SDK](https://www.microsoft.com/net/download/).</span></span>

---

<span data-ttu-id="a7e6a-134">A continuación, necesitará [Visual Studio Code](https://code.visualstudio.com) instalado.</span><span class="sxs-lookup"><span data-stu-id="a7e6a-134">You will then need [Visual Studio Code](https://code.visualstudio.com) installed.</span></span>

<span data-ttu-id="a7e6a-135">A continuación, haga clic en el icono de extensiones y busque "Ionide":</span><span class="sxs-lookup"><span data-stu-id="a7e6a-135">Next, click the Extensions icon and search for "Ionide":</span></span>

<span data-ttu-id="a7e6a-136">El complemento solo necesario para F# compatibilidad en Visual Studio Code es [Ionide-fsharp](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-fsharp).</span><span class="sxs-lookup"><span data-stu-id="a7e6a-136">The only plugin required for F# support in Visual Studio Code is [Ionide-fsharp](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-fsharp).</span></span> <span data-ttu-id="a7e6a-137">Sin embargo, también puede instalar [Ionide FALSIFICACIÓN](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-FAKE) obtener [IMITAR](https://fsharp.github.io/FAKE/) admite y [Ionide Paket](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-Paket) para obtener [Paket](https://fsprojects.github.io/Paket/) admite.</span><span class="sxs-lookup"><span data-stu-id="a7e6a-137">However, you can also install [Ionide-FAKE](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-FAKE) to get [FAKE](https://fsharp.github.io/FAKE/) support and [Ionide-Paket](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-Paket) to get [Paket](https://fsprojects.github.io/Paket/) support.</span></span> <span data-ttu-id="a7e6a-138">FALSIFICAR y Paket son adicionales F# herramientas de la Comunidad para crear proyectos y administrar las dependencias, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="a7e6a-138">FAKE and Paket are additional F# community tools for building projects and managing dependencies, respectively.</span></span>
