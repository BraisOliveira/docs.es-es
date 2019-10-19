---
title: GoTo (instrucción) (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.GoTo
helpviewer_keywords:
- GoTo statement [Visual Basic]
- control flow [Visual Basic], branching
- unconditional branching [Visual Basic]
- branching [Visual Basic]
- branching [Visual Basic], unconditional
- branching [Visual Basic], conditional
- conditional statements [Visual Basic], GoTo statement
- GoTo statement [Visual Basic], syntax
ms.assetid: 313274c2-8ab3-4b9c-9ba3-0fd6798e4f6d
ms.openlocfilehash: 4b7a5cce56dfdd2bdc7e068aadbc18b92bba269d
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2019
ms.locfileid: "72581816"
---
# <a name="goto-statement"></a><span data-ttu-id="4ff5c-102">GoTo (Instrucción)</span><span class="sxs-lookup"><span data-stu-id="4ff5c-102">GoTo Statement</span></span>
<span data-ttu-id="4ff5c-103">Bifurca incondicionalmente a una línea especificada en un procedimiento.</span><span class="sxs-lookup"><span data-stu-id="4ff5c-103">Branches unconditionally to a specified line in a procedure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4ff5c-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4ff5c-104">Syntax</span></span>  
  
```vb  
GoTo line  
```  
  
## <a name="part"></a><span data-ttu-id="4ff5c-105">Parte</span><span class="sxs-lookup"><span data-stu-id="4ff5c-105">Part</span></span>  
 `line`  
 <span data-ttu-id="4ff5c-106">Requerido.</span><span class="sxs-lookup"><span data-stu-id="4ff5c-106">Required.</span></span> <span data-ttu-id="4ff5c-107">Cualquier etiqueta de línea.</span><span class="sxs-lookup"><span data-stu-id="4ff5c-107">Any line label.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4ff5c-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="4ff5c-108">Remarks</span></span>  
 <span data-ttu-id="4ff5c-109">La instrucción `GoTo` solo puede bifurcar a las líneas del procedimiento en el que aparece.</span><span class="sxs-lookup"><span data-stu-id="4ff5c-109">The `GoTo` statement can branch only to lines in the procedure in which it appears.</span></span> <span data-ttu-id="4ff5c-110">La línea debe tener una etiqueta de línea a la que `GoTo` pueda hacer referencia.</span><span class="sxs-lookup"><span data-stu-id="4ff5c-110">The line must have a line label that `GoTo` can refer to.</span></span> <span data-ttu-id="4ff5c-111">Para obtener más información, vea [Cómo: etiquetar instrucciones](../../../visual-basic/programming-guide/program-structure/how-to-label-statements.md).</span><span class="sxs-lookup"><span data-stu-id="4ff5c-111">For more information, see [How to: Label Statements](../../../visual-basic/programming-guide/program-structure/how-to-label-statements.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="4ff5c-112">`GoTo` instrucciones pueden hacer que el código sea difícil de leer y mantener.</span><span class="sxs-lookup"><span data-stu-id="4ff5c-112">`GoTo` statements can make code difficult to read and maintain.</span></span> <span data-ttu-id="4ff5c-113">Siempre que sea posible, use una estructura de control en su lugar.</span><span class="sxs-lookup"><span data-stu-id="4ff5c-113">Whenever possible, use a control structure instead.</span></span> <span data-ttu-id="4ff5c-114">Para obtener más información, consulte [Control Flow](../../../visual-basic/programming-guide/language-features/control-flow/index.md).</span><span class="sxs-lookup"><span data-stu-id="4ff5c-114">For more information, see [Control Flow](../../../visual-basic/programming-guide/language-features/control-flow/index.md).</span></span>  
  
 <span data-ttu-id="4ff5c-115">No se puede usar una instrucción `GoTo` para bifurcar desde fuera de un `For`... `Next`, `For Each`... `Next`, `SyncLock`... `End SyncLock`, `Try`... `Catch`... `Finally`, 0... 1 o 2... 3 construcción en una etiqueta dentro de.</span><span class="sxs-lookup"><span data-stu-id="4ff5c-115">You cannot use a `GoTo` statement to branch from outside a `For`...`Next`, `For Each`...`Next`, `SyncLock`...`End SyncLock`, `Try`...`Catch`...`Finally`, `With`...`End With`, or `Using`...`End Using` construction to a label inside.</span></span>  
  
## <a name="branching-and-try-constructions"></a><span data-ttu-id="4ff5c-116">Bifurcación y construcciones try</span><span class="sxs-lookup"><span data-stu-id="4ff5c-116">Branching and Try Constructions</span></span>  
 <span data-ttu-id="4ff5c-117">Dentro de un `Try`... `Catch`... `Finally` construcción, se aplican las siguientes reglas a la bifurcación con la instrucción `GoTo`.</span><span class="sxs-lookup"><span data-stu-id="4ff5c-117">Within a `Try`...`Catch`...`Finally` construction, the following rules apply to branching with the `GoTo` statement.</span></span>  
  
|<span data-ttu-id="4ff5c-118">Bloque o región</span><span class="sxs-lookup"><span data-stu-id="4ff5c-118">Block or region</span></span>|<span data-ttu-id="4ff5c-119">Bifurcación desde fuera</span><span class="sxs-lookup"><span data-stu-id="4ff5c-119">Branching in from outside</span></span>|<span data-ttu-id="4ff5c-120">Bifurcar desde dentro</span><span class="sxs-lookup"><span data-stu-id="4ff5c-120">Branching out from inside</span></span>|  
|---------------------|-------------------------------|-------------------------------|  
|<span data-ttu-id="4ff5c-121">`Try` bloque)</span><span class="sxs-lookup"><span data-stu-id="4ff5c-121">`Try` block</span></span>|<span data-ttu-id="4ff5c-122">Solo desde un bloque de `Catch` de la misma construcción <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="4ff5c-122">Only from a `Catch` block of the same construction <sup>1</sup></span></span>|<span data-ttu-id="4ff5c-123">Solo hacia fuera de la construcción completa</span><span class="sxs-lookup"><span data-stu-id="4ff5c-123">Only to outside the whole construction</span></span>|  
|<span data-ttu-id="4ff5c-124">`Catch` bloque)</span><span class="sxs-lookup"><span data-stu-id="4ff5c-124">`Catch` block</span></span>|<span data-ttu-id="4ff5c-125">Nunca permitido</span><span class="sxs-lookup"><span data-stu-id="4ff5c-125">Never allowed</span></span>|<span data-ttu-id="4ff5c-126">Solo hacia fuera de la construcción completa o hasta el `Try` bloque de la misma construcción <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="4ff5c-126">Only to outside the whole construction, or to the `Try` block of the same construction <sup>1</sup></span></span>|  
|<span data-ttu-id="4ff5c-127">`Finally` bloque)</span><span class="sxs-lookup"><span data-stu-id="4ff5c-127">`Finally` block</span></span>|<span data-ttu-id="4ff5c-128">Nunca permitido</span><span class="sxs-lookup"><span data-stu-id="4ff5c-128">Never allowed</span></span>|<span data-ttu-id="4ff5c-129">Nunca permitido</span><span class="sxs-lookup"><span data-stu-id="4ff5c-129">Never allowed</span></span>|  
  
 <span data-ttu-id="4ff5c-130"><sup>1</sup> si una `Try`... `Catch`... `Finally` construcción está anidada dentro de otra, un bloque de `Catch` se puede bifurcar en el bloque de `Try` en su propio nivel de anidamiento, pero no en otro bloque de `Try`.</span><span class="sxs-lookup"><span data-stu-id="4ff5c-130"><sup>1</sup> If one `Try`...`Catch`...`Finally` construction is nested within another, a `Catch` block can branch into the `Try` block at its own nesting level, but not into any other `Try` block.</span></span> <span data-ttu-id="4ff5c-131">Un `Try` anidado... `Catch`... `Finally` construcción debe estar contenida completamente en un bloque de `Try` o `Catch` de la construcción en la que está anidada.</span><span class="sxs-lookup"><span data-stu-id="4ff5c-131">A nested `Try`...`Catch`...`Finally` construction must be contained completely in a `Try` or `Catch` block of the construction within which it is nested.</span></span>  
  
 <span data-ttu-id="4ff5c-132">En la ilustración siguiente se muestra una construcción `Try` anidada dentro de otra.</span><span class="sxs-lookup"><span data-stu-id="4ff5c-132">The following illustration shows one `Try` construction nested within another.</span></span> <span data-ttu-id="4ff5c-133">Varias ramas entre los bloques de las dos construcciones se indican como válidas o no válidas.</span><span class="sxs-lookup"><span data-stu-id="4ff5c-133">Various branches among the blocks of the two constructions are indicated as valid or invalid.</span></span>  
  
 ![Diagrama gráfico de bifurcación en construcciones Try](./media/goto-statement/try-construction-branching.gif)  
  
