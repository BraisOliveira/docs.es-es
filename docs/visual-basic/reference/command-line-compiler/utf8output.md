---
title: -utf8output (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- -utf8output compiler option [Visual Basic]
- utf8output compiler option [Visual Basic]
- /utf8output compiler option [Visual Basic]
ms.assetid: 8ab36b1e-027a-49ac-85b4-f48997d9e4d6
ms.openlocfilehash: 75369c3bcb19afbf98bfb80bc3e439f996d2a9d0
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2019
ms.locfileid: "58833653"
---
# <a name="-utf8output-visual-basic"></a><span data-ttu-id="d6fa8-102">-utf8output (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d6fa8-102">-utf8output (Visual Basic)</span></span>
<span data-ttu-id="d6fa8-103">Muestra los resultados del compilador en codificación UTF-8.</span><span class="sxs-lookup"><span data-stu-id="d6fa8-103">Displays compiler output using UTF-8 encoding.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d6fa8-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d6fa8-104">Syntax</span></span>  
  
```  
-utf8output[+ | -]  
```  
  
## <a name="arguments"></a><span data-ttu-id="d6fa8-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="d6fa8-105">Arguments</span></span>  
 <span data-ttu-id="d6fa8-106">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="d6fa8-106">`+` &#124; `-`</span></span>  
 <span data-ttu-id="d6fa8-107">Opcional.</span><span class="sxs-lookup"><span data-stu-id="d6fa8-107">Optional.</span></span> <span data-ttu-id="d6fa8-108">El valor predeterminado para esta opción es `-utf8output-`, lo que significa que el resultado del compilador no utiliza la codificación UTF-8.</span><span class="sxs-lookup"><span data-stu-id="d6fa8-108">The default for this option is `-utf8output-`, which means compiler output does not use UTF-8 encoding.</span></span> <span data-ttu-id="d6fa8-109">Especificar `-utf8output` es lo mismo que especificar `-utf8output+`.</span><span class="sxs-lookup"><span data-stu-id="d6fa8-109">Specifying `-utf8output` is the same as specifying `-utf8output+`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d6fa8-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d6fa8-110">Remarks</span></span>  
 <span data-ttu-id="d6fa8-111">En algunas configuraciones internacionales, resultados del compilador no pueden mostrarse correctamente en la consola.</span><span class="sxs-lookup"><span data-stu-id="d6fa8-111">In some international configurations, compiler output cannot be displayed correctly in the console.</span></span> <span data-ttu-id="d6fa8-112">En tales situaciones, utilice `-utf8output` y redirigir los resultados del compilador a un archivo.</span><span class="sxs-lookup"><span data-stu-id="d6fa8-112">In such situations, use `-utf8output` and redirect compiler output to a file.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d6fa8-113">El `-utf8output` opción no está disponible en el entorno de desarrollo de Visual Studio; está disponible solo cuando se compila desde la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="d6fa8-113">The `-utf8output` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d6fa8-114">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d6fa8-114">Example</span></span>  
 <span data-ttu-id="d6fa8-115">El siguiente código compila `In.vb` y hace que el compilador para mostrar resultados con la codificación UTF-8.</span><span class="sxs-lookup"><span data-stu-id="d6fa8-115">The following code compiles `In.vb` and directs the compiler to display output using UTF-8 encoding.</span></span>  
  
```console  
vbc -utf8output in.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="d6fa8-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="d6fa8-116">See also</span></span>

- [<span data-ttu-id="d6fa8-117">Compilador de línea de comandos de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="d6fa8-117">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="d6fa8-118">Líneas de comandos de compilación de ejemplo</span><span class="sxs-lookup"><span data-stu-id="d6fa8-118">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
