---
title: Coincidencia de modelos
description: Obtenga información sobre cómo se usan patrones en F# para comparar los datos con estructuras lógicas, descomponer datos en sus partes constituyentes o extraer información de los datos.
ms.date: 05/16/2016
ms.openlocfilehash: bb6b41f6d15612e4a65abd4a3d5d7291d84a8f3c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61795465"
---
# <a name="pattern-matching"></a><span data-ttu-id="f5256-103">Coincidencia de modelos</span><span class="sxs-lookup"><span data-stu-id="f5256-103">Pattern Matching</span></span>

<span data-ttu-id="f5256-104">Los modelos son reglas para transformar los datos de entrada.</span><span class="sxs-lookup"><span data-stu-id="f5256-104">Patterns are rules for transforming input data.</span></span> <span data-ttu-id="f5256-105">Se usan en toda la F# lenguaje para comparar los datos con una estructura lógica o las estructuras, descomponer datos en sus partes constituyentes o extraer información de los datos de varias maneras.</span><span class="sxs-lookup"><span data-stu-id="f5256-105">They are used throughout the F# language to compare data with a logical structure or structures, decompose data into constituent parts, or extract information from data in various ways.</span></span>

## <a name="remarks"></a><span data-ttu-id="f5256-106">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f5256-106">Remarks</span></span>

<span data-ttu-id="f5256-107">Los modelos se utilizan en muchas construcciones de lenguaje, como el `match` expresión.</span><span class="sxs-lookup"><span data-stu-id="f5256-107">Patterns are used in many language constructs, such as the `match` expression.</span></span> <span data-ttu-id="f5256-108">Se utilizan cuando se procesan argumentos para funciones en `let` enlaces, las expresiones lambda y en los controladores de excepción asociados del `try...with` expresión.</span><span class="sxs-lookup"><span data-stu-id="f5256-108">They are used when you are processing arguments for functions in `let` bindings, lambda expressions, and in the exception handlers associated with the `try...with` expression.</span></span> <span data-ttu-id="f5256-109">Para obtener más información, consulte [expresiones de coincidencia](match-expressions.md), [enlaces let](functions/let-bindings.md), [expresiones Lambda: El `fun` palabra clave](functions/lambda-expressions-the-fun-keyword.md), y [excepciones: El `try...with` expresión](exception-handling/the-try-with-expression.md).</span><span class="sxs-lookup"><span data-stu-id="f5256-109">For more information, see [Match Expressions](match-expressions.md), [let Bindings](functions/let-bindings.md), [Lambda Expressions: The `fun` Keyword](functions/lambda-expressions-the-fun-keyword.md), and [Exceptions: The `try...with` Expression](exception-handling/the-try-with-expression.md).</span></span>

<span data-ttu-id="f5256-110">Por ejemplo, en el `match` expresión, el *patrón* lo que sigue el símbolo de canalización.</span><span class="sxs-lookup"><span data-stu-id="f5256-110">For example, in the `match` expression, the *pattern* is what follows the pipe symbol.</span></span>

```fsharp
match expression with
| pattern [ when condition ] -> result-expression
...
```

