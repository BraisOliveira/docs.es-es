---
title: 'Cómo: Obtener acceso a un elemento de matriz con un puntero: Guía de programación de C#'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- pointers [C#], array access
ms.assetid: 6c46f2af-a730-4855-8638-f136d9abaa12
ms.openlocfilehash: 7b2991776ca032aa53111187a061835725cfe223
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2019
ms.locfileid: "56965610"
---
# <a name="how-to-access-an-array-element-with-a-pointer-c-programming-guide"></a><span data-ttu-id="164d2-102">Cómo: Obtener acceso a un elemento de matriz con un puntero (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="164d2-102">How to: access an array element with a pointer (C# Programming Guide)</span></span>

<span data-ttu-id="164d2-103">En un contexto no seguro, puede tener acceso a un elemento en la memoria con el acceso a un elemento de puntero, como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="164d2-103">In an unsafe context, you can access an element in memory by using pointer element access, as shown in the following example:</span></span>

```csharp
char* charPointer = stackalloc char[123];
for (int i = 65; i < 123; i++)
{
    charPointer[i] = (char)i; //access array elements
}
```

<span data-ttu-id="164d2-104">La expresión entre corchetes debe poder convertirse implícitamente en `int`, `uint`, `long` o `ulong`.</span><span class="sxs-lookup"><span data-stu-id="164d2-104">The expression in square brackets must be implicitly convertible to `int`, `uint`, `long`, or `ulong`.</span></span> <span data-ttu-id="164d2-105">La operación `p[e]` equivale a `*(p+e)`.</span><span class="sxs-lookup"><span data-stu-id="164d2-105">The operation `p[e]` is equivalent to `*(p+e)`.</span></span> <span data-ttu-id="164d2-106">Como C y C++, el acceso al elemento de puntero no comprueba errores fuera de los límites.</span><span class="sxs-lookup"><span data-stu-id="164d2-106">Like C and C++, the pointer element access does not check for out-of-bounds errors.</span></span>

## <a name="example"></a><span data-ttu-id="164d2-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="164d2-107">Example</span></span>

<span data-ttu-id="164d2-108">En este ejemplo, las ubicaciones de memoria 123 se asignan a una matriz de caracteres, `charPointer`.</span><span class="sxs-lookup"><span data-stu-id="164d2-108">In this example, 123 memory locations are allocated to a character array, `charPointer`.</span></span> <span data-ttu-id="164d2-109">La matriz se usa para mostrar las letras en minúsculas y las letras en mayúsculas en dos bucles [for](../../../csharp/language-reference/keywords/for.md).</span><span class="sxs-lookup"><span data-stu-id="164d2-109">The array is used to display the lowercase letters and the uppercase letters in two [for](../../../csharp/language-reference/keywords/for.md) loops.</span></span>

<span data-ttu-id="164d2-110">Tenga en cuenta que la expresión `charPointer[i]` es equivalente a la expresión `*(charPointer + i)`, y puede obtener el mismo resultado con cualquiera de las dos expresiones.</span><span class="sxs-lookup"><span data-stu-id="164d2-110">Notice that the expression `charPointer[i]` is equivalent to the expression `*(charPointer + i)`, and you can obtain the same result by using either of the two expressions.</span></span>

 [!code-csharp[csProgGuidePointers#11](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuidePointers/CS/Pointers2.cs#11)]

 [!code-csharp[csProgGuidePointers#12](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuidePointers/CS/Pointers.cs#12)]

<span data-ttu-id="164d2-111">**Letras mayúsculas:**</span><span class="sxs-lookup"><span data-stu-id="164d2-111">**Uppercase letters:**</span></span>  
<span data-ttu-id="164d2-112">**ABCDEFGHIJKLMNOPQRSTUVWXYZ**</span><span class="sxs-lookup"><span data-stu-id="164d2-112">**ABCDEFGHIJKLMNOPQRSTUVWXYZ**</span></span>  
<span data-ttu-id="164d2-113">**Letras minúsculas:**</span><span class="sxs-lookup"><span data-stu-id="164d2-113">**Lowercase letters:**</span></span>  
<span data-ttu-id="164d2-114">**abcdefghijklmnopqrstuvwxyz**</span><span class="sxs-lookup"><span data-stu-id="164d2-114">**abcdefghijklmnopqrstuvwxyz**</span></span>  

## <a name="see-also"></a><span data-ttu-id="164d2-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="164d2-115">See also</span></span>

- [<span data-ttu-id="164d2-116">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="164d2-116">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="164d2-117">Expresiones de puntero</span><span class="sxs-lookup"><span data-stu-id="164d2-117">Pointer Expressions</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md)
- [<span data-ttu-id="164d2-118">Tipos de puntero</span><span class="sxs-lookup"><span data-stu-id="164d2-118">Pointer types</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md)
- [<span data-ttu-id="164d2-119">Tipos</span><span class="sxs-lookup"><span data-stu-id="164d2-119">Types</span></span>](../../../csharp/language-reference/keywords/types.md)
- [<span data-ttu-id="164d2-120">unsafe</span><span class="sxs-lookup"><span data-stu-id="164d2-120">unsafe</span></span>](../../../csharp/language-reference/keywords/unsafe.md)
- [<span data-ttu-id="164d2-121">fixed (instrucción)</span><span class="sxs-lookup"><span data-stu-id="164d2-121">fixed Statement</span></span>](../../../csharp/language-reference/keywords/fixed-statement.md)
- [<span data-ttu-id="164d2-122">stackalloc</span><span class="sxs-lookup"><span data-stu-id="164d2-122">stackalloc</span></span>](../../../csharp/language-reference/keywords/stackalloc.md)
