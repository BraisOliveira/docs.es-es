---
title: 'Bucles: expresión for...in'
description: Vea cómo el F# for.. en expresión de construcción de bucle se utiliza para recorrer en iteración las coincidencias de un patrón en una colección enumerable.
ms.date: 05/16/2016
ms.openlocfilehash: adaf448a49cf53c63c41f9156d40ee5d1ad3caeb
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62024448"
---
# <a name="loops-forin-expression"></a><span data-ttu-id="2db1a-103">Bucles: expresión for...in</span><span class="sxs-lookup"><span data-stu-id="2db1a-103">Loops: for...in Expression</span></span>

<span data-ttu-id="2db1a-104">Se utiliza esta construcción de bucle para recorrer en iteración las coincidencias de un patrón en una colección enumerable como una expresión de intervalo, secuencia, lista, matriz u otra construcción que admita la enumeración.</span><span class="sxs-lookup"><span data-stu-id="2db1a-104">This looping construct is used to iterate over the matches of a pattern in an enumerable collection such as a range expression, sequence, list, array, or other construct that supports enumeration.</span></span>

## <a name="syntax"></a><span data-ttu-id="2db1a-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2db1a-105">Syntax</span></span>

```fsharp
for pattern in enumerable-expression do
    body-expression
```

## <a name="remarks"></a><span data-ttu-id="2db1a-106">Comentarios</span><span class="sxs-lookup"><span data-stu-id="2db1a-106">Remarks</span></span>

<span data-ttu-id="2db1a-107">El `for...in` expresión puede compararse con el `for each` instrucción en otros lenguajes .NET porque se usa para iterar por los valores en una colección enumerable.</span><span class="sxs-lookup"><span data-stu-id="2db1a-107">The `for...in` expression can be compared to the `for each` statement in other .NET languages because it is used to loop over the values in an enumerable collection.</span></span> <span data-ttu-id="2db1a-108">Sin embargo, `for...in` también admite el patrón de coincidencia a través de la colección en lugar de solo la iteración a través de toda la colección.</span><span class="sxs-lookup"><span data-stu-id="2db1a-108">However, `for...in` also supports pattern matching over the collection instead of just iteration over the whole collection.</span></span>

<span data-ttu-id="2db1a-109">La expresión enumerable se puede especificar como una colección enumerable o, mediante el `..` operador, como un intervalo en un tipo entero.</span><span class="sxs-lookup"><span data-stu-id="2db1a-109">The enumerable expression can be specified as an enumerable collection or, by using the `..` operator, as a range on an integral type.</span></span> <span data-ttu-id="2db1a-110">Colecciones enumerables incluyen listas, secuencias, matrices, conjuntos, mapas y así sucesivamente.</span><span class="sxs-lookup"><span data-stu-id="2db1a-110">Enumerable collections include lists, sequences, arrays, sets, maps, and so on.</span></span> <span data-ttu-id="2db1a-111">Cualquier tipo que implemente `System.Collections.IEnumerable` se puede usar.</span><span class="sxs-lookup"><span data-stu-id="2db1a-111">Any type that implements `System.Collections.IEnumerable` can be used.</span></span>

<span data-ttu-id="2db1a-112">Al expresar un intervalo mediante el `..` , puede usar la sintaxis siguiente.</span><span class="sxs-lookup"><span data-stu-id="2db1a-112">When you express a range by using the `..` operator, you can use the following syntax.</span></span>

<span data-ttu-id="2db1a-113">*iniciar* ...</span><span class="sxs-lookup"><span data-stu-id="2db1a-113">*start* ..</span></span> <span data-ttu-id="2db1a-114">*finish*</span><span class="sxs-lookup"><span data-stu-id="2db1a-114">*finish*</span></span>

<span data-ttu-id="2db1a-115">También puede usar una versión que incluye un incremento denominado el *omitir*, como en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="2db1a-115">You can also use a version that includes an increment called the *skip*, as in the following code.</span></span>

<span data-ttu-id="2db1a-116">*iniciar* ...</span><span class="sxs-lookup"><span data-stu-id="2db1a-116">*start* ..</span></span> <span data-ttu-id="2db1a-117">*omitir* ...</span><span class="sxs-lookup"><span data-stu-id="2db1a-117">*skip* ..</span></span> <span data-ttu-id="2db1a-118">*finish*</span><span class="sxs-lookup"><span data-stu-id="2db1a-118">*finish*</span></span>

<span data-ttu-id="2db1a-119">Al usar intervalos de enteros y una variable de contador simple como un patrón, el comportamiento típico es incrementar la variable de contador en 1 en cada iteración, pero si el intervalo incluye un valor de omisión, el contador se incrementa en el valor de omisión en su lugar.</span><span class="sxs-lookup"><span data-stu-id="2db1a-119">When you use integral ranges and a simple counter variable as a pattern, the typical behavior is to increment the counter variable by 1 on each iteration, but if the range includes a skip value, the counter is incremented by the skip value instead.</span></span>

<span data-ttu-id="2db1a-120">Los valores coincidentes en el patrón también pueden utilizarse en la expresión de cuerpo.</span><span class="sxs-lookup"><span data-stu-id="2db1a-120">Values matched in the pattern can also be used in the body expression.</span></span>

<span data-ttu-id="2db1a-121">Ejemplos de código siguientes ilustran el uso de la `for...in` expresión.</span><span class="sxs-lookup"><span data-stu-id="2db1a-121">The following code examples illustrate the use of the `for...in` expression.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5201.fs)]

<span data-ttu-id="2db1a-122">La salida es la siguiente.</span><span class="sxs-lookup"><span data-stu-id="2db1a-122">The output is as follows.</span></span>

