---
title: 'Operador new: Referencia de C#'
ms.custom: seodec18
ms.date: 03/15/2018
helpviewer_keywords:
- new operator keyword [C#]
ms.assetid: a212b697-a79b-4105-9923-1f7b108036e8
ms.openlocfilehash: 409a5307eaacd2eac865e2882cc7228521260dbe
ms.sourcegitcommit: 10986410e59ff29f2ec55c6759bde3eb4d1a00cb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/31/2019
ms.locfileid: "66421877"
---
# <a name="new-operator-c-reference"></a><span data-ttu-id="a8a76-102">Operador new (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="a8a76-102">new operator (C# Reference)</span></span>

<span data-ttu-id="a8a76-103">Se usa para crear objetos e invocar constructores.</span><span class="sxs-lookup"><span data-stu-id="a8a76-103">Used to create objects and invoke constructors.</span></span> <span data-ttu-id="a8a76-104">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="a8a76-104">For example:</span></span>

```csharp
Class1 obj  = new Class1();
```

<span data-ttu-id="a8a76-105">También se usa para crear instancias de tipos anónimos:</span><span class="sxs-lookup"><span data-stu-id="a8a76-105">It is also used to create instances of anonymous types:</span></span>

```csharp
var query = from cust in customers
            select new { Name = cust.Name, Address = cust.PrimaryAddress };
```

<span data-ttu-id="a8a76-106">El operador `new` también se usa para invocar al constructor sin parámetros para tipos de valor.</span><span class="sxs-lookup"><span data-stu-id="a8a76-106">The `new` operator is also used to invoke the parameterless constructor for value types.</span></span> <span data-ttu-id="a8a76-107">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="a8a76-107">For example:</span></span>

```csharp
int i = new int();
```

<span data-ttu-id="a8a76-108">En la instrucción anterior, `i` se ha inicializado en `0`, que es el valor predeterminado para el tipo `int`.</span><span class="sxs-lookup"><span data-stu-id="a8a76-108">In the preceding statement, `i` is initialized to `0`, which is the default value for the type `int`.</span></span> <span data-ttu-id="a8a76-109">La instrucción tiene el mismo efecto que lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="a8a76-109">The statement has the same effect as the following:</span></span>

```csharp
int i = 0;
```

<span data-ttu-id="a8a76-110">Para obtener una lista completa de valores predeterminados, vea [Tabla de valores predeterminados](default-values-table.md).</span><span class="sxs-lookup"><span data-stu-id="a8a76-110">For a complete list of default values, see [Default Values Table](default-values-table.md).</span></span>

<span data-ttu-id="a8a76-111">Recuerde que es un error declarar un constructor sin parámetros para un [struct](struct.md), ya que cada tipo de valor tiene implícitamente un constructor sin parámetros público.</span><span class="sxs-lookup"><span data-stu-id="a8a76-111">Remember that it is an error to declare a parameterless constructor for a [struct](struct.md) because every value type implicitly has a public parameterless constructor.</span></span> <span data-ttu-id="a8a76-112">Es posible declarar constructores parametrizados en un tipo struct para establecer sus valores iniciales, pero esto solo es necesario si se requieren valores distintos de los predeterminados.</span><span class="sxs-lookup"><span data-stu-id="a8a76-112">It is possible to declare parameterized constructors on a struct type to set its initial values, but this is only necessary if values other than the default are required.</span></span>

<span data-ttu-id="a8a76-113">Los objetos de tipo de valor, como las estructuras, y los objetos de tipo de referencia, como las clases, se destruyen automáticamente, pero los objetos de tipo de valor se destruyen junto al contexto que los contiene. En el caso de los objetos de tipo de referencia, los destruye el recolector de elementos no utilizados en un momento no especificado después de que se haya quitado la última referencia a ellos.</span><span class="sxs-lookup"><span data-stu-id="a8a76-113">Both value-type objects such as structs and reference-type objects such as classes are destroyed automatically, but value-type objects are destroyed when their containing context is destroyed, whereas reference-type objects are destroyed by the garbage collector at an unspecified time after the last reference to them is removed.</span></span> <span data-ttu-id="a8a76-114">Para los tipos que contienen recursos como identificadores de archivos o conexiones de red, lo recomendable es llevar a cabo una limpieza determinista para asegurarse de que los recursos que contienen se liberan tan pronto como sea posible.</span><span class="sxs-lookup"><span data-stu-id="a8a76-114">For types that contain resources such as file handles, or network connections, it is desirable to employ deterministic cleanup to ensure that the resources they contain are released as soon as possible.</span></span> <span data-ttu-id="a8a76-115">Para obtener más información, vea [Instrucción using](using-statement.md).</span><span class="sxs-lookup"><span data-stu-id="a8a76-115">For more information, see [using Statement](using-statement.md).</span></span>

<span data-ttu-id="a8a76-116">El operador `new` no se puede sobrecargar.</span><span class="sxs-lookup"><span data-stu-id="a8a76-116">The `new` operator cannot be overloaded.</span></span>

<span data-ttu-id="a8a76-117">Si el operador `new` no puede asignar memoria, se produce la excepción <xref:System.OutOfMemoryException>.</span><span class="sxs-lookup"><span data-stu-id="a8a76-117">If the `new` operator fails to allocate memory, it throws the exception, <xref:System.OutOfMemoryException>.</span></span>

## <a name="example"></a><span data-ttu-id="a8a76-118">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a8a76-118">Example</span></span>

<span data-ttu-id="a8a76-119">En el ejemplo siguiente, se crean y se inicializan un objeto `struct` y un objeto de clase mediante el operador `new` y, después, se les asignan valores.</span><span class="sxs-lookup"><span data-stu-id="a8a76-119">In the following example, a `struct` object and a class object are created and initialized by using the `new` operator and then assigned values.</span></span> <span data-ttu-id="a8a76-120">Se muestran el valor predeterminado y los valores asignados.</span><span class="sxs-lookup"><span data-stu-id="a8a76-120">The default and the assigned values are displayed.</span></span>

[!code-csharp[csrefKeywordsOperator#7](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsOperator/CS/csrefKeywordsOperators.cs#7)]

<span data-ttu-id="a8a76-121">Observe en el ejemplo que el valor predeterminado de una cadena es `null`.</span><span class="sxs-lookup"><span data-stu-id="a8a76-121">Notice in the example that the default value of a string is `null`.</span></span> <span data-ttu-id="a8a76-122">Por lo tanto, no se muestra.</span><span class="sxs-lookup"><span data-stu-id="a8a76-122">Therefore, it is not displayed.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="a8a76-123">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="a8a76-123">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="a8a76-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="a8a76-124">See also</span></span>

- [<span data-ttu-id="a8a76-125">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="a8a76-125">C# Reference</span></span>](../../language-reference/index.md)
- [<span data-ttu-id="a8a76-126">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="a8a76-126">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="a8a76-127">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="a8a76-127">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="a8a76-128">new</span><span class="sxs-lookup"><span data-stu-id="a8a76-128">new</span></span>](new.md)
- [<span data-ttu-id="a8a76-129">Tipos anónimos</span><span class="sxs-lookup"><span data-stu-id="a8a76-129">Anonymous Types</span></span>](../../programming-guide/classes-and-structs/anonymous-types.md)