<span data-ttu-id="f5256-111">Cada modelo actúa como una regla para transformar la entrada de alguna manera.</span><span class="sxs-lookup"><span data-stu-id="f5256-111">Each pattern acts as a rule for transforming input in some way.</span></span> <span data-ttu-id="f5256-112">En el `match` cada patrón de expresión se examina a su vez, para ver si están compatibles con el patrón de los datos de entrada.</span><span class="sxs-lookup"><span data-stu-id="f5256-112">In the `match` expression, each pattern is examined in turn to see if the input data is compatible with the pattern.</span></span> <span data-ttu-id="f5256-113">Si se encuentra una coincidencia, se ejecuta la expresión de resultado.</span><span class="sxs-lookup"><span data-stu-id="f5256-113">If a match is found, the result expression is executed.</span></span> <span data-ttu-id="f5256-114">Si no se encuentra una coincidencia, se prueba la regla del modelo siguiente.</span><span class="sxs-lookup"><span data-stu-id="f5256-114">If a match is not found, the next pattern rule is tested.</span></span> <span data-ttu-id="f5256-115">Opcional cuando *condición* parte se explica en [expresiones de coincidencia](match-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="f5256-115">The optional when *condition* part is explained in [Match Expressions](match-expressions.md).</span></span>

<span data-ttu-id="f5256-116">Modelos admitidos se muestran en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="f5256-116">Supported patterns are shown in the following table.</span></span> <span data-ttu-id="f5256-117">En tiempo de ejecución, la entrada se prueba con cada uno de los siguientes patrones en el orden mostrado en la tabla, y patrones aplica de forma recursiva, del primero al último tal y como aparecen en el código y de izquierda a derecha para los modelos en cada línea.</span><span class="sxs-lookup"><span data-stu-id="f5256-117">At run time, the input is tested against each of the following patterns in the order listed in the table, and patterns are applied recursively, from first to last as they appear in your code, and from left to right for the patterns on each line.</span></span>

|<span data-ttu-id="f5256-118">Name</span><span class="sxs-lookup"><span data-stu-id="f5256-118">Name</span></span>|<span data-ttu-id="f5256-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="f5256-119">Description</span></span>|<span data-ttu-id="f5256-120">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f5256-120">Example</span></span>|
|----|-----------|-------|
|<span data-ttu-id="f5256-121">Patrón de constante</span><span class="sxs-lookup"><span data-stu-id="f5256-121">Constant pattern</span></span>|<span data-ttu-id="f5256-122">Cualquier numérico, carácter o literal de cadena, una constante de enumeración o un identificador literal definido</span><span class="sxs-lookup"><span data-stu-id="f5256-122">Any numeric, character, or string literal, an enumeration constant, or a defined literal identifier</span></span>|<span data-ttu-id="f5256-123">`1.0`, `"test"`, `30`, `Color.Red`</span><span class="sxs-lookup"><span data-stu-id="f5256-123">`1.0`, `"test"`, `30`, `Color.Red`</span></span>|
|<span data-ttu-id="f5256-124">Patrón de identificador</span><span class="sxs-lookup"><span data-stu-id="f5256-124">Identifier pattern</span></span>|<span data-ttu-id="f5256-125">Un valor de caso de una unión discriminada, una etiqueta de excepción o un caso de modelo activo</span><span class="sxs-lookup"><span data-stu-id="f5256-125">A case value of a discriminated union, an exception label, or an active pattern case</span></span>|`Some(x)`<br /><br />`Failure(msg)`|
|<span data-ttu-id="f5256-126">Modelo de variable</span><span class="sxs-lookup"><span data-stu-id="f5256-126">Variable pattern</span></span>|<span data-ttu-id="f5256-127">*identifier*</span><span class="sxs-lookup"><span data-stu-id="f5256-127">*identifier*</span></span>|`a`|
|<span data-ttu-id="f5256-128">`as` Patrón</span><span class="sxs-lookup"><span data-stu-id="f5256-128">`as` pattern</span></span>|<span data-ttu-id="f5256-129">*patrón* como *identificador*</span><span class="sxs-lookup"><span data-stu-id="f5256-129">*pattern* as *identifier*</span></span>|`(a, b) as tuple1`|
|<span data-ttu-id="f5256-130">O un patrón</span><span class="sxs-lookup"><span data-stu-id="f5256-130">OR pattern</span></span>|<span data-ttu-id="f5256-131">*pattern1* &#124; *pattern2*</span><span class="sxs-lookup"><span data-stu-id="f5256-131">*pattern1* &#124; *pattern2*</span></span>|<code>([h] &#124; [h; _])</code>|
|<span data-ttu-id="f5256-132">Y el patrón</span><span class="sxs-lookup"><span data-stu-id="f5256-132">AND pattern</span></span>|<span data-ttu-id="f5256-133">*pattern1* &amp; *pattern2*</span><span class="sxs-lookup"><span data-stu-id="f5256-133">*pattern1* &amp; *pattern2*</span></span>|`(a, b) & (_, "test")`|
|<span data-ttu-id="f5256-134">Modelo de cons</span><span class="sxs-lookup"><span data-stu-id="f5256-134">Cons pattern</span></span>|<span data-ttu-id="f5256-135">*identificador* :: *identificador de la lista*</span><span class="sxs-lookup"><span data-stu-id="f5256-135">*identifier* :: *list-identifier*</span></span>|`h :: t`|
|<span data-ttu-id="f5256-136">Modelo de lista</span><span class="sxs-lookup"><span data-stu-id="f5256-136">List pattern</span></span>|<span data-ttu-id="f5256-137">[ *modelo_1*;...; *modelo_n* ]</span><span class="sxs-lookup"><span data-stu-id="f5256-137">[ *pattern_1*; ... ; *pattern_n* ]</span></span>|`[ a; b; c ]`|
|<span data-ttu-id="f5256-138">Patrón de matriz</span><span class="sxs-lookup"><span data-stu-id="f5256-138">Array pattern</span></span>|<span data-ttu-id="f5256-139">[&#124; *pattern_1*; .; *pattern_n* &#124;]</span><span class="sxs-lookup"><span data-stu-id="f5256-139">[&#124; *pattern_1*; ..; *pattern_n* &#124;]</span></span>|<code>[&#124; a; b; c &#124;]</code>|
|<span data-ttu-id="f5256-140">Modelo entre paréntesis</span><span class="sxs-lookup"><span data-stu-id="f5256-140">Parenthesized pattern</span></span>|<span data-ttu-id="f5256-141">( *pattern* )</span><span class="sxs-lookup"><span data-stu-id="f5256-141">( *pattern* )</span></span>|`( a )`|
|<span data-ttu-id="f5256-142">Modelo de tupla</span><span class="sxs-lookup"><span data-stu-id="f5256-142">Tuple pattern</span></span>|<span data-ttu-id="f5256-143">( *modelo_1*,..., *modelo_n* )</span><span class="sxs-lookup"><span data-stu-id="f5256-143">( *pattern_1*, ... , *pattern_n* )</span></span>|`( a, b )`|
|<span data-ttu-id="f5256-144">Modelo de registro</span><span class="sxs-lookup"><span data-stu-id="f5256-144">Record pattern</span></span>|<span data-ttu-id="f5256-145">{ *identificador1* = *modelo_1*;...; *identificador_n* = *modelo_n* }</span><span class="sxs-lookup"><span data-stu-id="f5256-145">{ *identifier1* = *pattern_1*; ... ; *identifier_n* = *pattern_n* }</span></span>|`{ Name = name; }`|
|<span data-ttu-id="f5256-146">Patrón de caracteres comodín</span><span class="sxs-lookup"><span data-stu-id="f5256-146">Wildcard pattern</span></span>|<span data-ttu-id="f5256-147">_</span><span class="sxs-lookup"><span data-stu-id="f5256-147">_</span></span>|`_`|
|<span data-ttu-id="f5256-148">Modelo junto con anotación de tipo</span><span class="sxs-lookup"><span data-stu-id="f5256-148">Pattern together with type annotation</span></span>|<span data-ttu-id="f5256-149">*patrón* : *tipo*</span><span class="sxs-lookup"><span data-stu-id="f5256-149">*pattern* : *type*</span></span>|`a : int`|
|<span data-ttu-id="f5256-150">Modelo de prueba de tipo</span><span class="sxs-lookup"><span data-stu-id="f5256-150">Type test pattern</span></span>|<span data-ttu-id="f5256-151">:?</span><span class="sxs-lookup"><span data-stu-id="f5256-151">:?</span></span> <span data-ttu-id="f5256-152">*type* [ as *identifier* ]</span><span class="sxs-lookup"><span data-stu-id="f5256-152">*type* [ as *identifier* ]</span></span>|`:? System.DateTime as dt`|
|<span data-ttu-id="f5256-153">Modelo de null</span><span class="sxs-lookup"><span data-stu-id="f5256-153">Null pattern</span></span>|<span data-ttu-id="f5256-154">nulo</span><span class="sxs-lookup"><span data-stu-id="f5256-154">null</span></span>|`null`|

## <a name="constant-patterns"></a><span data-ttu-id="f5256-155">Modelos de constante</span><span class="sxs-lookup"><span data-stu-id="f5256-155">Constant Patterns</span></span>

<span data-ttu-id="f5256-156">Modelos de constante son numéricos, caracteres y literales de cadena, constantes de enumeración (con el nombre de tipo de enumeración incluidos).</span><span class="sxs-lookup"><span data-stu-id="f5256-156">Constant patterns are numeric, character, and string literals, enumeration constants (with the enumeration type name included).</span></span> <span data-ttu-id="f5256-157">Un `match` expresión que tiene modelos de constante solo puede compararse con una instrucción case de otros lenguajes.</span><span class="sxs-lookup"><span data-stu-id="f5256-157">A `match` expression that has only constant patterns can be compared to a case statement in other languages.</span></span> <span data-ttu-id="f5256-158">La entrada se compara con el valor literal y el modelo coincide si los valores son iguales.</span><span class="sxs-lookup"><span data-stu-id="f5256-158">The input is compared with the literal value and the pattern matches if the values are equal.</span></span> <span data-ttu-id="f5256-159">El tipo del literal debe ser compatible con el tipo de la entrada.</span><span class="sxs-lookup"><span data-stu-id="f5256-159">The type of the literal must be compatible with the type of the input.</span></span>

<span data-ttu-id="f5256-160">El ejemplo siguiente muestra el uso de modelos de literal y también usa un modelo de variable y un modelo de OR.</span><span class="sxs-lookup"><span data-stu-id="f5256-160">The following example demonstrates the use of literal patterns, and also uses a variable pattern and an OR pattern.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4801.fs)]

