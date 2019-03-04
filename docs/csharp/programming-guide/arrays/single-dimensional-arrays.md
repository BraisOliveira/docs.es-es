---
title: 'Matrices unidimensionales: Guía de programación de C#'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- single-dimensional arrays [C#]
- arrays [C#], single-dimensional
ms.assetid: 2cec1196-1de0-49d2-baf2-c607c33310e8
ms.openlocfilehash: 719e4463806c9c7e8b5407f2494c3b548ffa43e8
ms.sourcegitcommit: 41c0637e894fbcd0713d46d6ef1866f08dc321a2
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/01/2019
ms.locfileid: "57200785"
---
# <a name="single-dimensional-arrays-c-programming-guide"></a><span data-ttu-id="645aa-102">Matrices unidimensionales (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="645aa-102">Single-Dimensional Arrays (C# Programming Guide)</span></span>

<span data-ttu-id="645aa-103">Puede declarar una matriz unidimensional de cinco enteros tal y como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="645aa-103">You can declare a single-dimensional array of five integers as shown in the following example:</span></span>  
  
 [!code-csharp[csProgGuideArrays#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#4)]  
  
 <span data-ttu-id="645aa-104">Esta matriz contiene los elementos de `array[0]` a `array[4]`.</span><span class="sxs-lookup"><span data-stu-id="645aa-104">This array contains the elements from `array[0]` to `array[4]`.</span></span> <span data-ttu-id="645aa-105">El operador [new](../../../csharp/language-reference/keywords/new.md) se usa para crear la matriz e inicializar los elementos de matriz con sus valores predeterminados.</span><span class="sxs-lookup"><span data-stu-id="645aa-105">The [new](../../../csharp/language-reference/keywords/new.md) operator is used to create the array and initialize the array elements to their default values.</span></span> <span data-ttu-id="645aa-106">En este ejemplo, todos los elementos de matriz se inicializan en cero.</span><span class="sxs-lookup"><span data-stu-id="645aa-106">In this example, all the array elements are initialized to zero.</span></span>  
  
 <span data-ttu-id="645aa-107">Una matriz que almacena elementos de cadena se puede declarar de la misma forma.</span><span class="sxs-lookup"><span data-stu-id="645aa-107">An array that stores string elements can be declared in the same way.</span></span> <span data-ttu-id="645aa-108">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="645aa-108">For example:</span></span>  
  
 [!code-csharp[csProgGuideArrays#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#5)]  
  
## <a name="array-initialization"></a><span data-ttu-id="645aa-109">Inicialización de matriz</span><span class="sxs-lookup"><span data-stu-id="645aa-109">Array Initialization</span></span>

 <span data-ttu-id="645aa-110">Es posible inicializar una matriz en la declaración, en cuyo caso, el especificador de longitud no es necesario porque ya lo proporciona el número de elementos de la lista de inicialización.</span><span class="sxs-lookup"><span data-stu-id="645aa-110">It is possible to initialize an array upon declaration, in which case, the length specifier is not needed because it is already supplied by the number of elements in the initialization list.</span></span> <span data-ttu-id="645aa-111">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="645aa-111">For example:</span></span>  
  
 [!code-csharp[csProgGuideArrays#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#6)]  
  
 <span data-ttu-id="645aa-112">Se puede inicializar una matriz de cadenas del mismo modo.</span><span class="sxs-lookup"><span data-stu-id="645aa-112">A string array can be initialized in the same way.</span></span> <span data-ttu-id="645aa-113">La siguiente es una declaración de una matriz de cadenas donde cada elemento de la matriz se inicializa mediante un nombre de un día:</span><span class="sxs-lookup"><span data-stu-id="645aa-113">The following is a declaration of a string array where each array element is initialized by a name of a day:</span></span>  
 
 ```csharp
 string[] weekDays = new string[] { "Sun", "Mon", "Tue", "Wed", "Thu", "Fri", "Sat" };
 ```
  
 <span data-ttu-id="645aa-114">Al inicializar una matriz en la declaración, puede usar los siguientes métodos abreviados:</span><span class="sxs-lookup"><span data-stu-id="645aa-114">When you initialize an array upon declaration, you can use the following shortcuts:</span></span>  
  
 [!code-csharp[csProgGuideArrays#8](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#8)]  
  
 <span data-ttu-id="645aa-115">Es posible declarar una variable de matriz sin inicializarla, pero debe usar el operador `new` al asignar una matriz a esta variable.</span><span class="sxs-lookup"><span data-stu-id="645aa-115">It is possible to declare an array variable without initialization, but you must use the `new` operator when you assign an array to this variable.</span></span> <span data-ttu-id="645aa-116">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="645aa-116">For example:</span></span>  
  
 [!code-csharp[csProgGuideArrays#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#9)]  
  
 <span data-ttu-id="645aa-117">C# 3.0 presenta matrices con tipo implícito.</span><span class="sxs-lookup"><span data-stu-id="645aa-117">C# 3.0 introduces implicitly typed arrays.</span></span> <span data-ttu-id="645aa-118">Para obtener más información, vea [Matrices con asignación implícita de tipos](../../../csharp/programming-guide/arrays/implicitly-typed-arrays.md).</span><span class="sxs-lookup"><span data-stu-id="645aa-118">For more information, see [Implicitly Typed Arrays](../../../csharp/programming-guide/arrays/implicitly-typed-arrays.md).</span></span>  
  
## <a name="value-type-and-reference-type-arrays"></a><span data-ttu-id="645aa-119">Matrices de tipo de valor y tipo de referencia</span><span class="sxs-lookup"><span data-stu-id="645aa-119">Value Type and Reference Type Arrays</span></span>

 <span data-ttu-id="645aa-120">Tenga en cuenta la siguiente declaración de matriz:</span><span class="sxs-lookup"><span data-stu-id="645aa-120">Consider the following array declaration:</span></span>  
  
 [!code-csharp[csProgGuideArrays#10](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#10)]  
  
 <span data-ttu-id="645aa-121">El resultado de esta instrucción depende de si `SomeType` es un tipo de valor o un tipo de referencia.</span><span class="sxs-lookup"><span data-stu-id="645aa-121">The result of this statement depends on whether `SomeType` is a value type or a reference type.</span></span> <span data-ttu-id="645aa-122">Si es un tipo de valor, la instrucción crea una matriz de 10 elementos y cada uno de ellos tiene el tipo `SomeType`.</span><span class="sxs-lookup"><span data-stu-id="645aa-122">If it is a value type, the statement creates an array of 10 elements, each of which has the type `SomeType`.</span></span> <span data-ttu-id="645aa-123">Si `SomeType` es un tipo de referencia, la instrucción crea una matriz de 10 elementos y cada uno de ellos se inicializa en una referencia nula.</span><span class="sxs-lookup"><span data-stu-id="645aa-123">If `SomeType` is a reference type, the statement creates an array of 10 elements, each of which is initialized to a null reference.</span></span>  
  
 <span data-ttu-id="645aa-124">Para obtener más información sobre los tipos de valor y de referencia, consulte [Types](../../../csharp/language-reference/keywords/types.md) (Tipos).</span><span class="sxs-lookup"><span data-stu-id="645aa-124">For more information about value types and reference types, see [Types](../../../csharp/language-reference/keywords/types.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="645aa-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="645aa-125">See also</span></span>

- <xref:System.Array>
- [<span data-ttu-id="645aa-126">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="645aa-126">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="645aa-127">Matrices</span><span class="sxs-lookup"><span data-stu-id="645aa-127">Arrays</span></span>](../../../csharp/programming-guide/arrays/index.md)
- [<span data-ttu-id="645aa-128">Matrices multidimensionales</span><span class="sxs-lookup"><span data-stu-id="645aa-128">Multidimensional Arrays</span></span>](../../../csharp/programming-guide/arrays/multidimensional-arrays.md)
- [<span data-ttu-id="645aa-129">Matrices escalonadas</span><span class="sxs-lookup"><span data-stu-id="645aa-129">Jagged Arrays</span></span>](../../../csharp/programming-guide/arrays/jagged-arrays.md)
