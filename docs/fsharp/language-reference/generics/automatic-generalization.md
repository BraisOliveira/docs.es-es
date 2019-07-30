---
title: Generalización automática
description: Obtenga información F# acerca de cómo generaliza automáticamente los argumentos y los tipos de funciones para que funcionen con varios tipos cuando sea posible.
ms.date: 05/16/2016
ms.openlocfilehash: 501749a190d9770cbcd9848e3d528cba32fe6762
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630627"
---
# <a name="automatic-generalization"></a><span data-ttu-id="cca2a-103">Generalización automática</span><span class="sxs-lookup"><span data-stu-id="cca2a-103">Automatic Generalization</span></span>

<span data-ttu-id="cca2a-104">F#utiliza la inferencia de tipos para evaluar los tipos de funciones y expresiones.</span><span class="sxs-lookup"><span data-stu-id="cca2a-104">F# uses type inference to evaluate the types of functions and expressions.</span></span> <span data-ttu-id="cca2a-105">En este tema se F# describe cómo generaliza automáticamente los argumentos y los tipos de funciones para que funcionen con varios tipos cuando sea posible.</span><span class="sxs-lookup"><span data-stu-id="cca2a-105">This topic describes how F# automatically generalizes the arguments and types of functions so that they work with multiple types when this is possible.</span></span>

## <a name="automatic-generalization"></a><span data-ttu-id="cca2a-106">Generalización automática</span><span class="sxs-lookup"><span data-stu-id="cca2a-106">Automatic Generalization</span></span>

<span data-ttu-id="cca2a-107">El F# compilador, cuando realiza la inferencia de tipos en una función, determina si un parámetro determinado puede ser genérico.</span><span class="sxs-lookup"><span data-stu-id="cca2a-107">The F# compiler, when it performs type inference on a function, determines whether a given parameter can be generic.</span></span> <span data-ttu-id="cca2a-108">El compilador examina cada parámetro y determina si la función tiene una dependencia en el tipo específico de ese parámetro.</span><span class="sxs-lookup"><span data-stu-id="cca2a-108">The compiler examines each parameter and determines whether the function has a dependency on the specific type of that parameter.</span></span> <span data-ttu-id="cca2a-109">Si no es así, se deduce que el tipo es genérico.</span><span class="sxs-lookup"><span data-stu-id="cca2a-109">If it does not, the type is inferred to be generic.</span></span>

<span data-ttu-id="cca2a-110">En el ejemplo de código siguiente se muestra una función que el compilador deduce que es genérica.</span><span class="sxs-lookup"><span data-stu-id="cca2a-110">The following code example illustrates a function that the compiler infers to be generic.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-3/snippet101.fs)]

<span data-ttu-id="cca2a-111">El tipo se deduce como `'a -> 'a -> 'a`.</span><span class="sxs-lookup"><span data-stu-id="cca2a-111">The type is inferred to be `'a -> 'a -> 'a`.</span></span>

<span data-ttu-id="cca2a-112">El tipo indica que se trata de una función que toma dos argumentos del mismo tipo desconocido y devuelve un valor del mismo tipo.</span><span class="sxs-lookup"><span data-stu-id="cca2a-112">The type indicates that this is a function that takes two arguments of the same unknown type and returns a value of that same type.</span></span> <span data-ttu-id="cca2a-113">Uno de los motivos por los que la función anterior puede ser genérico es que el operador "mayor`>`que" () es genérico.</span><span class="sxs-lookup"><span data-stu-id="cca2a-113">One of the reasons that the previous function can be generic is that the greater-than operator (`>`) is itself generic.</span></span> <span data-ttu-id="cca2a-114">El operador mayor que tiene la firma `'a -> 'a -> bool`.</span><span class="sxs-lookup"><span data-stu-id="cca2a-114">The greater-than operator has the signature `'a -> 'a -> bool`.</span></span> <span data-ttu-id="cca2a-115">No todos los operadores son genéricos y, si el código de una función usa un tipo de parámetro junto con una función o un operador no genéricos, ese tipo de parámetro no se puede generalizar.</span><span class="sxs-lookup"><span data-stu-id="cca2a-115">Not all operators are generic, and if the code in a function uses a parameter type together with a non-generic function or operator, that parameter type cannot be generalized.</span></span>

<span data-ttu-id="cca2a-116">Dado `max` que es genérico, se puede usar con tipos `int`como, `float`, etc., como se muestra en los ejemplos siguientes.</span><span class="sxs-lookup"><span data-stu-id="cca2a-116">Because `max` is generic, it can be used with types such as `int`, `float`, and so on, as shown in the following examples.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-3/snippet102.fs)]