<span data-ttu-id="f5256-161">Otro ejemplo de un modelo de literal es un modelo basado en constantes de enumeración.</span><span class="sxs-lookup"><span data-stu-id="f5256-161">Another example of a literal pattern is a pattern based on enumeration constants.</span></span> <span data-ttu-id="f5256-162">Debe especificar el nombre del tipo de enumeración al usar las constantes de enumeración.</span><span class="sxs-lookup"><span data-stu-id="f5256-162">You must specify the enumeration type name when you use enumeration constants.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4802.fs)]

## <a name="identifier-patterns"></a><span data-ttu-id="f5256-163">Patrones de identificador</span><span class="sxs-lookup"><span data-stu-id="f5256-163">Identifier Patterns</span></span>

<span data-ttu-id="f5256-164">Si el patrón es una cadena de caracteres que forman un identificador válido, el formato del identificador determina cómo se compara el patrón.</span><span class="sxs-lookup"><span data-stu-id="f5256-164">If the pattern is a string of characters that forms a valid identifier, the form of the identifier determines how the pattern is matched.</span></span> <span data-ttu-id="f5256-165">Si el identificador tiene más de un solo carácter y comienza con una letra mayúscula, el compilador intenta hallar una coincidencia con el patrón de identificador.</span><span class="sxs-lookup"><span data-stu-id="f5256-165">If the identifier is longer than a single character and starts with an uppercase character, the compiler tries to make a match to the identifier pattern.</span></span> <span data-ttu-id="f5256-166">El identificador de este modelo podría ser un valor marcado con el atributo Literal, un caso de unión discriminado, un identificador de excepción o un caso de modelo activo.</span><span class="sxs-lookup"><span data-stu-id="f5256-166">The identifier for this pattern could be a value marked with the Literal attribute, a discriminated union case, an exception identifier, or an active pattern case.</span></span> <span data-ttu-id="f5256-167">Si no se encuentra ningún identificador coincidente, la coincidencia produce un error y la regla del modelo siguiente, el modelo de variable, se compara con la entrada.</span><span class="sxs-lookup"><span data-stu-id="f5256-167">If no matching identifier is found, the match fails and the next pattern rule, the variable pattern, is compared to the input.</span></span>

