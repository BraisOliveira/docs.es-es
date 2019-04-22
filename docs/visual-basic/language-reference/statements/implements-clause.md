---
title: Implements (Cláusula, Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.ImplementsClause
helpviewer_keywords:
- interface implementation [Visual Basic], reimplementation
- interface members [Visual Basic], reimplementation
- interface members [Visual Basic], Implements keyword
- interface members
- members [Visual Basic], reimplementation
- interface implementation [Visual Basic], Implements keyword
- interface members [Visual Basic], implementing
- Implements keyword [Visual Basic]
- Implements statement [Visual Basic], about Implements
- members [Visual Basic], implementing
- members [Visual Basic], Implements keyword
- reimplementation
ms.assetid: 5252cdf9-964d-4fc6-af0f-0449b7126b5a
ms.openlocfilehash: 05de1d9f8966c17d84deba34f27819cce4aff3fe
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "58832624"
---
# <a name="implements-clause-visual-basic"></a><span data-ttu-id="c4bb3-102">Implements (Cláusula, Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c4bb3-102">Implements Clause (Visual Basic)</span></span>
<span data-ttu-id="c4bb3-103">Indica que un miembro de clase o estructura proporciona la implementación de un miembro definido en una interfaz.</span><span class="sxs-lookup"><span data-stu-id="c4bb3-103">Indicates that a class or structure member is providing the implementation for a member defined in an interface.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c4bb3-104">Comentarios</span><span class="sxs-lookup"><span data-stu-id="c4bb3-104">Remarks</span></span>  
<span data-ttu-id="c4bb3-105">El `Implements` palabra clave no es igual que el [instrucción Implements](../../../visual-basic/language-reference/statements/implements-statement.md).</span><span class="sxs-lookup"><span data-stu-id="c4bb3-105">The `Implements` keyword is not the same as the [Implements Statement](../../../visual-basic/language-reference/statements/implements-statement.md).</span></span> <span data-ttu-id="c4bb3-106">Usa el `Implements` instrucción para especificar que una clase o estructura implementa una o varias interfaces y, a continuación, para cada miembro que usa el `Implements` palabra clave para especificar qué interfaz y qué miembro implementa.</span><span class="sxs-lookup"><span data-stu-id="c4bb3-106">You use the `Implements` statement to specify that a class or structure implements one or more interfaces, and then for each member you use the `Implements` keyword to specify which interface and which member it implements.</span></span>

<span data-ttu-id="c4bb3-107">Si una clase o estructura implementa una interfaz, debe incluir el `Implements` instrucción inmediatamente después de la [Class (instrucción)](../../../visual-basic/language-reference/statements/class-statement.md) o [Structure (instrucción)](../../../visual-basic/language-reference/statements/structure-statement.md), y debe implementar todos los miembros define la interfaz.</span><span class="sxs-lookup"><span data-stu-id="c4bb3-107">If a class or structure implements an interface, it must include the `Implements` statement immediately after the [Class Statement](../../../visual-basic/language-reference/statements/class-statement.md) or [Structure Statement](../../../visual-basic/language-reference/statements/structure-statement.md), and it must implement all the members defined by the interface.</span></span>

## <a name="reimplementation"></a><span data-ttu-id="c4bb3-108">Reimplementación</span><span class="sxs-lookup"><span data-stu-id="c4bb3-108">Reimplementation</span></span>  
<span data-ttu-id="c4bb3-109">En una clase derivada, puede volver a implementar a un miembro de interfaz que ya ha implementado la clase base.</span><span class="sxs-lookup"><span data-stu-id="c4bb3-109">In a derived class, you can reimplement an interface member that the base class has already implemented.</span></span> <span data-ttu-id="c4bb3-110">Esto es diferente de reemplazar al miembro de clase base en los siguientes aspectos:</span><span class="sxs-lookup"><span data-stu-id="c4bb3-110">This is different from overriding the base class member in the following respects:</span></span>

- <span data-ttu-id="c4bb3-111">No es necesario ser miembro de clase base [Overridable](../../../visual-basic/language-reference/modifiers/overridable.md) para ser implementado de nuevo.</span><span class="sxs-lookup"><span data-stu-id="c4bb3-111">The base class member does not need to be [Overridable](../../../visual-basic/language-reference/modifiers/overridable.md) to be reimplemented.</span></span>
- <span data-ttu-id="c4bb3-112">Puede volver a implementar al miembro con un nombre diferente.</span><span class="sxs-lookup"><span data-stu-id="c4bb3-112">You can reimplement the member with a different name.</span></span>

<span data-ttu-id="c4bb3-113">El `Implements` palabra clave puede utilizarse en los contextos siguientes:</span><span class="sxs-lookup"><span data-stu-id="c4bb3-113">The `Implements` keyword can be used in the following contexts:</span></span>
- [<span data-ttu-id="c4bb3-114">Event (instrucción)</span><span class="sxs-lookup"><span data-stu-id="c4bb3-114">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)
- [<span data-ttu-id="c4bb3-115">Function (instrucción)</span><span class="sxs-lookup"><span data-stu-id="c4bb3-115">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)
- [<span data-ttu-id="c4bb3-116">Property (instrucción)</span><span class="sxs-lookup"><span data-stu-id="c4bb3-116">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)
- [<span data-ttu-id="c4bb3-117">Sub (instrucción)</span><span class="sxs-lookup"><span data-stu-id="c4bb3-117">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="c4bb3-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="c4bb3-118">See also</span></span>

- [<span data-ttu-id="c4bb3-119">Implements (instrucción)</span><span class="sxs-lookup"><span data-stu-id="c4bb3-119">Implements Statement</span></span>](../../../visual-basic/language-reference/statements/implements-statement.md)
- [<span data-ttu-id="c4bb3-120">Interface (instrucción)</span><span class="sxs-lookup"><span data-stu-id="c4bb3-120">Interface Statement</span></span>](../../../visual-basic/language-reference/statements/interface-statement.md)
- [<span data-ttu-id="c4bb3-121">Class (instrucción)</span><span class="sxs-lookup"><span data-stu-id="c4bb3-121">Class Statement</span></span>](../../../visual-basic/language-reference/statements/class-statement.md)
- [<span data-ttu-id="c4bb3-122">Structure (instrucción)</span><span class="sxs-lookup"><span data-stu-id="c4bb3-122">Structure Statement</span></span>](../../../visual-basic/language-reference/statements/structure-statement.md)
