---
title: -optioncompare
ms.date: 07/20/2015
f1_keywords:
- /optioncompare
- -optioncompare
helpviewer_keywords:
- optioncompare compiler option [Visual Basic]
- -optioncompare compiler option [Visual Basic]
- /optioncompare compiler option [Visual Basic]
ms.assetid: 7237b766-b44d-4cc5-9a3c-885348a7d9e4
ms.openlocfilehash: b88cba4d16c5a770a72b47868d11b16cbba6cae8
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59340443"
---
# <a name="-optioncompare"></a><span data-ttu-id="5bec4-102">-optioncompare</span><span class="sxs-lookup"><span data-stu-id="5bec4-102">-optioncompare</span></span>
<span data-ttu-id="5bec4-103">Especifica la forma en que se realizan las comparaciones de cadenas.</span><span class="sxs-lookup"><span data-stu-id="5bec4-103">Specifies how string comparisons are made.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5bec4-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5bec4-104">Syntax</span></span>  
  
```  
-optioncompare:{binary | text}  
```  
  
## <a name="remarks"></a><span data-ttu-id="5bec4-105">Comentarios</span><span class="sxs-lookup"><span data-stu-id="5bec4-105">Remarks</span></span>  
 <span data-ttu-id="5bec4-106">Puede especificar `-optioncompare` en uno de dos formas: `-optioncompare:binary` usar comparaciones de cadenas binarias y `-optioncompare:text` usar comparaciones de cadenas de texto.</span><span class="sxs-lookup"><span data-stu-id="5bec4-106">You can specify `-optioncompare` in one of two forms: `-optioncompare:binary` to use binary string comparisons, and `-optioncompare:text` to use text string comparisons.</span></span> <span data-ttu-id="5bec4-107">De forma predeterminada, el compilador usa `-optioncompare:binary`.</span><span class="sxs-lookup"><span data-stu-id="5bec4-107">By default, the compiler uses `-optioncompare:binary`.</span></span>  
  
 <span data-ttu-id="5bec4-108">En Microsoft Windows, la página de códigos actual determina el criterio de ordenación binario.</span><span class="sxs-lookup"><span data-stu-id="5bec4-108">In Microsoft Windows, the current code page determines the binary sort order.</span></span> <span data-ttu-id="5bec4-109">Un criterio de ordenación binario típico es como sigue:</span><span class="sxs-lookup"><span data-stu-id="5bec4-109">A typical binary sort order is as follows:</span></span>  
  
 `A < B < E < Z < a < b < e < z < À < Ê < Ø < à < ê < ø`  
  
 <span data-ttu-id="5bec4-110">Las comparaciones de cadenas textuales se basan en un criterio de ordenación de texto de mayúsculas y minúsculas determinado por la configuración regional del sistema.</span><span class="sxs-lookup"><span data-stu-id="5bec4-110">Text-based string comparisons are based on a case-insensitive text sort order determined by your system's locale.</span></span> <span data-ttu-id="5bec4-111">Un criterio de ordenación de texto típico es como sigue:</span><span class="sxs-lookup"><span data-stu-id="5bec4-111">A typical text sort order is as follows:</span></span>  
  
 `(A = a) < (À = à) < (B=b) < (E=e) < (Ê = ê) < (Z=z) < (Ø = ø)`  
  
### <a name="to-set--optioncompare-in-the-visual-studio-ide"></a><span data-ttu-id="5bec4-112">Para establecer - optioncompare en el IDE de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="5bec4-112">To set -optioncompare in the Visual Studio IDE</span></span>  
  
1. <span data-ttu-id="5bec4-113">Seleccione un proyecto en el **Explorador de soluciones**.</span><span class="sxs-lookup"><span data-stu-id="5bec4-113">Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="5bec4-114">En el menú **Proyecto**, haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="5bec4-114">On the **Project** menu, click **Properties**.</span></span>   
  
2. <span data-ttu-id="5bec4-115">Haga clic en la pestaña **Compilar**.</span><span class="sxs-lookup"><span data-stu-id="5bec4-115">Click the **Compile** tab.</span></span>  
  
3. <span data-ttu-id="5bec4-116">Modifique el valor en el **Option Compare** cuadro.</span><span class="sxs-lookup"><span data-stu-id="5bec4-116">Modify the value in the **Option Compare** box.</span></span>  
  
### <a name="to-set--optioncompare-programmatically"></a><span data-ttu-id="5bec4-117">Para establecer mediante programación - optioncompare</span><span class="sxs-lookup"><span data-stu-id="5bec4-117">To set -optioncompare programmatically</span></span>  
  
-   <span data-ttu-id="5bec4-118">Consulte [instrucción Option Compare](../../../visual-basic/language-reference/statements/option-compare-statement.md).</span><span class="sxs-lookup"><span data-stu-id="5bec4-118">See [Option Compare Statement](../../../visual-basic/language-reference/statements/option-compare-statement.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="5bec4-119">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="5bec4-119">Example</span></span>  
 <span data-ttu-id="5bec4-120">El siguiente código compila `ProjFile.vb` y usa comparaciones de cadenas binarias.</span><span class="sxs-lookup"><span data-stu-id="5bec4-120">The following code compiles `ProjFile.vb` and uses binary string comparisons.</span></span>  
  
```console
vbc -optioncompare:binary projFile.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="5bec4-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="5bec4-121">See also</span></span>

- [<span data-ttu-id="5bec4-122">Compilador de línea de comandos de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="5bec4-122">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="5bec4-123">-optionexplicit</span><span class="sxs-lookup"><span data-stu-id="5bec4-123">-optionexplicit</span></span>](../../../visual-basic/reference/command-line-compiler/optionexplicit.md)
- [<span data-ttu-id="5bec4-124">-optionstrict</span><span class="sxs-lookup"><span data-stu-id="5bec4-124">-optionstrict</span></span>](../../../visual-basic/reference/command-line-compiler/optionstrict.md)
- [<span data-ttu-id="5bec4-125">-optioninfer</span><span class="sxs-lookup"><span data-stu-id="5bec4-125">-optioninfer</span></span>](../../../visual-basic/reference/command-line-compiler/optioninfer.md)
- [<span data-ttu-id="5bec4-126">Líneas de comandos de compilación de ejemplo</span><span class="sxs-lookup"><span data-stu-id="5bec4-126">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [<span data-ttu-id="5bec4-127">Option Compare (instrucción)</span><span class="sxs-lookup"><span data-stu-id="5bec4-127">Option Compare Statement</span></span>](../../../visual-basic/language-reference/statements/option-compare-statement.md)
- [<span data-ttu-id="5bec4-128">Valores predeterminados de Visual Basic, Proyectos, Opciones (Cuadro de diálogo)</span><span class="sxs-lookup"><span data-stu-id="5bec4-128">Visual Basic Defaults, Projects, Options Dialog Box</span></span>](/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)
