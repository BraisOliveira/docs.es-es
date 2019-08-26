---
title: 'into: Referencia de C#'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- into_CSharpKeyword
- into
helpviewer_keywords:
- into keyword [C#]
ms.assetid: 81ec62c1-f0b1-4755-8a31-959876e77f65
ms.openlocfilehash: dc1e2ee004c21bb3d05155eec3e42ea80bf641a1
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/19/2019
ms.locfileid: "69608641"
---
# <a name="into-c-reference"></a><span data-ttu-id="23d00-102">into (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="23d00-102">into (C# Reference)</span></span>

<span data-ttu-id="23d00-103">La palabra clave contextual `into` puede usarse para crear un identificador temporal para almacenar los resultados de una cláusula [group](group-clause.md), [join](join-clause.md) o [select](select-clause.md) en un nuevo identificador.</span><span class="sxs-lookup"><span data-stu-id="23d00-103">The `into` contextual keyword can be used to create a temporary identifier to store the results of a [group](group-clause.md), [join](join-clause.md) or [select](select-clause.md) clause into a new identifier.</span></span> <span data-ttu-id="23d00-104">Este identificador puede ser un generador de comandos de consulta adicionales.</span><span class="sxs-lookup"><span data-stu-id="23d00-104">This identifier can itself be a generator for additional query commands.</span></span> <span data-ttu-id="23d00-105">Cuando se usa en una cláusula `group` o `select`, el uso del nuevo identificador se denomina a veces una *continuación*.</span><span class="sxs-lookup"><span data-stu-id="23d00-105">When used in a `group` or `select` clause, the use of the new identifier is sometimes referred to as a *continuation*.</span></span>

## <a name="example"></a><span data-ttu-id="23d00-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="23d00-106">Example</span></span>

<span data-ttu-id="23d00-107">En el ejemplo siguiente, se muestra el uso de la palabra clave `into` para habilitar un identificador temporal `fruitGroup` que tiene un tipo deducido de `IGrouping`.</span><span class="sxs-lookup"><span data-stu-id="23d00-107">The following example shows the use of the `into` keyword to enable a temporary identifier `fruitGroup` which has an inferred type of `IGrouping`.</span></span> <span data-ttu-id="23d00-108">Mediante el identificador, puede invocar el método <xref:System.Linq.Enumerable.Count%2A> en cada grupo y seleccionar solo los grupos que contienen dos o más palabras.</span><span class="sxs-lookup"><span data-stu-id="23d00-108">By using the identifier, you can invoke the <xref:System.Linq.Enumerable.Count%2A> method on each group and select only those groups that contain two or more words.</span></span>

[!code-csharp[cscsrefQueryKeywords#18](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsCsrefQueryKeywords/CS/Into.cs#18)]

<span data-ttu-id="23d00-109">El uso de `into` en una cláusula `group` solo es necesario cuando quiere realizar operaciones de consulta adicionales en cada grupo.</span><span class="sxs-lookup"><span data-stu-id="23d00-109">The use of `into` in a `group` clause is only necessary when you want to perform additional query operations on each group.</span></span> <span data-ttu-id="23d00-110">Para obtener más información, vea [group (Cláusula)](group-clause.md).</span><span class="sxs-lookup"><span data-stu-id="23d00-110">For more information, see [group clause](group-clause.md).</span></span>

<span data-ttu-id="23d00-111">Para obtener un ejemplo del uso de `into` en una cláusula `join`, vea [join (Cláusula)](join-clause.md).</span><span class="sxs-lookup"><span data-stu-id="23d00-111">For an example of the use of `into` in a `join` clause, see [join clause](join-clause.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="23d00-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="23d00-112">See also</span></span>

- [<span data-ttu-id="23d00-113">Palabras clave para consultas (LINQ)</span><span class="sxs-lookup"><span data-stu-id="23d00-113">Query Keywords (LINQ)</span></span>](query-keywords.md)
- [<span data-ttu-id="23d00-114">Expresiones de consulta LINQ</span><span class="sxs-lookup"><span data-stu-id="23d00-114">LINQ Query Expressions</span></span>](../../programming-guide/linq-query-expressions/index.md)
- [<span data-ttu-id="23d00-115">group (cláusula)</span><span class="sxs-lookup"><span data-stu-id="23d00-115">group clause</span></span>](group-clause.md)