```
1
5
100
450
788
```

<span data-ttu-id="2db1a-123">El ejemplo siguiente muestra cómo crear bucles a través de una secuencia y cómo usar un modelo de tupla en lugar de una variable simple.</span><span class="sxs-lookup"><span data-stu-id="2db1a-123">The following example shows how to loop over a sequence, and how to use a tuple pattern instead of a simple variable.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5202.fs)]

<span data-ttu-id="2db1a-124">La salida es la siguiente.</span><span class="sxs-lookup"><span data-stu-id="2db1a-124">The output is as follows.</span></span>

```
1 squared is 1
2 squared is 4
3 squared is 9
4 squared is 16
5 squared is 25
6 squared is 36
7 squared is 49
8 squared is 64
9 squared is 81
10 squared is 100
```

<span data-ttu-id="2db1a-125">El ejemplo siguiente muestra cómo recorrer en un intervalo de número entero simple.</span><span class="sxs-lookup"><span data-stu-id="2db1a-125">The following example shows how to loop over a simple integer range.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5203.fs)]

<span data-ttu-id="2db1a-126">La salida de function1 es como sigue.</span><span class="sxs-lookup"><span data-stu-id="2db1a-126">The output of function1 is as follows.</span></span>

```
1 2 3 4 5 6 7 8 9 10
```

<span data-ttu-id="2db1a-127">El ejemplo siguiente muestra cómo recorrer en iteración un intervalo con un salto 2, que incluye todos los elementos del intervalo.</span><span class="sxs-lookup"><span data-stu-id="2db1a-127">The following example shows how to loop over a range with a skip of 2, which includes every other element of the range.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5204.fs)]

<span data-ttu-id="2db1a-128">La salida de `function2` es como sigue.</span><span class="sxs-lookup"><span data-stu-id="2db1a-128">The output of `function2` is as follows.</span></span>

```
1 3 5 7 9
```

<span data-ttu-id="2db1a-129">El ejemplo siguiente muestra cómo usar un intervalo de caracteres.</span><span class="sxs-lookup"><span data-stu-id="2db1a-129">The following example shows how to use a character range.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5205.fs)]

<span data-ttu-id="2db1a-130">La salida de `function3` es como sigue.</span><span class="sxs-lookup"><span data-stu-id="2db1a-130">The output of `function3` is as follows.</span></span>

```
a b c d e f g h i j k l m n o p q r s t u v w x y z
```

<span data-ttu-id="2db1a-131">El ejemplo siguiente muestra cómo usar un valor negativo skip para una iteración inversa.</span><span class="sxs-lookup"><span data-stu-id="2db1a-131">The following example shows how to use a negative skip value for a reverse iteration.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5208.fs)]

<span data-ttu-id="2db1a-132">La salida de `function4` es como sigue.</span><span class="sxs-lookup"><span data-stu-id="2db1a-132">The output of `function4` is as follows.</span></span>

```
10 9 8 7 6 5 4 3 2 1 ... Lift off!
```

<span data-ttu-id="2db1a-133">El principio y el final del intervalo también pueden ser expresiones, como funciones, como se muestra en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="2db1a-133">The beginning and ending of the range can also be expressions, such as functions, as in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5206.fs)]

<span data-ttu-id="2db1a-134">La salida de `function5` con esta entrada es la siguiente.</span><span class="sxs-lookup"><span data-stu-id="2db1a-134">The output of `function5` with this input is as follows.</span></span>

```
2 3 4 5 6 7 8 9 10 11 12 13 14 15 16 17 18
```

<span data-ttu-id="2db1a-135">En el ejemplo siguiente se muestra el uso de un carácter comodín (\_) cuando el elemento no es necesario en el bucle.</span><span class="sxs-lookup"><span data-stu-id="2db1a-135">The next example shows the use of a wildcard character (\_) when the element is not needed in the loop.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5207.fs)]

<span data-ttu-id="2db1a-136">La salida es la siguiente.</span><span class="sxs-lookup"><span data-stu-id="2db1a-136">The output is as follows.</span></span>

```
Number of elements in list1: 5
```

<span data-ttu-id="2db1a-137">`Note` Puede usar `for...in` en las expresiones de secuencia y otras expresiones de cálculo, en cuyo caso una versión personalizada de la `for...in` se usa la expresión.</span><span class="sxs-lookup"><span data-stu-id="2db1a-137">`Note` You can use `for...in` in sequence expressions and other computation expressions, in which case a customized version of the `for...in` expression is used.</span></span> <span data-ttu-id="2db1a-138">Para obtener más información, consulte [secuencias](sequences.md), [flujos de trabajo asincrónicos](asynchronous-workflows.md), y [expresiones de cálculo](computation-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="2db1a-138">For more information, see [Sequences](sequences.md), [Asynchronous Workflows](asynchronous-workflows.md), and [Computation Expressions](computation-expressions.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="2db1a-139">Vea también</span><span class="sxs-lookup"><span data-stu-id="2db1a-139">See also</span></span>

- [<span data-ttu-id="2db1a-140">Referencia del lenguaje F#</span><span class="sxs-lookup"><span data-stu-id="2db1a-140">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="2db1a-141">Bucles: `for...to` Expresión</span><span class="sxs-lookup"><span data-stu-id="2db1a-141">Loops: `for...to` Expression</span></span>](loops-for-to-expression.md)
- [<span data-ttu-id="2db1a-142">Bucles: `while...do` Expresión</span><span class="sxs-lookup"><span data-stu-id="2db1a-142">Loops: `while...do` Expression</span></span>](loops-while-do-expression.md)