<span data-ttu-id="f5256-168">Modelos de unión discriminada pueden ser simples casos con nombre o pueden tener un valor o una tupla que contiene varios valores.</span><span class="sxs-lookup"><span data-stu-id="f5256-168">Discriminated union patterns can be simple named cases or they can have a value, or a tuple containing multiple values.</span></span> <span data-ttu-id="f5256-169">Si hay un valor, debe especificar un identificador para el valor.</span><span class="sxs-lookup"><span data-stu-id="f5256-169">If there is a value, you must specify an identifier for the value.</span></span> <span data-ttu-id="f5256-170">En el caso de una tupla, debe proporcionar un modelo de tupla con un identificador para cada elemento de la tupla o un identificador con un nombre de campo para uno o más campos de unión de llamada.</span><span class="sxs-lookup"><span data-stu-id="f5256-170">In the case of a tuple, you must supply a tuple pattern with an identifier for each element of the tuple or an identifier with a field name for one or more named union fields.</span></span> <span data-ttu-id="f5256-171">Vea los ejemplos de código en esta sección para obtener ejemplos.</span><span class="sxs-lookup"><span data-stu-id="f5256-171">See the code examples in this section for examples.</span></span>

<span data-ttu-id="f5256-172">El `option` tipo es una unión discriminada que tiene dos casos, `Some` y `None`.</span><span class="sxs-lookup"><span data-stu-id="f5256-172">The `option` type is a discriminated union that has two cases, `Some` and `None`.</span></span> <span data-ttu-id="f5256-173">Un caso (`Some`) tiene un valor, pero el otro (`None`) es simplemente un caso con nombre.</span><span class="sxs-lookup"><span data-stu-id="f5256-173">One case (`Some`) has a value, but the other (`None`) is just a named case.</span></span> <span data-ttu-id="f5256-174">Por lo tanto, `Some` debe tener una variable para el valor asociado con el `Some` case, pero `None` deben aparecer por sí mismo.</span><span class="sxs-lookup"><span data-stu-id="f5256-174">Therefore, `Some` needs to have a variable for the value associated with the `Some` case, but `None` must appear by itself.</span></span> <span data-ttu-id="f5256-175">En el código siguiente, la variable `var1` se asigna el valor que se obtiene mediante la coincidencia para el `Some` caso.</span><span class="sxs-lookup"><span data-stu-id="f5256-175">In the following code, the variable `var1` is given the value that is obtained by matching to the `Some` case.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4803.fs)]

<span data-ttu-id="f5256-176">En el ejemplo siguiente, la `PersonName` unión discriminada contiene una combinación de cadenas y caracteres que representan posibles formas de nombres.</span><span class="sxs-lookup"><span data-stu-id="f5256-176">In the following example, the `PersonName` discriminated union contains a mixture of strings and characters that represent possible forms of names.</span></span> <span data-ttu-id="f5256-177">Los casos de la unión discriminada son `FirstOnly`, `LastOnly`, y `FirstLast`.</span><span class="sxs-lookup"><span data-stu-id="f5256-177">The cases of the discriminated union are `FirstOnly`, `LastOnly`, and `FirstLast`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4804.fs)]