<span data-ttu-id="cca2a-117">Sin embargo, los dos argumentos deben ser del mismo tipo.</span><span class="sxs-lookup"><span data-stu-id="cca2a-117">However, the two arguments must be of the same type.</span></span> <span data-ttu-id="cca2a-118">La firma es `'a -> 'a -> 'a`, no `'a -> 'b -> 'a`.</span><span class="sxs-lookup"><span data-stu-id="cca2a-118">The signature is `'a -> 'a -> 'a`, not `'a -> 'b -> 'a`.</span></span> <span data-ttu-id="cca2a-119">Por lo tanto, el código siguiente genera un error porque los tipos no coinciden.</span><span class="sxs-lookup"><span data-stu-id="cca2a-119">Therefore, the following code produces an error because the types do not match.</span></span>

```fsharp
// Error: type mismatch.
let biggestIntFloat = max 2.0 3
```

<span data-ttu-id="cca2a-120">La `max` función también funciona con cualquier tipo que admita el operador mayor que.</span><span class="sxs-lookup"><span data-stu-id="cca2a-120">The `max` function also works with any type that supports the greater-than operator.</span></span> <span data-ttu-id="cca2a-121">Por lo tanto, también puede utilizarlo en una cadena, como se muestra en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="cca2a-121">Therefore, you could also use it on a string, as shown in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-3/snippet104.fs)]

## <a name="value-restriction"></a><span data-ttu-id="cca2a-122">Restricción de valor</span><span class="sxs-lookup"><span data-stu-id="cca2a-122">Value Restriction</span></span>

<span data-ttu-id="cca2a-123">El compilador realiza la generalización automática solo en definiciones de función completas que tienen argumentos explícitos y en valores inmutables simples.</span><span class="sxs-lookup"><span data-stu-id="cca2a-123">The compiler performs automatic generalization only on complete function definitions that have explicit arguments, and on simple immutable values.</span></span>

<span data-ttu-id="cca2a-124">Esto significa que el compilador emite un error si se intenta compilar código que no está suficientemente restringido para ser un tipo específico, sino que tampoco se puede generalizar.</span><span class="sxs-lookup"><span data-stu-id="cca2a-124">This means that the compiler issues an error if you try to compile code that is not sufficiently constrained to be a specific type, but is also not generalizable.</span></span> <span data-ttu-id="cca2a-125">El mensaje de error para este problema hace referencia a esta restricción en la generalización automática de los valores como *restricción de valor*.</span><span class="sxs-lookup"><span data-stu-id="cca2a-125">The error message for this problem refers to this restriction on automatic generalization for values as the *value restriction*.</span></span>

<span data-ttu-id="cca2a-126">Normalmente, el error de restricción de valor se produce cuando se desea que una construcción sea genérica pero el compilador no tiene información suficiente para generalizarla, o cuando se omite involuntariamente suficiente información de tipo en una construcción no genérica.</span><span class="sxs-lookup"><span data-stu-id="cca2a-126">Typically, the value restriction error occurs either when you want a construct to be generic but the compiler has insufficient information to generalize it, or when you unintentionally omit sufficient type information in a nongeneric construct.</span></span> <span data-ttu-id="cca2a-127">La solución al error de restricción de valor es proporcionar información más explícita para restringir más el problema de inferencia de tipos de una de las siguientes maneras:</span><span class="sxs-lookup"><span data-stu-id="cca2a-127">The solution to the value restriction error is to provide more explicit information to more fully constrain the type inference problem, in one of the following ways:</span></span>

- <span data-ttu-id="cca2a-128">Restrinja un tipo para que no sea genérico agregando una anotación de tipo explícito a un valor o parámetro.</span><span class="sxs-lookup"><span data-stu-id="cca2a-128">Constrain a type to be nongeneric by adding an explicit type annotation to a value or parameter.</span></span>

- <span data-ttu-id="cca2a-129">Si el problema utiliza una construcción no generalizable para definir una función genérica, como una composición de función o argumentos de función currificados aplicados incompletamente, intente volver a escribir la función como una definición de función normal.</span><span class="sxs-lookup"><span data-stu-id="cca2a-129">If the problem is using a nongeneralizable construct to define a generic function, such as a function composition or incompletely applied curried function arguments, try to rewrite the function as an ordinary function definition.</span></span>

- <span data-ttu-id="cca2a-130">Si el problema es una expresión que es demasiado compleja para generalizarla, puede convertirla en una función agregando un parámetro adicional sin usar.</span><span class="sxs-lookup"><span data-stu-id="cca2a-130">If the problem is an expression that is too complex to be generalized, make it into a function by adding an extra, unused parameter.</span></span>

