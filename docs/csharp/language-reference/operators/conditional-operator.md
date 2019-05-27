---
title: '?: Operador - Referencia de C#'
ms.custom: seodec18
ms.date: 11/20/2018
f1_keywords:
- ?:_CSharpKeyword
- ?_CSharpKeyword
- :_CSharpKeyword
helpviewer_keywords:
- '?: operator [C#]'
- conditional operator (?:) [C#]
ms.assetid: e83a17f1-7500-48ba-8bee-2fbc4c847af4
ms.openlocfilehash: a40dd4addfaf8a505cf334876192f0b2ccf66a09
ms.sourcegitcommit: 4c10802ad003374641a2c2373b8a92e3c88babc8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/08/2019
ms.locfileid: "65452403"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="94fa9-102">?: Operador (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="94fa9-102">?: Operator (C# Reference)</span></span>

<span data-ttu-id="94fa9-103">El operador condicional `?:`, normalmente conocido como operador condicional ternario, evalúa una expresión booleana y devuelve el resultado de evaluar una de dos expresiones, en función de que la expresión booleana se evalúe como `true` o `false`.</span><span class="sxs-lookup"><span data-stu-id="94fa9-103">The conditional operator `?:`, commonly known as the ternary conditional operator, evaluates a Boolean expression, and returns the result of evaluating one of two expressions, depending on whether the Boolean expression evaluates to `true` or `false`.</span></span> <span data-ttu-id="94fa9-104">A partir C# 7.2, la [expresión condicional ref](#conditional-ref-expression) devuelve la referencia al resultado de una de las dos expresiones.</span><span class="sxs-lookup"><span data-stu-id="94fa9-104">Beginning with C# 7.2, the [conditional ref expression](#conditional-ref-expression) returns the reference to the result of one of the two expressions.</span></span>

<span data-ttu-id="94fa9-105">La sintaxis del operador condicional es la siguiente:</span><span class="sxs-lookup"><span data-stu-id="94fa9-105">The syntax for the conditional operator is as follows:</span></span>

```csharp
condition ? consequent : alternative
```

<span data-ttu-id="94fa9-106">La expresión `condition` debe evaluarse como `true` o `false`.</span><span class="sxs-lookup"><span data-stu-id="94fa9-106">The `condition` expression must evaluate to `true` or `false`.</span></span> <span data-ttu-id="94fa9-107">Si `condition` se evalúa como `true`, se evalúa la expresión `consequent` y su resultado se convierte en el resultado de la operación.</span><span class="sxs-lookup"><span data-stu-id="94fa9-107">If `condition` evaluates to `true`, the `consequent` expression is evaluated, and its result becomes the result of the operation.</span></span> <span data-ttu-id="94fa9-108">Si `condition` se evalúa como `false`, se evalúa la expresión `alternative` y su resultado se convierte en el resultado de la operación.</span><span class="sxs-lookup"><span data-stu-id="94fa9-108">If `condition` evaluates to `false`, the `alternative` expression is evaluated, and its result becomes the result of the operation.</span></span> <span data-ttu-id="94fa9-109">Solo se evalúan `consequent` o `alternative`.</span><span class="sxs-lookup"><span data-stu-id="94fa9-109">Only `consequent` or `alternative` is evaluated.</span></span>

<span data-ttu-id="94fa9-110">Los tipos de `consequent` y `alternative` deben coincidir o debe haber una conversión implícita de un tipo al otro.</span><span class="sxs-lookup"><span data-stu-id="94fa9-110">The type of `consequent` and `alternative` must be the same, or there must be an implicit conversion from one type to the other.</span></span>

<span data-ttu-id="94fa9-111">El operador condicional es asociativo a la derecha, es decir, una expresión de la forma</span><span class="sxs-lookup"><span data-stu-id="94fa9-111">The conditional operator is right-associative, that is, an expression of the form</span></span>

```csharp
a ? b : c ? d : e
```

<span data-ttu-id="94fa9-112">se evalúa como</span><span class="sxs-lookup"><span data-stu-id="94fa9-112">is evaluated as</span></span>

```csharp
a ? b : (c ? d : e)
```

<span data-ttu-id="94fa9-113">Un recurso mnemotécnico que se puede usar para recordar cómo evalúa este operador es preguntar:</span><span class="sxs-lookup"><span data-stu-id="94fa9-113">A mnemonic device you can use to remember how this operator evaluates is to ask:</span></span>

```text
is this condition true ? yes : no
```

<span data-ttu-id="94fa9-114">Con la parte "?"</span><span class="sxs-lookup"><span data-stu-id="94fa9-114">with the ?</span></span> <span data-ttu-id="94fa9-115">del operador que actúa como signo de interrogación para la instrucción anterior y el consiguiente actúa como respuesta lógica a esta pregunta.</span><span class="sxs-lookup"><span data-stu-id="94fa9-115">part of the operator acting as a question mark for the previous statement, and the consequent acting as the logical response to this question.</span></span>

<span data-ttu-id="94fa9-116">En el siguiente ejemplo se muestra el uso del operador condicional:</span><span class="sxs-lookup"><span data-stu-id="94fa9-116">The following example demonstrates the usage of the conditional operator:</span></span>

[!code-csharp[non ref conditional](~/samples/snippets/csharp/language-reference/operators/ConditionalExamples.cs#ConditionalValue)]

## <a name="conditional-ref-expression"></a><span data-ttu-id="94fa9-117">Expresión condicional ref</span><span class="sxs-lookup"><span data-stu-id="94fa9-117">Conditional ref expression</span></span>

<span data-ttu-id="94fa9-118">A partir C# 7.2, puede utilizar la expresión condicional ref para devolver la referencia al resultado de una de las dos expresiones.</span><span class="sxs-lookup"><span data-stu-id="94fa9-118">Beginning with C# 7.2, you can use the conditional ref expression to return the reference to the result of one of the two expressions.</span></span> <span data-ttu-id="94fa9-119">Puede asignar esa referencia a una variable [ref local](../keywords/ref.md#ref-locals) o [ref readonly local](../keywords/ref.md#ref-readonly-locals), o bien usarla como un [valor devuelto de referencia](../keywords/ref.md#reference-return-values) o como un [parámetro de método `ref`](../keywords/ref.md#passing-an-argument-by-reference).</span><span class="sxs-lookup"><span data-stu-id="94fa9-119">You can assign that reference to a [ref local](../keywords/ref.md#ref-locals) or [ref readonly local](../keywords/ref.md#ref-readonly-locals) variable, or use it as a [reference return value](../keywords/ref.md#reference-return-values) or as a [`ref` method parameter](../keywords/ref.md#passing-an-argument-by-reference).</span></span>

<span data-ttu-id="94fa9-120">La sintaxis de la expresión condicional ref es la siguiente:</span><span class="sxs-lookup"><span data-stu-id="94fa9-120">The syntax for the conditional ref expression is as follows:</span></span>

```csharp
condition ? ref consequent : ref alternative
```

<span data-ttu-id="94fa9-121">Al igual que el operador condicional original, la expresión condicional ref evalúa solo una de las dos expresiones: ya sea `consequent` o `alternative`.</span><span class="sxs-lookup"><span data-stu-id="94fa9-121">Like the original conditional operator, the conditional ref expression evaluates only one of the two expressions: either `consequent` or `alternative`.</span></span>

<span data-ttu-id="94fa9-122">En el caso de la expresión condicional ref, los tipos de `consequent` y `alternative` deben coincidir.</span><span class="sxs-lookup"><span data-stu-id="94fa9-122">In the case of the conditional ref expression, the type of `consequent` and `alternative` must be the same.</span></span>

<span data-ttu-id="94fa9-123">En el siguiente ejemplo se muestra el uso de la expresión condicional ref:</span><span class="sxs-lookup"><span data-stu-id="94fa9-123">The following example demonstrates the usage of the conditional ref expression:</span></span>

[!code-csharp[conditional ref](~/samples/snippets/csharp/language-reference/operators/ConditionalExamples.cs#ConditionalRef)]

<span data-ttu-id="94fa9-124">Para más información, vea la [nota de propuesta de características](../../../../_csharplang/proposals/csharp-7.2/conditional-ref.md).</span><span class="sxs-lookup"><span data-stu-id="94fa9-124">For more information, see the [feature proposal note](../../../../_csharplang/proposals/csharp-7.2/conditional-ref.md).</span></span>

## <a name="conditional-operator-and-an-ifelse-statement"></a><span data-ttu-id="94fa9-125">Operador condicional y una instrucción `if..else`</span><span class="sxs-lookup"><span data-stu-id="94fa9-125">Conditional operator and an `if..else` statement</span></span>

<span data-ttu-id="94fa9-126">El uso del operador condicional a través de una instrucción [if-else](../keywords/if-else.md) podría traducirse en código más conciso en aquellos casos en los que potencialmente tenga que calcular un valor.</span><span class="sxs-lookup"><span data-stu-id="94fa9-126">Use of the conditional operator over an [if-else](../keywords/if-else.md) statement might result in more concise code in cases when you need conditionally to compute a value.</span></span> <span data-ttu-id="94fa9-127">El ejemplo siguiente muestra dos maneras de clasificar un entero como negativo o no negativo:</span><span class="sxs-lookup"><span data-stu-id="94fa9-127">The following example demonstrates two ways to classify an integer as negative or nonnegative:</span></span>

[!code-csharp[conditional and if-else](~/samples/snippets/csharp/language-reference/operators/ConditionalExamples.cs#CompareWithIf)]

## <a name="operator-overloadability"></a><span data-ttu-id="94fa9-128">Posibilidad de sobrecarga del operador</span><span class="sxs-lookup"><span data-stu-id="94fa9-128">Operator overloadability</span></span>

<span data-ttu-id="94fa9-129">El operador condicional no se puede sobrecargar.</span><span class="sxs-lookup"><span data-stu-id="94fa9-129">The conditional operator cannot be overloaded.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="94fa9-130">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="94fa9-130">C# language specification</span></span>

<span data-ttu-id="94fa9-131">Para más información, vea la sección sobre [operadores condicionales](~/_csharplang/spec/expressions.md#conditional-operator) de la [Especificación del lenguaje C#](../language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="94fa9-131">For more information, see the [Conditional operator](~/_csharplang/spec/expressions.md#conditional-operator) section of the [C# language specification](../language-specification/index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="94fa9-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="94fa9-132">See also</span></span>

- [<span data-ttu-id="94fa9-133">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="94fa9-133">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="94fa9-134">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="94fa9-134">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="94fa9-135">Operadores de C#</span><span class="sxs-lookup"><span data-stu-id="94fa9-135">C# Operators</span></span>](index.md)
- [<span data-ttu-id="94fa9-136">Instrucción if-else</span><span class="sxs-lookup"><span data-stu-id="94fa9-136">if-else statement</span></span>](../keywords/if-else.md)
- <span data-ttu-id="94fa9-137">[Operadores ?. y ?[]](member-access-operators.md#null-conditional-operators--and-)</span><span class="sxs-lookup"><span data-stu-id="94fa9-137">[?. and ?[] Operators](member-access-operators.md#null-conditional-operators--and-)</span></span>
- [<span data-ttu-id="94fa9-138">Operador !</span><span class="sxs-lookup"><span data-stu-id="94fa9-138">?? Operator</span></span>](null-coalescing-operator.md)
- [<span data-ttu-id="94fa9-139">ref (palabra clave)</span><span class="sxs-lookup"><span data-stu-id="94fa9-139">ref keyword</span></span>](../keywords/ref.md)