## <a name="example"></a><span data-ttu-id="4ff5c-135">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="4ff5c-135">Example</span></span>  
 <span data-ttu-id="4ff5c-136">En el ejemplo siguiente se usa la instrucción `GoTo` para bifurcar a las etiquetas de línea de un procedimiento.</span><span class="sxs-lookup"><span data-stu-id="4ff5c-136">The following example uses the `GoTo` statement to branch to line labels in a procedure.</span></span>  
  
 [!code-vb[VbVbalrStatements#31](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#31)]  
  
## <a name="see-also"></a><span data-ttu-id="4ff5c-137">Vea también</span><span class="sxs-lookup"><span data-stu-id="4ff5c-137">See also</span></span>

- [<span data-ttu-id="4ff5c-138">Do...Loop (instrucción)</span><span class="sxs-lookup"><span data-stu-id="4ff5c-138">Do...Loop Statement</span></span>](../../../visual-basic/language-reference/statements/do-loop-statement.md)
- [<span data-ttu-id="4ff5c-139">For...Next (instrucción)</span><span class="sxs-lookup"><span data-stu-id="4ff5c-139">For...Next Statement</span></span>](../../../visual-basic/language-reference/statements/for-next-statement.md)
- [<span data-ttu-id="4ff5c-140">For Each...Next (instrucción)</span><span class="sxs-lookup"><span data-stu-id="4ff5c-140">For Each...Next Statement</span></span>](../../../visual-basic/language-reference/statements/for-each-next-statement.md)
- [<span data-ttu-id="4ff5c-141">If...Then...Else (instrucción)</span><span class="sxs-lookup"><span data-stu-id="4ff5c-141">If...Then...Else Statement</span></span>](../../../visual-basic/language-reference/statements/if-then-else-statement.md)
- [<span data-ttu-id="4ff5c-142">Select...Case (instrucción)</span><span class="sxs-lookup"><span data-stu-id="4ff5c-142">Select...Case Statement</span></span>](../../../visual-basic/language-reference/statements/select-case-statement.md)
- [<span data-ttu-id="4ff5c-143">Try...Catch...Finally (instrucción)</span><span class="sxs-lookup"><span data-stu-id="4ff5c-143">Try...Catch...Finally Statement</span></span>](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
- [<span data-ttu-id="4ff5c-144">While...End While (instrucción)</span><span class="sxs-lookup"><span data-stu-id="4ff5c-144">While...End While Statement</span></span>](../../../visual-basic/language-reference/statements/while-end-while-statement.md)
- [<span data-ttu-id="4ff5c-145">With...End With (instrucción)</span><span class="sxs-lookup"><span data-stu-id="4ff5c-145">With...End With Statement</span></span>](../../../visual-basic/language-reference/statements/with-end-with-statement.md)