<span data-ttu-id="f5256-178">Las uniones discriminadas que tienen campos de nombre, utilice el signo igual (=) para extraer el valor de un campo con nombre.</span><span class="sxs-lookup"><span data-stu-id="f5256-178">For discriminated unions that have named fields, you use the equals sign (=) to extract the value of a named field.</span></span> <span data-ttu-id="f5256-179">Por ejemplo, considere una unión discriminada con una declaración similar al siguiente.</span><span class="sxs-lookup"><span data-stu-id="f5256-179">For example, consider a discriminated union with a declaration like the following.</span></span>

```fsharp
type Shape =
    | Rectangle of height : float * width : float
    | Circle of radius : float
```

<span data-ttu-id="f5256-180">Puede usar los campos con nombre en una expresión de coincidencia de patrón como sigue.</span><span class="sxs-lookup"><span data-stu-id="f5256-180">You can use the named fields in a pattern matching expression as follows.</span></span>

```fsharp
let matchShape shape =
    match shape with
    | Rectangle(height = h) -> printfn "Rectangle with length %f" h
    | Circle(r) -> printfn "Circle with radius %f" r
```

<span data-ttu-id="f5256-181">El uso del campo con nombre es opcional, por lo que en el ejemplo anterior, ambos `Circle(r)` y `Circle(radius = r)` tienen el mismo efecto.</span><span class="sxs-lookup"><span data-stu-id="f5256-181">The use of the named field is optional, so in the previous example, both `Circle(r)` and `Circle(radius = r)` have the same effect.</span></span>

<span data-ttu-id="f5256-182">Al especificar varios campos, use el punto y coma (;) como separador.</span><span class="sxs-lookup"><span data-stu-id="f5256-182">When you specify multiple fields, use the semicolon (;) as a separator.</span></span>

```
match shape with
| Rectangle(height = h; width = w) -> printfn "Rectangle with height %f and width %f" h w
| _ -> ()
```

<span data-ttu-id="f5256-183">Modelos activos permiten definir coincidencias de modelos personalizadas más complejas.</span><span class="sxs-lookup"><span data-stu-id="f5256-183">Active patterns enable you to define more complex custom pattern matching.</span></span> <span data-ttu-id="f5256-184">Para obtener más información acerca de los patrones activos, vea [modelos activos](active-patterns.md).</span><span class="sxs-lookup"><span data-stu-id="f5256-184">For more information about active patterns, see [Active Patterns](active-patterns.md).</span></span>

<span data-ttu-id="f5256-185">El caso en que el identificador es una excepción se usa en la coincidencia de patrones en el contexto de los controladores de excepciones.</span><span class="sxs-lookup"><span data-stu-id="f5256-185">The case in which the identifier is an exception is used in pattern matching in the context of exception handlers.</span></span> <span data-ttu-id="f5256-186">Para obtener información acerca de la coincidencia de patrones en el control de excepciones, vea [excepciones: El `try...with` expresión](exception-handling/the-try-with-expression.md).</span><span class="sxs-lookup"><span data-stu-id="f5256-186">For information about pattern matching in exception handling, see [Exceptions: The `try...with` Expression](exception-handling/the-try-with-expression.md).</span></span>

## <a name="variable-patterns"></a><span data-ttu-id="f5256-187">Modelos de variable</span><span class="sxs-lookup"><span data-stu-id="f5256-187">Variable Patterns</span></span>

<span data-ttu-id="f5256-188">El modelo de variable asigna el valor coincide con un nombre de variable, que está disponible para su uso en la expresión de ejecución a la derecha de la `->` símbolos.</span><span class="sxs-lookup"><span data-stu-id="f5256-188">The variable pattern assigns the value being matched to a variable name, which is then available for use in the execution expression to the right of the `->` symbol.</span></span> <span data-ttu-id="f5256-189">Un modelo de variable individual coincide con cualquier entrada, pero los modelos de variable suelen aparecen dentro de otros modelos, por lo tanto, habilitar estructuras más complejas, como las tuplas y matrices para descomposición en variables.</span><span class="sxs-lookup"><span data-stu-id="f5256-189">A variable pattern alone matches any input, but variable patterns often appear within other patterns, therefore enabling more complex structures such as tuples and arrays to be decomposed into variables.</span></span>

<span data-ttu-id="f5256-190">El ejemplo siguiente muestra un modelo de variable dentro de un modelo de tupla.</span><span class="sxs-lookup"><span data-stu-id="f5256-190">The following example demonstrates a variable pattern within a tuple pattern.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4805.fs)]

## <a name="as-pattern"></a><span data-ttu-id="f5256-191">como el patrón</span><span class="sxs-lookup"><span data-stu-id="f5256-191">as Pattern</span></span>

