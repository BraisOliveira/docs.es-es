---
title: 'where (restricción de tipo genérico): Referencia de C#'
ms.custom: seodec18
ms.date: 04/12/2018
f1_keywords:
- whereconstraint
- whereconstraint_CSharpKeyword
helpviewer_keywords:
- where (generic type constraint) [C#]
ms.openlocfilehash: bccc22f5362b22540dadf08e6b21a07cbc578327
ms.sourcegitcommit: 1e7ac70be1b4d89708c0d9552897515f2cbf52c4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2019
ms.locfileid: "68433863"
---
# <a name="where-generic-type-constraint-c-reference"></a><span data-ttu-id="10720-102">where (restricción de tipo genérico) (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="10720-102">where (generic type constraint) (C# Reference)</span></span>

<span data-ttu-id="10720-103">La cláusula `where` en una definición genérica especifica restricciones en los tipos que se usan como argumentos para los parámetros de tipo en un tipo genérico, método, delegado o función local.</span><span class="sxs-lookup"><span data-stu-id="10720-103">The `where` clause in a generic definition specifies constraints on the types that are used as arguments for type parameters in a generic type, method, delegate, or local function.</span></span> <span data-ttu-id="10720-104">Las restricciones pueden especificar interfaces o clases base, o bien requerir que un tipo genérico sea una referencia, un valor o un tipo no administrado.</span><span class="sxs-lookup"><span data-stu-id="10720-104">Constraints can specify interfaces, base classes, or require a generic type to be a reference, value or unmanaged type.</span></span> <span data-ttu-id="10720-105">Declaran las funcionalidades que debe poseer el argumento de tipo.</span><span class="sxs-lookup"><span data-stu-id="10720-105">They declare capabilities that the type argument must possess.</span></span>

<span data-ttu-id="10720-106">Por ejemplo, se puede declarar una clase genérica, `MyGenericClass`, de modo que el parámetro de tipo `T` implemente la interfaz <xref:System.IComparable%601>:</span><span class="sxs-lookup"><span data-stu-id="10720-106">For example, you can declare a generic class, `MyGenericClass`, such that the type parameter `T` implements the <xref:System.IComparable%601> interface:</span></span>

[!code-csharp[using an interface constraint](../../../../samples/snippets/csharp/keywords/GenericWhereConstraints.cs#1)]

> [!NOTE]
> <span data-ttu-id="10720-107">Para obtener más información sobre la cláusula where en una expresión de consulta, vea [where (Cláusula)](where-clause.md).</span><span class="sxs-lookup"><span data-stu-id="10720-107">For more information on the where clause in a query expression, see [where clause](where-clause.md).</span></span>

<span data-ttu-id="10720-108">La cláusula `where` también puede incluir una restricción de clase base.</span><span class="sxs-lookup"><span data-stu-id="10720-108">The `where` clause can also include a base class constraint.</span></span> <span data-ttu-id="10720-109">La restricción de clase base indica que un tipo que se usará como argumento de tipo para ese tipo genérico tiene la clase especificada como clase base (o es la clase base) para que se use como argumento de tipo para ese tipo genérico.</span><span class="sxs-lookup"><span data-stu-id="10720-109">The base class constraint states that a type to be used as a type argument for that generic type has the specified class as a base class (or is that base class) to be used as a type argument for that generic type.</span></span> <span data-ttu-id="10720-110">Si se usa la restricción de clase base, debe aparecer antes que cualquier otra restricción de ese parámetro de tipo.</span><span class="sxs-lookup"><span data-stu-id="10720-110">If the base class constraint is used, it must appear before any other constraints on that type parameter.</span></span> <span data-ttu-id="10720-111">Algunos tipos no están permitidos como restricción de clase base: <xref:System.Object>, <xref:System.Array> y <xref:System.ValueType>.</span><span class="sxs-lookup"><span data-stu-id="10720-111">Some types are disallowed as a base class constraint: <xref:System.Object>, <xref:System.Array>, and <xref:System.ValueType>.</span></span> <span data-ttu-id="10720-112">Antes de C# 7.3, tampoco se permitían <xref:System.Enum>, <xref:System.Delegate> y <xref:System.MulticastDelegate> como restricciones de clase base.</span><span class="sxs-lookup"><span data-stu-id="10720-112">Prior to C# 7.3, <xref:System.Enum>, <xref:System.Delegate>, and <xref:System.MulticastDelegate> were also disallowed as base class constraints.</span></span> <span data-ttu-id="10720-113">En el ejemplo siguiente se muestran los tipos que ahora se pueden especificar como clase base:</span><span class="sxs-lookup"><span data-stu-id="10720-113">The following example shows the types that can now be specified as a base class:</span></span>

[!code-csharp[using an interface constraint](../../../../samples/snippets/csharp/keywords/GenericWhereConstraints.cs#2)]

<span data-ttu-id="10720-114">La cláusula `where` puede especificar que el tipo es `class` o `struct`.</span><span class="sxs-lookup"><span data-stu-id="10720-114">The `where` clause can specify that the type is a `class` or a `struct`.</span></span> <span data-ttu-id="10720-115">La restricción `struct` elimina la necesidad de especificar una restricción de clase base de `System.ValueType`.</span><span class="sxs-lookup"><span data-stu-id="10720-115">The `struct` constraint removes the need to specify a base class constraint of `System.ValueType`.</span></span> <span data-ttu-id="10720-116">El tipo `System.ValueType` no se puede usar como restricción de clase base.</span><span class="sxs-lookup"><span data-stu-id="10720-116">The `System.ValueType` type may not be used as a base class constraint.</span></span> <span data-ttu-id="10720-117">En el ejemplo siguiente se muestran las restricciones `class` y `struct`:</span><span class="sxs-lookup"><span data-stu-id="10720-117">The following example shows both the `class` and `struct` constraints:</span></span>

[!code-csharp[using the class and struct constraints](../../../../samples/snippets/csharp/keywords/GenericWhereConstraints.cs#3)]

<span data-ttu-id="10720-118">La cláusula `where` también podría incluir una restricción `unmanaged`.</span><span class="sxs-lookup"><span data-stu-id="10720-118">The `where` clause may also include an `unmanaged` constraint.</span></span> <span data-ttu-id="10720-119">La restricción `unmanaged` limita el parámetro de tipo a los tipos conocidos como [tipos no administrados](../builtin-types/unmanaged-types.md).</span><span class="sxs-lookup"><span data-stu-id="10720-119">The `unmanaged` constraint limits the type parameter to types known as [unmanaged types](../builtin-types/unmanaged-types.md).</span></span> <span data-ttu-id="10720-120">La restricción `unmanaged` hace que sea más fácil escribir código de interoperabilidad de bajo nivel en C#.</span><span class="sxs-lookup"><span data-stu-id="10720-120">The `unmanaged` constraint makes it easier to write low-level interop code in C#.</span></span> <span data-ttu-id="10720-121">Esta restricción habilita las rutinas reutilizables en todos los tipos no administrados.</span><span class="sxs-lookup"><span data-stu-id="10720-121">This constraint enables reusable routines across all unmanaged types.</span></span> <span data-ttu-id="10720-122">La restricción `unmanaged` no se puede combinar con las restricciones `class` o `struct`.</span><span class="sxs-lookup"><span data-stu-id="10720-122">The `unmanaged` constraint can't be combined with the `class` or `struct` constraint.</span></span> <span data-ttu-id="10720-123">La restricción `unmanaged` exige que el tipo sea `struct`:</span><span class="sxs-lookup"><span data-stu-id="10720-123">The `unmanaged` constraint enforces that the type must be a `struct`:</span></span>

[!code-csharp[using the unmanaged constraint](../../../../samples/snippets/csharp/keywords/GenericWhereConstraints.cs#4)]

<span data-ttu-id="10720-124">La cláusula `where` también podría incluir una restricción de constructor, `new()`.</span><span class="sxs-lookup"><span data-stu-id="10720-124">The `where` clause may also include a constructor constraint, `new()`.</span></span> <span data-ttu-id="10720-125">Esta restricción hace posible crear una instancia de un parámetro de tipo con el operador `new`.</span><span class="sxs-lookup"><span data-stu-id="10720-125">That constraint makes it possible to create an instance of a type parameter using the `new` operator.</span></span> <span data-ttu-id="10720-126">La [restricción new()](new-constraint.md) permite que el compilador sepa que cualquier argumento de tipo especificado debe tener accesible un constructor sin parámetros o el constructor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="10720-126">The [new() Constraint](new-constraint.md) lets the compiler know that any type argument supplied must have an accessible parameterless--or default-- constructor.</span></span> <span data-ttu-id="10720-127">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="10720-127">For example:</span></span>

[!code-csharp[using the new constraint](../../../../samples/snippets/csharp/keywords/GenericWhereConstraints.cs#5)]

<span data-ttu-id="10720-128">La restricción `new()` aparece en último lugar en la cláusula `where`.</span><span class="sxs-lookup"><span data-stu-id="10720-128">The `new()` constraint appears last in the `where` clause.</span></span> <span data-ttu-id="10720-129">La restricción `new()` no se puede combinar con las restricciones `struct` o `unmanaged`.</span><span class="sxs-lookup"><span data-stu-id="10720-129">The `new()` constraint can't be combined with the `struct` or `unmanaged` constraints.</span></span> <span data-ttu-id="10720-130">Todos los tipos que cumplan esas restricciones deben tener un constructor sin parámetros accesible, lo que hace que la restricción `new()` sea redundante.</span><span class="sxs-lookup"><span data-stu-id="10720-130">All types satisfying those constraints must have an accessible parameterless constructor, making the `new()` constraint redundant.</span></span>

<span data-ttu-id="10720-131">Con varios parámetros de tipo, use una cláusula `where` para cada parámetro de tipo, por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="10720-131">With multiple type parameters, use one `where` clause for each type parameter, for example:</span></span>

[!code-csharp[using multiple where constraints](../../../../samples/snippets/csharp/keywords/GenericWhereConstraints.cs#6)]

<span data-ttu-id="10720-132">También puede asociar restricciones a parámetros de tipo de métodos genéricos, como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="10720-132">You can also attach constraints to type parameters of generic methods, as shown in the following example:</span></span>

[!code-csharp[where constraints with generic methods](../../../../samples/snippets/csharp/keywords/GenericWhereConstraints.cs#7)]

<span data-ttu-id="10720-133">Observe que la sintaxis para describir las restricciones de parámetro de tipo en delegados es igual que la de métodos:</span><span class="sxs-lookup"><span data-stu-id="10720-133">Notice that the syntax to describe type parameter constraints on delegates is the same as that of methods:</span></span>

[!code-csharp[where constraints with generic methods](../../../../samples/snippets/csharp/keywords/GenericWhereConstraints.cs#8)]

<span data-ttu-id="10720-134">Para obtener información sobre los delegados genéricos, vea [Delegados genéricos](../../../csharp/programming-guide/generics/generic-delegates.md).</span><span class="sxs-lookup"><span data-stu-id="10720-134">For information on generic delegates, see [Generic Delegates](../../../csharp/programming-guide/generics/generic-delegates.md).</span></span>

<span data-ttu-id="10720-135">Para obtener más información sobre la sintaxis y el uso de restricciones, vea [Restricciones de tipos de parámetros](../../../csharp/programming-guide/generics/constraints-on-type-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="10720-135">For details on the syntax and use of constraints, see [Constraints on Type Parameters](../../../csharp/programming-guide/generics/constraints-on-type-parameters.md).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="10720-136">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="10720-136">C# language specification</span></span>

 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="10720-137">Vea también</span><span class="sxs-lookup"><span data-stu-id="10720-137">See also</span></span>

- [<span data-ttu-id="10720-138">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="10720-138">C# Reference</span></span>](../../../csharp/language-reference/index.md)
- [<span data-ttu-id="10720-139">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="10720-139">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="10720-140">Introducción a los genéricos</span><span class="sxs-lookup"><span data-stu-id="10720-140">Introduction to Generics</span></span>](../../../csharp/programming-guide/generics/index.md)
- [<span data-ttu-id="10720-141">new (restricción)</span><span class="sxs-lookup"><span data-stu-id="10720-141">new Constraint</span></span>](../../../csharp/language-reference/keywords/new-constraint.md)
- [<span data-ttu-id="10720-142">Restricciones de tipos de parámetros</span><span class="sxs-lookup"><span data-stu-id="10720-142">Constraints on Type Parameters</span></span>](../../../csharp/programming-guide/generics/constraints-on-type-parameters.md)
