---
title: 'Palabra clave base: Referencia de C#'
ms.custom: seodec18
description: Obtenga información sobre la palabra clave base, que se usa para acceder a los miembros de la clase base desde una clase derivada en C#.
ms.date: 07/20/2015
f1_keywords:
- base
- BaseClass.BaseClass
- base_CSharpKeyword
helpviewer_keywords:
- base keyword [C#]
ms.assetid: 8b645dbe-1a33-49b8-8716-1c401f9a5ea5
ms.openlocfilehash: b882a8d1e5979ac184d184be379dd76f7bf3600f
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/19/2019
ms.locfileid: "69602260"
---
# <a name="base-c-reference"></a><span data-ttu-id="1390a-103">base (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="1390a-103">base (C# Reference)</span></span>

<span data-ttu-id="1390a-104">La palabra clave `base` se usa para acceder a los miembros de la clase base desde una clase derivada:</span><span class="sxs-lookup"><span data-stu-id="1390a-104">The `base` keyword is used to access members of the base class from within a derived class:</span></span>

- <span data-ttu-id="1390a-105">Llamar a un método en la clase base que haya sido reemplazado por otro método.</span><span class="sxs-lookup"><span data-stu-id="1390a-105">Call a method on the base class that has been overridden by another method.</span></span>

- <span data-ttu-id="1390a-106">Especificar a qué constructor de clase base se debe llamar cuando se crean instancias de la clase derivada.</span><span class="sxs-lookup"><span data-stu-id="1390a-106">Specify which base-class constructor should be called when creating instances of the derived class.</span></span>

<span data-ttu-id="1390a-107">Solo se permite el acceso a una clase base en un constructor, un método de instancia o un descriptor de acceso de propiedad de instancia.</span><span class="sxs-lookup"><span data-stu-id="1390a-107">A base class access is permitted only in a constructor, an instance method, or an instance property accessor.</span></span>

<span data-ttu-id="1390a-108">Usar la palabra clave `base` desde dentro de un método estático constituye un error.</span><span class="sxs-lookup"><span data-stu-id="1390a-108">It is an error to use the `base` keyword from within a static method.</span></span>

<span data-ttu-id="1390a-109">La clase base a la que se obtiene acceso es la especificada en la declaración de clase.</span><span class="sxs-lookup"><span data-stu-id="1390a-109">The base class that is accessed is the base class specified in the class declaration.</span></span> <span data-ttu-id="1390a-110">Por ejemplo, si especifica `class ClassB : ClassA`, se obtiene acceso a los miembros de ClassA desde ClassB, independientemente de la clase base de ClassA.</span><span class="sxs-lookup"><span data-stu-id="1390a-110">For example, if you specify `class ClassB : ClassA`, the members of ClassA are accessed from ClassB, regardless of the base class of ClassA.</span></span>

## <a name="example"></a><span data-ttu-id="1390a-111">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="1390a-111">Example</span></span>

<span data-ttu-id="1390a-112">En este ejemplo, la clase base, `Person`, y la clase derivada, `Employee`, tienen un método denominado `Getinfo`.</span><span class="sxs-lookup"><span data-stu-id="1390a-112">In this example, both the base class, `Person`, and the derived class, `Employee`, have a method named `Getinfo`.</span></span> <span data-ttu-id="1390a-113">Mediante el uso de la palabra clave `base`, es posible llamar al método `Getinfo` en la clase base desde la clase derivada.</span><span class="sxs-lookup"><span data-stu-id="1390a-113">By using the `base` keyword, it is possible to call the `Getinfo` method on the base class, from within the derived class.</span></span>

[!code-csharp[csrefKeywordsAccess#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsAccess/CS/csrefKeywordsAccess.cs#1)]

<span data-ttu-id="1390a-114">Para ver más ejemplos, consulte [new](new-modifier.md), [virtual](virtual.md) y [override](override.md).</span><span class="sxs-lookup"><span data-stu-id="1390a-114">For additional examples, see [new](new-modifier.md), [virtual](virtual.md), and [override](override.md).</span></span>

## <a name="example"></a><span data-ttu-id="1390a-115">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="1390a-115">Example</span></span>

<span data-ttu-id="1390a-116">En este ejemplo se muestra cómo especificar el constructor de clase base al que se llama al crear instancias de una clase derivada.</span><span class="sxs-lookup"><span data-stu-id="1390a-116">This example shows how to specify the base-class constructor called when creating instances of a derived class.</span></span>

[!code-csharp[csrefKeywordsAccess#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsAccess/CS/csrefKeywordsAccess.cs#2)]

## <a name="c-language-specification"></a><span data-ttu-id="1390a-117">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="1390a-117">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="1390a-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="1390a-118">See also</span></span>

- [<span data-ttu-id="1390a-119">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="1390a-119">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="1390a-120">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="1390a-120">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="1390a-121">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="1390a-121">C# Keywords</span></span>](./index.md)
- [<span data-ttu-id="1390a-122">this</span><span class="sxs-lookup"><span data-stu-id="1390a-122">this</span></span>](./this.md)