<span data-ttu-id="f5256-192">El `as` patrón es un modelo que tiene un `as` cláusula anexado a él.</span><span class="sxs-lookup"><span data-stu-id="f5256-192">The `as` pattern is a pattern that has an `as` clause appended to it.</span></span> <span data-ttu-id="f5256-193">El `as` cláusula enlaza el valor coincidente con un nombre que se puede usar en la expresión de ejecución de un `match` expresión, o bien, en el caso de que se usa este patrón en una `let` de enlace, el nombre se agrega como un enlace con el ámbito local.</span><span class="sxs-lookup"><span data-stu-id="f5256-193">The `as` clause binds the matched value to a name that can be used in the execution expression of a `match` expression, or, in the case where this pattern is used in a `let` binding, the name is added as a binding to the local scope.</span></span>

<span data-ttu-id="f5256-194">En el ejemplo siguiente se usa un `as` patrón.</span><span class="sxs-lookup"><span data-stu-id="f5256-194">The following example uses an `as` pattern.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4806.fs)]

## <a name="or-pattern"></a><span data-ttu-id="f5256-195">O un patrón</span><span class="sxs-lookup"><span data-stu-id="f5256-195">OR Pattern</span></span>

<span data-ttu-id="f5256-196">Cuando los datos de entrada pueden coincidir con varios modelos, y desea ejecutar el mismo código como resultado, se usa el modelo de OR.</span><span class="sxs-lookup"><span data-stu-id="f5256-196">The OR pattern is used when input data can match multiple patterns, and you want to execute the same code as a result.</span></span> <span data-ttu-id="f5256-197">Los tipos de ambos lados del modelo de OR deben ser compatibles.</span><span class="sxs-lookup"><span data-stu-id="f5256-197">The types of both sides of the OR pattern must be compatible.</span></span>

<span data-ttu-id="f5256-198">El ejemplo siguiente muestra el modelo de OR.</span><span class="sxs-lookup"><span data-stu-id="f5256-198">The following example demonstrates the OR pattern.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4807.fs)]

## <a name="and-pattern"></a><span data-ttu-id="f5256-199">Y el patrón</span><span class="sxs-lookup"><span data-stu-id="f5256-199">AND Pattern</span></span>

<span data-ttu-id="f5256-200">El modelo de AND exige que la entrada coincida con dos modelos.</span><span class="sxs-lookup"><span data-stu-id="f5256-200">The AND pattern requires that the input match two patterns.</span></span> <span data-ttu-id="f5256-201">Los tipos de ambos lados del modelo de AND deben ser compatibles.</span><span class="sxs-lookup"><span data-stu-id="f5256-201">The types of both sides of the AND pattern must be compatible.</span></span>

<span data-ttu-id="f5256-202">El ejemplo siguiente es similar a `detectZeroTuple` se muestra en el [modelo de tupla](https://msdn.microsoft.com/library/#tuple) sección más adelante en este tema, pero aquí ambos `var1` y `var2` se obtienen como valores utilizando el modelo de AND.</span><span class="sxs-lookup"><span data-stu-id="f5256-202">The following example is like `detectZeroTuple` shown in the [Tuple Pattern](https://msdn.microsoft.com/library/#tuple) section later in this topic, but here both `var1` and `var2` are obtained as values by using the AND pattern.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4808.fs)]

## <a name="cons-pattern"></a><span data-ttu-id="f5256-203">Modelo de cons</span><span class="sxs-lookup"><span data-stu-id="f5256-203">Cons Pattern</span></span>

<span data-ttu-id="f5256-204">El modelo de cons se utiliza para descomponer una lista en el primer elemento, el *head*y una lista que contiene los elementos restantes, el *final*.</span><span class="sxs-lookup"><span data-stu-id="f5256-204">The cons pattern is used to decompose a list into the first element, the *head*, and a list that contains the remaining elements, the *tail*.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4809.fs)]

## <a name="list-pattern"></a><span data-ttu-id="f5256-205">Modelo de lista</span><span class="sxs-lookup"><span data-stu-id="f5256-205">List Pattern</span></span>

<span data-ttu-id="f5256-206">El patrón de lista permite descomponer en un número de elementos de las listas.</span><span class="sxs-lookup"><span data-stu-id="f5256-206">The list pattern enables lists to be decomposed into a number of elements.</span></span> <span data-ttu-id="f5256-207">El mismo patrón de lista puede coincidir con sólo las listas de un número específico de elementos.</span><span class="sxs-lookup"><span data-stu-id="f5256-207">The list pattern itself can match only lists of a specific number of elements.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4810.fs)]

## <a name="array-pattern"></a><span data-ttu-id="f5256-208">Patrón de matriz</span><span class="sxs-lookup"><span data-stu-id="f5256-208">Array Pattern</span></span>

