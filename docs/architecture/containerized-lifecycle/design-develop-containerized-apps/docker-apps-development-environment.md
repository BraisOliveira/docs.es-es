---
title: Entorno de desarrollo para aplicaciones de Docker
description: Familiarícese con las opciones de herramientas de desarrollo más importantes que son compatibles con el ciclo de vida de desarrollo de Docker.
ms.date: 02/15/2019
ms.openlocfilehash: 35236e75f47e830d0970ca9cfd074d9a69e6f85c
ms.sourcegitcommit: 56f1d1203d0075a461a10a301459d3aa452f4f47
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2019
ms.locfileid: "71214294"
---
# <a name="development-environment-for-docker-apps"></a>Entorno de desarrollo para aplicaciones de Docker

## <a name="development-tools-choices-ide-or-editor"></a>Opciones de herramientas de desarrollo: IDE o editor

Con independencia de que prefiera un IDE eficaz y completo, o un editor ligero y ágil, Microsoft le puede ayudar en el desarrollo de aplicaciones de Docker.

### <a name="visual-studio-code-and-docker-cli-cross-platform-tools-for-mac-linux-and-windows"></a>Visual Studio Code y la CLI de Docker (herramientas multiplataforma para Mac, Linux y Windows)

Si prefiere un editor ligero y multiplataforma que admita cualquier lenguaje de programación, puede usar Visual Studio Code y la CLI de Docker. Estos productos proporcionan una experiencia sencilla y sólida que es fundamental para agilizar el flujo de trabajo del desarrollador. Al instalar "Docker para Mac" o "Docker para Windows" (entorno de desarrollo), los desarrolladores de Docker pueden usar una sola CLI de Docker para compilar aplicaciones para Windows o Linux (entorno de tiempo de ejecución). Además, Visual Studio Code admite extensiones para Docker con IntelliSense para archivos Dockerfile y tareas de acceso directo para ejecutar comandos de Docker desde el editor.

> [!NOTE]
> Para descargar Visual Studio Code, vaya a <https://code.visualstudio.com/download>.
>
> Para descargar Docker para Mac y Windows, vaya a <https://www.docker.com/products/docker>.

### <a name="visual-studio-with-docker-tools-windows-development-machine"></a>Visual Studio con herramientas de Docker (equipo de desarrollo de Windows)

Se recomienda usar Visual Studio 2017 (o versiones posteriores) con las herramientas de Docker integradas habilitadas. Con Visual Studio, puede desarrollar, ejecutar y validar las aplicaciones directamente en el entorno de Docker seleccionado. Presione F5 para depurar la aplicación (de un solo contenedor o de varios contenedores) directamente en un host de Docker, o bien presione CTRL+F5 para editar y actualizar la aplicación sin tener que volver a compilar el contenedor. Esta es la opción más sencilla y más eficaz para los desarrolladores de Windows que crean contenedores de Docker para Linux o Windows.

### <a name="visual-studio-for-mac-mac-development-machine"></a>Visual Studio para Mac (equipo de desarrollo de Mac)

Puede usar [Visual Studio para Mac](https://visualstudio.microsoft.com/vs/mac/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link) al desarrollar aplicaciones basadas en Docker. Visual Studio para Mac ofrece un IDE más completo en comparación con Visual Studio Code para Mac.

## <a name="language-and-framework-choices"></a>Opciones de lenguaje y marco

Puede desarrollar aplicaciones de Docker mediante el uso de herramientas de Microsoft con los lenguajes más modernos. A continuación se muestra una lista inicial, aunque no está limitado a ella:

- .NET Core y ASP.NET Core
- Node.js
- Ir
- Java
- Ruby
- Python

Básicamente, puede usar cualquier lenguaje moderno compatible con Docker en Linux o Windows.

>[!div class="step-by-step"]
>[Anterior](deploy-azure-kubernetes-service.md)
>[Siguiente](docker-apps-inner-loop-workflow.md)
