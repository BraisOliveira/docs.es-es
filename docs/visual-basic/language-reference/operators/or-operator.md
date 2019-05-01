---
title: Or (Operador, Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Or
helpviewer_keywords:
- Or operator [Visual Basic]
- operators [Visual Basic], bitwise
- inclusive Or operator [Visual Basic]
- bitwise operators [Visual Basic], OR operator
- Or keyword [Visual Basic]
- operators [Visual Basic], inclusive or
- operators [Visual Basic], disjunction
- bitwise comparison [Visual Basic]
- logical disjunction
- disjunction operator [Visual Basic]
ms.assetid: 41ed6905-bf3d-468a-9e3b-03c10d461891
ms.openlocfilehash: 0277b6f24e62ed5f0cad3dae225c86fffc4c09b9
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62013522"
---
# <a name="or-operator-visual-basic"></a><span data-ttu-id="a0138-102">Or (Operador, Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a0138-102">Or Operator (Visual Basic)</span></span>
<span data-ttu-id="a0138-103">Realiza una disyunción lógica en dos `Boolean` expresiones o una disyunción bit a bit de dos expresiones numéricas.</span><span class="sxs-lookup"><span data-stu-id="a0138-103">Performs a logical disjunction on two `Boolean` expressions, or a bitwise disjunction on two numeric expressions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a0138-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a0138-104">Syntax</span></span>  
  
```  
result = expression1 Or expression2  
```  
  
## <a name="parts"></a><span data-ttu-id="a0138-105">Elementos</span><span class="sxs-lookup"><span data-stu-id="a0138-105">Parts</span></span>  
 `result`  
 <span data-ttu-id="a0138-106">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="a0138-106">Required.</span></span> <span data-ttu-id="a0138-107">Cualquier `Boolean` o expresión numérica.</span><span class="sxs-lookup"><span data-stu-id="a0138-107">Any `Boolean` or numeric expression.</span></span> <span data-ttu-id="a0138-108">Para `Boolean` comparación, `result` es la disyunción lógica inclusiva de dos `Boolean` valores.</span><span class="sxs-lookup"><span data-stu-id="a0138-108">For `Boolean` comparison, `result` is the inclusive logical disjunction of two `Boolean` values.</span></span> <span data-ttu-id="a0138-109">Para las operaciones bit a bit, `result` es un valor numérico que representa la disyunción inclusiva bit a bit de dos patrones de bits numéricos.</span><span class="sxs-lookup"><span data-stu-id="a0138-109">For bitwise operations, `result` is a numeric value representing the inclusive bitwise disjunction of two numeric bit patterns.</span></span>  
  
 `expression1`  
 <span data-ttu-id="a0138-110">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="a0138-110">Required.</span></span> <span data-ttu-id="a0138-111">Cualquier `Boolean` o expresión numérica.</span><span class="sxs-lookup"><span data-stu-id="a0138-111">Any `Boolean` or numeric expression.</span></span>  
  
 `expression2`  
 <span data-ttu-id="a0138-112">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="a0138-112">Required.</span></span> <span data-ttu-id="a0138-113">Cualquier `Boolean` o expresión numérica.</span><span class="sxs-lookup"><span data-stu-id="a0138-113">Any `Boolean` or numeric expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a0138-114">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a0138-114">Remarks</span></span>  
 <span data-ttu-id="a0138-115">Para `Boolean` comparación, `result` es `False` si y solo si ambos `expression1` y `expression2` se evalúan como `False`.</span><span class="sxs-lookup"><span data-stu-id="a0138-115">For `Boolean` comparison, `result` is `False` if and only if both `expression1` and `expression2` evaluate to `False`.</span></span> <span data-ttu-id="a0138-116">La tabla siguiente se muestra cómo `result` viene determinada.</span><span class="sxs-lookup"><span data-stu-id="a0138-116">The following table illustrates how `result` is determined.</span></span>  
  
|<span data-ttu-id="a0138-117">Si `expression1` es</span><span class="sxs-lookup"><span data-stu-id="a0138-117">If `expression1` is</span></span>|<span data-ttu-id="a0138-118">Y `expression2` es</span><span class="sxs-lookup"><span data-stu-id="a0138-118">And `expression2` is</span></span>|<span data-ttu-id="a0138-119">El valor de `result` es</span><span class="sxs-lookup"><span data-stu-id="a0138-119">The value of `result` is</span></span>|  
|-------------------------|--------------------------|------------------------------|  
|`True`|`True`|`True`|  
|`True`|`False`|`True`|  
|`False`|`True`|`True`|  
|`False`|`False`|`False`|  
  
> [!NOTE]
>  <span data-ttu-id="a0138-120">En un `Boolean` comparación, el `Or` operador siempre evalúa ambas expresiones, lo que podrían incluir la realización de llamadas de procedimiento.</span><span class="sxs-lookup"><span data-stu-id="a0138-120">In a `Boolean` comparison, the `Or` operator always evaluates both expressions, which could include making procedure calls.</span></span> <span data-ttu-id="a0138-121">El [OrElse Operator](../../../visual-basic/language-reference/operators/orelse-operator.md) realiza *evaluación "cortocircuitada"*, lo que significa que si `expression1` es `True`, a continuación, `expression2` no se evalúa.</span><span class="sxs-lookup"><span data-stu-id="a0138-121">The [OrElse Operator](../../../visual-basic/language-reference/operators/orelse-operator.md) performs *short-circuiting*, which means that if `expression1` is `True`, then `expression2` is not evaluated.</span></span>  
  
 <span data-ttu-id="a0138-122">Para las operaciones bit a bit, el `Or` operador realiza una comparación bit a bit de los bits colocados de forma idéntica en dos expresiones numéricas y establece el bit en correspondiente `result` según la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="a0138-122">For bitwise operations, the `Or` operator performs a bitwise comparison of identically positioned bits in two numeric expressions and sets the corresponding bit in `result` according to the following table.</span></span>  
  
|<span data-ttu-id="a0138-123">Si bit en `expression1` es</span><span class="sxs-lookup"><span data-stu-id="a0138-123">If bit in `expression1` is</span></span>|<span data-ttu-id="a0138-124">Y que el bit en `expression2` es</span><span class="sxs-lookup"><span data-stu-id="a0138-124">And bit in `expression2` is</span></span>|<span data-ttu-id="a0138-125">El bit de `result` es</span><span class="sxs-lookup"><span data-stu-id="a0138-125">The bit in `result` is</span></span>|  
|--------------------------------|---------------------------------|----------------------------|  
|<span data-ttu-id="a0138-126">1</span><span class="sxs-lookup"><span data-stu-id="a0138-126">1</span></span>|<span data-ttu-id="a0138-127">1</span><span class="sxs-lookup"><span data-stu-id="a0138-127">1</span></span>|<span data-ttu-id="a0138-128">1</span><span class="sxs-lookup"><span data-stu-id="a0138-128">1</span></span>|  
|<span data-ttu-id="a0138-129">1</span><span class="sxs-lookup"><span data-stu-id="a0138-129">1</span></span>|<span data-ttu-id="a0138-130">0</span><span class="sxs-lookup"><span data-stu-id="a0138-130">0</span></span>|<span data-ttu-id="a0138-131">1</span><span class="sxs-lookup"><span data-stu-id="a0138-131">1</span></span>|  
|<span data-ttu-id="a0138-132">0</span><span class="sxs-lookup"><span data-stu-id="a0138-132">0</span></span>|<span data-ttu-id="a0138-133">1</span><span class="sxs-lookup"><span data-stu-id="a0138-133">1</span></span>|<span data-ttu-id="a0138-134">1</span><span class="sxs-lookup"><span data-stu-id="a0138-134">1</span></span>|  
|<span data-ttu-id="a0138-135">0</span><span class="sxs-lookup"><span data-stu-id="a0138-135">0</span></span>|<span data-ttu-id="a0138-136">0</span><span class="sxs-lookup"><span data-stu-id="a0138-136">0</span></span>|<span data-ttu-id="a0138-137">0</span><span class="sxs-lookup"><span data-stu-id="a0138-137">0</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="a0138-138">Dado que los operadores lógicos y bit a bit tienen una prioridad menor que otros operadores relacionales y aritméticos, las operaciones bit a bit deben ir entre paréntesis para garantizar una correcta ejecución.</span><span class="sxs-lookup"><span data-stu-id="a0138-138">Since the logical and bitwise operators have a lower precedence than other arithmetic and relational operators, any bitwise operations should be enclosed in parentheses to ensure accurate execution.</span></span>  
  
## <a name="data-types"></a><span data-ttu-id="a0138-139">Tipos de datos</span><span class="sxs-lookup"><span data-stu-id="a0138-139">Data Types</span></span>  
 <span data-ttu-id="a0138-140">Si los operandos se componen de uno `Boolean` expresión y una expresión numérica, Visual Basic convierte la `Boolean` expresión en un valor numérico (– 1 para `True` y 0 para `False`) y realiza una operación bit a bit.</span><span class="sxs-lookup"><span data-stu-id="a0138-140">If the operands consist of one `Boolean` expression and one numeric expression, Visual Basic converts the `Boolean` expression to a numeric value (–1 for `True` and 0 for `False`) and performs a bitwise operation.</span></span>  
  
 <span data-ttu-id="a0138-141">Para un `Boolean` comparación, el tipo de datos del resultado es `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="a0138-141">For a `Boolean` comparison, the data type of the result is `Boolean`.</span></span> <span data-ttu-id="a0138-142">Para obtener una comparación bit a bit, el tipo de datos de resultado es un tipo numérico adecuado para los tipos de datos de `expression1` y `expression2`.</span><span class="sxs-lookup"><span data-stu-id="a0138-142">For a bitwise comparison, the result data type is a numeric type appropriate for the data types of `expression1` and `expression2`.</span></span> <span data-ttu-id="a0138-143">Vea la tabla "relacional y bit a bit comparaciones" de [tipos de datos de resultados de operador](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).</span><span class="sxs-lookup"><span data-stu-id="a0138-143">See the "Relational and Bitwise Comparisons" table in [Data Types of Operator Results](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="a0138-144">Sobrecarga</span><span class="sxs-lookup"><span data-stu-id="a0138-144">Overloading</span></span>  
 <span data-ttu-id="a0138-145">El `Or` operador puede ser *sobrecargado*, lo que significa que una clase o estructura puede redefinir su comportamiento cuando un operando tiene el tipo de esa clase o estructura.</span><span class="sxs-lookup"><span data-stu-id="a0138-145">The `Or` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="a0138-146">Si el código usa este operador en una clase o estructura de este tipo, asegúrese de que conocer su comportamiento redefinido.</span><span class="sxs-lookup"><span data-stu-id="a0138-146">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="a0138-147">Para obtener más información, consulta [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="a0138-147">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="a0138-148">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a0138-148">Example</span></span>  
 <span data-ttu-id="a0138-149">En el ejemplo siguiente se usa el `Or` operador para realizar una disyunción lógica inclusiva en dos expresiones.</span><span class="sxs-lookup"><span data-stu-id="a0138-149">The following example uses the `Or` operator to perform an inclusive logical disjunction on two expressions.</span></span> <span data-ttu-id="a0138-150">El resultado es un `Boolean` valor que representa si alguna de las dos expresiones es `True`.</span><span class="sxs-lookup"><span data-stu-id="a0138-150">The result is a `Boolean` value that represents whether either of the two expressions is `True`.</span></span>  
  
 [!code-vb[VbVbalrOperators#35](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#35)]  
  
 <span data-ttu-id="a0138-151">El ejemplo anterior genera los resultados de `True`, `True`, y `False`, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="a0138-151">The preceding example produces results of `True`, `True`, and `False`, respectively.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a0138-152">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a0138-152">Example</span></span>  
 <span data-ttu-id="a0138-153">En el ejemplo siguiente se usa el `Or` operador para realizar una disyunción lógica inclusiva de los bits individuales de dos expresiones numéricas.</span><span class="sxs-lookup"><span data-stu-id="a0138-153">The following example uses the `Or` operator to perform inclusive logical disjunction on the individual bits of two numeric expressions.</span></span> <span data-ttu-id="a0138-154">El bit en el modelo resultante se establece si cualquiera de los bits correspondientes de los operandos se establece en 1.</span><span class="sxs-lookup"><span data-stu-id="a0138-154">The bit in the result pattern is set if either of the corresponding bits in the operands is set to 1.</span></span>  
  
 [!code-vb[VbVbalrOperators#36](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#36)]  
  
 <span data-ttu-id="a0138-155">El ejemplo anterior genera los resultados de 10, 14 y 14, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="a0138-155">The preceding example produces results of 10, 14, and 14, respectively.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a0138-156">Vea también</span><span class="sxs-lookup"><span data-stu-id="a0138-156">See also</span></span>

- [<span data-ttu-id="a0138-157">Operadores lógicos y bit a bit (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a0138-157">Logical/Bitwise Operators (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)
- [<span data-ttu-id="a0138-158">Prioridad de operador en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="a0138-158">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="a0138-159">Operadores enumerados por funcionalidad</span><span class="sxs-lookup"><span data-stu-id="a0138-159">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="a0138-160">OrElse (operador)</span><span class="sxs-lookup"><span data-stu-id="a0138-160">OrElse Operator</span></span>](../../../visual-basic/language-reference/operators/orelse-operator.md)
- [<span data-ttu-id="a0138-161">Operadores lógicos y bit a bit en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="a0138-161">Logical and Bitwise Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
