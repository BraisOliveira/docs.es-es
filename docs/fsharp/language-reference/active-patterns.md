---
title: Patrones activos
description: Aprenda a usar los patrones activos para definir particiones con nombre que subdividen los datos de entrada en el F# lenguaje de programación.
ms.date: 05/16/2016
ms.openlocfilehash: 25ab255574390d3761fe788aeb413c8ee04fda2a
ms.sourcegitcommit: d8ebe0ee198f5d38387a80ba50f395386779334f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/05/2019
ms.locfileid: "66690415"
---
# <a name="active-patterns"></a><span data-ttu-id="9d3de-103">Patrones activos</span><span class="sxs-lookup"><span data-stu-id="9d3de-103">Active Patterns</span></span>

<span data-ttu-id="9d3de-104">*Modelos activos* le permiten definir particiones con nombre que subdividen los datos de entrada, por lo que puede usar estos nombres en una expresión de coincidencia como haría para una unión discriminada.</span><span class="sxs-lookup"><span data-stu-id="9d3de-104">*Active patterns* enable you to define named partitions that subdivide input data, so that you can use these names in a pattern matching expression just as you would for a discriminated union.</span></span> <span data-ttu-id="9d3de-105">Se pueden usar patrones activos para descomponer los datos de manera personalizada para cada partición.</span><span class="sxs-lookup"><span data-stu-id="9d3de-105">You can use active patterns to decompose data in a customized manner for each partition.</span></span>

## <a name="syntax"></a><span data-ttu-id="9d3de-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9d3de-106">Syntax</span></span>

```fsharp
// Active pattern of one choice.
let (|identifier|) [arguments] valueToMatch= expression

// Active Pattern with multiple choices.
// Uses a FSharp.Core.Choice<_,...,_> based on the number of case names. In F#, the limitation n <= 7 applies.
let (|identifer1|identifier2|...|) valueToMatch = expression

// Partial active pattern definition.
// Uses a FSharp.Core.option<_> to represent if the type is satisfied at the call site.
let (|identifier|_|) [arguments ] valueToMatch = expression
```

## <a name="remarks"></a><span data-ttu-id="9d3de-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="9d3de-107">Remarks</span></span>

<span data-ttu-id="9d3de-108">En la sintaxis anterior, los identificadores son los nombres de las particiones de los datos de entrada que se representan mediante *argumentos*, o bien, en otras palabras, los nombres de subconjuntos del conjunto de todos los valores de los argumentos.</span><span class="sxs-lookup"><span data-stu-id="9d3de-108">In the previous syntax, the identifiers are names for partitions of the input data that is represented by *arguments*, or, in other words, names for subsets of the set of all values of the arguments.</span></span> <span data-ttu-id="9d3de-109">Puede haber hasta siete particiones en una definición de modelo activo.</span><span class="sxs-lookup"><span data-stu-id="9d3de-109">There can be up to seven partitions in an active pattern definition.</span></span> <span data-ttu-id="9d3de-110">El *expresión* describe la forma en que se va a descomponer los datos.</span><span class="sxs-lookup"><span data-stu-id="9d3de-110">The *expression* describes the form into which to decompose the data.</span></span> <span data-ttu-id="9d3de-111">Puede usar una definición de modelo activo para definir las reglas para determinar cuál de las particiones con nombre de los valores proporcionados como argumentos pertenecen a.</span><span class="sxs-lookup"><span data-stu-id="9d3de-111">You can use an active pattern definition to define the rules for determining which of the named partitions the values given as arguments belong to.</span></span> <span data-ttu-id="9d3de-112">La (| y |) se conocen como símbolos *clips plátano* y se llama a la función creada por este tipo de enlace let un *reconocedor active*.</span><span class="sxs-lookup"><span data-stu-id="9d3de-112">The (| and |) symbols are referred to as *banana clips* and the function created by this type of let binding is called an *active recognizer*.</span></span>

<span data-ttu-id="9d3de-113">Por ejemplo, considere el siguiente patrón activo con un argumento.</span><span class="sxs-lookup"><span data-stu-id="9d3de-113">As an example, consider the following active pattern with an argument.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5001.fs)]

<span data-ttu-id="9d3de-114">Puede usar el modelo activo en una coincidencia de expresión, como en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="9d3de-114">You can use the active pattern in a pattern matching expression, as in the following example.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5002.fs)]

<span data-ttu-id="9d3de-115">El resultado de este programa es como sigue:</span><span class="sxs-lookup"><span data-stu-id="9d3de-115">The output of this program is as follows:</span></span>

```
7 is odd
11 is odd
32 is even
```

