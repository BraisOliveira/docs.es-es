---
title: / (Operador, Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb./
helpviewer_keywords:
- division operator [Visual Basic], floating point
- floating-point numbers [Visual Basic], division operator
- slash (/) operator
- zero, division by zero
- operators [Visual Basic], arithmetic
- arithmetic operators [Visual Basic], division
- division [Visual Basic], by zero
- operators [Visual Basic], division
- division operator [Visual Basic], syntax
- / operator [Visual Basic]
- math operators [Visual Basic]
ms.assetid: 335e97f2-c434-439e-9064-76973a051101
ms.openlocfilehash: af2316f92e2904eee1e8c046b34b8147e40cb513
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2019
ms.locfileid: "58825071"
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="7d577-102">/ (Operador, Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7d577-102">/ Operator (Visual Basic)</span></span>
<span data-ttu-id="7d577-103">Divide dos números y devuelve un resultado de coma flotante.</span><span class="sxs-lookup"><span data-stu-id="7d577-103">Divides two numbers and returns a floating-point result.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7d577-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7d577-104">Syntax</span></span>  
  
```  
expression1 / expression2  
```  
  
## <a name="parts"></a><span data-ttu-id="7d577-105">Elementos</span><span class="sxs-lookup"><span data-stu-id="7d577-105">Parts</span></span>  
 `expression1`  
 <span data-ttu-id="7d577-106">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="7d577-106">Required.</span></span> <span data-ttu-id="7d577-107">Cualquier expresión numérica.</span><span class="sxs-lookup"><span data-stu-id="7d577-107">Any numeric expression.</span></span>  
  
 `expression2`  
 <span data-ttu-id="7d577-108">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="7d577-108">Required.</span></span> <span data-ttu-id="7d577-109">Cualquier expresión numérica.</span><span class="sxs-lookup"><span data-stu-id="7d577-109">Any numeric expression.</span></span>  
  
## <a name="supported-types"></a><span data-ttu-id="7d577-110">Tipos admitidos</span><span class="sxs-lookup"><span data-stu-id="7d577-110">Supported Types</span></span>  
 <span data-ttu-id="7d577-111">Todos los tipos numéricos, incluidos los tipos sin signo y de punto flotante y `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="7d577-111">All numeric types, including the unsigned and floating-point types and `Decimal`.</span></span>  
  
## <a name="result"></a><span data-ttu-id="7d577-112">Resultado</span><span class="sxs-lookup"><span data-stu-id="7d577-112">Result</span></span>  
 <span data-ttu-id="7d577-113">El resultado es el cociente completo de `expression1` dividido por `expression2`, incluido cualquier resto.</span><span class="sxs-lookup"><span data-stu-id="7d577-113">The result is the full quotient of `expression1` divided by `expression2`, including any remainder.</span></span>  
  
 <span data-ttu-id="7d577-114">El [\ (operador) (Visual Basic)](../../../visual-basic/language-reference/operators/integer-division-operator.md) devuelve el cociente entero, que omite el resto.</span><span class="sxs-lookup"><span data-stu-id="7d577-114">The [\ Operator (Visual Basic)](../../../visual-basic/language-reference/operators/integer-division-operator.md) returns the integer quotient, which drops the remainder.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7d577-115">Comentarios</span><span class="sxs-lookup"><span data-stu-id="7d577-115">Remarks</span></span>  
 <span data-ttu-id="7d577-116">El tipo de datos del resultado depende de los tipos de los operandos.</span><span class="sxs-lookup"><span data-stu-id="7d577-116">The data type of the result depends on the types of the operands.</span></span> <span data-ttu-id="7d577-117">En la tabla siguiente se muestra cómo se determina el tipo de datos del resultado.</span><span class="sxs-lookup"><span data-stu-id="7d577-117">The following table shows how the data type of the result is determined.</span></span>  
  
|<span data-ttu-id="7d577-118">Tipos de datos de operando</span><span class="sxs-lookup"><span data-stu-id="7d577-118">Operand data types</span></span>|<span data-ttu-id="7d577-119">Tipo de resultado de datos</span><span class="sxs-lookup"><span data-stu-id="7d577-119">Result data type</span></span>|  
|------------------------|----------------------|  
|<span data-ttu-id="7d577-120">Ambas expresiones son tipos de datos enteros ([SByte](../../../visual-basic/language-reference/data-types/sbyte-data-type.md), [bytes](../../../visual-basic/language-reference/data-types/byte-data-type.md), [corto](../../../visual-basic/language-reference/data-types/short-data-type.md), [UShort](../../../visual-basic/language-reference/data-types/ushort-data-type.md), [entero](../../../visual-basic/language-reference/data-types/integer-data-type.md), [UInteger](../../../visual-basic/language-reference/data-types/uinteger-data-type.md), [largo](../../../visual-basic/language-reference/data-types/long-data-type.md), [ULong](../../../visual-basic/language-reference/data-types/ulong-data-type.md))</span><span class="sxs-lookup"><span data-stu-id="7d577-120">Both expressions are integral data types ([SByte](../../../visual-basic/language-reference/data-types/sbyte-data-type.md), [Byte](../../../visual-basic/language-reference/data-types/byte-data-type.md), [Short](../../../visual-basic/language-reference/data-types/short-data-type.md), [UShort](../../../visual-basic/language-reference/data-types/ushort-data-type.md), [Integer](../../../visual-basic/language-reference/data-types/integer-data-type.md), [UInteger](../../../visual-basic/language-reference/data-types/uinteger-data-type.md), [Long](../../../visual-basic/language-reference/data-types/long-data-type.md), [ULong](../../../visual-basic/language-reference/data-types/ulong-data-type.md))</span></span>|`Double`|  
|<span data-ttu-id="7d577-121">Una expresión es un [único](../../../visual-basic/language-reference/data-types/single-data-type.md) tipo de datos y el otro no es un [dobles](../../../visual-basic/language-reference/data-types/double-data-type.md)</span><span class="sxs-lookup"><span data-stu-id="7d577-121">One expression is a [Single](../../../visual-basic/language-reference/data-types/single-data-type.md) data type and the other is not a [Double](../../../visual-basic/language-reference/data-types/double-data-type.md)</span></span>|`Single`|  
|<span data-ttu-id="7d577-122">Una expresión es un [Decimal](../../../visual-basic/language-reference/data-types/decimal-data-type.md) tipo de datos y el otro no es un [único](../../../visual-basic/language-reference/data-types/single-data-type.md) o un [dobles](../../../visual-basic/language-reference/data-types/double-data-type.md)</span><span class="sxs-lookup"><span data-stu-id="7d577-122">One expression is a [Decimal](../../../visual-basic/language-reference/data-types/decimal-data-type.md) data type and the other is not a [Single](../../../visual-basic/language-reference/data-types/single-data-type.md) or a [Double](../../../visual-basic/language-reference/data-types/double-data-type.md)</span></span>|`Decimal`|  
|<span data-ttu-id="7d577-123">Cualquier expresión es un [doble](../../../visual-basic/language-reference/data-types/double-data-type.md) tipo de datos</span><span class="sxs-lookup"><span data-stu-id="7d577-123">Either expression is a [Double](../../../visual-basic/language-reference/data-types/double-data-type.md) data type</span></span>|`Double`|  
  
 <span data-ttu-id="7d577-124">Antes de realiza la división, las expresiones numéricas de enteras se amplían a `Double`.</span><span class="sxs-lookup"><span data-stu-id="7d577-124">Before division is performed, any integral numeric expressions are widened to `Double`.</span></span> <span data-ttu-id="7d577-125">Si asigna el resultado a un tipo de datos entero, Visual Basic intenta convertir el resultado de `Double` a ese tipo.</span><span class="sxs-lookup"><span data-stu-id="7d577-125">If you assign the result to an integral data type, Visual Basic attempts to convert the result from `Double` to that type.</span></span> <span data-ttu-id="7d577-126">Esto puede producir una excepción si el resultado no se ajusta a ese tipo.</span><span class="sxs-lookup"><span data-stu-id="7d577-126">This can throw an exception if the result does not fit in that type.</span></span> <span data-ttu-id="7d577-127">En concreto, vea "Intentado de división por cero" en esta página de ayuda.</span><span class="sxs-lookup"><span data-stu-id="7d577-127">In particular, see "Attempted Division by Zero" on this Help page.</span></span>  
  
 <span data-ttu-id="7d577-128">Si `expression1` o `expression2` se evalúa como [nada](../../../visual-basic/language-reference/nothing.md), se trata como cero.</span><span class="sxs-lookup"><span data-stu-id="7d577-128">If `expression1` or `expression2` evaluates to [Nothing](../../../visual-basic/language-reference/nothing.md), it is treated as zero.</span></span>  
  
## <a name="attempted-division-by-zero"></a><span data-ttu-id="7d577-129">División por cero intentada</span><span class="sxs-lookup"><span data-stu-id="7d577-129">Attempted Division by Zero</span></span>  
 <span data-ttu-id="7d577-130">Si `expression2` se evalúa como cero, el `/` operador tiene un comportamiento diferente para los tipos de datos diferentes de operando.</span><span class="sxs-lookup"><span data-stu-id="7d577-130">If `expression2` evaluates to zero, the `/` operator behaves differently for different operand data types.</span></span> <span data-ttu-id="7d577-131">La siguiente tabla muestra los comportamientos posibles.</span><span class="sxs-lookup"><span data-stu-id="7d577-131">The following table shows the possible behaviors.</span></span>  
  
|<span data-ttu-id="7d577-132">Tipos de datos de operando</span><span class="sxs-lookup"><span data-stu-id="7d577-132">Operand data types</span></span>|<span data-ttu-id="7d577-133">Comportamiento si `expression2` es cero</span><span class="sxs-lookup"><span data-stu-id="7d577-133">Behavior if `expression2` is zero</span></span>|  
|------------------------|---------------------------------------|  
|<span data-ttu-id="7d577-134">Punto flotante (`Single` o `Double`)</span><span class="sxs-lookup"><span data-stu-id="7d577-134">Floating-point (`Single` or `Double`)</span></span>|<span data-ttu-id="7d577-135">Devuelve infinito (<xref:System.Double.PositiveInfinity> o <xref:System.Double.NegativeInfinity>), o <xref:System.Double.NaN> (no un número) si `expression1` también es cero</span><span class="sxs-lookup"><span data-stu-id="7d577-135">Returns infinity (<xref:System.Double.PositiveInfinity> or <xref:System.Double.NegativeInfinity>), or <xref:System.Double.NaN> (not a number) if `expression1` is also zero</span></span>|  
|`Decimal`|<span data-ttu-id="7d577-136">Se produce <xref:System.DivideByZeroException></span><span class="sxs-lookup"><span data-stu-id="7d577-136">Throws <xref:System.DivideByZeroException></span></span>|  
|<span data-ttu-id="7d577-137">Entero (con o sin signo)</span><span class="sxs-lookup"><span data-stu-id="7d577-137">Integral (signed or unsigned)</span></span>|<span data-ttu-id="7d577-138">Ha intentado la conversión a tipo entero produce <xref:System.OverflowException> porque no pueden aceptar tipos enteros <xref:System.Double.PositiveInfinity>, <xref:System.Double.NegativeInfinity>, o <xref:System.Double.NaN></span><span class="sxs-lookup"><span data-stu-id="7d577-138">Attempted conversion back to integral type throws <xref:System.OverflowException> because integral types cannot accept <xref:System.Double.PositiveInfinity>, <xref:System.Double.NegativeInfinity>, or <xref:System.Double.NaN></span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="7d577-139">El `/` operador puede ser *sobrecargado*, lo que significa que una clase o estructura puede redefinir su comportamiento cuando un operando tiene el tipo de esa clase o estructura.</span><span class="sxs-lookup"><span data-stu-id="7d577-139">The `/` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="7d577-140">Si el código usa este operador en una clase o estructura de este tipo, asegúrese de que conocer su comportamiento redefinido.</span><span class="sxs-lookup"><span data-stu-id="7d577-140">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="7d577-141">Para obtener más información, consulta [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="7d577-141">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="7d577-142">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="7d577-142">Example</span></span>  
 <span data-ttu-id="7d577-143">Este ejemplo se usa el `/` operador para realizar la división de punto flotante.</span><span class="sxs-lookup"><span data-stu-id="7d577-143">This example uses the `/` operator to perform floating-point division.</span></span> <span data-ttu-id="7d577-144">El resultado es el cociente de los dos operandos.</span><span class="sxs-lookup"><span data-stu-id="7d577-144">The result is the quotient of the two operands.</span></span>  
  
 [!code-vb[VbVbalrOperators#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#16)]  
  
 <span data-ttu-id="7d577-145">Las expresiones en el ejemplo anterior devuelven valores de 2,5 y 3,333333.</span><span class="sxs-lookup"><span data-stu-id="7d577-145">The expressions in the preceding example return values of 2.5 and 3.333333.</span></span> <span data-ttu-id="7d577-146">Tenga en cuenta que el resultado siempre es de punto flotante (`Double`), aunque ambos operandos son constantes de tipo entero.</span><span class="sxs-lookup"><span data-stu-id="7d577-146">Note that the result is always floating-point (`Double`), even though both operands are integer constants.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7d577-147">Vea también</span><span class="sxs-lookup"><span data-stu-id="7d577-147">See also</span></span>

- [<span data-ttu-id="7d577-148">/ = (Operador) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7d577-148">/= Operator (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/floating-point-division-assignment-operator.md)
- [<span data-ttu-id="7d577-149">\ (Operador) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7d577-149">\ Operator (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/integer-division-operator.md)
- [<span data-ttu-id="7d577-150">Tipos de datos de resultados de operador</span><span class="sxs-lookup"><span data-stu-id="7d577-150">Data Types of Operator Results</span></span>](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md)
- [<span data-ttu-id="7d577-151">Operadores aritméticos</span><span class="sxs-lookup"><span data-stu-id="7d577-151">Arithmetic Operators</span></span>](../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [<span data-ttu-id="7d577-152">Prioridad de operador en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="7d577-152">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="7d577-153">Operadores enumerados por funcionalidad</span><span class="sxs-lookup"><span data-stu-id="7d577-153">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="7d577-154">Operadores aritméticos en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="7d577-154">Arithmetic Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
