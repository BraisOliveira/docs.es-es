---
title: -nowarn (Opciones del compilador de C#)
ms.date: 07/20/2015
f1_keywords:
- /nowarn
helpviewer_keywords:
- nowarn compiler option [C#]
- /nowarn compiler option [C#]
- -nowarn compiler option [C#]
ms.assetid: 6dcbc5e8-ae67-4566-9df3-f63cfdd9c4e4
ms.openlocfilehash: 13bb50366d9c19751ef3387baf809ab69e27b5dc
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59324154"
---
# <a name="-nowarn-c-compiler-options"></a><span data-ttu-id="fbc32-102">-nowarn (Opciones del compilador de C#)</span><span class="sxs-lookup"><span data-stu-id="fbc32-102">-nowarn (C# Compiler Options)</span></span>
<span data-ttu-id="fbc32-103">La opción **-nowarn** permite impedir que el compilador muestre una o más advertencias.</span><span class="sxs-lookup"><span data-stu-id="fbc32-103">The **-nowarn** option lets you suppress the compiler from displaying one or more warnings.</span></span> <span data-ttu-id="fbc32-104">Separe varios números de advertencia con una coma.</span><span class="sxs-lookup"><span data-stu-id="fbc32-104">Separate multiple warning numbers with a comma.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fbc32-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="fbc32-105">Syntax</span></span>  
  
```console  
-nowarn:number1[,number2,...]  
```  
  
## <a name="arguments"></a><span data-ttu-id="fbc32-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="fbc32-106">Arguments</span></span>  
 <span data-ttu-id="fbc32-107">`number1`, `number2`</span><span class="sxs-lookup"><span data-stu-id="fbc32-107">`number1`, `number2`</span></span>  
 <span data-ttu-id="fbc32-108">Números de advertencia que quiere que el compilador suprima.</span><span class="sxs-lookup"><span data-stu-id="fbc32-108">Warning number(s) that you want the compiler to suppress.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fbc32-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="fbc32-109">Remarks</span></span>  
 <span data-ttu-id="fbc32-110">Solo debe especificar la parte numérica del identificador de advertencia.</span><span class="sxs-lookup"><span data-stu-id="fbc32-110">You should only specify the numeric part of the warning identifier.</span></span> <span data-ttu-id="fbc32-111">Por ejemplo, si quiere suprimir CS0028, puede especificar `-nowarn:28`.</span><span class="sxs-lookup"><span data-stu-id="fbc32-111">For example, if you want to suppress CS0028, you could specify `-nowarn:28`.</span></span>  
  
 <span data-ttu-id="fbc32-112">El compilador omitirá silenciosamente los números de advertencia pasados a `-nowarn` que eran válidos en versiones anteriores, pero que se han quitado del compilador.</span><span class="sxs-lookup"><span data-stu-id="fbc32-112">The compiler will silently ignore warning numbers passed to `-nowarn` that were valid in previous releases, but that have been removed from the compiler.</span></span> <span data-ttu-id="fbc32-113">Por ejemplo, CS0679 era válido en el compilador de Visual Studio .NET 2002, pero se ha eliminado posteriormente.</span><span class="sxs-lookup"><span data-stu-id="fbc32-113">For example, CS0679 was valid in the compiler in Visual Studio .NET 2002 but was subsequently removed.</span></span>  
  
 <span data-ttu-id="fbc32-114">Las advertencias siguientes no se pueden suprimir mediante la opción `-nowarn`:</span><span class="sxs-lookup"><span data-stu-id="fbc32-114">The following warnings cannot be suppressed by the `-nowarn` option:</span></span>  
  
-   <span data-ttu-id="fbc32-115">Advertencia del compilador (nivel 1) CS2002</span><span class="sxs-lookup"><span data-stu-id="fbc32-115">Compiler Warning (level 1) CS2002</span></span>  
  
-   <span data-ttu-id="fbc32-116">Advertencia del compilador (nivel 1) CS2023</span><span class="sxs-lookup"><span data-stu-id="fbc32-116">Compiler Warning (level 1) CS2023</span></span>  
  
-   <span data-ttu-id="fbc32-117">Advertencia del compilador (nivel 1) CS2029</span><span class="sxs-lookup"><span data-stu-id="fbc32-117">Compiler Warning (level 1) CS2029</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="fbc32-118">Para establecer esta opción del compilador en el entorno de desarrollo de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="fbc32-118">To set this compiler option in the Visual Studio development environment</span></span>  
  
1. <span data-ttu-id="fbc32-119">Abra la página **Propiedades** del proyecto.</span><span class="sxs-lookup"><span data-stu-id="fbc32-119">Open the **Properties** page for the project.</span></span> <span data-ttu-id="fbc32-120">Para obtener más información, vea [Compilar (Página, Diseñador de proyectos) (C#)](/visualstudio/ide/reference/build-page-project-designer-csharp).</span><span class="sxs-lookup"><span data-stu-id="fbc32-120">For details, see [Build Page, Project Designer (C#)](/visualstudio/ide/reference/build-page-project-designer-csharp).</span></span>  
  
2. <span data-ttu-id="fbc32-121">Haga clic en la página de propiedades de **Compilar**.</span><span class="sxs-lookup"><span data-stu-id="fbc32-121">Click the **Build** property page.</span></span>  
  
3. <span data-ttu-id="fbc32-122">Modifique la propiedad **Suprimir advertencias**.</span><span class="sxs-lookup"><span data-stu-id="fbc32-122">Modify the **Suppress Warnings** property.</span></span>  
  
 <span data-ttu-id="fbc32-123">Para obtener información sobre cómo establecer esta opción del compilador mediante programación, vea <xref:VSLangProj80.ProjectProperties3.DelaySign%2A>.</span><span class="sxs-lookup"><span data-stu-id="fbc32-123">For information about how to set this compiler option programmatically, see <xref:VSLangProj80.ProjectProperties3.DelaySign%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fbc32-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="fbc32-124">See also</span></span>

- [<span data-ttu-id="fbc32-125">Opciones del compilador de C#</span><span class="sxs-lookup"><span data-stu-id="fbc32-125">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)
- [<span data-ttu-id="fbc32-126">Administrar propiedades de soluciones y proyectos</span><span class="sxs-lookup"><span data-stu-id="fbc32-126">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
- [<span data-ttu-id="fbc32-127">Errores del compilador de C#</span><span class="sxs-lookup"><span data-stu-id="fbc32-127">C# Compiler Errors</span></span>](../../../csharp/language-reference/compiler-messages/index.md)
