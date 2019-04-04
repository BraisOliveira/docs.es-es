---
title: 'Indexadores: Guía de programación de C#'
ms.custom: seodec18
ms.date: 03/10/2017
f1_keywords:
- cs.indexers
helpviewer_keywords:
- indexers [C#]
- C# language, indexers
ms.assetid: 022cd27d-d5e0-4cfe-8b97-dc018cc3355d
ms.openlocfilehash: 5ab0a5e524979110c355391cf800cc82e6d6244f
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2019
ms.locfileid: "57365027"
---
# <a name="indexers-c-programming-guide"></a><span data-ttu-id="86431-102">Indizadores (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="86431-102">Indexers (C# Programming Guide)</span></span>

<span data-ttu-id="86431-103">Los indizadores permiten indizar las instancias de una clase o struct como matrices.</span><span class="sxs-lookup"><span data-stu-id="86431-103">Indexers allow instances of a class or struct to be indexed just like arrays.</span></span> <span data-ttu-id="86431-104">El valor indizado se puede establecer o recuperar sin especificar explícitamente un miembro de tipo o de instancia.</span><span class="sxs-lookup"><span data-stu-id="86431-104">The indexed value can be set or retrieved without explicitly specifying a type or instance member.</span></span> <span data-ttu-id="86431-105">Son similares a [propiedades](../../../csharp/programming-guide/classes-and-structs/properties.md), excepto en que sus descriptores de acceso usan parámetros.</span><span class="sxs-lookup"><span data-stu-id="86431-105">Indexers resemble [properties](../../../csharp/programming-guide/classes-and-structs/properties.md) except that their accessors take parameters.</span></span>  
 
 <span data-ttu-id="86431-106">En el ejemplo siguiente se define una clase genérica con métodos de descriptor de acceso [get](../../../csharp/language-reference/keywords/get.md) y [set](../../../csharp/language-reference/keywords/set.md) sencillos para asignar y recuperar valores.</span><span class="sxs-lookup"><span data-stu-id="86431-106">The following example defines a generic class with simple [get](../../../csharp/language-reference/keywords/get.md) and [set](../../../csharp/language-reference/keywords/set.md) accessor methods to assign and retrieve values.</span></span> <span data-ttu-id="86431-107">La clase `Program` crea una instancia de esta clase para almacenar cadenas.</span><span class="sxs-lookup"><span data-stu-id="86431-107">The `Program` class creates an instance of this class for storing strings.</span></span>  
  
 [!code-csharp[indexers#1](../../../../samples/snippets/csharp/programming-guide/indexers/indexer-1.cs)]  
  
> [!NOTE]
>  <span data-ttu-id="86431-108">Para obtener más ejemplos, vea [Secciones relacionadas](../../../csharp/programming-guide/indexers/index.md#BKMK_RelatedSections).</span><span class="sxs-lookup"><span data-stu-id="86431-108">For more examples, see [Related Sections](../../../csharp/programming-guide/indexers/index.md#BKMK_RelatedSections).</span></span>  
  
## <a name="expression-body-definitions"></a><span data-ttu-id="86431-109">Definiciones de cuerpos de expresión</span><span class="sxs-lookup"><span data-stu-id="86431-109">Expression Body Definitions</span></span>  
 
<span data-ttu-id="86431-110">Es habitual que un descriptor de acceso get o set de un indizador conste de una única instrucción que devuelve o establece un valor.</span><span class="sxs-lookup"><span data-stu-id="86431-110">It is common for an indexer's get or set accessor to consist of a single statement that either returns or sets a value.</span></span> <span data-ttu-id="86431-111">Los miembros con forma de expresión proporcionan una sintaxis simplificada para admitir este escenario.</span><span class="sxs-lookup"><span data-stu-id="86431-111">Expression-bodied members provide a simplified syntax to support this scenario.</span></span> <span data-ttu-id="86431-112">A partir de C# 6, un indizador de solo lectura puede implementarse como un miembro con forma de expresión, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="86431-112">Starting with C# 6, a read-only indexer can be implemented as an expression-bodied member, as the following example shows.</span></span>

[!code-csharp[indexers#2](../../../../samples/snippets/csharp/programming-guide/indexers/indexer-2.cs)]  

<span data-ttu-id="86431-113">Tenga en cuenta que `=>` presenta el cuerpo de la expresión y que la palabra clave `get` no se utiliza.</span><span class="sxs-lookup"><span data-stu-id="86431-113">Note that `=>` introduces the expression body, and that the `get` keyword is not used.</span></span> 

<span data-ttu-id="86431-114">A partir de C# 7.0, los descriptores de acceso get y set se pueden implementar como miembros con forma de expresión.</span><span class="sxs-lookup"><span data-stu-id="86431-114">Starting with C# 7.0, both the get and set accessor can be an implemented as expression-bodied members.</span></span> <span data-ttu-id="86431-115">En este caso, sí deben utilizarse las palabras clave `get` y `set`.</span><span class="sxs-lookup"><span data-stu-id="86431-115">In this case, both `get` and `set` keywords must be used.</span></span> <span data-ttu-id="86431-116">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="86431-116">For example:</span></span>

[!code-csharp[indexers#3](../../../../samples/snippets/csharp/programming-guide/indexers/indexer-3.cs)]  
  
## <a name="indexers-overview"></a><span data-ttu-id="86431-117">Información general sobre los indizadores</span><span class="sxs-lookup"><span data-stu-id="86431-117">Indexers Overview</span></span>  
  
-   <span data-ttu-id="86431-118">Los indizadores permiten indizar objetos de manera similar a como se hace con las matrices.</span><span class="sxs-lookup"><span data-stu-id="86431-118">Indexers enable objects to be indexed in a similar manner to arrays.</span></span>  
  
-   <span data-ttu-id="86431-119">Un descriptor de acceso `get` devuelve un valor.</span><span class="sxs-lookup"><span data-stu-id="86431-119">A `get` accessor returns a value.</span></span> <span data-ttu-id="86431-120">Un descriptor de acceso `set` asigna un valor.</span><span class="sxs-lookup"><span data-stu-id="86431-120">A `set` accessor assigns a value.</span></span>  
  
-   <span data-ttu-id="86431-121">La palabra clave [this](../../../csharp/language-reference/keywords/this.md) se usa para definir los indizadores.</span><span class="sxs-lookup"><span data-stu-id="86431-121">The [this](../../../csharp/language-reference/keywords/this.md) keyword is used to define the indexer.</span></span>  
  
-   <span data-ttu-id="86431-122">La palabra clave [value](../../../csharp/language-reference/keywords/value.md) se usa para definir el valor asignado por el indizador `set`.</span><span class="sxs-lookup"><span data-stu-id="86431-122">The [value](../../../csharp/language-reference/keywords/value.md) keyword is used to define the value being assigned by the `set` indexer.</span></span>  
  
-   <span data-ttu-id="86431-123">Los indizadores no tienen que ser indizados por un valor entero; depende de usted cómo definir el mecanismo de búsqueda concreto.</span><span class="sxs-lookup"><span data-stu-id="86431-123">Indexers do not have to be indexed by an integer value; it is up to you how to define the specific look-up mechanism.</span></span>  
  
-   <span data-ttu-id="86431-124">Los indizadores se pueden sobrecargar.</span><span class="sxs-lookup"><span data-stu-id="86431-124">Indexers can be overloaded.</span></span>  
  
-   <span data-ttu-id="86431-125">Los indizadores pueden tener más de un parámetro formal, por ejemplo, al tener acceso a una matriz bidimensional.</span><span class="sxs-lookup"><span data-stu-id="86431-125">Indexers can have more than one formal parameter, for example, when accessing a two-dimensional array.</span></span>  
  
## <a name="BKMK_RelatedSections"></a> <span data-ttu-id="86431-126">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="86431-126">Related Sections</span></span>  
  
-   [<span data-ttu-id="86431-127">Utilizar indizadores</span><span class="sxs-lookup"><span data-stu-id="86431-127">Using Indexers</span></span>](../../../csharp/programming-guide/indexers/using-indexers.md)  
  
-   [<span data-ttu-id="86431-128">Indizadores en Interfaces</span><span class="sxs-lookup"><span data-stu-id="86431-128">Indexers in Interfaces</span></span>](../../../csharp/programming-guide/indexers/indexers-in-interfaces.md)  
  
-   [<span data-ttu-id="86431-129">Comparación entre propiedades e indizadores</span><span class="sxs-lookup"><span data-stu-id="86431-129">Comparison Between Properties and Indexers</span></span>](../../../csharp/programming-guide/indexers/comparison-between-properties-and-indexers.md)  
  
-   [<span data-ttu-id="86431-130">Restringir la accesibilidad del descriptor de acceso</span><span class="sxs-lookup"><span data-stu-id="86431-130">Restricting Accessor Accessibility</span></span>](../../../csharp/programming-guide/classes-and-structs/restricting-accessor-accessibility.md)  
  
## <a name="c-language-specification"></a><span data-ttu-id="86431-131">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="86431-131">C# Language Specification</span></span>  

<span data-ttu-id="86431-132">Para obtener más información, vea la sección [Indizadores](~/_csharplang/spec/classes.md#indexers) de [Especificación del lenguaje C#](../../language-reference/language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="86431-132">For more information, see [Indexers](~/_csharplang/spec/classes.md#indexers) in the [C# Language Specification](../../language-reference/language-specification/index.md).</span></span> <span data-ttu-id="86431-133">La especificación del lenguaje es la fuente definitiva de la sintaxis y el uso de C#.</span><span class="sxs-lookup"><span data-stu-id="86431-133">The language specification is the definitive source for C# syntax and usage.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="86431-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="86431-134">See also</span></span>

- [<span data-ttu-id="86431-135">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="86431-135">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="86431-136">Propiedades</span><span class="sxs-lookup"><span data-stu-id="86431-136">Properties</span></span>](../../../csharp/programming-guide/classes-and-structs/properties.md)
