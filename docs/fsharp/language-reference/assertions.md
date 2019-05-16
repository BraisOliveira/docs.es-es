---
title: Aserciones
description: Aprenda a usar la expresión 'assert' como una característica de depuración para probar expresiones en el F# lenguaje de programación.
ms.date: 05/16/2016
ms.openlocfilehash: 5fe24195c7548e9fbb927e4b95b752c7a963c6b3
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "65642057"
---
# <a name="assertions"></a><span data-ttu-id="13340-103">Aserciones</span><span class="sxs-lookup"><span data-stu-id="13340-103">Assertions</span></span>

<span data-ttu-id="13340-104">El `assert` expresión es una característica de depuración que puede usar para probar una expresión.</span><span class="sxs-lookup"><span data-stu-id="13340-104">The `assert` expression is a debugging feature that you can use to test an expression.</span></span> <span data-ttu-id="13340-105">En caso de error en modo de depuración, una aserción genera un cuadro de diálogo de error del sistema.</span><span class="sxs-lookup"><span data-stu-id="13340-105">Upon failure in Debug mode, an assertion generates a system error dialog box.</span></span>

## <a name="syntax"></a><span data-ttu-id="13340-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="13340-106">Syntax</span></span>

```fsharp
assert condition
```

## <a name="remarks"></a><span data-ttu-id="13340-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="13340-107">Remarks</span></span>

<span data-ttu-id="13340-108">El `assert` expresión tiene el tipo `bool -> unit`.</span><span class="sxs-lookup"><span data-stu-id="13340-108">The `assert` expression has type `bool -> unit`.</span></span>

<span data-ttu-id="13340-109">En la sintaxis anterior, *condición* representa una expresión booleana que se va a probar.</span><span class="sxs-lookup"><span data-stu-id="13340-109">In the previous syntax, *condition* represents a Boolean expression that is to be tested.</span></span> <span data-ttu-id="13340-110">Si la expresión se evalúa como `true`, la ejecución continúa sin ninguna variación.</span><span class="sxs-lookup"><span data-stu-id="13340-110">If the expression evaluates to `true`, execution continues unaffected.</span></span> <span data-ttu-id="13340-111">Si se evalúa como `false`, se genera un cuadro de diálogo de error del sistema.</span><span class="sxs-lookup"><span data-stu-id="13340-111">If it evaluates to `false`, a system error dialog box is generated.</span></span> <span data-ttu-id="13340-112">El cuadro de diálogo de error tiene un título que contiene la cadena **error de aserción**.</span><span class="sxs-lookup"><span data-stu-id="13340-112">The error dialog box has a caption that contains the string **Assertion Failed**.</span></span> <span data-ttu-id="13340-113">El cuadro de diálogo contiene un seguimiento de pila que indica dónde se produjo el error de aserción.</span><span class="sxs-lookup"><span data-stu-id="13340-113">The dialog box contains a stack trace that indicates where the assertion failure occurred.</span></span>

<span data-ttu-id="13340-114">Comprobación de aserción está habilitada sólo cuando se compila en modo de depuración; es decir, si la constante `DEBUG` está definido.</span><span class="sxs-lookup"><span data-stu-id="13340-114">Assertion checking is enabled only when you compile in Debug mode; that is, if the constant `DEBUG` is defined.</span></span> <span data-ttu-id="13340-115">En el sistema del proyecto, de forma predeterminada, el `DEBUG` constante se define en la configuración de depuración pero no en la configuración de lanzamiento.</span><span class="sxs-lookup"><span data-stu-id="13340-115">In the project system, by default, the `DEBUG` constant is defined in the Debug configuration but not in the Release configuration.</span></span>

<span data-ttu-id="13340-116">No se puede detectar el error de aserción utilizando F# control de excepciones.</span><span class="sxs-lookup"><span data-stu-id="13340-116">The assertion failure error cannot be caught by using F# exception handling.</span></span>

> [!NOTE]
> <span data-ttu-id="13340-117">El `assert` función se resuelve en <xref:System.Diagnostics.Debug.Assert*?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="13340-117">The `assert` function resolves to <xref:System.Diagnostics.Debug.Assert*?displayProperty=nameWithType>.</span></span>

## <a name="example"></a><span data-ttu-id="13340-118">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="13340-118">Example</span></span>

<span data-ttu-id="13340-119">El ejemplo de código siguiente muestra el uso de la `assert` expresión.</span><span class="sxs-lookup"><span data-stu-id="13340-119">The following code example illustrates the use of the `assert` expression.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5401.fs)]

## <a name="see-also"></a><span data-ttu-id="13340-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="13340-120">See also</span></span>

- [<span data-ttu-id="13340-121">Referencia del lenguaje F#</span><span class="sxs-lookup"><span data-stu-id="13340-121">F# Language Reference</span></span>](index.md)
