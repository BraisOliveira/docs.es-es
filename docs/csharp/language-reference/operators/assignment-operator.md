---
title: Operador = - Referencia de C#
ms.custom: seodec18
ms.date: 11/26/2018
f1_keywords:
- =_CSharpKeyword
helpviewer_keywords:
- = operator [C#]
ms.assetid: d802a6d5-32f0-42b8-b180-12f5a081bfc1
ms.openlocfilehash: 85182acb84ea79cb00a9edb315c3954f440305f4
ms.sourcegitcommit: 904b98d8d706f0e2d5ceaa00ce17ffbd92adfb88
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/07/2019
ms.locfileid: "66758355"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="c68b9-102">Operador = (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="c68b9-102">= Operator (C# Reference)</span></span>

<span data-ttu-id="c68b9-103">El operador de asignación `=` asigna el valor de su operando de la derecha a una variable, una [propiedad](../../programming-guide/classes-and-structs/properties.md) o un elemento de [indizador](../../../csharp/programming-guide/indexers/index.md) proporcionado por el operando de la izquierda.</span><span class="sxs-lookup"><span data-stu-id="c68b9-103">The assignment operator `=` assigns the value of its right-hand operand to a variable, a [property](../../programming-guide/classes-and-structs/properties.md), or an [indexer](../../../csharp/programming-guide/indexers/index.md) element given by its left-hand operand.</span></span> <span data-ttu-id="c68b9-104">El resultado de una expresión de asignación es el valor asignado al operando izquierdo.</span><span class="sxs-lookup"><span data-stu-id="c68b9-104">The result of an assignment expression is the value assigned to the left-hand operand.</span></span> <span data-ttu-id="c68b9-105">El tipo del operando de la derecha debe ser el mismo que el del operando de la izquierda o debe poder convertirse implícitamente en él.</span><span class="sxs-lookup"><span data-stu-id="c68b9-105">The type of the right-hand operand must be the same as the type of the left-hand operand or implicitly convertible to it.</span></span>

<span data-ttu-id="c68b9-106">El operador de asignación es asociativo a la derecha, es decir, una expresión de la forma</span><span class="sxs-lookup"><span data-stu-id="c68b9-106">The assignment operator is right-associative, that is, an expression of the form</span></span>

```csharp
a = b = c
```

<span data-ttu-id="c68b9-107">se evalúa como</span><span class="sxs-lookup"><span data-stu-id="c68b9-107">is evaluated as</span></span>

```csharp
a = (b = c)
```

<span data-ttu-id="c68b9-108">El ejemplo siguiente muestra el uso del operador de asignación para asignar valores a una variable local, una propiedad y un elemento de indizador:</span><span class="sxs-lookup"><span data-stu-id="c68b9-108">The following example demonstrates the usage of the assignment operator to assign values to a local variable, a property, and an indexer element:</span></span>

[!code-csharp-interactive[assignment operator](~/samples/csharp/language-reference/operators/AssignmentExamples.cs#Assignments)]

## <a name="ref-assignment-operator"></a><span data-ttu-id="c68b9-109">Operador de asignación ref</span><span class="sxs-lookup"><span data-stu-id="c68b9-109">ref assignment operator</span></span>

<span data-ttu-id="c68b9-110">A partir C# 7.3, puede usar el operador de asignación ref `= ref` para reasignar una variable [local de tipo ref](../keywords/ref.md#ref-locals) o [local de tipo ref readonly](../keywords/ref.md#ref-readonly-locals).</span><span class="sxs-lookup"><span data-stu-id="c68b9-110">Beginning with C# 7.3, you can use the ref assignment operator `= ref` to reassign a [ref local](../keywords/ref.md#ref-locals) or [ref readonly local](../keywords/ref.md#ref-readonly-locals) variable.</span></span> <span data-ttu-id="c68b9-111">En el siguiente ejemplo se muestra el uso del operador de asignación ref:</span><span class="sxs-lookup"><span data-stu-id="c68b9-111">The following example demonstrates the usage of the ref assignment operator:</span></span>

[!code-csharp[ref assignment operator](~/samples/csharp/language-reference/operators/AssignmentExamples.cs#RefAssignment)]

<span data-ttu-id="c68b9-112">En el caso del operador de asignación ref, el tipo del operando de la izquierda y el operando de la derecha debe ser los mismos.</span><span class="sxs-lookup"><span data-stu-id="c68b9-112">In the case of the ref assignment operator, the type of the left operand and the right operand must be the same.</span></span>

<span data-ttu-id="c68b9-113">Para más información, vea la [nota de propuesta de características](../../../../_csharplang/proposals/csharp-7.3/ref-local-reassignment.md).</span><span class="sxs-lookup"><span data-stu-id="c68b9-113">For more information, see the [feature proposal note](../../../../_csharplang/proposals/csharp-7.3/ref-local-reassignment.md).</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="c68b9-114">Posibilidad de sobrecarga del operador</span><span class="sxs-lookup"><span data-stu-id="c68b9-114">Operator overloadability</span></span>

<span data-ttu-id="c68b9-115">Un tipo definido por el usuario no puede sobrecargar el operador de asignación.</span><span class="sxs-lookup"><span data-stu-id="c68b9-115">A user-defined type cannot overload the assignment operator.</span></span> <span data-ttu-id="c68b9-116">Sin embargo, un tipo definido por el usuario puede definir una conversión implícita a otro tipo.</span><span class="sxs-lookup"><span data-stu-id="c68b9-116">However, a user-defined type can define an implicit conversion to another type.</span></span> <span data-ttu-id="c68b9-117">De este modo, el valor de un tipo definido por el usuario puede asignarse a una variable, una propiedad o un elemento de indizador de otro tipo.</span><span class="sxs-lookup"><span data-stu-id="c68b9-117">That way, the value of a user-defined type can be assigned to a variable, a property, or an indexer element of another type.</span></span> <span data-ttu-id="c68b9-118">Para más información, consulte el artículo sobre la palabra clave [implicit](../keywords/implicit.md).</span><span class="sxs-lookup"><span data-stu-id="c68b9-118">For more information, see the [implicit](../keywords/implicit.md) keyword article.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="c68b9-119">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="c68b9-119">C# language specification</span></span>

<span data-ttu-id="c68b9-120">Para más información, vea la sección [Asignación simple](~/_csharplang/spec/expressions.md#simple-assignment) de la [Especificación del lenguaje C#](../language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="c68b9-120">For more information, see the [Simple assignment](~/_csharplang/spec/expressions.md#simple-assignment) section of the [C# language specification](../language-specification/index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="c68b9-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="c68b9-121">See also</span></span>

- [<span data-ttu-id="c68b9-122">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="c68b9-122">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="c68b9-123">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="c68b9-123">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="c68b9-124">Operadores de C#</span><span class="sxs-lookup"><span data-stu-id="c68b9-124">C# Operators</span></span>](index.md)
- [<span data-ttu-id="c68b9-125">ref (palabra clave)</span><span class="sxs-lookup"><span data-stu-id="c68b9-125">ref keyword</span></span>](../keywords/ref.md)
