---
title: Procedimiento Contraer y ocultar secciones de código (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic, code collapsing
- Visual Basic, code hiding
- Visual Basic code, collapsing and hiding
ms.assetid: b770e8f5-e07d-491a-ab4b-a977980f9ba2
ms.openlocfilehash: bf2a7188456097ac227039e4d902a14eb182664c
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "58822306"
---
# <a name="how-to-collapse-and-hide-sections-of-code-visual-basic"></a><span data-ttu-id="89906-102">Procedimiento Contraer y ocultar secciones de código (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="89906-102">How to: Collapse and Hide Sections of Code (Visual Basic)</span></span>
<span data-ttu-id="89906-103">El `#Region` directiva le permite contraer y ocultar secciones de código en archivos de Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="89906-103">The `#Region` directive enables you to collapse and hide sections of code in Visual Basic files.</span></span> <span data-ttu-id="89906-104">El `#Region` directiva le permite especificar un bloque de código que se puede expandir o contraer cuando se usa el editor de código de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="89906-104">The `#Region` directive lets you specify a block of code that you can expand or collapse when using the Visual Studio code editor.</span></span> <span data-ttu-id="89906-105">La capacidad de ocultar selectivamente el código hace que los archivos más fáciles de administrar y más fácil de leer.</span><span class="sxs-lookup"><span data-stu-id="89906-105">The ability to hide code selectively makes your files more manageable and easier to read.</span></span> <span data-ttu-id="89906-106">Para obtener más información, vea [Esquematización](/visualstudio/ide/outlining).</span><span class="sxs-lookup"><span data-stu-id="89906-106">For more information, see [Outlining](/visualstudio/ide/outlining).</span></span>  
  
 <span data-ttu-id="89906-107">`#Region` las directivas son compatibles con semántica del bloque de código como `#If...#End If`.</span><span class="sxs-lookup"><span data-stu-id="89906-107">`#Region` directives support code block semantics such as `#If...#End If`.</span></span> <span data-ttu-id="89906-108">Esto significa que no se pueden empezar en un bloque y terminar en otra; en el mismo bloque deben ser el inicio y finalización.</span><span class="sxs-lookup"><span data-stu-id="89906-108">This means they cannot begin in one block and end in another; the start and end must be in the same block.</span></span> <span data-ttu-id="89906-109">`#Region` no se admiten directivas dentro de las funciones.</span><span class="sxs-lookup"><span data-stu-id="89906-109">`#Region` directives are not supported within functions.</span></span>  
  
### <a name="to-collapse-and-hide-a-section-of-code"></a><span data-ttu-id="89906-110">Para contraer y ocultar una sección de código</span><span class="sxs-lookup"><span data-stu-id="89906-110">To collapse and hide a section of code</span></span>  
  
-   <span data-ttu-id="89906-111">Coloque la sección de código entre la `#Region` y `#End Region` instrucciones, como en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="89906-111">Place the section of code between the `#Region` and `#End Region` statements, as in the following example:</span></span>  
  
     [!code-vb[VbVbalrConditionalComp#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrConditionalComp/VB/Class1.vb#6)]  
  
     <span data-ttu-id="89906-112">El `#Region` bloque se puede usar varias veces en un archivo de código; por lo tanto, los usuarios pueden definir sus propios bloques de procedimientos y las clases que a su vez, se pueden contraer.</span><span class="sxs-lookup"><span data-stu-id="89906-112">The `#Region` block can be used multiple times in a code file; thus, users can define their own blocks of procedures and classes that can, in turn, be collapsed.</span></span> <span data-ttu-id="89906-113">`#Region` También pueden anidarse dentro de otros bloques `#Region` bloques.</span><span class="sxs-lookup"><span data-stu-id="89906-113">`#Region` blocks can also be nested within other `#Region` blocks.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="89906-114">Ocultar el código no evita que se está compilando y no afecta a `#If...#End If` instrucciones.</span><span class="sxs-lookup"><span data-stu-id="89906-114">Hiding code does not prevent it from being compiled and does not affect `#If...#End If` statements.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="89906-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="89906-115">See also</span></span>

- [<span data-ttu-id="89906-116">Compilación condicional</span><span class="sxs-lookup"><span data-stu-id="89906-116">Conditional Compilation</span></span>](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)
- [<span data-ttu-id="89906-117">#Region (directiva)</span><span class="sxs-lookup"><span data-stu-id="89906-117">#Region Directive</span></span>](../../../visual-basic/language-reference/directives/region-directive.md)
- [<span data-ttu-id="89906-118">#If...Then...#Else (directivas)</span><span class="sxs-lookup"><span data-stu-id="89906-118">#If...Then...#Else Directives</span></span>](../../../visual-basic/language-reference/directives/if-then-else-directives.md)
- [<span data-ttu-id="89906-119">Esquematización</span><span class="sxs-lookup"><span data-stu-id="89906-119">Outlining</span></span>](/visualstudio/ide/outlining)
