---
title: Private (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Private
helpviewer_keywords:
- Private keyword [Visual Basic]
- Private keyword [Visual Basic], syntax
ms.assetid: aba74a2e-5824-4613-bf63-b9ec7787f4e6
ms.openlocfilehash: d6e28e5e87c3a88e4db3fc81177894683dbb0908
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61920450"
---
# <a name="private-visual-basic"></a><span data-ttu-id="23a12-102">Private (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="23a12-102">Private (Visual Basic)</span></span>
<span data-ttu-id="23a12-103">Especifica que uno o varios elementos de programación declarados son accesibles solo desde dentro de su contexto de declaración, incluido dentro de los tipos contenidos.</span><span class="sxs-lookup"><span data-stu-id="23a12-103">Specifies that one or more declared programming elements are accessible only from within their declaration context, including from within any contained types.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="23a12-104">Comentarios</span><span class="sxs-lookup"><span data-stu-id="23a12-104">Remarks</span></span>  
 <span data-ttu-id="23a12-105">Si un elemento de programación representa la funcionalidad de propietario, o contiene datos confidenciales, normalmente desea limitar el acceso a él como estrictamente como sea posible.</span><span class="sxs-lookup"><span data-stu-id="23a12-105">If a programming element represents proprietary functionality, or contains confidential data, you usually want to limit access to it as strictly as possible.</span></span> <span data-ttu-id="23a12-106">Lograr el límite máximo, ya que permite solo el módulo, clase o estructura que define para tener acceso a él.</span><span class="sxs-lookup"><span data-stu-id="23a12-106">You achieve the maximum limitation by allowing only the module, class, or structure that defines it to access it.</span></span> <span data-ttu-id="23a12-107">Para limitar el acceso a un elemento de esta manera, puede declarar con `Private`.</span><span class="sxs-lookup"><span data-stu-id="23a12-107">To limit access to an element in this way, you can declare it with `Private`.</span></span>  

> [!NOTE]
> <span data-ttu-id="23a12-108">También puede usar el [Private Protected](private-protected.md) modificador de acceso, lo que hace que un miembro accesible desde dentro de esa clase y de las clases derivadas ubicadas en el ensamblado que lo contiene.</span><span class="sxs-lookup"><span data-stu-id="23a12-108">You can also use the [Private Protected](private-protected.md) access modifier, which makes a member accessible from within that class and from derived classes located in its containing assembly.</span></span>

## <a name="rules"></a><span data-ttu-id="23a12-109">Reglas</span><span class="sxs-lookup"><span data-stu-id="23a12-109">Rules</span></span>  

-   <span data-ttu-id="23a12-110">**Contexto de declaración.**</span><span class="sxs-lookup"><span data-stu-id="23a12-110">**Declaration Context.**</span></span> <span data-ttu-id="23a12-111">Solo se puede usar `Private` en un nivel de módulo.</span><span class="sxs-lookup"><span data-stu-id="23a12-111">You can use `Private` only at module level.</span></span> <span data-ttu-id="23a12-112">Esto significa que el contexto de declaración de un `Private` elemento debe ser un módulo, clase o estructura y no puede ser un archivo de código fuente, espacio de nombres, interfaz o procedimiento.</span><span class="sxs-lookup"><span data-stu-id="23a12-112">This means the declaration context for a `Private` element must be a module, class, or structure, and cannot be a source file, namespace, interface, or procedure.</span></span>  
  
## <a name="behavior"></a><span data-ttu-id="23a12-113">Comportamiento</span><span class="sxs-lookup"><span data-stu-id="23a12-113">Behavior</span></span>  
  
-   <span data-ttu-id="23a12-114">**Nivel de acceso.**</span><span class="sxs-lookup"><span data-stu-id="23a12-114">**Access Level.**</span></span> <span data-ttu-id="23a12-115">Puede tener acceso todo el código dentro de un contexto de declaración su `Private` elementos.</span><span class="sxs-lookup"><span data-stu-id="23a12-115">All code within a declaration context can access its `Private` elements.</span></span> <span data-ttu-id="23a12-116">Esto incluye el código dentro de un tipo contenido, como una clase anidada o una expresión de asignación en una enumeración.</span><span class="sxs-lookup"><span data-stu-id="23a12-116">This includes code within a contained type, such as a nested class or an assignment expression in an enumeration.</span></span> <span data-ttu-id="23a12-117">No puede tener acceso ningún código fuera del contexto de declaración su `Private` elementos.</span><span class="sxs-lookup"><span data-stu-id="23a12-117">No code outside of the declaration context can access its `Private` elements.</span></span>  
  
-   <span data-ttu-id="23a12-118">**Modificadores de acceso.**</span><span class="sxs-lookup"><span data-stu-id="23a12-118">**Access Modifiers.**</span></span> <span data-ttu-id="23a12-119">Las palabras clave que especifican el nivel de acceso se denominan *modificadores de acceso*.</span><span class="sxs-lookup"><span data-stu-id="23a12-119">The keywords that specify access level are called *access modifiers*.</span></span> <span data-ttu-id="23a12-120">Para obtener una comparación de los modificadores de acceso, consulte [tener acceso a los niveles en Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="23a12-120">For a comparison of the access modifiers, see [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
 <span data-ttu-id="23a12-121">El modificador `Private` se puede utilizar en los contextos siguientes:</span><span class="sxs-lookup"><span data-stu-id="23a12-121">The `Private` modifier can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="23a12-122">Class (instrucción)</span><span class="sxs-lookup"><span data-stu-id="23a12-122">Class Statement</span></span>](../../../visual-basic/language-reference/statements/class-statement.md)  
  
 [<span data-ttu-id="23a12-123">Const (instrucción)</span><span class="sxs-lookup"><span data-stu-id="23a12-123">Const Statement</span></span>](../../../visual-basic/language-reference/statements/const-statement.md)  
  
 [<span data-ttu-id="23a12-124">Declare (instrucción)</span><span class="sxs-lookup"><span data-stu-id="23a12-124">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
 [<span data-ttu-id="23a12-125">Delegate (instrucción)</span><span class="sxs-lookup"><span data-stu-id="23a12-125">Delegate Statement</span></span>](../../../visual-basic/language-reference/statements/delegate-statement.md)  
  
 [<span data-ttu-id="23a12-126">Dim (instrucción)</span><span class="sxs-lookup"><span data-stu-id="23a12-126">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
 [<span data-ttu-id="23a12-127">Enum (instrucción)</span><span class="sxs-lookup"><span data-stu-id="23a12-127">Enum Statement</span></span>](../../../visual-basic/language-reference/statements/enum-statement.md)  
  
 [<span data-ttu-id="23a12-128">Event (instrucción)</span><span class="sxs-lookup"><span data-stu-id="23a12-128">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)  
  
 [<span data-ttu-id="23a12-129">Function (instrucción)</span><span class="sxs-lookup"><span data-stu-id="23a12-129">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [<span data-ttu-id="23a12-130">Interface (instrucción)</span><span class="sxs-lookup"><span data-stu-id="23a12-130">Interface Statement</span></span>](../../../visual-basic/language-reference/statements/interface-statement.md)  
  
 [<span data-ttu-id="23a12-131">Property (instrucción)</span><span class="sxs-lookup"><span data-stu-id="23a12-131">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [<span data-ttu-id="23a12-132">Structure (instrucción)</span><span class="sxs-lookup"><span data-stu-id="23a12-132">Structure Statement</span></span>](../../../visual-basic/language-reference/statements/structure-statement.md)  
  
 [<span data-ttu-id="23a12-133">Sub (instrucción)</span><span class="sxs-lookup"><span data-stu-id="23a12-133">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="23a12-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="23a12-134">See also</span></span>

- [<span data-ttu-id="23a12-135">Public</span><span class="sxs-lookup"><span data-stu-id="23a12-135">Public</span></span>](../../../visual-basic/language-reference/modifiers/public.md)
- [<span data-ttu-id="23a12-136">Protected</span><span class="sxs-lookup"><span data-stu-id="23a12-136">Protected</span></span>](../../../visual-basic/language-reference/modifiers/protected.md)
- [<span data-ttu-id="23a12-137">Friend</span><span class="sxs-lookup"><span data-stu-id="23a12-137">Friend</span></span>](../../../visual-basic/language-reference/modifiers/friend.md)
- [<span data-ttu-id="23a12-138">Private Protected</span><span class="sxs-lookup"><span data-stu-id="23a12-138">Private Protected</span></span>](./private-protected.md)
- <span data-ttu-id="23a12-139">[Protected Friend](./protected-friend.md)[tener acceso a los niveles en Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)</span><span class="sxs-lookup"><span data-stu-id="23a12-139">[Protected Friend](./protected-friend.md)    [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)</span></span>
- [<span data-ttu-id="23a12-140">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="23a12-140">Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/index.md)
- [<span data-ttu-id="23a12-141">Estructuras</span><span class="sxs-lookup"><span data-stu-id="23a12-141">Structures</span></span>](../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [<span data-ttu-id="23a12-142">Objetos y clases</span><span class="sxs-lookup"><span data-stu-id="23a12-142">Objects and Classes</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
