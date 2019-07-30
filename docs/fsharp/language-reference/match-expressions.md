---
title: Expresiones de coincidencia
description: Obtenga información sobre F# cómo la expresión de coincidencia proporciona control de bifurcación que se basa en la comparación de una expresión con un conjunto de patrones.
ms.date: 04/19/2018
ms.openlocfilehash: 222cb0604300039d86ed0c80293651631d212eb6
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/30/2019
ms.locfileid: "68627614"
---
# <a name="match-expressions"></a><span data-ttu-id="68afb-103">Expresiones de coincidencia</span><span class="sxs-lookup"><span data-stu-id="68afb-103">Match expressions</span></span>

<span data-ttu-id="68afb-104">La `match` expresión proporciona control de bifurcación que se basa en la comparación de una expresión con un conjunto de patrones.</span><span class="sxs-lookup"><span data-stu-id="68afb-104">The `match` expression provides branching control that is based on the comparison of an expression with a set of patterns.</span></span>

## <a name="syntax"></a><span data-ttu-id="68afb-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="68afb-105">Syntax</span></span>

```fsharp
// Match expression.
match test-expression with
| pattern1 [ when condition ] -> result-expression1
| pattern2 [ when condition ] -> result-expression2
| ...

// Pattern matching function.
function
| pattern1 [ when condition ] -> result-expression1
| pattern2 [ when condition ] -> result-expression2
| ...
```

## <a name="remarks"></a><span data-ttu-id="68afb-106">Comentarios</span><span class="sxs-lookup"><span data-stu-id="68afb-106">Remarks</span></span>

<span data-ttu-id="68afb-107">Las expresiones de coincidencia de patrones permiten la bifurcación compleja basada en la comparación de una expresión de prueba con un conjunto de patrones.</span><span class="sxs-lookup"><span data-stu-id="68afb-107">The pattern matching expressions allow for complex branching based on the comparison of a test expression with a set of patterns.</span></span> <span data-ttu-id="68afb-108">En la `match` expresión, *Test-Expression* se compara con cada patrón a su vez y, cuando se encuentra una coincidencia, se evalúa la *expresión de resultado* correspondiente y el valor resultante se devuelve como el valor de la expresión de coincidencia.</span><span class="sxs-lookup"><span data-stu-id="68afb-108">In the `match` expression, the *test-expression* is compared with each pattern in turn, and when a match is found, the corresponding *result-expression* is evaluated and the resulting value is returned as the value of the match expression.</span></span>

<span data-ttu-id="68afb-109">La función de coincidencia de patrones mostrada en la sintaxis anterior es una expresión lambda en la que la coincidencia de patrones se realiza inmediatamente en el argumento.</span><span class="sxs-lookup"><span data-stu-id="68afb-109">The pattern matching function shown in the previous syntax is a lambda expression in which pattern matching is performed immediately on the argument.</span></span> <span data-ttu-id="68afb-110">La función de coincidencia de patrones que se muestra en la sintaxis anterior es equivalente a la siguiente.</span><span class="sxs-lookup"><span data-stu-id="68afb-110">The pattern matching function shown in the previous syntax is equivalent to the following.</span></span>

```fsharp
fun arg ->
    match arg with
    | pattern1 [ when condition ] -> result-expression1
    | pattern2 [ when condition ] -> result-expression2
    | ...
```

<span data-ttu-id="68afb-111">Para obtener más información sobre las expresiones lambda [, vea expresiones lambda: `fun` Palabra clave](./functions/lambda-expressions-the-fun-keyword.md).</span><span class="sxs-lookup"><span data-stu-id="68afb-111">For more information about lambda expressions, see [Lambda Expressions: The `fun` Keyword](./functions/lambda-expressions-the-fun-keyword.md).</span></span>

<span data-ttu-id="68afb-112">Todo el conjunto de patrones debe cubrir todas las posibles coincidencias de la variable de entrada.</span><span class="sxs-lookup"><span data-stu-id="68afb-112">The whole set of patterns should cover all the possible matches of the input variable.</span></span> <span data-ttu-id="68afb-113">Con frecuencia, se usa el patrón de`_`carácter comodín () como último patrón para buscar coincidencias con los valores de entrada no coincidentes previamente.</span><span class="sxs-lookup"><span data-stu-id="68afb-113">Frequently, you use the wildcard pattern (`_`) as the last pattern to match any previously unmatched input values.</span></span>

