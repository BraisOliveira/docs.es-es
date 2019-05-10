---
title: Mod (Operador, Visual Basic)
ms.date: 04/24/2018
f1_keywords:
- vb.Mod
helpviewer_keywords:
- remainder (Mod operator)
- division operator [Visual Basic], Mod operator
- modulus operator [Visual Basic], Visual Basic
- Mod operator [Visual Basic]
- operators [Visual Basic], division
- arithmetic operators [Visual Basic], Mod
- math operators [Visual Basic]
ms.assetid: 6ff7e40e-cec8-4c77-bff6-8ddd2791c25b
ms.openlocfilehash: f1334ff7aa07f49139bfe684746ae9cc3cf8087c
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64663167"
---
# <a name="mod-operator-visual-basic"></a><span data-ttu-id="f2b6a-102">Mod (operador) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f2b6a-102">Mod operator (Visual Basic)</span></span>
<span data-ttu-id="f2b6a-103">Divide dos números y devuelve solo el resto.</span><span class="sxs-lookup"><span data-stu-id="f2b6a-103">Divides two numbers and returns only the remainder.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f2b6a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f2b6a-104">Syntax</span></span>  
  
```  
number1 Mod number2  
```  
  
## <a name="parts"></a><span data-ttu-id="f2b6a-105">Elementos</span><span class="sxs-lookup"><span data-stu-id="f2b6a-105">Parts</span></span>  
 `number1`  
 <span data-ttu-id="f2b6a-106">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="f2b6a-106">Required.</span></span> <span data-ttu-id="f2b6a-107">Cualquier expresión numérica.</span><span class="sxs-lookup"><span data-stu-id="f2b6a-107">Any numeric expression.</span></span>  
  
 `number2`  
 <span data-ttu-id="f2b6a-108">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="f2b6a-108">Required.</span></span> <span data-ttu-id="f2b6a-109">Cualquier expresión numérica.</span><span class="sxs-lookup"><span data-stu-id="f2b6a-109">Any numeric expression.</span></span>  
  
## <a name="supported-types"></a><span data-ttu-id="f2b6a-110">Tipos admitidos</span><span class="sxs-lookup"><span data-stu-id="f2b6a-110">Supported types</span></span>  
 <span data-ttu-id="f2b6a-111">todos los tipos numéricos.</span><span class="sxs-lookup"><span data-stu-id="f2b6a-111">All numeric types.</span></span> <span data-ttu-id="f2b6a-112">Esto incluye los tipos sin signo y de punto flotante y `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="f2b6a-112">This includes the unsigned and floating-point types and `Decimal`.</span></span>  
  
## <a name="result"></a><span data-ttu-id="f2b6a-113">Resultado</span><span class="sxs-lookup"><span data-stu-id="f2b6a-113">Result</span></span>

<span data-ttu-id="f2b6a-114">El resultado es el resto después de `number1` se divide por `number2`.</span><span class="sxs-lookup"><span data-stu-id="f2b6a-114">The result is the remainder after `number1` is divided by `number2`.</span></span> <span data-ttu-id="f2b6a-115">Por ejemplo, la expresión `14 Mod 4` se evalúa como 2.</span><span class="sxs-lookup"><span data-stu-id="f2b6a-115">For example, the expression `14 Mod 4` evaluates to 2.</span></span>  

> [!NOTE]
> <span data-ttu-id="f2b6a-116">Hay una diferencia entre *resto* y *modulus* en matemáticas, con resultados diferentes para los números negativos.</span><span class="sxs-lookup"><span data-stu-id="f2b6a-116">There is a difference between *remainder* and *modulus* in mathematics, with different results for negative numbers.</span></span> <span data-ttu-id="f2b6a-117">El `Mod` operador en Visual Basic, .NET Framework `op_Modulus` operador y subyacente [rem](<xref:System.Reflection.Emit.OpCodes.Rem>) instrucción IL realizan una operación de resto.</span><span class="sxs-lookup"><span data-stu-id="f2b6a-117">The `Mod` operator in Visual Basic, the .NET Framework `op_Modulus` operator, and the underlying [rem](<xref:System.Reflection.Emit.OpCodes.Rem>) IL instruction all perform a remainder operation.</span></span>

<span data-ttu-id="f2b6a-118">El resultado de una `Mod` operación conserva el signo del dividendo, `number1`, por lo que puede ser positivo o negativo.</span><span class="sxs-lookup"><span data-stu-id="f2b6a-118">The result of a `Mod` operation retains the sign of the dividend, `number1`, and so it may be positive or negative.</span></span> <span data-ttu-id="f2b6a-119">El resultado siempre está en el intervalo (-`number2`, `number2`), exclusivo.</span><span class="sxs-lookup"><span data-stu-id="f2b6a-119">The result is always in the range (-`number2`, `number2`), exclusive.</span></span> <span data-ttu-id="f2b6a-120">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="f2b6a-120">For example:</span></span>

```vb
Public Module Example
   Public Sub Main()
      Console.WriteLine($" 8 Mod  3 = {8 Mod 3}")
      Console.WriteLine($"-8 Mod  3 = {-8 Mod 3}")
      Console.WriteLine($" 8 Mod -3 = {8 Mod -3}")
      Console.WriteLine($"-8 Mod -3 = {-8 Mod -3}")
   End Sub
