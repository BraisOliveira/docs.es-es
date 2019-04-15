---
title: -main (Opciones del compilador de C#)
ms.date: 07/20/2015
f1_keywords:
- /main
helpviewer_keywords:
- -main compiler option [C#]
- main compiler option [C#]
- /main compiler option [C#]
ms.assetid: 975cf4d5-36ac-4530-826c-4aad0c7f2049
ms.openlocfilehash: 133aa22f16285f94f58722cb18c83b96f1ff885c
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/09/2019
ms.locfileid: "59302795"
---
# <a name="-main-c-compiler-options"></a><span data-ttu-id="203d3-102">-main (Opciones del compilador de C#)</span><span class="sxs-lookup"><span data-stu-id="203d3-102">-main (C# Compiler Options)</span></span>
<span data-ttu-id="203d3-103">Esta opción especifica la clase que contiene el punto de entrada al programa si hay más de una clase que contenga un método **Main**.</span><span class="sxs-lookup"><span data-stu-id="203d3-103">This option specifies the class that contains the entry point to the program, if more than one class contains a **Main** method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="203d3-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="203d3-104">Syntax</span></span>  
  
```console  
-main:class  
```  
  
## <a name="arguments"></a><span data-ttu-id="203d3-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="203d3-105">Arguments</span></span>  
 `class`  
 <span data-ttu-id="203d3-106">Tipo que contiene el método **Main**.</span><span class="sxs-lookup"><span data-stu-id="203d3-106">The type that contains the **Main** method.</span></span>  
 <span data-ttu-id="203d3-107">El nombre de clase proporcionado debe ser completo: debe incluir el espacio de nombres completo que contiene la clase, seguido del nombre de clase.</span><span class="sxs-lookup"><span data-stu-id="203d3-107">The provided class name must be fully qualified; it must include the full namespace containing the class, followed by the class name.</span></span> <span data-ttu-id="203d3-108">Por ejemplo, cuando el método `Main` se encuentra dentro de la clase `Program` en el espacio de nombres `MyApplication.Core`, la opción del compilador tiene que ser `-main:MyApplication.Core.Program`.</span><span class="sxs-lookup"><span data-stu-id="203d3-108">For example, when the `Main` method is located inside the `Program` class in the `MyApplication.Core` namespace, the compiler option has to be `-main:MyApplication.Core.Program`.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="203d3-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="203d3-109">Remarks</span></span>  
 <span data-ttu-id="203d3-110">Si la compilación incluye más de un tipo con un método [Main](../../../csharp/programming-guide/main-and-command-args/index.md), puede especificar el tipo que contiene el método **Main** que quiere usar como punto de entrada en el programa.</span><span class="sxs-lookup"><span data-stu-id="203d3-110">If your compilation includes more than one type with a [Main](../../../csharp/programming-guide/main-and-command-args/index.md) method, you can specify which type contains the **Main** method that you want to use as the entry point into the program.</span></span>  
  
 <span data-ttu-id="203d3-111">Esta opción se usa al compilar un archivo .exe.</span><span class="sxs-lookup"><span data-stu-id="203d3-111">This option is for use when compiling an .exe file.</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="203d3-112">Para establecer esta opción del compilador en el entorno de desarrollo de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="203d3-112">To set this compiler option in the Visual Studio development environment</span></span>  
  
1. <span data-ttu-id="203d3-113">Abra la página **Propiedades** del proyecto.</span><span class="sxs-lookup"><span data-stu-id="203d3-113">Open the project's **Properties** page.</span></span>  
  
2. <span data-ttu-id="203d3-114">Haga clic en la página de propiedades **Aplicación**.</span><span class="sxs-lookup"><span data-stu-id="203d3-114">Click the **Application** property page.</span></span>  
  
3. <span data-ttu-id="203d3-115">Modifique la propiedad **Objeto de inicio**.</span><span class="sxs-lookup"><span data-stu-id="203d3-115">Modify the **Startup object** property.</span></span>  
  
     <span data-ttu-id="203d3-116">Para establecer esta opción del compilador mediante programación, vea <xref:VSLangProj80.ProjectProperties3.StartupObject%2A>.</span><span class="sxs-lookup"><span data-stu-id="203d3-116">To set this compiler option programmatically, see <xref:VSLangProj80.ProjectProperties3.StartupObject%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="203d3-117">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="203d3-117">Example</span></span>  
 <span data-ttu-id="203d3-118">Compile `t2.cs` y `t3.cs` y especifique que el método **Main** se encuentra en `Test2`:</span><span class="sxs-lookup"><span data-stu-id="203d3-118">Compile `t2.cs` and `t3.cs`, specifying that the **Main** method will be found in `Test2`:</span></span>  
  
```console  
csc t2.cs t3.cs -main:Test2  
```  
  
## <a name="see-also"></a><span data-ttu-id="203d3-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="203d3-119">See also</span></span>

- [<span data-ttu-id="203d3-120">Opciones del compilador de C#</span><span class="sxs-lookup"><span data-stu-id="203d3-120">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)
- [<span data-ttu-id="203d3-121">Administrar propiedades de soluciones y proyectos</span><span class="sxs-lookup"><span data-stu-id="203d3-121">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
