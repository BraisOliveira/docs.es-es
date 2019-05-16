---
title: Unit (Tipo)
description: Obtenga información sobre cómo el F# tipo "unit" a menudo se usa para contener el lugar donde se requiere un valor mediante la sintaxis del lenguaje cuando se necesita ningún valor o se desea.
ms.date: 05/16/2016
ms.openlocfilehash: d515e19489bfa7de6f17194fd74176cfa0bcd7c9
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "65645121"
---
# <a name="unit-type"></a><span data-ttu-id="4a715-103">Unit (Tipo)</span><span class="sxs-lookup"><span data-stu-id="4a715-103">Unit Type</span></span>

<span data-ttu-id="4a715-104">El `unit` tipo es un tipo que indica la ausencia de un valor específico; el `unit` tipo tiene un solo valor, que actúa como un marcador de posición cuando ningún otro valor existe o es necesario.</span><span class="sxs-lookup"><span data-stu-id="4a715-104">The `unit` type is a type that indicates the absence of a specific value; the `unit` type has only a single value, which acts as a placeholder when no other value exists or is needed.</span></span>

## <a name="syntax"></a><span data-ttu-id="4a715-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4a715-105">Syntax</span></span>

```fsharp
// The value of the unit type.
()
```

## <a name="remarks"></a><span data-ttu-id="4a715-106">Comentarios</span><span class="sxs-lookup"><span data-stu-id="4a715-106">Remarks</span></span>

<span data-ttu-id="4a715-107">Cada F# expresión debe evaluarse como un valor.</span><span class="sxs-lookup"><span data-stu-id="4a715-107">Every F# expression must evaluate to a value.</span></span> <span data-ttu-id="4a715-108">Para las expresiones que no generan un valor que es de interés, el valor de tipo `unit` se utiliza.</span><span class="sxs-lookup"><span data-stu-id="4a715-108">For expressions that do not generate a value that is of interest, the value of type `unit` is used.</span></span> <span data-ttu-id="4a715-109">El `unit` tipo es similar a la `void` tipo en lenguajes como C# y C++.</span><span class="sxs-lookup"><span data-stu-id="4a715-109">The `unit` type resembles the `void` type in languages such as C# and C++.</span></span>

<span data-ttu-id="4a715-110">El `unit` tipo tiene un valor único, y ese valor se indica mediante el token `()`.</span><span class="sxs-lookup"><span data-stu-id="4a715-110">The `unit` type has a single value, and that value is indicated by the token `()`.</span></span>

<span data-ttu-id="4a715-111">El valor de la `unit` a menudo se usa el tipo F# programación para mantener la posición donde se requiere un valor mediante la sintaxis del lenguaje, pero cuando se necesita ningún valor o se desea.</span><span class="sxs-lookup"><span data-stu-id="4a715-111">The value of the `unit` type is often used in F# programming to hold the place where a value is required by the language syntax, but when no value is needed or desired.</span></span> <span data-ttu-id="4a715-112">Un ejemplo podría ser el valor devuelto de un `printf` función.</span><span class="sxs-lookup"><span data-stu-id="4a715-112">An example might be the return value of a `printf` function.</span></span> <span data-ttu-id="4a715-113">Dado que las acciones importantes de la `printf` operación se producen en la función, la función no tiene que devolver un valor real.</span><span class="sxs-lookup"><span data-stu-id="4a715-113">Because the important actions of the `printf` operation occur in the function, the function does not have to return an actual value.</span></span> <span data-ttu-id="4a715-114">Por lo tanto, el valor devuelto es de tipo `unit`.</span><span class="sxs-lookup"><span data-stu-id="4a715-114">Therefore, the return value is of type `unit`.</span></span>

<span data-ttu-id="4a715-115">Algunas construcciones esperan un `unit` valor.</span><span class="sxs-lookup"><span data-stu-id="4a715-115">Some constructs expect a `unit` value.</span></span> <span data-ttu-id="4a715-116">Por ejemplo, un `do` enlace o cualquier código en el nivel superior de un módulo que se espera que se evalúan como un `unit` valor.</span><span class="sxs-lookup"><span data-stu-id="4a715-116">For example, a `do` binding or any code at the top level of a module is expected to evaluate to a `unit` value.</span></span> <span data-ttu-id="4a715-117">El compilador emite una advertencia cuando un `do` enlace o código en el nivel superior de un módulo genera un resultado distinto el `unit` valor que no se usa, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="4a715-117">The compiler reports a warning when a `do` binding or code at the top level of a module produces a result other than the `unit` value that is not used, as shown in the following example.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet901.fs)]

<span data-ttu-id="4a715-118">Esta advertencia es una característica de programación funcional; no aparecen en otros lenguajes de programación. NET.</span><span class="sxs-lookup"><span data-stu-id="4a715-118">This warning is a characteristic of functional programming; it does not appear in other .NET programming languages.</span></span> <span data-ttu-id="4a715-119">En un programa puramente funcional, en el que las funciones no tienen efectos secundarios, el valor devuelto final es el único resultado de una llamada de función.</span><span class="sxs-lookup"><span data-stu-id="4a715-119">In a purely functional program, in which functions do not have any side effects, the final return value is the only result of a function call.</span></span> <span data-ttu-id="4a715-120">Por lo tanto, cuando se omite el resultado es un posible error de programación.</span><span class="sxs-lookup"><span data-stu-id="4a715-120">Therefore, when the result is ignored, it is a possible programming error.</span></span> <span data-ttu-id="4a715-121">Aunque F# no es puramente funcional lenguaje de programación, resulta conveniente seguir el estilo de programación funcional, siempre que sea posible.</span><span class="sxs-lookup"><span data-stu-id="4a715-121">Although F# is not a purely functional programming language, it is a good practice to follow functional programming style whenever possible.</span></span>

## <a name="see-also"></a><span data-ttu-id="4a715-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="4a715-122">See also</span></span>

- [<span data-ttu-id="4a715-123">Primitivos</span><span class="sxs-lookup"><span data-stu-id="4a715-123">Primitive</span></span>](primitive-types.md)
- [<span data-ttu-id="4a715-124">Referencia del lenguaje F#</span><span class="sxs-lookup"><span data-stu-id="4a715-124">F# Language Reference</span></span>](index.md)