<span data-ttu-id="f5256-209">El patrón de matriz parece al modelo de lista y se puede usar para descomponer matrices de una longitud concreta.</span><span class="sxs-lookup"><span data-stu-id="f5256-209">The array pattern resembles the list pattern and can be used to decompose arrays of a specific length.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4811.fs)]

## <a name="parenthesized-pattern"></a><span data-ttu-id="f5256-210">Modelo entre paréntesis</span><span class="sxs-lookup"><span data-stu-id="f5256-210">Parenthesized Pattern</span></span>

<span data-ttu-id="f5256-211">Los paréntesis pueden agruparse en torno a los modelos para lograr la asociatividad deseada.</span><span class="sxs-lookup"><span data-stu-id="f5256-211">Parentheses can be grouped around patterns to achieve the desired associativity.</span></span> <span data-ttu-id="f5256-212">En el ejemplo siguiente, se utilizan paréntesis para controlar la asociatividad entre un modelo de AND y un modelo de cons.</span><span class="sxs-lookup"><span data-stu-id="f5256-212">In the following example, parentheses are used to control associativity between an AND pattern and a cons pattern.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4812.fs)]

## <a name="tuple-pattern"></a><span data-ttu-id="f5256-213">Modelo de tupla</span><span class="sxs-lookup"><span data-stu-id="f5256-213">Tuple Pattern</span></span>

<span data-ttu-id="f5256-214">El modelo de tupla asocia la entrada en forma de tupla y permite la tupla que se descompone en sus elementos constituyentes utilizando variables para cada posición de la tupla de coincidencia de patrones.</span><span class="sxs-lookup"><span data-stu-id="f5256-214">The tuple pattern matches input in tuple form and enables the tuple to be decomposed into its constituent elements by using pattern matching variables for each position in the tuple.</span></span>

<span data-ttu-id="f5256-215">El ejemplo siguiente muestra el modelo de tupla y también usa modelos de literal, modelos de variable y el patrón de caracteres comodín.</span><span class="sxs-lookup"><span data-stu-id="f5256-215">The following example demonstrates the tuple pattern and also uses literal patterns, variable patterns, and the wildcard pattern.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4813.fs)]

## <a name="record-pattern"></a><span data-ttu-id="f5256-216">Modelo de registro</span><span class="sxs-lookup"><span data-stu-id="f5256-216">Record Pattern</span></span>

<span data-ttu-id="f5256-217">El modelo de registro se utiliza para descomponer los registros para extraer los valores de campos.</span><span class="sxs-lookup"><span data-stu-id="f5256-217">The record pattern is used to decompose records to extract the values of fields.</span></span> <span data-ttu-id="f5256-218">El patrón no tiene que hacer referencia a todos los campos del registro; solo los campos omitidos no participan en la coincidencia y no se extraen.</span><span class="sxs-lookup"><span data-stu-id="f5256-218">The pattern does not have to reference all fields of the record; any omitted fields just do not participate in matching and are not extracted.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4814.fs)]

## <a name="wildcard-pattern"></a><span data-ttu-id="f5256-219">Patrón de caracteres comodín</span><span class="sxs-lookup"><span data-stu-id="f5256-219">Wildcard Pattern</span></span>

<span data-ttu-id="f5256-220">El modelo de carácter comodín se representa mediante el carácter de subrayado (`_`) de caracteres y coincide con cualquier entrada, al igual que el modelo de variable, salvo que la entrada se descarta en lugar de asignar a una variable.</span><span class="sxs-lookup"><span data-stu-id="f5256-220">The wildcard pattern is represented by the underscore (`_`) character and matches any input, just like the variable pattern, except that the input is discarded instead of assigned to a variable.</span></span> <span data-ttu-id="f5256-221">El modelo de carácter comodín se utiliza a menudo dentro de otros modelos como marcador de posición para los valores que no son necesarios en la expresión a la derecha de la `->` símbolos.</span><span class="sxs-lookup"><span data-stu-id="f5256-221">The wildcard pattern is often used within other patterns as a placeholder for values that are not needed in the expression to the right of the `->` symbol.</span></span> <span data-ttu-id="f5256-222">El modelo de carácter comodín también con frecuencia se utiliza al final de una lista de patrones para que coincida con cualquier entrada no coincidente.</span><span class="sxs-lookup"><span data-stu-id="f5256-222">The wildcard pattern is also frequently used at the end of a list of patterns to match any unmatched input.</span></span> <span data-ttu-id="f5256-223">En muchos ejemplos de código de este tema se muestra el patrón de caracteres comodín.</span><span class="sxs-lookup"><span data-stu-id="f5256-223">The wildcard pattern is demonstrated in many code examples in this topic.</span></span> <span data-ttu-id="f5256-224">Vea el código anterior para obtener un ejemplo.</span><span class="sxs-lookup"><span data-stu-id="f5256-224">See the preceding code for one example.</span></span>

