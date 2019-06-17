---
title: Tipos de puntero - Guía de programación de C#
ms.custom: seodec18
ms.date: 04/20/2018
helpviewer_keywords:
- unsafe code [C#], pointers
- pointers [C#]
ms.openlocfilehash: 3183f8434dd8a6bc8182e2257d0ab3c7e7c014c4
ms.sourcegitcommit: 34593b4d0be779699d38a9949d6aec11561657ec
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/11/2019
ms.locfileid: "66833438"
---
# <a name="pointer-types-c-programming-guide"></a><span data-ttu-id="e82bc-102">Tipos de puntero (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="e82bc-102">Pointer types (C# Programming Guide)</span></span>

<span data-ttu-id="e82bc-103">En un contexto no seguro, un tipo puede ser un tipo de puntero, un tipo de valor o un tipo de referencia.</span><span class="sxs-lookup"><span data-stu-id="e82bc-103">In an unsafe context, a type may be a pointer type, a value type, or a reference type.</span></span> <span data-ttu-id="e82bc-104">Una declaración de tipos de puntero toma una de las siguientes formas:</span><span class="sxs-lookup"><span data-stu-id="e82bc-104">A pointer type declaration takes one of the following forms:</span></span>

``` csharp
type* identifier;
void* identifier; //allowed but not recommended
```

<span data-ttu-id="e82bc-105">El tipo especificado antes de `*` en un tipo de puntero se denomina **tipo referente**.</span><span class="sxs-lookup"><span data-stu-id="e82bc-105">The type specified before the `*` in a pointer type is called the **referent type**.</span></span> <span data-ttu-id="e82bc-106">Cualquiera de los tipos siguientes puede ser un tipo referente:</span><span class="sxs-lookup"><span data-stu-id="e82bc-106">Any of the following types may be a referent type:</span></span>

- <span data-ttu-id="e82bc-107">Cualquier tipo integral: [sbyte](../../language-reference/keywords/sbyte.md), [byte](../../language-reference/keywords/byte.md), [short](../../language-reference/keywords/short.md), [ushort](../../language-reference/keywords/ushort.md), [int](../../language-reference/keywords/int.md), [uint](../../language-reference/keywords/uint.md), [long](../../language-reference/keywords/long.md), [ulong](../../language-reference/keywords/ulong.md).</span><span class="sxs-lookup"><span data-stu-id="e82bc-107">Any integral type: [sbyte](../../language-reference/keywords/sbyte.md), [byte](../../language-reference/keywords/byte.md), [short](../../language-reference/keywords/short.md), [ushort](../../language-reference/keywords/ushort.md), [int](../../language-reference/keywords/int.md), [uint](../../language-reference/keywords/uint.md), [long](../../language-reference/keywords/long.md), [ulong](../../language-reference/keywords/ulong.md).</span></span>
- <span data-ttu-id="e82bc-108">Cualquier tipo de punto flotante: [float](../../language-reference/keywords/float.md), [doble](../../language-reference/keywords/double.md).</span><span class="sxs-lookup"><span data-stu-id="e82bc-108">Any floating-point type: [float](../../language-reference/keywords/float.md), [double](../../language-reference/keywords/double.md).</span></span>
- <span data-ttu-id="e82bc-109">[char](../../language-reference/keywords/char.md).</span><span class="sxs-lookup"><span data-stu-id="e82bc-109">[char](../../language-reference/keywords/char.md).</span></span>
- <span data-ttu-id="e82bc-110">[bool](../../language-reference/keywords/bool.md).</span><span class="sxs-lookup"><span data-stu-id="e82bc-110">[bool](../../language-reference/keywords/bool.md).</span></span>
- <span data-ttu-id="e82bc-111">[decimal](../../language-reference/keywords/decimal.md).</span><span class="sxs-lookup"><span data-stu-id="e82bc-111">[decimal](../../language-reference/keywords/decimal.md).</span></span>
- <span data-ttu-id="e82bc-112">Cualquier tipo [enum](../../language-reference/keywords/enum.md).</span><span class="sxs-lookup"><span data-stu-id="e82bc-112">Any [enum](../../language-reference/keywords/enum.md) type.</span></span>
- <span data-ttu-id="e82bc-113">Cualquier tipo de puntero.</span><span class="sxs-lookup"><span data-stu-id="e82bc-113">Any pointer type.</span></span> <span data-ttu-id="e82bc-114">Esto permite expresiones como `void**`.</span><span class="sxs-lookup"><span data-stu-id="e82bc-114">This allows expressions such as `void**`.</span></span>
- <span data-ttu-id="e82bc-115">Cualquier tipo struct definido por el usuario que solo contenga campos de tipos no administrados.</span><span class="sxs-lookup"><span data-stu-id="e82bc-115">Any user-defined struct type that contains fields of unmanaged types only.</span></span>

<span data-ttu-id="e82bc-116">Los tipos de puntero no heredan de [object](../../language-reference/keywords/object.md) y no existe ninguna conversión entre tipos de puntero y `object`.</span><span class="sxs-lookup"><span data-stu-id="e82bc-116">Pointer types do not inherit from [object](../../language-reference/keywords/object.md) and no conversions exist between pointer types and `object`.</span></span> <span data-ttu-id="e82bc-117">Además, las conversiones boxing y unboxing no admiten punteros.</span><span class="sxs-lookup"><span data-stu-id="e82bc-117">Also, boxing and unboxing do not support pointers.</span></span> <span data-ttu-id="e82bc-118">Sin embargo, puede realizar la conversión entre diferentes tipos de puntero y entre tipos de puntero y tipos enteros.</span><span class="sxs-lookup"><span data-stu-id="e82bc-118">However, you can convert between different pointer types and between pointer types and integral types.</span></span>

<span data-ttu-id="e82bc-119">Cuando declare varios punteros en la misma declaración, únicamente debe escribir el asterisco (\*) con el tipo subyacente; no se usa como prefijo en cada nombre de puntero.</span><span class="sxs-lookup"><span data-stu-id="e82bc-119">When you declare multiple pointers in the same declaration, the asterisk (\*) is written together with the underlying type only; it is not used as a prefix to each pointer name.</span></span> <span data-ttu-id="e82bc-120">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="e82bc-120">For example:</span></span>

```csharp
int* p1, p2, p3;   // Ok
int *p1, *p2, *p3;   // Invalid in C#
```

<span data-ttu-id="e82bc-121">Un puntero no puede señalar a una referencia ni a un [struct](../../language-reference/keywords/struct.md) que contenga referencias, porque una referencia de objeto puede recolectarse como elemento no utilizado aunque haya un puntero que la señale.</span><span class="sxs-lookup"><span data-stu-id="e82bc-121">A pointer cannot point to a reference or to a [struct](../../language-reference/keywords/struct.md) that contains references, because an object reference can be garbage collected even if a pointer is pointing to it.</span></span> <span data-ttu-id="e82bc-122">El recolector de elementos no utilizados no realiza un seguimiento de si algún tipo de puntero señala a un objeto.</span><span class="sxs-lookup"><span data-stu-id="e82bc-122">The garbage collector does not keep track of whether an object is being pointed to by any pointer types.</span></span>

<span data-ttu-id="e82bc-123">El valor de la variable de puntero de tipo `myType*` es la dirección de una variable de tipo `myType`.</span><span class="sxs-lookup"><span data-stu-id="e82bc-123">The value of the pointer variable of type `myType*` is the address of a variable of type `myType`.</span></span> <span data-ttu-id="e82bc-124">A continuación se muestran ejemplos de declaraciones de tipos de puntero:</span><span class="sxs-lookup"><span data-stu-id="e82bc-124">The following are examples of pointer type declarations:</span></span>

|<span data-ttu-id="e82bc-125">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e82bc-125">Example</span></span>|<span data-ttu-id="e82bc-126">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="e82bc-126">Description</span></span>|
|-------------|-----------------|
|`int* p`|<span data-ttu-id="e82bc-127">`p` es un puntero a un entero.</span><span class="sxs-lookup"><span data-stu-id="e82bc-127">`p` is a pointer to an integer.</span></span>|
|`int** p`|<span data-ttu-id="e82bc-128">`p` es un puntero a un puntero a un entero.</span><span class="sxs-lookup"><span data-stu-id="e82bc-128">`p` is a pointer to a pointer to an integer.</span></span>|
|`int*[] p`|<span data-ttu-id="e82bc-129">`p` es una matriz unidimensional de punteros a enteros.</span><span class="sxs-lookup"><span data-stu-id="e82bc-129">`p` is a single-dimensional array of pointers to integers.</span></span>|
|`char* p`|<span data-ttu-id="e82bc-130">`p` es un puntero a un valor char.</span><span class="sxs-lookup"><span data-stu-id="e82bc-130">`p` is a pointer to a char.</span></span>|
|`void* p`|<span data-ttu-id="e82bc-131">`p` es un puntero a un tipo desconocido.</span><span class="sxs-lookup"><span data-stu-id="e82bc-131">`p` is a pointer to an unknown type.</span></span>|

<span data-ttu-id="e82bc-132">El operador de direccionamiento indirecto del puntero \* puede usarse para obtener acceso al contenido de la ubicación señalada por la variable de puntero.</span><span class="sxs-lookup"><span data-stu-id="e82bc-132">The pointer indirection operator \* can be used to access the contents at the location pointed to by the pointer variable.</span></span> <span data-ttu-id="e82bc-133">Por ejemplo, consideremos la siguiente declaración:</span><span class="sxs-lookup"><span data-stu-id="e82bc-133">For example, consider the following declaration:</span></span>

```csharp
int* myVariable;
```

<span data-ttu-id="e82bc-134">La expresión `*myVariable` denota la variable `int` que se encuentra en la dirección contenida en `myVariable`.</span><span class="sxs-lookup"><span data-stu-id="e82bc-134">The expression `*myVariable` denotes the `int` variable found at the address contained in `myVariable`.</span></span>

<span data-ttu-id="e82bc-135">Hay varios ejemplos de punteros en los temas [fixed Statement](../../language-reference/keywords/fixed-statement.md) (fixed [Instrucción, Referencia de C#])y [Pointer Conversions](../../programming-guide/unsafe-code-pointers/pointer-conversions.md) (Conversiones de puntero [Guía de programación de C#]).</span><span class="sxs-lookup"><span data-stu-id="e82bc-135">There are several examples of pointers in the topics [fixed Statement](../../language-reference/keywords/fixed-statement.md) and [Pointer Conversions](../../programming-guide/unsafe-code-pointers/pointer-conversions.md).</span></span> <span data-ttu-id="e82bc-136">En el ejemplo siguiente se usa la palabra clave `unsafe` y la instrucción `fixed` y se muestra cómo incrementar un puntero interior.</span><span class="sxs-lookup"><span data-stu-id="e82bc-136">The following example uses the `unsafe` keyword and the `fixed` statement, and shows how to increment an interior pointer.</span></span>  <span data-ttu-id="e82bc-137">Puede pegar este código en la función Main de una aplicación de consola para ejecutarla.</span><span class="sxs-lookup"><span data-stu-id="e82bc-137">You can paste this code into the Main function of a console application to run it.</span></span> <span data-ttu-id="e82bc-138">Estos ejemplos deben compilarse con el conjunto de opciones del compilador [-unsafe](../../language-reference/compiler-options/unsafe-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="e82bc-138">These examples must be compiled with the [-unsafe](../../language-reference/compiler-options/unsafe-compiler-option.md) compiler option set.</span></span>

[!code-csharp[Using pointer types](../../../../samples/snippets/csharp/keywords/FixedKeywordExamples.cs#5)]

<span data-ttu-id="e82bc-139">No se puede aplicar el operador de direccionamiento indirecto a un puntero de tipo `void*`.</span><span class="sxs-lookup"><span data-stu-id="e82bc-139">You cannot apply the indirection operator to a pointer of type `void*`.</span></span> <span data-ttu-id="e82bc-140">Sin embargo, es posible usar una conversión para convertir un puntero void en cualquier otro tipo de puntero y viceversa.</span><span class="sxs-lookup"><span data-stu-id="e82bc-140">However, you can use a cast to convert a void pointer to any other pointer type, and vice versa.</span></span>

<span data-ttu-id="e82bc-141">Un puntero puede ser `null`.</span><span class="sxs-lookup"><span data-stu-id="e82bc-141">A pointer can be `null`.</span></span> <span data-ttu-id="e82bc-142">La aplicación del operador de direccionamiento indirecto a un puntero NULL da como resultado un comportamiento definido por la implementación.</span><span class="sxs-lookup"><span data-stu-id="e82bc-142">Applying the indirection operator to a null pointer causes an implementation-defined behavior.</span></span>

<span data-ttu-id="e82bc-143">Pasar punteros entre métodos puede provocar un comportamiento no definido.</span><span class="sxs-lookup"><span data-stu-id="e82bc-143">Passing pointers between methods can cause undefined behavior.</span></span> <span data-ttu-id="e82bc-144">Valore la posibilidad de usar un método que devuelva un puntero a una variable local mediante un parámetro `in`, `out` o `ref`, o bien como resultado de la función.</span><span class="sxs-lookup"><span data-stu-id="e82bc-144">Consider a method that returns a pointer to a local variable through an `in`, `out`, or `ref` parameter or as the function result.</span></span> <span data-ttu-id="e82bc-145">Si el puntero se estableció en un bloque fijo, es posible que la variable a la que señala ya no sea fija.</span><span class="sxs-lookup"><span data-stu-id="e82bc-145">If the pointer was set in a fixed block, the variable to which it points may no longer be fixed.</span></span>

<span data-ttu-id="e82bc-146">En la tabla siguiente se muestran los operadores e instrucciones que pueden funcionar en punteros en un contexto no seguro:</span><span class="sxs-lookup"><span data-stu-id="e82bc-146">The following table lists the operators and statements that can operate on pointers in an unsafe context:</span></span>

|<span data-ttu-id="e82bc-147">Operador/Instrucción</span><span class="sxs-lookup"><span data-stu-id="e82bc-147">Operator/Statement</span></span>|<span data-ttu-id="e82bc-148">Usar</span><span class="sxs-lookup"><span data-stu-id="e82bc-148">Use</span></span>|
|-------------------------|---------|
|`*`|<span data-ttu-id="e82bc-149">Realiza el direccionamiento indirecto del puntero.</span><span class="sxs-lookup"><span data-stu-id="e82bc-149">Performs pointer indirection.</span></span>|
|`->`|<span data-ttu-id="e82bc-150">Obtiene acceso a un miembro de un struct a través de un puntero.</span><span class="sxs-lookup"><span data-stu-id="e82bc-150">Accesses a member of a struct through a pointer.</span></span>|
|`[]`|<span data-ttu-id="e82bc-151">Indiza un puntero.</span><span class="sxs-lookup"><span data-stu-id="e82bc-151">Indexes a pointer.</span></span>|
|`&`|<span data-ttu-id="e82bc-152">Obtiene la dirección de una variable.</span><span class="sxs-lookup"><span data-stu-id="e82bc-152">Obtains the address of a variable.</span></span>|
|<span data-ttu-id="e82bc-153">`++` y `--`</span><span class="sxs-lookup"><span data-stu-id="e82bc-153">`++` and `--`</span></span>|<span data-ttu-id="e82bc-154">Incrementa y disminuye los punteros.</span><span class="sxs-lookup"><span data-stu-id="e82bc-154">Increments and decrements pointers.</span></span>|
|<span data-ttu-id="e82bc-155">`+` y `-`</span><span class="sxs-lookup"><span data-stu-id="e82bc-155">`+` and `-`</span></span>|<span data-ttu-id="e82bc-156">Realiza aritmética con punteros.</span><span class="sxs-lookup"><span data-stu-id="e82bc-156">Performs pointer arithmetic.</span></span>|
|<span data-ttu-id="e82bc-157">`==`, `!=`, `<`, `>`, `<=` y `>=`</span><span class="sxs-lookup"><span data-stu-id="e82bc-157">`==`, `!=`, `<`, `>`, `<=`, and `>=`</span></span>|<span data-ttu-id="e82bc-158">Compara los punteros.</span><span class="sxs-lookup"><span data-stu-id="e82bc-158">Compares pointers.</span></span>|
|[<span data-ttu-id="e82bc-159">`stackalloc` operator</span><span class="sxs-lookup"><span data-stu-id="e82bc-159">`stackalloc` operator</span></span>](../../language-reference/operators/stackalloc.md)|<span data-ttu-id="e82bc-160">Asigna memoria en la pila.</span><span class="sxs-lookup"><span data-stu-id="e82bc-160">Allocates memory on the stack.</span></span>|
|[<span data-ttu-id="e82bc-161">Instrucción `fixed`</span><span class="sxs-lookup"><span data-stu-id="e82bc-161">`fixed` statement</span></span>](../../language-reference/keywords/fixed-statement.md)|<span data-ttu-id="e82bc-162">Fija provisionalmente una variable para que pueda encontrarse su dirección.</span><span class="sxs-lookup"><span data-stu-id="e82bc-162">Temporarily fixes a variable so that its address may be found.</span></span>|

<span data-ttu-id="e82bc-163">Para obtener más información sobre los operadores relacionados con el puntero, vea [Operadores relacionados con el puntero](../../language-reference/operators/pointer-related-operators.md).</span><span class="sxs-lookup"><span data-stu-id="e82bc-163">For more information about pointer related operators, see [Pointer related operators](../../language-reference/operators/pointer-related-operators.md).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="e82bc-164">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="e82bc-164">C# language specification</span></span>

<span data-ttu-id="e82bc-165">Para obtener más información, vea la sección [Tipos de puntero](~/_csharplang/spec/unsafe-code.md#pointer-types) de [Especificación del lenguaje C#](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="e82bc-165">For more information, see the [Pointer types](~/_csharplang/spec/unsafe-code.md#pointer-types) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="e82bc-166">Vea también</span><span class="sxs-lookup"><span data-stu-id="e82bc-166">See also</span></span>

- [<span data-ttu-id="e82bc-167">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="e82bc-167">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="e82bc-168">Código no seguro y punteros</span><span class="sxs-lookup"><span data-stu-id="e82bc-168">Unsafe Code and Pointers</span></span>](index.md)
- [<span data-ttu-id="e82bc-169">Conversiones de puntero</span><span class="sxs-lookup"><span data-stu-id="e82bc-169">Pointer Conversions</span></span>](pointer-conversions.md)
- [<span data-ttu-id="e82bc-170">Tipos</span><span class="sxs-lookup"><span data-stu-id="e82bc-170">Types</span></span>](../../language-reference/keywords/types.md)
- [<span data-ttu-id="e82bc-171">unsafe</span><span class="sxs-lookup"><span data-stu-id="e82bc-171">unsafe</span></span>](../../language-reference/keywords/unsafe.md)
