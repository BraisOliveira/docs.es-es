---
title: ¿Qué es F#?
description: Conozca los aspectos del F# lenguaje de programación es y qué F# programación es similar a. Obtenga información sobre los tipos de datos enriquecidos, funciones y cómo encajan entre sí.
ms.date: 08/03/2018
ms.openlocfilehash: fc4f4db771c43a4ec08cc9d3a247cf1f38e60457
ms.sourcegitcommit: 2d42b7ae4252cfe1232777f501ea9ac97df31b63
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2019
ms.locfileid: "67486830"
---
# <a name="what-is-f"></a><span data-ttu-id="96b79-104">¿Qué es F\#</span><span class="sxs-lookup"><span data-stu-id="96b79-104">What is F\#</span></span>

<span data-ttu-id="96b79-105">F#es un lenguaje de programación funcional que resulta muy fácil escribir código correcto y fácil de mantener.</span><span class="sxs-lookup"><span data-stu-id="96b79-105">F# is a functional programming language that makes it easy to write correct and maintainable code.</span></span>

<span data-ttu-id="96b79-106">F#programación principalmente implica la definición de tipos y funciones que son de tipo deduce y generalizadas automáticamente.</span><span class="sxs-lookup"><span data-stu-id="96b79-106">F# programming primarily involves defining types and functions that are type-inferred and generalized automatically.</span></span> <span data-ttu-id="96b79-107">Esto permite que el enfoque a permanecer en el dominio del problema y manipular los datos, en lugar de los detalles de la programación.</span><span class="sxs-lookup"><span data-stu-id="96b79-107">This allows your focus to remain on the problem domain and manipulating its data, rather than the details of programming.</span></span>

```fsharp
open System // Gets access to functionality in System namespace.

// Defines a function that takes a name and produces a greeting.
let getGreeting name =
    sprintf "Hello, %s! Isn't F# great?" name

[<EntryPoint>]
let main args =
    // Defines a list of names
    let names = [ "Don"; "Julia"; "Xi" ]

    // Prints a greeting for each name!
    names
    |> List.map getGreeting
    |> List.iter (fun greeting -> printfn "%s" greeting)

    0
```

<span data-ttu-id="96b79-108">F#tiene numerosas características, incluidos:</span><span class="sxs-lookup"><span data-stu-id="96b79-108">F# has numerous features, including:</span></span>

* <span data-ttu-id="96b79-109">Sintaxis ligera</span><span class="sxs-lookup"><span data-stu-id="96b79-109">Lightweight syntax</span></span>
* <span data-ttu-id="96b79-110">Inmutables de manera predeterminada</span><span class="sxs-lookup"><span data-stu-id="96b79-110">Immutable by default</span></span>
* <span data-ttu-id="96b79-111">Generalización automática y la inferencia de tipos</span><span class="sxs-lookup"><span data-stu-id="96b79-111">Type inference and automatic generalization</span></span>
* <span data-ttu-id="96b79-112">Funciones de primera clase</span><span class="sxs-lookup"><span data-stu-id="96b79-112">First-class functions</span></span>
* <span data-ttu-id="96b79-113">Tipos de datos eficaces</span><span class="sxs-lookup"><span data-stu-id="96b79-113">Powerful data types</span></span>
* <span data-ttu-id="96b79-114">Detección de patrones</span><span class="sxs-lookup"><span data-stu-id="96b79-114">Pattern matching</span></span>
* <span data-ttu-id="96b79-115">Programación asincrónica</span><span class="sxs-lookup"><span data-stu-id="96b79-115">Async programming</span></span>

