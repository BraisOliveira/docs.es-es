---
title: 'Palabra clave explicit: Referencia de C#'
ms.custom: seodec18
ms.date: 08/24/2018
f1_keywords:
- explicit_CSharpKeyword
- explicit
helpviewer_keywords:
- explicit keyword [C#]
ms.assetid: cfb8f42a-e411-4db2-af9b-796b05644846
ms.openlocfilehash: a260c6f1ccac6e09770f1cb8f43d5d872b4b2650
ms.sourcegitcommit: eaa6d5cd0f4e7189dbe0bd756e9f53508b01989e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/07/2019
ms.locfileid: "67610102"
---
# <a name="explicit-c-reference"></a><span data-ttu-id="0dc0f-102">explicit (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="0dc0f-102">explicit (C# Reference)</span></span>

<span data-ttu-id="0dc0f-103">La palabra clave `explicit` declara un operador de conversión de tipo definido por el usuario que se debe invocar con una conversión.</span><span class="sxs-lookup"><span data-stu-id="0dc0f-103">The `explicit` keyword declares a user-defined type conversion operator that must be invoked with a cast.</span></span>

<span data-ttu-id="0dc0f-104">En el ejemplo siguiente se define el operador que convierte de una clase `Fahrenheit` a una clase `Celsius`.</span><span class="sxs-lookup"><span data-stu-id="0dc0f-104">The following example defines the operator that converts from a `Fahrenheit` class to a `Celsius` class.</span></span> <span data-ttu-id="0dc0f-105">El operador debe definirse en una clase `Fahrenheit` o en una clase `Celsius`:</span><span class="sxs-lookup"><span data-stu-id="0dc0f-105">The operator must be defined either inside a `Fahrenheit` class or a `Celsius` class:</span></span>

[!code-csharp[csrefKeywordsConversion#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsConversion/CS/csrefKeywordsConversion.cs#2)]

<span data-ttu-id="0dc0f-106">El operador de conversión definido se invoca con una conversión, como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="0dc0f-106">You invoke the defined conversion operator with a cast, as the following example shows:</span></span>

[!code-csharp[csrefKeywordsConversion#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsConversion/CS/csrefKeywordsConversion.cs#3)]

<span data-ttu-id="0dc0f-107">El operador de conversión convierte un tipo de origen en un tipo de destino.</span><span class="sxs-lookup"><span data-stu-id="0dc0f-107">The conversion operator converts from a source type to a target type.</span></span> <span data-ttu-id="0dc0f-108">El tipo de origen proporciona el operador de conversión.</span><span class="sxs-lookup"><span data-stu-id="0dc0f-108">The source type provides the conversion operator.</span></span> <span data-ttu-id="0dc0f-109">A diferencia de la conversión implícita, los operadores de conversión explícitos deben invocarse mediante una conversión.</span><span class="sxs-lookup"><span data-stu-id="0dc0f-109">Unlike implicit conversion, explicit conversion operators must be invoked by means of a cast.</span></span> <span data-ttu-id="0dc0f-110">Si una operación de conversión puede producir excepciones o pérdida de información, debe marcarse como `explicit`.</span><span class="sxs-lookup"><span data-stu-id="0dc0f-110">If a conversion operation can cause exceptions or lose information, you should mark it `explicit`.</span></span> <span data-ttu-id="0dc0f-111">Esto impide que el compilador invoque silenciosamente la operación de conversión con posibles consecuencias no deseadas.</span><span class="sxs-lookup"><span data-stu-id="0dc0f-111">This prevents the compiler from silently invoking the conversion operation with possibly unforeseen consequences.</span></span>

<span data-ttu-id="0dc0f-112">Omitir la conversión produce el error en tiempo de compilación CS0266.</span><span class="sxs-lookup"><span data-stu-id="0dc0f-112">Omitting the cast results in compile-time error CS0266.</span></span>

<span data-ttu-id="0dc0f-113">Para obtener más información, vea [Uso de operadores de conversión](../../programming-guide/statements-expressions-operators/using-conversion-operators.md).</span><span class="sxs-lookup"><span data-stu-id="0dc0f-113">For more information, see [Using Conversion Operators](../../programming-guide/statements-expressions-operators/using-conversion-operators.md).</span></span>

## <a name="example"></a><span data-ttu-id="0dc0f-114">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="0dc0f-114">Example</span></span>

<span data-ttu-id="0dc0f-115">En el ejemplo siguiente se proporciona una clase `Fahrenheit` y una clase `Celsius`, y cada una proporciona un operador de conversión explícita a la otra clase.</span><span class="sxs-lookup"><span data-stu-id="0dc0f-115">The following example provides a `Fahrenheit` and a `Celsius` class, each of which provides an explicit conversion operator to the other class.</span></span>

[!code-csharp[csrefKeywordsConversion#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsConversion/CS/csrefKeywordsConversion.cs#1)]

## <a name="example"></a><span data-ttu-id="0dc0f-116">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="0dc0f-116">Example</span></span>

<span data-ttu-id="0dc0f-117">En el ejemplo siguiente se define una struct, `Digit`, que representa un único dígito decimal.</span><span class="sxs-lookup"><span data-stu-id="0dc0f-117">The following example defines a struct, `Digit`, that represents a single decimal digit.</span></span> <span data-ttu-id="0dc0f-118">Se define un operador para conversiones de `byte` a `Digit`, pero como no todos los bytes se pueden convertir a un `Digit`, la conversión es explícita.</span><span class="sxs-lookup"><span data-stu-id="0dc0f-118">An operator is defined for conversions from `byte` to `Digit`, but because not all bytes can be converted to a `Digit`, the conversion is explicit.</span></span>

[!code-csharp[csrefKeywordsConversion#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsConversion/CS/csrefKeywordsConversion.cs#4)]

## <a name="c-language-specification"></a><span data-ttu-id="0dc0f-119">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="0dc0f-119">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="0dc0f-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="0dc0f-120">See also</span></span>

- [<span data-ttu-id="0dc0f-121">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="0dc0f-121">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="0dc0f-122">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="0dc0f-122">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="0dc0f-123">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="0dc0f-123">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="0dc0f-124">implicit</span><span class="sxs-lookup"><span data-stu-id="0dc0f-124">implicit</span></span>](implicit.md)
- [<span data-ttu-id="0dc0f-125">Sobrecarga de operadores</span><span class="sxs-lookup"><span data-stu-id="0dc0f-125">Operator overloading</span></span>](../operators/operator-overloading.md)
- [<span data-ttu-id="0dc0f-126">Cómo: Implementar conversiones definidas por el usuario entre structs</span><span class="sxs-lookup"><span data-stu-id="0dc0f-126">How to: Implement User-Defined Conversions Between Structs</span></span>](../../programming-guide/statements-expressions-operators/how-to-implement-user-defined-conversions-between-structs.md)
- <span data-ttu-id="0dc0f-127">[Chained user-defined explicit conversions in C#](https://blogs.msdn.microsoft.com/ericlippert/2007/04/16/chained-user-defined-explicit-conversions-in-c/) (Conversiones explícitas encadenadas definidas por el usuario en C#)</span><span class="sxs-lookup"><span data-stu-id="0dc0f-127">[Chained user-defined explicit conversions in C#](https://blogs.msdn.microsoft.com/ericlippert/2007/04/16/chained-user-defined-explicit-conversions-in-c/)</span></span>