<span data-ttu-id="9d3de-116">Es otro uso de modelos activos descomponer los tipos de datos de varias formas, por ejemplo, cuando los mismos datos subyacentes tienen varias representaciones posibles.</span><span class="sxs-lookup"><span data-stu-id="9d3de-116">Another use of active patterns is to decompose data types in multiple ways, such as when the same underlying data has various possible representations.</span></span> <span data-ttu-id="9d3de-117">Por ejemplo, un `Color` objeto se puede descomponer en una representación RGB o HSB.</span><span class="sxs-lookup"><span data-stu-id="9d3de-117">For example, a `Color` object could be decomposed into an RGB representation or an HSB representation.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5003.fs)]

<span data-ttu-id="9d3de-118">La salida del programa anterior es como sigue:</span><span class="sxs-lookup"><span data-stu-id="9d3de-118">The output of the above program is as follows:</span></span>

```
Red
 Red: 255 Green: 0 Blue: 0
 Hue: 360.000000 Saturation: 1.000000 Brightness: 0.500000
Black
 Red: 0 Green: 0 Blue: 0
 Hue: 0.000000 Saturation: 0.000000 Brightness: 0.000000
White
 Red: 255 Green: 255 Blue: 255
 Hue: 0.000000 Saturation: 0.000000 Brightness: 1.000000
Gray
 Red: 128 Green: 128 Blue: 128
 Hue: 0.000000 Saturation: 0.000000 Brightness: 0.501961
BlanchedAlmond
 Red: 255 Green: 235 Blue: 205
 Hue: 36.000000 Saturation: 1.000000 Brightness: 0.901961
```

<span data-ttu-id="9d3de-119">En combinación, estas dos formas de usar los patrones activos permiten a la partición y descomponen los datos en el formulario de adecuado y realizan los cálculos adecuados en los datos apropiados en la forma más conveniente para el cálculo.</span><span class="sxs-lookup"><span data-stu-id="9d3de-119">In combination, these two ways of using active patterns enable you to partition and decompose data into just the appropriate form and perform the appropriate computations on the appropriate data in the form most convenient for the computation.</span></span>

<span data-ttu-id="9d3de-120">Las expresiones de coincidencia de patrón resultante permiten a los datos se escriban en forma cómoda de bifurcación potencialmente complejo muy legible, lo que simplificó en gran medida y el código de análisis de datos.</span><span class="sxs-lookup"><span data-stu-id="9d3de-120">The resulting pattern matching expressions enable data to be written in a convenient way that is very readable, greatly simplifying potentially complex branching and data analysis code.</span></span>

## <a name="partial-active-patterns"></a><span data-ttu-id="9d3de-121">Modelos activos parciales</span><span class="sxs-lookup"><span data-stu-id="9d3de-121">Partial Active Patterns</span></span>

<span data-ttu-id="9d3de-122">En ocasiones, necesitará sólo una parte del espacio de entrada de partición.</span><span class="sxs-lookup"><span data-stu-id="9d3de-122">Sometimes, you need to partition only part of the input space.</span></span> <span data-ttu-id="9d3de-123">En ese caso, escribe un conjunto de modelos parciales cada que coinciden con algunas entradas pero no coincide con otras entradas.</span><span class="sxs-lookup"><span data-stu-id="9d3de-123">In that case, you write a set of partial patterns each of which match some inputs but fail to match other inputs.</span></span> <span data-ttu-id="9d3de-124">Modelos activos que no generan un valor siempre se denominan *modelos activos parciales*; tienen un valor devuelto que es un tipo de opción.</span><span class="sxs-lookup"><span data-stu-id="9d3de-124">Active patterns that do not always produce a value are called *partial active patterns*; they have a return value that is an option type.</span></span> <span data-ttu-id="9d3de-125">Para definir un modelo activo parcial, se utiliza un carácter comodín (\_) al final de la lista de modelos dentro de lo delimitadores de modelo activo.</span><span class="sxs-lookup"><span data-stu-id="9d3de-125">To define a partial active pattern, you use a wildcard character (\_) at the end of the list of patterns inside the banana clips.</span></span> <span data-ttu-id="9d3de-126">El código siguiente muestra el uso de un modelo activo parcial.</span><span class="sxs-lookup"><span data-stu-id="9d3de-126">The following code illustrates the use of a partial active pattern.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5004.fs)]

<span data-ttu-id="9d3de-127">La salida del ejemplo anterior es el siguiente:</span><span class="sxs-lookup"><span data-stu-id="9d3de-127">The output of the previous example is as follows:</span></span>

```
1.100000 : Floating point
0 : Integer
0.000000 : Floating point
10 : Integer
Something else : Not matched.
```