<span data-ttu-id="68afb-114">En el código siguiente se muestran algunas de las formas en que `match` se usa la expresión.</span><span class="sxs-lookup"><span data-stu-id="68afb-114">The following code illustrates some of the ways in which the `match` expression is used.</span></span> <span data-ttu-id="68afb-115">Para obtener una referencia y ejemplos de todos los patrones posibles que se pueden usar, vea [coincidencia de patrones](pattern-matching.md).</span><span class="sxs-lookup"><span data-stu-id="68afb-115">For a reference and examples of all the possible patterns that can be used, see [Pattern Matching](pattern-matching.md).</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4601.fs)]

## <a name="guards-on-patterns"></a><span data-ttu-id="68afb-116">Protecciones en patrones</span><span class="sxs-lookup"><span data-stu-id="68afb-116">Guards on patterns</span></span>

<span data-ttu-id="68afb-117">Puede usar una `when` cláusula para especificar una condición adicional que la variable debe cumplir para que coincida con un patrón.</span><span class="sxs-lookup"><span data-stu-id="68afb-117">You can use a `when` clause to specify an additional condition that the variable must satisfy to match a pattern.</span></span> <span data-ttu-id="68afb-118">Este tipo de cláusula se conoce como *protección*.</span><span class="sxs-lookup"><span data-stu-id="68afb-118">Such a clause is referred to as a *guard*.</span></span> <span data-ttu-id="68afb-119">La expresión que sigue `when` a la palabra clave no se evalúa a menos que se haga una coincidencia con el patrón asociado a dicha protección.</span><span class="sxs-lookup"><span data-stu-id="68afb-119">The expression following the `when` keyword is not evaluated unless a match is made to the pattern associated with that guard.</span></span>

<span data-ttu-id="68afb-120">En el ejemplo siguiente se muestra el uso de una protección para especificar un intervalo numérico para un patrón de variable.</span><span class="sxs-lookup"><span data-stu-id="68afb-120">The following example illustrates the use of a guard to specify a numeric range for a variable pattern.</span></span> <span data-ttu-id="68afb-121">Tenga en cuenta que se combinan varias condiciones mediante el uso de operadores booleanos.</span><span class="sxs-lookup"><span data-stu-id="68afb-121">Note that multiple conditions are combined by using Boolean operators.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4602.fs)]

<span data-ttu-id="68afb-122">Tenga en cuenta que, dado que los valores distintos de los literales no se pueden usar en `when` el modelo, debe utilizar una cláusula si tiene que comparar alguna parte de la entrada con un valor.</span><span class="sxs-lookup"><span data-stu-id="68afb-122">Note that because values other than literals cannot be used in the pattern, you must use a `when` clause if you have to compare some part of the input against a value.</span></span> <span data-ttu-id="68afb-123">Esto se muestra en el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="68afb-123">This is shown in the following code:</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4603.fs)]

<span data-ttu-id="68afb-124">Tenga en cuenta que cuando un modelo de Unión está incluido en una protección, la protección se aplica a **todos** los patrones, no solo al último.</span><span class="sxs-lookup"><span data-stu-id="68afb-124">Note that when a union pattern is covered by a guard, the guard applies to **all** of the patterns, not just the last one.</span></span> <span data-ttu-id="68afb-125">Por ejemplo, según el código siguiente, la protección `when a > 12` se aplica tanto `A a` a `B a`como a:</span><span class="sxs-lookup"><span data-stu-id="68afb-125">For example, given the following code, the guard `when a > 12` applies to both `A a` and `B a`:</span></span>

```fsharp
type Union =
    | A of int
    | B of int

let foo() =
    let test = A 42
    match test with
    | A a
    | B a when a > 41 -> a // the guard applies to both patterns
    | _ -> 1

foo() // returns 42
```

## <a name="see-also"></a><span data-ttu-id="68afb-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="68afb-126">See also</span></span>

- [<span data-ttu-id="68afb-127">Referencia del lenguaje F#</span><span class="sxs-lookup"><span data-stu-id="68afb-127">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="68afb-128">Patrones activos</span><span class="sxs-lookup"><span data-stu-id="68afb-128">Active Patterns</span></span>](active-patterns.md)
- [<span data-ttu-id="68afb-129">Coincidencia de patrones</span><span class="sxs-lookup"><span data-stu-id="68afb-129">Pattern Matching</span></span>](pattern-matching.md)
