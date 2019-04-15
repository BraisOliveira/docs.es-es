---
title: -unsafe (Opciones del compilador de C#)
ms.date: 04/25/2018
f1_keywords:
- /unsafe
helpviewer_keywords:
- -unsafe compiler option [C#]
- unsafe compiler option [C#]
- /unsafe compiler option [C#]
ms.openlocfilehash: 4cfd7c82bc2cbf816164b235642c0647eeb7e5b6
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/09/2019
ms.locfileid: "59337336"
---
# <a name="-unsafe-c-compiler-options"></a><span data-ttu-id="23bfd-102">-unsafe (Opciones del compilador de C#)</span><span class="sxs-lookup"><span data-stu-id="23bfd-102">-unsafe (C# Compiler Options)</span></span>
<span data-ttu-id="23bfd-103">La opción del compilador **-unsafe** permite la compilación de código en el que se usa la palabra clave [unsafe](../../../csharp/language-reference/keywords/unsafe.md).</span><span class="sxs-lookup"><span data-stu-id="23bfd-103">The **-unsafe** compiler option allows code that uses the [unsafe](../../../csharp/language-reference/keywords/unsafe.md) keyword to compile.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="23bfd-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="23bfd-104">Syntax</span></span>  
  
```console  
-unsafe  
```  
  
## <a name="remarks"></a><span data-ttu-id="23bfd-105">Comentarios</span><span class="sxs-lookup"><span data-stu-id="23bfd-105">Remarks</span></span>  
 <span data-ttu-id="23bfd-106">Para obtener más información sobre el código no seguro, vea [Código no seguro y punteros](../../../csharp/programming-guide/unsafe-code-pointers/index.md).</span><span class="sxs-lookup"><span data-stu-id="23bfd-106">For more information about unsafe code, see [Unsafe Code and Pointers](../../../csharp/programming-guide/unsafe-code-pointers/index.md).</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="23bfd-107">Para establecer esta opción del compilador en el entorno de desarrollo de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="23bfd-107">To set this compiler option in the Visual Studio development environment</span></span>  
  
1. <span data-ttu-id="23bfd-108">Abra la página **Propiedades** del proyecto.</span><span class="sxs-lookup"><span data-stu-id="23bfd-108">Open the project's **Properties** page.</span></span>  
  
2. <span data-ttu-id="23bfd-109">Haga clic en la página de propiedades de **Compilar**.</span><span class="sxs-lookup"><span data-stu-id="23bfd-109">Click the **Build** property page.</span></span>  
  
3. <span data-ttu-id="23bfd-110">Active la casilla **Permitir código no seguro**.</span><span class="sxs-lookup"><span data-stu-id="23bfd-110">Select the **Allow Unsafe Code** check box.</span></span>  
  
### <a name="to-add-this-option-in-a-csproj-file"></a><span data-ttu-id="23bfd-111">Para agregar esta opción en un archivo csproj</span><span class="sxs-lookup"><span data-stu-id="23bfd-111">To add this option in a csproj file</span></span>

<span data-ttu-id="23bfd-112">Abra el archivo .csproj de un proyecto y agregue los siguientes elementos:</span><span class="sxs-lookup"><span data-stu-id="23bfd-112">Open the .csproj file for a project, and add the following elements:</span></span>

```xml
  <PropertyGroup>
    <AllowUnsafeBlocks>true</AllowUnsafeBlocks>
  </PropertyGroup>
```

 <span data-ttu-id="23bfd-113">Para obtener información sobre cómo establecer esta opción del compilador mediante programación, vea <xref:VSLangProj80.CSharpProjectConfigurationProperties3.AllowUnsafeBlocks%2A>.</span><span class="sxs-lookup"><span data-stu-id="23bfd-113">For information about how to set this compiler option programmatically, see <xref:VSLangProj80.CSharpProjectConfigurationProperties3.AllowUnsafeBlocks%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="23bfd-114">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="23bfd-114">Example</span></span>  
 <span data-ttu-id="23bfd-115">Compile `in.cs` para el modo no seguro:</span><span class="sxs-lookup"><span data-stu-id="23bfd-115">Compile `in.cs` for unsafe mode:</span></span>  
  
```console  
csc -unsafe in.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="23bfd-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="23bfd-116">See also</span></span>

- [<span data-ttu-id="23bfd-117">Opciones del compilador de C#</span><span class="sxs-lookup"><span data-stu-id="23bfd-117">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)
- [<span data-ttu-id="23bfd-118">Administrar propiedades de soluciones y proyectos</span><span class="sxs-lookup"><span data-stu-id="23bfd-118">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
