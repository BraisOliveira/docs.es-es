---
title: La instrucción 'For Each' en el tipo '<typename>' es ambigua porque el tipo implementa varias creaciones de instancias de 'System.Collections.Generic.IEnumerable(Of T)'
ms.date: 07/20/2015
f1_keywords:
- vbc32096
- bc32096
helpviewer_keywords:
- BC32096
ms.assetid: ed20d09c-913f-482e-89f8-c0a596c3ec24
ms.openlocfilehash: 6c34ca43decc3c5d8c72b529d8f51d7cc3b0c6b3
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "58833391"
---
# <a name="for-each-on-type-typename-is-ambiguous-because-the-type-implements-multiple-instantiations-of-systemcollectionsgenericienumerableof-t"></a><span data-ttu-id="e1ab2-102">'For Each' en el tipo '\<typename >' es ambigua porque el tipo implementa varias creaciones de instancias de 'IEnumerable (Of T)'</span><span class="sxs-lookup"><span data-stu-id="e1ab2-102">'For Each' on type '\<typename>' is ambiguous because the type implements multiple instantiations of 'System.Collections.Generic.IEnumerable(Of T)'</span></span>
<span data-ttu-id="e1ab2-103">Un `For Each` instrucción especifica una variable de iterador que tiene más de un <xref:System.Collections.IEnumerable.GetEnumerator%2A> método.</span><span class="sxs-lookup"><span data-stu-id="e1ab2-103">A `For Each` statement specifies an iterator variable that has more than one <xref:System.Collections.IEnumerable.GetEnumerator%2A> method.</span></span>  
  
 <span data-ttu-id="e1ab2-104">La variable de iterador debe ser de un tipo que implementa el <xref:System.Collections.IEnumerable?displayProperty=nameWithType> o <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType> interfaz en uno de los `Collections` espacios de nombres de los [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e1ab2-104">The iterator variable must be of a type that implements the <xref:System.Collections.IEnumerable?displayProperty=nameWithType> or <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType> interface in one of the `Collections` namespaces of the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)].</span></span> <span data-ttu-id="e1ab2-105">Es posible que una clase implementar más de una interfaz genérica construida, con un argumento de tipo diferente para cada construcción.</span><span class="sxs-lookup"><span data-stu-id="e1ab2-105">It is possible for a class to implement more than one constructed generic interface, using a different type argument for each construction.</span></span> <span data-ttu-id="e1ab2-106">Si se usa una clase que hace esto para la variable de iterador, esa variable tiene más de un <xref:System.Collections.IEnumerable.GetEnumerator%2A> método.</span><span class="sxs-lookup"><span data-stu-id="e1ab2-106">If a class that does this is used for the iterator variable, that variable has more than one <xref:System.Collections.IEnumerable.GetEnumerator%2A> method.</span></span> <span data-ttu-id="e1ab2-107">En tal caso, Visual Basic no puede elegir qué método va a llamar.</span><span class="sxs-lookup"><span data-stu-id="e1ab2-107">In such a case, Visual Basic cannot choose which method to call.</span></span>  
  
 <span data-ttu-id="e1ab2-108">**Identificador de error:** BC32096</span><span class="sxs-lookup"><span data-stu-id="e1ab2-108">**Error ID:** BC32096</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="e1ab2-109">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="e1ab2-109">To correct this error</span></span>  
  
-   <span data-ttu-id="e1ab2-110">Usar [DirectCast (operador)](../../../visual-basic/language-reference/operators/directcast-operator.md) o [TryCast (operador)](../../../visual-basic/language-reference/operators/trycast-operator.md) convertir el tipo de variable de iterador para la interfaz que define el <xref:System.Collections.IEnumerable.GetEnumerator%2A> método que desee usar.</span><span class="sxs-lookup"><span data-stu-id="e1ab2-110">Use [DirectCast Operator](../../../visual-basic/language-reference/operators/directcast-operator.md) or [TryCast Operator](../../../visual-basic/language-reference/operators/trycast-operator.md) to cast the iterator variable type to the interface defining the <xref:System.Collections.IEnumerable.GetEnumerator%2A> method you want to use.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e1ab2-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="e1ab2-111">See also</span></span>

- [<span data-ttu-id="e1ab2-112">For Each...Next (instrucción)</span><span class="sxs-lookup"><span data-stu-id="e1ab2-112">For Each...Next Statement</span></span>](../../../visual-basic/language-reference/statements/for-each-next-statement.md)
- [<span data-ttu-id="e1ab2-113">Interfaces</span><span class="sxs-lookup"><span data-stu-id="e1ab2-113">Interfaces</span></span>](../../../visual-basic/programming-guide/language-features/interfaces/index.md)
