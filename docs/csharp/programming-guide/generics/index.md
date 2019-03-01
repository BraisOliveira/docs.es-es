---
title: 'Genéricos: Guía de programación de C#'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
  - 'C# language, generics'
  - 'generics [C#]'
ms.assetid: 75ea8509-a4ea-4e7a-a2b3-cf72482e9282
---
# <a name="generics-c-programming-guide"></a><span data-ttu-id="5d80b-102">Genéricos (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="5d80b-102">Generics (C# Programming Guide)</span></span>
<span data-ttu-id="5d80b-103">Los genéricos se han agregado a la versión 2.0 del lenguaje C# y Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="5d80b-103">Generics were added to version 2.0 of the C# language and the common language runtime (CLR).</span></span> <span data-ttu-id="5d80b-104">Los genéricos introducen en .NET Framework el concepto de parámetros de tipo, lo que le permite diseñar clases y métodos que aplazan la especificación de uno o varios tipos hasta que el código de cliente declare y cree una instancia de la clase o el método.</span><span class="sxs-lookup"><span data-stu-id="5d80b-104">Generics introduce to the .NET Framework the concept of type parameters, which make it possible to design classes and methods that defer the specification of one or more types until the class or method is declared and instantiated by client code.</span></span> <span data-ttu-id="5d80b-105">Por ejemplo, al usar un parámetro de tipo genérico T puede escribir una clase única que otro código de cliente puede usar sin incurrir en el costo o riesgo de conversiones en tiempo de ejecución u operaciones de conversión boxing, como se muestra aquí:</span><span class="sxs-lookup"><span data-stu-id="5d80b-105">For example, by using a generic type parameter T you can write a single class that other client code can use without incurring the cost or risk of runtime casts or boxing operations, as shown here:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#1)]  
  
## <a name="generics-overview"></a><span data-ttu-id="5d80b-106">Información general sobre los genéricos</span><span class="sxs-lookup"><span data-stu-id="5d80b-106">Generics Overview</span></span>  
  
-   <span data-ttu-id="5d80b-107">Use tipos genéricos para maximizar la reutilización del código, la seguridad de tipos y el rendimiento.</span><span class="sxs-lookup"><span data-stu-id="5d80b-107">Use generic types to maximize code reuse, type safety, and performance.</span></span>  
  
-   <span data-ttu-id="5d80b-108">El uso más común de los genéricos es crear clases de colección.</span><span class="sxs-lookup"><span data-stu-id="5d80b-108">The most common use of generics is to create collection classes.</span></span>  
  
-   <span data-ttu-id="5d80b-109">La biblioteca de clases .NET Framework contiene varias clases de colección genéricas nuevas en el espacio de nombres <xref:System.Collections.Generic>.</span><span class="sxs-lookup"><span data-stu-id="5d80b-109">The .NET Framework class library contains several new generic collection classes in the <xref:System.Collections.Generic> namespace.</span></span> <span data-ttu-id="5d80b-110">Estas se deberían usar siempre que sea posible en lugar de clases como <xref:System.Collections.ArrayList> en el espacio de nombres <xref:System.Collections>.</span><span class="sxs-lookup"><span data-stu-id="5d80b-110">These should be used whenever possible instead of classes such as <xref:System.Collections.ArrayList> in the <xref:System.Collections> namespace.</span></span>  
  
-   <span data-ttu-id="5d80b-111">Puede crear sus propias interfaces, clases, métodos, eventos y delegados genéricos.</span><span class="sxs-lookup"><span data-stu-id="5d80b-111">You can create your own generic interfaces, classes, methods, events and delegates.</span></span>  
  
-   <span data-ttu-id="5d80b-112">Puede limitar las clases genéricas para habilitar el acceso a métodos en tipos de datos determinados.</span><span class="sxs-lookup"><span data-stu-id="5d80b-112">Generic classes may be constrained to enable access to methods on particular data types.</span></span>  
  
-   <span data-ttu-id="5d80b-113">Puede obtener información sobre los tipos que se usan en un tipo de datos genérico en tiempo de ejecución mediante la reflexión.</span><span class="sxs-lookup"><span data-stu-id="5d80b-113">Information on the types that are used in a generic data type may be obtained at run-time by using reflection.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="5d80b-114">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="5d80b-114">Related Sections</span></span>  
 <span data-ttu-id="5d80b-115">Para obtener más información:</span><span class="sxs-lookup"><span data-stu-id="5d80b-115">For more information:</span></span>  
  
