---
title: 'Espacios de nombres: Guía de programación de C#'
ms.custom: seodec18
ms.date: 08/21/2018
helpviewer_keywords:
- C# language, namespaces
- namespaces [C#]
ms.assetid: b1c4ab46-3fad-4ffa-9deb-dd50a2d8c65a
ms.openlocfilehash: 79b7057b1f6a9cdba2215124160b28efb9a1c0be
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/30/2019
ms.locfileid: "68629521"
---
# <a name="namespaces-c-programming-guide"></a><span data-ttu-id="168f0-102">Espacios de nombres (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="168f0-102">Namespaces (C# Programming Guide)</span></span>

<span data-ttu-id="168f0-103">Los espacios de nombres se usan mucho en programación de C# de dos maneras.</span><span class="sxs-lookup"><span data-stu-id="168f0-103">Namespaces are heavily used in C# programming in two ways.</span></span> <span data-ttu-id="168f0-104">En primer lugar, .NET Framework usa espacios de nombres para organizar sus clases, de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="168f0-104">First, the .NET Framework uses namespaces to organize its many classes, as follows:</span></span>  
  
 [!code-csharp[csProgGuide#22](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuide/CS/progGuide.cs#22)]  
  
<span data-ttu-id="168f0-105">`System` es un espacio de nombres y `Console` es una clase de ese espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="168f0-105">`System` is a namespace and `Console` is a class in that namespace.</span></span> <span data-ttu-id="168f0-106">La palabra clave `using` se puede usar para que no se necesite el nombre completo, como en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="168f0-106">The `using` keyword can be used so that the complete name is not required, as in the following example:</span></span>  
  
 [!code-csharp[csProgGuide#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuide/CS/using.cs#1)]  
  
 [!code-csharp[csProgGuide#25](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuide/CS/progGuide.cs#25)]  
  
<span data-ttu-id="168f0-107">Para más información, vea [using (Directiva)](../../language-reference/keywords/using-directive.md).</span><span class="sxs-lookup"><span data-stu-id="168f0-107">For more information, see the [using Directive](../../language-reference/keywords/using-directive.md).</span></span>  
  
<span data-ttu-id="168f0-108">En segundo lugar, declarar sus propios espacios de nombres puede ayudarle a controlar el ámbito de nombres de clase y método en proyectos de programación grandes.</span><span class="sxs-lookup"><span data-stu-id="168f0-108">Second, declaring your own namespaces can help you control the scope of class and method names in larger programming projects.</span></span> <span data-ttu-id="168f0-109">Use la palabra clave [namespace](../../language-reference/keywords/namespace.md) para declarar un espacio de nombres, como en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="168f0-109">Use the [namespace](../../language-reference/keywords/namespace.md) keyword to declare a namespace, as in the following example:</span></span>  
  
 [!code-csharp[csProgGuideNamespaces#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideNamespaces/CS/Namespaces.cs#6)]

<span data-ttu-id="168f0-110">El nombre del espacio de nombres debe ser un [nombre de identificador](../inside-a-program/identifier-names.md) de C# válido.</span><span class="sxs-lookup"><span data-stu-id="168f0-110">The name of the namespace must be a valid C# [identifier name](../inside-a-program/identifier-names.md).</span></span>

## <a name="namespaces-overview"></a><span data-ttu-id="168f0-111">Información general sobre los espacios de nombres</span><span class="sxs-lookup"><span data-stu-id="168f0-111">Namespaces Overview</span></span>  

<span data-ttu-id="168f0-112">Los espacios de nombres tienen las propiedades siguientes:</span><span class="sxs-lookup"><span data-stu-id="168f0-112">Namespaces have the following properties:</span></span>  
  
- <span data-ttu-id="168f0-113">Organizan proyectos de código de gran tamaño.</span><span class="sxs-lookup"><span data-stu-id="168f0-113">They organize large code projects.</span></span>  
- <span data-ttu-id="168f0-114">Se delimitan mediante el operador `.`.</span><span class="sxs-lookup"><span data-stu-id="168f0-114">They are delimited by using the `.` operator.</span></span>  
- <span data-ttu-id="168f0-115">La directiva `using` obvia la necesidad de especificar el nombre del espacio de nombres para cada clase.</span><span class="sxs-lookup"><span data-stu-id="168f0-115">The `using` directive obviates the requirement to specify the name of the namespace for every class.</span></span>  
- <span data-ttu-id="168f0-116">El espacio de nombres `global` es el espacio de nombres "raíz": `global::System` siempre hará referencia al espacio de nombres <xref:System> de .NET.</span><span class="sxs-lookup"><span data-stu-id="168f0-116">The `global` namespace is the "root" namespace: `global::System` will always refer to the .NET <xref:System> namespace.</span></span>  

## <a name="c-language-specification"></a><span data-ttu-id="168f0-117">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="168f0-117">C# Language Specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="168f0-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="168f0-118">See also</span></span>

- [<span data-ttu-id="168f0-119">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="168f0-119">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="168f0-120">Utilizar espacios de nombres</span><span class="sxs-lookup"><span data-stu-id="168f0-120">Using Namespaces</span></span>](using-namespaces.md)
- [<span data-ttu-id="168f0-121">Cómo: Utilizar el alias del espacio de nombres global</span><span class="sxs-lookup"><span data-stu-id="168f0-121">How to: Use the Global Namespace Alias</span></span>](how-to-use-the-global-namespace-alias.md)
- [<span data-ttu-id="168f0-122">Cómo: Utilizar el espacio de nombres My</span><span class="sxs-lookup"><span data-stu-id="168f0-122">How to: Use the My Namespace</span></span>](how-to-use-the-my-namespace.md)
- [<span data-ttu-id="168f0-123">Nombres de identificador</span><span class="sxs-lookup"><span data-stu-id="168f0-123">Identifier names</span></span>](../inside-a-program/identifier-names.md)
- [<span data-ttu-id="168f0-124">using (directiva)</span><span class="sxs-lookup"><span data-stu-id="168f0-124">using Directive</span></span>](../../language-reference/keywords/using-directive.md)
- [<span data-ttu-id="168f0-125">:: !</span><span class="sxs-lookup"><span data-stu-id="168f0-125">:: Operator</span></span>](../../language-reference/operators/namespace-alias-qualifier.md)