- <span data-ttu-id="cca2a-131">Agregue parámetros de tipo genérico explícitos.</span><span class="sxs-lookup"><span data-stu-id="cca2a-131">Add explicit generic type parameters.</span></span> <span data-ttu-id="cca2a-132">Esta opción rara vez se usa.</span><span class="sxs-lookup"><span data-stu-id="cca2a-132">This option is rarely used.</span></span>

- <span data-ttu-id="cca2a-133">En los siguientes ejemplos de código se muestra cada uno de estos escenarios.</span><span class="sxs-lookup"><span data-stu-id="cca2a-133">The following code examples illustrate each of these scenarios.</span></span>

<span data-ttu-id="cca2a-134">Caso 1: Una expresión demasiado compleja.</span><span class="sxs-lookup"><span data-stu-id="cca2a-134">Case 1: Too complex an expression.</span></span> <span data-ttu-id="cca2a-135">En este ejemplo, la lista `counter` está pensada para `int option ref`ser, pero no se define como un valor inmutable simple.</span><span class="sxs-lookup"><span data-stu-id="cca2a-135">In this example, the list `counter` is intended to be `int option ref`, but it is not defined as a simple immutable value.</span></span>

```fsharp
let counter = ref None
// Adding a type annotation fixes the problem:
let counter : int option ref = ref None
```

<span data-ttu-id="cca2a-136">Caso 2: Usar una construcción no generalizable para definir una función genérica.</span><span class="sxs-lookup"><span data-stu-id="cca2a-136">Case 2: Using a nongeneralizable construct to define a generic function.</span></span> <span data-ttu-id="cca2a-137">En este ejemplo, la construcción no es generalizable porque implica la aplicación parcial de argumentos de función.</span><span class="sxs-lookup"><span data-stu-id="cca2a-137">In this example, the construct is nongeneralizable because it involves partial application of function arguments.</span></span>

```fsharp
let maxhash = max << hash
// The following is acceptable because the argument for maxhash is explicit:
let maxhash obj = (max << hash) obj
```

<span data-ttu-id="cca2a-138">Caso 3: Agregar un parámetro adicional sin usar.</span><span class="sxs-lookup"><span data-stu-id="cca2a-138">Case 3: Adding an extra, unused parameter.</span></span> <span data-ttu-id="cca2a-139">Dado que esta expresión no es lo suficientemente sencilla para la generalización, el compilador emite el error de restricción de valor.</span><span class="sxs-lookup"><span data-stu-id="cca2a-139">Because this expression is not simple enough for generalization, the compiler issues the value restriction error.</span></span>

```fsharp
let emptyList10 = Array.create 10 []
// Adding an extra (unused) parameter makes it a function, which is generalizable.
let emptyList10 () = Array.create 10 []
```

<span data-ttu-id="cca2a-140">Caso 4: Agregar parámetros de tipo.</span><span class="sxs-lookup"><span data-stu-id="cca2a-140">Case 4: Adding type parameters.</span></span>

```fsharp
let arrayOf10Lists = Array.create 10 []
// Adding a type parameter and type annotation lets you write a generic value.
let arrayOf10Lists<'T> = Array.create 10 ([]:'T list)
```

<span data-ttu-id="cca2a-141">En el último caso, el valor se convierte en una función de tipo, que se puede usar para crear valores de muchos tipos diferentes, como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="cca2a-141">In the last case, the value becomes a type function, which may be used to create values of many different types, for example as follows:</span></span>

```fsharp
let intLists = arrayOf10Lists<int>
let floatLists = arrayOf10Lists<float>
```

## <a name="see-also"></a><span data-ttu-id="cca2a-142">Vea también</span><span class="sxs-lookup"><span data-stu-id="cca2a-142">See also</span></span>

- [<span data-ttu-id="cca2a-143">Inferencia de tipos</span><span class="sxs-lookup"><span data-stu-id="cca2a-143">Type Inference</span></span>](../type-inference.md)
- [<span data-ttu-id="cca2a-144">Genéricos</span><span class="sxs-lookup"><span data-stu-id="cca2a-144">Generics</span></span>](index.md)
- [<span data-ttu-id="cca2a-145">Parámetros de tipo resueltos estáticamente</span><span class="sxs-lookup"><span data-stu-id="cca2a-145">Statically Resolved Type Parameters</span></span>](statically-resolved-type-parameters.md)
- [<span data-ttu-id="cca2a-146">Restricciones</span><span class="sxs-lookup"><span data-stu-id="cca2a-146">Constraints</span></span>](constraints.md)