-   [<span data-ttu-id="5d80b-116">Introducción a los genéricos</span><span class="sxs-lookup"><span data-stu-id="5d80b-116">Introduction to Generics</span></span>](../../../csharp/programming-guide/generics/introduction-to-generics.md)  
  
-   [<span data-ttu-id="5d80b-117">Ventajas de los genéricos</span><span class="sxs-lookup"><span data-stu-id="5d80b-117">Benefits of Generics</span></span>](../../../csharp/programming-guide/generics/benefits-of-generics.md)  
  
-   [<span data-ttu-id="5d80b-118">Parámetros de tipo genérico</span><span class="sxs-lookup"><span data-stu-id="5d80b-118">Generic Type Parameters</span></span>](../../../csharp/programming-guide/generics/generic-type-parameters.md)  
  
-   [<span data-ttu-id="5d80b-119">Restricciones de tipos de parámetros</span><span class="sxs-lookup"><span data-stu-id="5d80b-119">Constraints on Type Parameters</span></span>](../../../csharp/programming-guide/generics/constraints-on-type-parameters.md)  
  
-   [<span data-ttu-id="5d80b-120">Clases genéricas</span><span class="sxs-lookup"><span data-stu-id="5d80b-120">Generic Classes</span></span>](../../../csharp/programming-guide/generics/generic-classes.md)  
  
-   [<span data-ttu-id="5d80b-121">Interfaces genéricas</span><span class="sxs-lookup"><span data-stu-id="5d80b-121">Generic Interfaces</span></span>](../../../csharp/programming-guide/generics/generic-interfaces.md)  
  
-   [<span data-ttu-id="5d80b-122">Métodos genéricos</span><span class="sxs-lookup"><span data-stu-id="5d80b-122">Generic Methods</span></span>](../../../csharp/programming-guide/generics/generic-methods.md)  
  
-   [<span data-ttu-id="5d80b-123">Delegados genéricos</span><span class="sxs-lookup"><span data-stu-id="5d80b-123">Generic Delegates</span></span>](../../../csharp/programming-guide/generics/generic-delegates.md)  
  
-   [<span data-ttu-id="5d80b-124">Diferencias entre plantillas de C++ y tipos genéricos de C#</span><span class="sxs-lookup"><span data-stu-id="5d80b-124">Differences Between C++ Templates and C# Generics</span></span>](../../../csharp/programming-guide/generics/differences-between-cpp-templates-and-csharp-generics.md)  
  
-   [<span data-ttu-id="5d80b-125">Genéricos y reflexión</span><span class="sxs-lookup"><span data-stu-id="5d80b-125">Generics and Reflection</span></span>](../../../csharp/programming-guide/generics/generics-and-reflection.md)  
  
-   [<span data-ttu-id="5d80b-126">Genéricos en el motor en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="5d80b-126">Generics in the Run Time</span></span>](../../../csharp/programming-guide/generics/generics-in-the-run-time.md)  
  
## <a name="c-language-specification"></a><span data-ttu-id="5d80b-127">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="5d80b-127">C# Language Specification</span></span>  
 <span data-ttu-id="5d80b-128">Para obtener más información, consulte la [Especificación del lenguaje C#](~/_csharplang/spec/types.md#constructed-types).</span><span class="sxs-lookup"><span data-stu-id="5d80b-128">For more information, see the [C# Language Specification](~/_csharplang/spec/types.md#constructed-types).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5d80b-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="5d80b-129">See also</span></span>

- <xref:System.Collections.Generic>
- [<span data-ttu-id="5d80b-130">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="5d80b-130">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="5d80b-131">Tipos</span><span class="sxs-lookup"><span data-stu-id="5d80b-131">Types</span></span>](../../../csharp/programming-guide/types/index.md)
- [<span data-ttu-id="5d80b-132">\<typeparam></span><span class="sxs-lookup"><span data-stu-id="5d80b-132">\<typeparam></span></span>](../../../csharp/programming-guide/xmldoc/typeparam.md)
- [<span data-ttu-id="5d80b-133">\<typeparamref></span><span class="sxs-lookup"><span data-stu-id="5d80b-133">\<typeparamref></span></span>](../../../csharp/programming-guide/xmldoc/typeparamref.md)
- [<span data-ttu-id="5d80b-134">Elementos genéricos en .NET</span><span class="sxs-lookup"><span data-stu-id="5d80b-134">Generics in .NET</span></span>](../../../standard/generics/index.md)