<span data-ttu-id="9d3de-128">Al usar patrones activos parciales, en ocasiones, las opciones individuales pueden ser separados o mutuamente excluyentes, pero no se necesita.</span><span class="sxs-lookup"><span data-stu-id="9d3de-128">When using partial active patterns, sometimes the individual choices can be disjoint or mutually exclusive, but they need not be.</span></span> <span data-ttu-id="9d3de-129">En el ejemplo siguiente, el cuadrado de patrón y el modelo del cubo no son separados, porque algunos números son cuadrados y cubos, como los 64.</span><span class="sxs-lookup"><span data-stu-id="9d3de-129">In the following example, the pattern Square and the pattern Cube are not disjoint, because some numbers are both squares and cubes, such as 64.</span></span> <span data-ttu-id="9d3de-130">El siguiente programa usa el modelo de AND para combinar los patrones de cuadrado y el cubo.</span><span class="sxs-lookup"><span data-stu-id="9d3de-130">The following program uses the AND pattern to combine the Square and Cube patterns.</span></span> <span data-ttu-id="9d3de-131">Imprimen todos los enteros hasta 1000 que son tanto cuadrados y cubos, así como a los que solo los cubos.</span><span class="sxs-lookup"><span data-stu-id="9d3de-131">It print out all integers up to 1000 that are both squares and cubes, as well as those which are only cubes.</span></span> 

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5005.fs)]

<span data-ttu-id="9d3de-132">La salida es la siguiente:</span><span class="sxs-lookup"><span data-stu-id="9d3de-132">The output is as follows:</span></span>

```
1 is a cube and a square
8 is a cube
27 is a cube
64 is a cube and a square
125 is a cube
216 is a cube
343 is a cube
512 is a cube
729 is a cube and a square
1000 is a cube
```

## <a name="parameterized-active-patterns"></a><span data-ttu-id="9d3de-133">Modelos activos con parámetros</span><span class="sxs-lookup"><span data-stu-id="9d3de-133">Parameterized Active Patterns</span></span>

<span data-ttu-id="9d3de-134">Modelos activos siempre tienen al menos un argumento para el elemento que se coteja, pero es posible que tarden argumentos adicionales, en cuyo caso el nombre *modelo activo parametrizado* se aplica.</span><span class="sxs-lookup"><span data-stu-id="9d3de-134">Active patterns always take at least one argument for the item being matched, but they may take additional arguments as well, in which case the name *parameterized active pattern* applies.</span></span> <span data-ttu-id="9d3de-135">Argumentos adicionales permiten un patrón general estar especializados.</span><span class="sxs-lookup"><span data-stu-id="9d3de-135">Additional arguments allow a general pattern to be specialized.</span></span> <span data-ttu-id="9d3de-136">Por ejemplo, los patrones activos que utilizan expresiones regulares para analizar cadenas suelen incluyen la expresión regular como un parámetro adicional, como se muestra en el código siguiente, que también usa el patrón activo parcial `Integer` definido en el ejemplo de código anterior.</span><span class="sxs-lookup"><span data-stu-id="9d3de-136">For example, active patterns that use regular expressions to parse strings often include the regular expression as an extra parameter, as in the following code, which also uses the partial active pattern `Integer` defined in the previous code example.</span></span> <span data-ttu-id="9d3de-137">En este ejemplo, se proporcionan las cadenas que usan expresiones regulares para varios formatos de fecha para personalizar el activo ParseRegex general.</span><span class="sxs-lookup"><span data-stu-id="9d3de-137">In this example, strings that use regular expressions for various date formats are given to customize the general ParseRegex active pattern.</span></span> <span data-ttu-id="9d3de-138">El modelo activo de entero se utiliza para convertir las cadenas coincidentes en enteros que se pueden pasar al constructor DateTime.</span><span class="sxs-lookup"><span data-stu-id="9d3de-138">The Integer active pattern is used to convert the matched strings into integers that can be passed to the DateTime constructor.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5006.fs)]

<span data-ttu-id="9d3de-139">La salida del código anterior es el siguiente:</span><span class="sxs-lookup"><span data-stu-id="9d3de-139">The output of the previous code is as follows:</span></span>

```
12/22/2008 12:00:00 AM 1/1/2009 12:00:00 AM 1/15/2008 12:00:00 AM 12/28/1995 12:00:00 AM
```

<span data-ttu-id="9d3de-140">Modelos activos no se limitan únicamente a las expresiones de coincidencia de patrones, también puede usar en enlaces de let.</span><span class="sxs-lookup"><span data-stu-id="9d3de-140">Active patterns are not restricted only to pattern matching expressions, you can also use them on let-bindings.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5007.fs)]

<span data-ttu-id="9d3de-141">La salida del código anterior es el siguiente:</span><span class="sxs-lookup"><span data-stu-id="9d3de-141">The output of the previous code is as follows:</span></span>

```
Hello, random citizen!
Hello, George!
```

## <a name="see-also"></a><span data-ttu-id="9d3de-142">Vea también</span><span class="sxs-lookup"><span data-stu-id="9d3de-142">See also</span></span>

- [<span data-ttu-id="9d3de-143">Referencia del lenguaje F#</span><span class="sxs-lookup"><span data-stu-id="9d3de-143">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="9d3de-144">Expresiones de coincidencia</span><span class="sxs-lookup"><span data-stu-id="9d3de-144">Match Expressions</span></span>](match-expressions.md)
