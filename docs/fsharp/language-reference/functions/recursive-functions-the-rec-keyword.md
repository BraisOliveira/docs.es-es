---
title: 'Funciones recursivas: La palabra clave rec'
description: Obtenga información sobre cómo el F# palabra clave 'rec' se utiliza con la palabra clave 'let' para definir una función recursiva.
ms.date: 05/16/2016
ms.openlocfilehash: 86eaf1c8a5566d8b9cbc4dcb72f945e2497e5439
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "65645302"
---
# <a name="recursive-functions-the-rec-keyword"></a><span data-ttu-id="6c36a-103">Funciones recursivas: La palabra clave rec</span><span class="sxs-lookup"><span data-stu-id="6c36a-103">Recursive Functions: The rec Keyword</span></span>

<span data-ttu-id="6c36a-104">El `rec` palabra clave se utiliza junto con el `let` palabra clave para definir una función recursiva.</span><span class="sxs-lookup"><span data-stu-id="6c36a-104">The `rec` keyword is used together with the `let` keyword to define a recursive function.</span></span>

## <a name="syntax"></a><span data-ttu-id="6c36a-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6c36a-105">Syntax</span></span>

```fsharp
// Recursive function:
let rec function-nameparameter-list =
function-body

// Mutually recursive functions:
let rec function1-nameparameter-list =
function1-body
and function2-nameparameter-list =
function2-body
...
```

## <a name="remarks"></a><span data-ttu-id="6c36a-106">Comentarios</span><span class="sxs-lookup"><span data-stu-id="6c36a-106">Remarks</span></span>

<span data-ttu-id="6c36a-107">Funciones recursivas, las funciones que llaman a sí mismos, se identifican explícitamente en el F# lenguaje.</span><span class="sxs-lookup"><span data-stu-id="6c36a-107">Recursive functions, functions that call themselves, are identified explicitly in the F# language.</span></span> <span data-ttu-id="6c36a-108">Esto hace que el identificador que se está definiendo disponibles en el ámbito de la función.</span><span class="sxs-lookup"><span data-stu-id="6c36a-108">This makes the identifer that is being defined available in the scope of the function.</span></span>

<span data-ttu-id="6c36a-109">El código siguiente muestra una función recursiva que calcula el *n*<sup>th</sup> número de Fibonacci.</span><span class="sxs-lookup"><span data-stu-id="6c36a-109">The following code illustrates a recursive function that computes the *n*<sup>th</sup> Fibonacci number.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet4001.fs)]

> [!NOTE]
> <span data-ttu-id="6c36a-110">En la práctica, el código como ese anterior es un desperdicio de tiempo de procesador y memoria, ya que implica el cálculo de valores calculados previamente.</span><span class="sxs-lookup"><span data-stu-id="6c36a-110">In practice, code like that above is wasteful of memory and processor time because it involves the recomputation of previously computed values.</span></span>

<span data-ttu-id="6c36a-111">Los métodos son implícitamente recursivos dentro del tipo; no es necesario para agregar el `rec` palabra clave.</span><span class="sxs-lookup"><span data-stu-id="6c36a-111">Methods are implicitly recursive within the type; there is no need to add the `rec` keyword.</span></span> <span data-ttu-id="6c36a-112">Enlaces let en clases no son implícitamente recursivos.</span><span class="sxs-lookup"><span data-stu-id="6c36a-112">Let bindings within classes are not implicitly recursive.</span></span>

## <a name="mutually-recursive-functions"></a><span data-ttu-id="6c36a-113">Funciones mutuamente recursivas</span><span class="sxs-lookup"><span data-stu-id="6c36a-113">Mutually Recursive Functions</span></span>

<span data-ttu-id="6c36a-114">A veces, las funciones son *mutuamente recursivas*, lo que significa que las llamadas forman un círculo, donde una función llama a otro que a su vez llama a la primera, con cualquier número de llamadas entre ellos.</span><span class="sxs-lookup"><span data-stu-id="6c36a-114">Sometimes functions are *mutually recursive*, meaning that calls form a circle, where one function calls another which in turn calls the first, with any number of calls in between.</span></span> <span data-ttu-id="6c36a-115">Debe definir estas funciones juntas en una `let` enlace, mediante el `and` palabra clave para vincularlas.</span><span class="sxs-lookup"><span data-stu-id="6c36a-115">You must define such functions together in the one `let` binding, using the `and` keyword to link them together.</span></span>

<span data-ttu-id="6c36a-116">El ejemplo siguiente muestra dos mutuamente las funciones recursivas.</span><span class="sxs-lookup"><span data-stu-id="6c36a-116">The following example shows two mutually recursive functions.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet4002.fs)]

## <a name="see-also"></a><span data-ttu-id="6c36a-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="6c36a-117">See also</span></span>

- [<span data-ttu-id="6c36a-118">Funciones</span><span class="sxs-lookup"><span data-stu-id="6c36a-118">Functions</span></span>](index.md)