<span data-ttu-id="96b79-116">Un conjunto completo de características se documentan en el [ F# referencia del lenguaje](language-reference/index.md).</span><span class="sxs-lookup"><span data-stu-id="96b79-116">A full set of features are documented in the [F# language reference](language-reference/index.md).</span></span>

## <a name="rich-data-types"></a><span data-ttu-id="96b79-117">Tipos de datos enriquecido</span><span class="sxs-lookup"><span data-stu-id="96b79-117">Rich data types</span></span>

<span data-ttu-id="96b79-118">Tipos de datos como [registros](language-reference/records.md) y [uniones discriminadas](language-reference/discriminated-unions.md) le permite representar datos complejos y dominios.</span><span class="sxs-lookup"><span data-stu-id="96b79-118">Data types such as [Records](language-reference/records.md) and [Discriminated Unions](language-reference/discriminated-unions.md) let you represent complex data and domains.</span></span>

```fsharp
// Group data with Records
type SuccessfulWithdrawal = {
    Amount: decimal
    Balance: decimal
}

type FailedWithdrawal = {
    Amount: decimal
    Balance: decimal
    IsOverdraft: bool
}

// Use discriminated unions to represent data of 1 or more forms
type WithdrawalResult =
    | Success of SuccessfulWithdrawal
    | InsufficientFunds of FailedWithdrawal
    | CardExpired of System.DateTime
    | UndisclosedFailure
```

<span data-ttu-id="96b79-119">F#registros y uniones discriminadas son distintos de null, inmutable y comparable de forma predeterminada, haciéndolos muy fácil de usar.</span><span class="sxs-lookup"><span data-stu-id="96b79-119">F# records and discriminated unions are non-null, immutable, and comparable by default, making them very easy to use.</span></span>

## <a name="enforced-correctness-with-functions-and-pattern-matching"></a><span data-ttu-id="96b79-120">Corrección impuesto con funciones y coincidencia de patrones</span><span class="sxs-lookup"><span data-stu-id="96b79-120">Enforced correctness with functions and pattern matching</span></span>

<span data-ttu-id="96b79-121">F#las funciones son eficaces en la práctica y fácil declarar.</span><span class="sxs-lookup"><span data-stu-id="96b79-121">F# functions are easy to declare and powerful in practice.</span></span> <span data-ttu-id="96b79-122">Cuando se combina con [coincidencia de patrones](language-reference/pattern-matching.md), le permiten definir comportamiento cuya corrección se aplica por el compilador.</span><span class="sxs-lookup"><span data-stu-id="96b79-122">When combined with [pattern matching](language-reference/pattern-matching.md), they allow you to define behavior whose correctness is enforced by the compiler.</span></span>

```fsharp
// Returns a WithdrawalResult
let withdrawMoney amount = // Implementation elided

let handleWithdrawal amount =
    let w = withdrawMoney amount

    // The F# compiler enforces accounting for each case!
    match w with
    | Success s -> printfn "Successfully withdrew %f" s.Amount
    | InsufficientFunds f -> printfn "Failed: balance is %f" f.Balance
    | CardExpired d -> printfn "Failed: card expired on %O" d
    | UndisclosedFailure -> printfn "Failed: unknown :("
```

<span data-ttu-id="96b79-123">F#las funciones también son de primera clase, lo que significa que se pueden pasar como parámetros y devueltos por otras funciones.</span><span class="sxs-lookup"><span data-stu-id="96b79-123">F# functions are also first-class, meaning they can be passed as parameters and returned from other functions.</span></span>

## <a name="functions-to-define-operations-on-objects"></a><span data-ttu-id="96b79-124">Funciones para definir las operaciones en objetos</span><span class="sxs-lookup"><span data-stu-id="96b79-124">Functions to define operations on objects</span></span>

<span data-ttu-id="96b79-125">F#es totalmente compatible con objetos, que son tipos de datos útiles cuando es necesario combinar datos y la funcionalidad.</span><span class="sxs-lookup"><span data-stu-id="96b79-125">F# has full support for objects, which are useful data types when you need to blend data and functionality.</span></span> <span data-ttu-id="96b79-126">F#las funciones se usan para manipular objetos.</span><span class="sxs-lookup"><span data-stu-id="96b79-126">F# functions are used to manipulate objects.</span></span>

```fsharp
type Set<[<EqualityConditionOn>] 'T when 'T: comparison>(elements: seq<'T>) =
    member s.IsEmpty = // Implementation elided
    member s.Contains (value) =// Implementation elided
    member s.Add (value) = // Implementation elided
    // ...
    // Further Implementation elided
    // ...
    interface IEnumerable<‘T>
    interface IReadOnlyCollection<‘T>

[<RequireQualifiedAccess>]
module Set =
    let isEmpty (set: Set<'T>) = set.IsEmpty

    let contains element (set: Set<'T>) = set.Contains(element)

    let add value (set: Set<'T>) = set.Add(value)
```

<span data-ttu-id="96b79-127">En lugar de escribir código que está orientada a objetos, en F#, a menudo escribirá código que se trata como otro tipo de datos para las funciones para manipular los objetos.</span><span class="sxs-lookup"><span data-stu-id="96b79-127">Rather than writing code that is object-oriented, in F#, you will often write code that treats objects as another data type for functions to manipulate.</span></span> <span data-ttu-id="96b79-128">Características como [interfaces genéricas](language-reference/interfaces.md), [expresiones de objeto](language-reference/object-expressions.md)y un uso razonable de [miembros](language-reference/members/index.md) son comunes en mayor F# programas.</span><span class="sxs-lookup"><span data-stu-id="96b79-128">Features such as [generic interfaces](language-reference/interfaces.md), [object expressions](language-reference/object-expressions.md), and judicious use of [members](language-reference/members/index.md) are common in larger F# programs.</span></span>

## <a name="next-steps"></a><span data-ttu-id="96b79-129">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="96b79-129">Next steps</span></span>

<span data-ttu-id="96b79-130">Para obtener más información sobre un conjunto mayor de F# características, consulte el [ F# paseo](tour.md).</span><span class="sxs-lookup"><span data-stu-id="96b79-130">To learn more about a larger set of F# features, check out the [F# Tour](tour.md).</span></span>
