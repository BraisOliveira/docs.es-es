---
title: Crear un proyecto de LINQ to DataSet en Visual Studio
ms.date: 08/15/2018
ms.assetid: 49ba6cb0-cdd2-4571-aeaa-25bf0f40e9b3
ms.openlocfilehash: 22763d3b9581d09d7bdda0c09480f8d36bb8e2ec
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61667057"
---
# <a name="how-to-create-a-linq-to-dataset-project-in-visual-studio"></a><span data-ttu-id="b6925-102">Procedimiento Crear un proyecto de LINQ to DataSet en Visual Studio</span><span class="sxs-lookup"><span data-stu-id="b6925-102">How to: Create a LINQ to DataSet project In Visual Studio</span></span>

<span data-ttu-id="b6925-103">Los distintos tipos de proyectos LINQ requieren determinadas referencias a ensamblados y espacios de nombres importados (Visual Basic) o [mediante](../../../csharp/language-reference/keywords/using-directive.md) directivas (C#).</span><span class="sxs-lookup"><span data-stu-id="b6925-103">The different types of LINQ projects require certain assembly references and imported namespaces (Visual Basic) or [using](../../../csharp/language-reference/keywords/using-directive.md) directives (C#).</span></span> <span data-ttu-id="b6925-104">El requisito mínimo para LINQ es una referencia a *System.Core.dll* y un `using` directiva <xref:System.Linq>.</span><span class="sxs-lookup"><span data-stu-id="b6925-104">The minimum requirement for LINQ is a reference to *System.Core.dll* and a `using` directive for <xref:System.Linq>.</span></span>

<span data-ttu-id="b6925-105">Estos requisitos se proporcionan de forma predeterminada si crea un nuevo proyecto de aplicación de consola de C# en Visual Studio 2017.</span><span class="sxs-lookup"><span data-stu-id="b6925-105">These requirements are supplied by default if you create a new C# console app project in Visual Studio 2017.</span></span> <span data-ttu-id="b6925-106">Si está actualizando un proyecto desde una versión anterior de Visual Studio, es posible que deba proporcionar estas referencias relacionadas con LINQ de forma manual.</span><span class="sxs-lookup"><span data-stu-id="b6925-106">If you're upgrading a project from an earlier version of Visual Studio, you might have to supply these LINQ-related references manually.</span></span>

<span data-ttu-id="b6925-107">LINQ a conjunto de datos requiere dos referencias adicionales a *System.Data.dll* y *System.Data.DataSetExtensions.dll*.</span><span class="sxs-lookup"><span data-stu-id="b6925-107">LINQ to DataSet requires two additional references to *System.Data.dll* and *System.Data.DataSetExtensions.dll*.</span></span>

> [!NOTE]
> <span data-ttu-id="b6925-108">Si va a crear desde un símbolo del sistema, deben hacer referencia manualmente las DLL relacionadas con LINQ en *%ProgramFiles%\Reference Assemblies\Microsoft\Framework\v3.5*.</span><span class="sxs-lookup"><span data-stu-id="b6925-108">If you're building from a command prompt, you must manually reference the LINQ-related DLLs in *%ProgramFiles%\Reference Assemblies\Microsoft\Framework\v3.5*.</span></span>

## <a name="to-enable-linq-to-dataset-functionality"></a><span data-ttu-id="b6925-109">Para habilitar la funcionalidad LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="b6925-109">To enable LINQ to DataSet functionality</span></span>

<span data-ttu-id="b6925-110">Siga estos pasos para habilitar LINQ a la funcionalidad del conjunto de datos en un proyecto existente.</span><span class="sxs-lookup"><span data-stu-id="b6925-110">Follow these steps to enable LINQ to DataSet functionality in an existing project.</span></span>

1. <span data-ttu-id="b6925-111">Agregue referencias a **System.Core**, **System.Data**, y **System.Data.DataSetExtensions**.</span><span class="sxs-lookup"><span data-stu-id="b6925-111">Add references to **System.Core**, **System.Data**, and **System.Data.DataSetExtensions**.</span></span>

   <span data-ttu-id="b6925-112">En **el Explorador de soluciones**, haga doble clic en el **referencias** nodo y seleccione **Agregar referencia**.</span><span class="sxs-lookup"><span data-stu-id="b6925-112">In **Solution Explorer**, right-click on the **References** node and select **Add Reference**.</span></span> <span data-ttu-id="b6925-113">En el **Administrador de referencias** cuadro de diálogo, seleccione **System.Core**, **System.Data**, y **System.Data.DataSetExtensions**.</span><span class="sxs-lookup"><span data-stu-id="b6925-113">In the **Reference Manager** dialog box, select **System.Core**, **System.Data**, and **System.Data.DataSetExtensions**.</span></span> <span data-ttu-id="b6925-114">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="b6925-114">Select **OK**.</span></span>

1. <span data-ttu-id="b6925-115">Agregar [mediante](../../../csharp/language-reference/keywords/using-directive.md) directivas (o [instrucciones Imports](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) en Visual Basic) para **System.Data** y **System.Linq**.</span><span class="sxs-lookup"><span data-stu-id="b6925-115">Add [using](../../../csharp/language-reference/keywords/using-directive.md) directives (or [Imports statements](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) in Visual Basic) for **System.Data** and **System.Linq**.</span></span>

   ```csharp
   using System.Data;
   using System.Linq;
   ```

1. <span data-ttu-id="b6925-116">Opcionalmente, agregue un `using` directiva (o `Imports` instrucción) para **System.Data.Common** o **System.Data.SqlClient**, dependiendo de cómo conectarse a la base de datos.</span><span class="sxs-lookup"><span data-stu-id="b6925-116">Optionally, add a `using` directive (or `Imports` statement) for **System.Data.Common** or **System.Data.SqlClient**, depending on how you connect to the database.</span></span>

## <a name="see-also"></a><span data-ttu-id="b6925-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="b6925-117">See also</span></span>

- [<span data-ttu-id="b6925-118">Empezar a trabajar con LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="b6925-118">Get started with LINQ to DataSet</span></span>](../../../../docs/framework/data/adonet/getting-started-linq-to-dataset.md)
