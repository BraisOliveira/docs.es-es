---
title: '#Directiva de región (Visual Basic)'
ms.date: 07/20/2015
f1_keywords:
- vb.Region
- vb.#Region
helpviewer_keywords:
- Visual Basic compiler, compiler directives
- '#region directive'
- region directive (#region)
- '#Region keyword [Visual Basic]'
ms.assetid: 90a6a104-3cbf-47d0-bdc4-b585d0921b87
ms.openlocfilehash: eaaf0f8279ec905767be3f364a88357f0d393bba
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61812650"
---
# <a name="region-directive"></a><span data-ttu-id="cb1ac-102">#Region (Directiva)</span><span class="sxs-lookup"><span data-stu-id="cb1ac-102">#Region Directive</span></span>
<span data-ttu-id="cb1ac-103">Contrae y oculta secciones de código en archivos de Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="cb1ac-103">Collapses and hides sections of code in Visual Basic files.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cb1ac-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="cb1ac-104">Syntax</span></span>  

```vb
#Region "identifier_string"  
#End Region  
```  
  
## <a name="parts"></a><span data-ttu-id="cb1ac-105">Elementos</span><span class="sxs-lookup"><span data-stu-id="cb1ac-105">Parts</span></span>  
  
|<span data-ttu-id="cb1ac-106">Término</span><span class="sxs-lookup"><span data-stu-id="cb1ac-106">Term</span></span>|<span data-ttu-id="cb1ac-107">Definición</span><span class="sxs-lookup"><span data-stu-id="cb1ac-107">Definition</span></span>|  
|---|---|  
|`identifier_string`|<span data-ttu-id="cb1ac-108">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="cb1ac-108">Required.</span></span> <span data-ttu-id="cb1ac-109">Cadena que actúa como título de una región cuando esta se contrae.</span><span class="sxs-lookup"><span data-stu-id="cb1ac-109">String that acts as the title of a region when it is collapsed.</span></span> <span data-ttu-id="cb1ac-110">Las regiones están contraídas de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="cb1ac-110">Regions are collapsed by default.</span></span>|  
|`#End Region`|<span data-ttu-id="cb1ac-111">Finaliza el bloque `#Region`.</span><span class="sxs-lookup"><span data-stu-id="cb1ac-111">Terminates the `#Region` block.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cb1ac-112">Comentarios</span><span class="sxs-lookup"><span data-stu-id="cb1ac-112">Remarks</span></span>  
 <span data-ttu-id="cb1ac-113">La directiva `#Region` permite especificar un bloque de código que se puede expandir o contraer cuando se usa la característica de esquematización del Editor de código de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="cb1ac-113">Use the `#Region` directive to specify a block of code to expand or collapse when using the outlining feature of the Visual Studio Code Editor.</span></span> <span data-ttu-id="cb1ac-114">Puede colocar, o *anidar*, las regiones dentro de otras regiones para agrupar regiones similares.</span><span class="sxs-lookup"><span data-stu-id="cb1ac-114">You can place, or *nest*, regions within other regions to group similar regions together.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cb1ac-115">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="cb1ac-115">Example</span></span>  
 <span data-ttu-id="cb1ac-116">En este ejemplo se usa la directiva `#Region`.</span><span class="sxs-lookup"><span data-stu-id="cb1ac-116">This example uses the `#Region` directive.</span></span>  
  
 [!code-vb[VbVbalrConditionalComp#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrConditionalComp/VB/Class1.vb#4)]  
  
## <a name="see-also"></a><span data-ttu-id="cb1ac-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="cb1ac-117">See also</span></span>

- [<span data-ttu-id="cb1ac-118">#If...Then...#Else (directivas)</span><span class="sxs-lookup"><span data-stu-id="cb1ac-118">#If...Then...#Else Directives</span></span>](../../../visual-basic/language-reference/directives/if-then-else-directives.md)
- [<span data-ttu-id="cb1ac-119">Esquematización</span><span class="sxs-lookup"><span data-stu-id="cb1ac-119">Outlining</span></span>](/visualstudio/ide/outlining)
- [<span data-ttu-id="cb1ac-120">Cómo: Contraer y ocultar secciones de código</span><span class="sxs-lookup"><span data-stu-id="cb1ac-120">How to: Collapse and Hide Sections of Code</span></span>](../../../visual-basic/programming-guide/program-structure/how-to-collapse-and-hide-sections-of-code.md)