## <a name="patterns-that-have-type-annotations"></a><span data-ttu-id="f5256-225">Patrones que tienen anotaciones de tipo</span><span class="sxs-lookup"><span data-stu-id="f5256-225">Patterns That Have Type Annotations</span></span>

<span data-ttu-id="f5256-226">Los modelos pueden tener anotaciones de tipo.</span><span class="sxs-lookup"><span data-stu-id="f5256-226">Patterns can have type annotations.</span></span> <span data-ttu-id="f5256-227">Estas se comportan igual que otras anotaciones de tipo y orientan la inferencia como las demás anotaciones de tipo.</span><span class="sxs-lookup"><span data-stu-id="f5256-227">These behave like other type annotations and guide inference like other type annotations.</span></span> <span data-ttu-id="f5256-228">Se necesitan paréntesis en torno a las anotaciones de tipos de patrones.</span><span class="sxs-lookup"><span data-stu-id="f5256-228">Parentheses are required around type annotations in patterns.</span></span> <span data-ttu-id="f5256-229">El código siguiente muestra un modelo que tiene una anotación de tipo.</span><span class="sxs-lookup"><span data-stu-id="f5256-229">The following code shows a pattern that has a type annotation.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4815.fs)]

## <a name="type-test-pattern"></a><span data-ttu-id="f5256-230">Modelo de prueba de tipo</span><span class="sxs-lookup"><span data-stu-id="f5256-230">Type Test Pattern</span></span>

<span data-ttu-id="f5256-231">El modelo de prueba de tipo se usa para comparar la entrada con un tipo.</span><span class="sxs-lookup"><span data-stu-id="f5256-231">The type test pattern is used to match the input against a type.</span></span> <span data-ttu-id="f5256-232">Si el tipo de entrada es una coincidencia (o un tipo derivado de) el tipo especificado en el modelo, la coincidencia se realiza correctamente.</span><span class="sxs-lookup"><span data-stu-id="f5256-232">If the input type is a match to (or a derived type of) the type specified in the pattern, the match succeeds.</span></span>

<span data-ttu-id="f5256-233">El ejemplo siguiente muestra el patrón de prueba de tipo.</span><span class="sxs-lookup"><span data-stu-id="f5256-233">The following example demonstrates the type test pattern.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4816.fs)]

## <a name="null-pattern"></a><span data-ttu-id="f5256-234">Modelo de null</span><span class="sxs-lookup"><span data-stu-id="f5256-234">Null Pattern</span></span>

<span data-ttu-id="f5256-235">El modelo de null coincide con el valor null que puede aparecer cuando se trabaja con tipos que permiten un valor null.</span><span class="sxs-lookup"><span data-stu-id="f5256-235">The null pattern matches the null value that can appear when you are working with types that allow a null value.</span></span> <span data-ttu-id="f5256-236">Los modelos de NULL se utilizan con frecuencia al interoperar con código de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="f5256-236">Null patterns are frequently used when interoperating with .NET Framework code.</span></span> <span data-ttu-id="f5256-237">Por ejemplo, el valor devuelto de una API de .NET puede ser la entrada a un `match` expresión.</span><span class="sxs-lookup"><span data-stu-id="f5256-237">For example, the return value of a .NET API might be the input to a `match` expression.</span></span> <span data-ttu-id="f5256-238">Puede controlar el flujo del programa en función de si el valor devuelto es null y también en otras características del valor devuelto.</span><span class="sxs-lookup"><span data-stu-id="f5256-238">You can control program flow based on whether the return value is null, and also on other characteristics of the returned value.</span></span> <span data-ttu-id="f5256-239">Puede usar el modelo de null para impedir que se propaguen al resto del programa valores null.</span><span class="sxs-lookup"><span data-stu-id="f5256-239">You can use the null pattern to prevent null values from propagating to the rest of your program.</span></span>

<span data-ttu-id="f5256-240">En el ejemplo siguiente se usa el modelo de null y el modelo de variable.</span><span class="sxs-lookup"><span data-stu-id="f5256-240">The following example uses the null pattern and the variable pattern.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4817.fs)]

## <a name="see-also"></a><span data-ttu-id="f5256-241">Vea también</span><span class="sxs-lookup"><span data-stu-id="f5256-241">See also</span></span>

- [<span data-ttu-id="f5256-242">Expresiones de coincidencia</span><span class="sxs-lookup"><span data-stu-id="f5256-242">Match Expressions</span></span>](match-expressions.md)
- [<span data-ttu-id="f5256-243">Patrones activos</span><span class="sxs-lookup"><span data-stu-id="f5256-243">Active Patterns</span></span>](active-patterns.md)
- [<span data-ttu-id="f5256-244">Referencia del lenguaje F#</span><span class="sxs-lookup"><span data-stu-id="f5256-244">F# Language Reference</span></span>](index.md)