End Module
' The example displays the following output:
'       8 Mod  3 = 2
'      -8 Mod  3 = -2
'       8 Mod -3 = 2
'      -8 Mod -3 = -2
```

## <a name="remarks"></a><span data-ttu-id="f2b6a-121">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f2b6a-121">Remarks</span></span>  
 <span data-ttu-id="f2b6a-122">Si bien `number1` o `number2` es un valor de punto flotante, se devuelve el resto de la división de punto flotante.</span><span class="sxs-lookup"><span data-stu-id="f2b6a-122">If either `number1` or `number2` is a floating-point value, the floating-point remainder of the division is returned.</span></span> <span data-ttu-id="f2b6a-123">El tipo de datos del resultado es el tipo de datos más pequeño que puede contener todos los valores posibles que resultan de la división con los tipos de datos de `number1` y `number2`.</span><span class="sxs-lookup"><span data-stu-id="f2b6a-123">The data type of the result is the smallest data type that can hold all possible values that result from division with the data types of `number1` and `number2`.</span></span>  
  
 <span data-ttu-id="f2b6a-124">Si `number1` o `number2` se evalúa como [nada](../../../visual-basic/language-reference/nothing.md), se trata como cero.</span><span class="sxs-lookup"><span data-stu-id="f2b6a-124">If `number1` or `number2` evaluates to [Nothing](../../../visual-basic/language-reference/nothing.md), it is treated as zero.</span></span>  
  
 <span data-ttu-id="f2b6a-125">Los operadores relacionados incluyen lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="f2b6a-125">Related operators include the following:</span></span>  
  
- <span data-ttu-id="f2b6a-126">El [\ (operador) (Visual Basic)](../../../visual-basic/language-reference/operators/integer-division-operator.md) devuelve el cociente entero de una división.</span><span class="sxs-lookup"><span data-stu-id="f2b6a-126">The [\ Operator (Visual Basic)](../../../visual-basic/language-reference/operators/integer-division-operator.md) returns the integer quotient of a division.</span></span> <span data-ttu-id="f2b6a-127">Por ejemplo, la expresión `14 \ 4` da como resultado 3.</span><span class="sxs-lookup"><span data-stu-id="f2b6a-127">For example, the expression `14 \ 4` evaluates to 3.</span></span>  
  
- <span data-ttu-id="f2b6a-128">El [/ (operador) (Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-operator.md) devuelve el cociente completo, incluido el resto, como un número de punto flotante.</span><span class="sxs-lookup"><span data-stu-id="f2b6a-128">The [/ Operator (Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-operator.md) returns the full quotient, including the remainder, as a floating-point number.</span></span> <span data-ttu-id="f2b6a-129">Por ejemplo, la expresión `14 / 4` se evalúa como 3.5.</span><span class="sxs-lookup"><span data-stu-id="f2b6a-129">For example, the expression `14 / 4` evaluates to 3.5.</span></span>  
  
## <a name="attempted-division-by-zero"></a><span data-ttu-id="f2b6a-130">División por cero intentada</span><span class="sxs-lookup"><span data-stu-id="f2b6a-130">Attempted division by zero</span></span>  
 <span data-ttu-id="f2b6a-131">Si `number2` se evalúa como cero, el comportamiento de la `Mod` operador depende del tipo de datos de los operandos.</span><span class="sxs-lookup"><span data-stu-id="f2b6a-131">If `number2` evaluates to zero, the behavior of the `Mod` operator depends on the data type of the operands.</span></span> <span data-ttu-id="f2b6a-132">Una división de enteros produce una <xref:System.DivideByZeroException> excepción.</span><span class="sxs-lookup"><span data-stu-id="f2b6a-132">An integral division throws a <xref:System.DivideByZeroException> exception.</span></span> <span data-ttu-id="f2b6a-133">Devuelve una división de punto flotante <xref:System.Double.NaN>.</span><span class="sxs-lookup"><span data-stu-id="f2b6a-133">A floating-point division returns <xref:System.Double.NaN>.</span></span>  
  
## <a name="equivalent-formula"></a><span data-ttu-id="f2b6a-134">Fórmula equivalente</span><span class="sxs-lookup"><span data-stu-id="f2b6a-134">Equivalent formula</span></span>  
 <span data-ttu-id="f2b6a-135">La expresión `a Mod b` es equivalente a cualquiera de las siguientes fórmulas:</span><span class="sxs-lookup"><span data-stu-id="f2b6a-135">The expression `a Mod b` is equivalent to either of the following formulas:</span></span>  
  
 `a - (b * (a \ b))`  
  
 `a - (b * Fix(a / b))`  
  
## <a name="floating-point-imprecision"></a><span data-ttu-id="f2b6a-136">Punto flotante imprecisión</span><span class="sxs-lookup"><span data-stu-id="f2b6a-136">Floating-point imprecision</span></span>  
 <span data-ttu-id="f2b6a-137">Cuando se trabaja con números de punto flotante, recuerde que no siempre tienen una representación decimal precisa en memoria.</span><span class="sxs-lookup"><span data-stu-id="f2b6a-137">When you work with floating-point numbers, remember that they do not always have a precise decimal representation in memory.</span></span> <span data-ttu-id="f2b6a-138">Esto puede provocar resultados inesperados en ciertas operaciones, como la comparación de valor y el `Mod` operador.</span><span class="sxs-lookup"><span data-stu-id="f2b6a-138">This can lead to unexpected results from certain operations, such as value comparison and the `Mod` operator.</span></span> <span data-ttu-id="f2b6a-139">Para obtener más información, consulte [solución de problemas de los tipos de datos](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="f2b6a-139">For more information, see [Troubleshooting Data Types](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md).</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="f2b6a-140">Sobrecarga</span><span class="sxs-lookup"><span data-stu-id="f2b6a-140">Overloading</span></span>  
 <span data-ttu-id="f2b6a-141">El `Mod` operador puede ser *sobrecargado*, lo que significa que una clase o estructura puede volver a definir su comportamiento.</span><span class="sxs-lookup"><span data-stu-id="f2b6a-141">The `Mod` operator can be *overloaded*, which means that a class or structure can redefine its behavior.</span></span> <span data-ttu-id="f2b6a-142">Si el código se aplica `Mod` a una instancia de una clase o estructura que incluye una sobrecarga de este tipo, asegúrese de conocer su comportamiento redefinido.</span><span class="sxs-lookup"><span data-stu-id="f2b6a-142">If your code applies `Mod` to an instance of a class or structure that includes such an overload, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="f2b6a-143">Para obtener más información, consulta [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="f2b6a-143">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="f2b6a-144">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f2b6a-144">Example</span></span>  
 <span data-ttu-id="f2b6a-145">En el ejemplo siguiente se usa el `Mod` operador para dividir dos números y devolver solo el resto.</span><span class="sxs-lookup"><span data-stu-id="f2b6a-145">The following example uses the `Mod` operator to divide two numbers and return only the remainder.</span></span> <span data-ttu-id="f2b6a-146">Si uno de ellos es un número de punto flotante, el resultado es un número de punto flotante que representa el resto.</span><span class="sxs-lookup"><span data-stu-id="f2b6a-146">If either number is a floating-point number, the result is a floating-point number that represents the remainder.</span></span>  
  
 [!code-vb[VbVbalrOperators#31](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#31)]  
  
## <a name="example"></a><span data-ttu-id="f2b6a-147">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f2b6a-147">Example</span></span>  
 <span data-ttu-id="f2b6a-148">El ejemplo siguiente muestra el potencial de imprecisión de operandos de punto flotante.</span><span class="sxs-lookup"><span data-stu-id="f2b6a-148">The following example demonstrates the potential imprecision of floating-point operands.</span></span> <span data-ttu-id="f2b6a-149">En la primera instrucción, los operandos son `Double`, y 0.2 es una fracción binaria con un valor almacenado de 0,20000000000000001.</span><span class="sxs-lookup"><span data-stu-id="f2b6a-149">In the first statement, the operands are `Double`, and 0.2 is an infinitely repeating binary fraction with a stored value of 0.20000000000000001.</span></span> <span data-ttu-id="f2b6a-150">En la segunda instrucción, el literal de tipo carácter `D` obliga a que ambos operandos a `Decimal`, y 0.2 tiene una representación precisa.</span><span class="sxs-lookup"><span data-stu-id="f2b6a-150">In the second statement, the literal type character `D` forces both operands to `Decimal`, and 0.2 has a precise representation.</span></span>  
  
 [!code-vb[VbVbalrOperators#32](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#32)]  
  
## <a name="see-also"></a><span data-ttu-id="f2b6a-151">Vea también</span><span class="sxs-lookup"><span data-stu-id="f2b6a-151">See also</span></span>

- <xref:Microsoft.VisualBasic.Conversion.Int%2A>
- <xref:Microsoft.VisualBasic.Conversion.Fix%2A>
- [<span data-ttu-id="f2b6a-152">Operadores aritméticos</span><span class="sxs-lookup"><span data-stu-id="f2b6a-152">Arithmetic Operators</span></span>](../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [<span data-ttu-id="f2b6a-153">Prioridad de operador en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="f2b6a-153">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="f2b6a-154">Operadores enumerados por funcionalidad</span><span class="sxs-lookup"><span data-stu-id="f2b6a-154">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="f2b6a-155">Solución de problemas de tipos de datos</span><span class="sxs-lookup"><span data-stu-id="f2b6a-155">Troubleshooting Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)
- [<span data-ttu-id="f2b6a-156">Operadores aritméticos en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="f2b6a-156">Arithmetic Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
- [<span data-ttu-id="f2b6a-157">\ (Operador) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f2b6a-157">\ Operator (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/integer-division-operator.md)
