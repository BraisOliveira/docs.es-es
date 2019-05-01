---
title: Operadores de igualdad
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- class library design guidelines [.NET Framework], Equals method
- class library design guidelines [.NET Framework], equality operator
- equality operator (==) [.NET Framework]
- Equals method
- == operator (equality) [.NET Framework]
ms.assetid: bc496a91-fefb-4ce0-ab4c-61f09964119a
author: KrzysztofCwalina
ms.openlocfilehash: ef1a0aff1ac59434d9d9a6f0371bf236f637050e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61960342"
---
# <a name="equality-operators"></a><span data-ttu-id="f7402-102">Operadores de igualdad</span><span class="sxs-lookup"><span data-stu-id="f7402-102">Equality Operators</span></span>
<span data-ttu-id="f7402-103">En esta sección se describe la sobrecarga de operadores de igualdad y hace referencia a `operator==` y `operator!=` como operadores de igualdad.</span><span class="sxs-lookup"><span data-stu-id="f7402-103">This section discusses overloading equality operators and refers to `operator==` and `operator!=` as equality operators.</span></span>  
  
 <span data-ttu-id="f7402-104">**X DO NOT** uno de los operadores de igualdad y la otra sobrecarga.</span><span class="sxs-lookup"><span data-stu-id="f7402-104">**X DO NOT** overload one of the equality operators and not the other.</span></span>  
  
 <span data-ttu-id="f7402-105">**✓ DO** Asegúrese de que <xref:System.Object.Equals%2A?displayProperty=nameWithType> y los operadores de igualdad tienen exactamente la misma semántica y las características de rendimiento similares.</span><span class="sxs-lookup"><span data-stu-id="f7402-105">**✓ DO** ensure that <xref:System.Object.Equals%2A?displayProperty=nameWithType> and the equality operators have exactly the same semantics and similar performance characteristics.</span></span>  
  
 <span data-ttu-id="f7402-106">Esto significa que a menudo `Object.Equals` debe invalidarse cuando se sobrecargan los operadores de igualdad.</span><span class="sxs-lookup"><span data-stu-id="f7402-106">This often means that `Object.Equals` needs to be overridden when the equality operators are overloaded.</span></span>  
  
 <span data-ttu-id="f7402-107">**X AVOID** iniciar excepciones desde los operadores de igualdad.</span><span class="sxs-lookup"><span data-stu-id="f7402-107">**X AVOID** throwing exceptions from equality operators.</span></span>  
  
 <span data-ttu-id="f7402-108">Por ejemplo, devolver false si uno de los argumentos es null en lugar de producir `NullReferenceException`.</span><span class="sxs-lookup"><span data-stu-id="f7402-108">For example, return false if one of the arguments is null instead of throwing `NullReferenceException`.</span></span>  
  
## <a name="equality-operators-on-value-types"></a><span data-ttu-id="f7402-109">Operadores de igualdad en los tipos de valor</span><span class="sxs-lookup"><span data-stu-id="f7402-109">Equality Operators on Value Types</span></span>  
 <span data-ttu-id="f7402-110">**✓ DO** sobrecargar los operadores de igualdad en los tipos de valor, si son iguales es significativo.</span><span class="sxs-lookup"><span data-stu-id="f7402-110">**✓ DO** overload the equality operators on value types, if equality is meaningful.</span></span>  
  
 <span data-ttu-id="f7402-111">En la mayoría de los lenguajes de programación, no hay ninguna implementación predeterminada de `operator==` para tipos de valor.</span><span class="sxs-lookup"><span data-stu-id="f7402-111">In most programming languages, there is no default implementation of `operator==` for value types.</span></span>  
  
## <a name="equality-operators-on-reference-types"></a><span data-ttu-id="f7402-112">Operadores de igualdad con tipos de referencia</span><span class="sxs-lookup"><span data-stu-id="f7402-112">Equality Operators on Reference Types</span></span>  
 <span data-ttu-id="f7402-113">**X AVOID** sobrecargar operadores de igualdad de tipos de referencias mutables.</span><span class="sxs-lookup"><span data-stu-id="f7402-113">**X AVOID** overloading equality operators on mutable reference types.</span></span>  
  
 <span data-ttu-id="f7402-114">Muchos lenguajes tienen operadores de igualdad integrada para tipos de referencia.</span><span class="sxs-lookup"><span data-stu-id="f7402-114">Many languages have built-in equality operators for reference types.</span></span> <span data-ttu-id="f7402-115">Los operadores integrados implementan generalmente la igualdad de referencia, y muchos desarrolladores se sorprenden cuando se cambia el comportamiento predeterminado para la igualdad de valor.</span><span class="sxs-lookup"><span data-stu-id="f7402-115">The built-in operators usually implement the reference equality, and many developers are surprised when the default behavior is changed to the value equality.</span></span>  
  
 <span data-ttu-id="f7402-116">Este problema se mitiga para tipos de referencia inmutable porque inmutabilidad hace mucho más difícil Observe la diferencia entre la igualdad de referencia y la igualdad de valores.</span><span class="sxs-lookup"><span data-stu-id="f7402-116">This problem is mitigated for immutable reference types because immutability makes it much harder to notice the difference between reference equality and value equality.</span></span>  
  
 <span data-ttu-id="f7402-117">**X AVOID** sobrecargar operadores de igualdad de tipos de referencia si la implementación sería mucho más lenta que el de igualdad de referencia.</span><span class="sxs-lookup"><span data-stu-id="f7402-117">**X AVOID** overloading equality operators on reference types if the implementation would be significantly slower than that of reference equality.</span></span>  
  
 <span data-ttu-id="f7402-118">*Portions © 2005, 2009 Microsoft Corporation. Reservados todos los derechos.*</span><span class="sxs-lookup"><span data-stu-id="f7402-118">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="f7402-119">*Reimpreso con permiso de Pearson Education, Inc. de [instrucciones de diseño de Framework: Convenciones, expresiones y patrones para bibliotecas reutilizables. NET, 2ª edición](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina y Brad Abrams, publicada el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie de desarrollo de Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="f7402-119">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f7402-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="f7402-120">See also</span></span>

- [<span data-ttu-id="f7402-121">Instrucciones de diseño de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="f7402-121">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
- [<span data-ttu-id="f7402-122">Instrucciones de uso</span><span class="sxs-lookup"><span data-stu-id="f7402-122">Usage Guidelines</span></span>](../../../docs/standard/design-guidelines/usage-guidelines.md)
