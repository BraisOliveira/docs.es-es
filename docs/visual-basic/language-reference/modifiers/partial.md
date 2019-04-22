---
title: Partial (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Partial
- partial
helpviewer_keywords:
- structures [Visual Basic], partial
- classes [Visual Basic]
- partial, types [Visual Basic]
- partial, structures
- partial, classes [Visual Basic]
- classes [Visual Basic], partial
- Partial keyword [Visual Basic]
- type promotion
ms.assetid: 7adaef80-f435-46e1-970a-269fff63b448
ms.openlocfilehash: 0f74935d58d47e65b5eb614abc86a3fc9c8e6c42
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "58838370"
---
# <a name="partial-visual-basic"></a><span data-ttu-id="e33d3-102">Partial (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e33d3-102">Partial (Visual Basic)</span></span>
<span data-ttu-id="e33d3-103">Indica que una declaración de tipo es una definición parcial del tipo.</span><span class="sxs-lookup"><span data-stu-id="e33d3-103">Indicates that a type declaration is a partial definition of the type.</span></span>  
  
 <span data-ttu-id="e33d3-104">Puede dividir la definición de un tipo en varias declaraciones con la palabra clave `Partial`.</span><span class="sxs-lookup"><span data-stu-id="e33d3-104">You can divide the definition of a type among several declarations by using the `Partial` keyword.</span></span> <span data-ttu-id="e33d3-105">Puede usar todas las declaraciones parciales que quiera en todos los archivos de código fuente que desee,</span><span class="sxs-lookup"><span data-stu-id="e33d3-105">You can use as many partial declarations as you want, in as many different source files as you want.</span></span> <span data-ttu-id="e33d3-106">pero todas las declaraciones deben estar en el mismo ensamblado y en el mismo espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="e33d3-106">However, all the declarations must be in the same assembly and the same namespace.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e33d3-107">Visual Basic admite *métodos parciales*, que normalmente se implementan en clases parciales.</span><span class="sxs-lookup"><span data-stu-id="e33d3-107">Visual Basic supports *partial methods*, which are typically implemented in partial classes.</span></span> <span data-ttu-id="e33d3-108">Para obtener más información, consulte [métodos parciales](../../../visual-basic/programming-guide/language-features/procedures/partial-methods.md) y [Sub (instrucción)](../../../visual-basic/language-reference/statements/sub-statement.md).</span><span class="sxs-lookup"><span data-stu-id="e33d3-108">For more information, see [Partial Methods](../../../visual-basic/programming-guide/language-features/procedures/partial-methods.md) and [Sub Statement](../../../visual-basic/language-reference/statements/sub-statement.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e33d3-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e33d3-109">Syntax</span></span>  
  
```  
[ <attrlist> ] [ accessmodifier ] [ Shadows ] [ MustInherit | NotInheritable ] _  
Partial { Class | Structure | Interface | Module } name [ (Of typelist) ]  
    [ Inherits classname ]  
    [ Implements interfacenames ]  
    [ variabledeclarations ]  
    [ proceduredeclarations ]  
{ End Class | End Structure }  
```  
  
## <a name="parts"></a><span data-ttu-id="e33d3-110">Elementos</span><span class="sxs-lookup"><span data-stu-id="e33d3-110">Parts</span></span>  
  
|<span data-ttu-id="e33d3-111">Término</span><span class="sxs-lookup"><span data-stu-id="e33d3-111">Term</span></span>|<span data-ttu-id="e33d3-112">Definición</span><span class="sxs-lookup"><span data-stu-id="e33d3-112">Definition</span></span>|  
|---|---|  
|`attrlist`|<span data-ttu-id="e33d3-113">Opcional.</span><span class="sxs-lookup"><span data-stu-id="e33d3-113">Optional.</span></span> <span data-ttu-id="e33d3-114">Lista de atributos que se aplican a este tipo.</span><span class="sxs-lookup"><span data-stu-id="e33d3-114">List of attributes that apply to this type.</span></span> <span data-ttu-id="e33d3-115">Debe incluir el [lista de atributos](../../../visual-basic/language-reference/statements/attribute-list.md) en corchetes angulares (`< >`).</span><span class="sxs-lookup"><span data-stu-id="e33d3-115">You must enclose the [Attribute List](../../../visual-basic/language-reference/statements/attribute-list.md) in angle brackets (`< >`).</span></span>|  
|`accessmodifier`|<span data-ttu-id="e33d3-116">Opcional.</span><span class="sxs-lookup"><span data-stu-id="e33d3-116">Optional.</span></span> <span data-ttu-id="e33d3-117">Especifica qué código puede tener acceso a este tipo.</span><span class="sxs-lookup"><span data-stu-id="e33d3-117">Specifies what code can access this type.</span></span> <span data-ttu-id="e33d3-118">Vea [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="e33d3-118">See [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>|  
|`Shadows`|<span data-ttu-id="e33d3-119">Opcional.</span><span class="sxs-lookup"><span data-stu-id="e33d3-119">Optional.</span></span> <span data-ttu-id="e33d3-120">Consulte [sombras](../../../visual-basic/language-reference/modifiers/shadows.md).</span><span class="sxs-lookup"><span data-stu-id="e33d3-120">See [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md).</span></span>|  
|`MustInherit`|<span data-ttu-id="e33d3-121">Opcional.</span><span class="sxs-lookup"><span data-stu-id="e33d3-121">Optional.</span></span> <span data-ttu-id="e33d3-122">Consulte [MustInherit](../../../visual-basic/language-reference/modifiers/mustinherit.md).</span><span class="sxs-lookup"><span data-stu-id="e33d3-122">See [MustInherit](../../../visual-basic/language-reference/modifiers/mustinherit.md).</span></span>|  
|`NotInheritable`|<span data-ttu-id="e33d3-123">Opcional.</span><span class="sxs-lookup"><span data-stu-id="e33d3-123">Optional.</span></span> <span data-ttu-id="e33d3-124">Consulte [NotInheritable](../../../visual-basic/language-reference/modifiers/notinheritable.md).</span><span class="sxs-lookup"><span data-stu-id="e33d3-124">See [NotInheritable](../../../visual-basic/language-reference/modifiers/notinheritable.md).</span></span>|  
|`name`|<span data-ttu-id="e33d3-125">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="e33d3-125">Required.</span></span> <span data-ttu-id="e33d3-126">Nombre de este tipo.</span><span class="sxs-lookup"><span data-stu-id="e33d3-126">Name of this type.</span></span> <span data-ttu-id="e33d3-127">Debe coincidir con el nombre definido en el resto de las declaraciones parciales del mismo tipo.</span><span class="sxs-lookup"><span data-stu-id="e33d3-127">Must match the name defined in all other partial declarations of the same type.</span></span>|  
|`Of`|<span data-ttu-id="e33d3-128">Opcional.</span><span class="sxs-lookup"><span data-stu-id="e33d3-128">Optional.</span></span> <span data-ttu-id="e33d3-129">Especifica que se trata de un tipo genérico.</span><span class="sxs-lookup"><span data-stu-id="e33d3-129">Specifies that this is a generic type.</span></span> <span data-ttu-id="e33d3-130">Consulte [tipos genéricos en Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md).</span><span class="sxs-lookup"><span data-stu-id="e33d3-130">See [Generic Types in Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md).</span></span>|  
|`typelist`|<span data-ttu-id="e33d3-131">Es necesario si se usan [de](../../../visual-basic/language-reference/statements/of-clause.md).</span><span class="sxs-lookup"><span data-stu-id="e33d3-131">Required if you use [Of](../../../visual-basic/language-reference/statements/of-clause.md).</span></span> <span data-ttu-id="e33d3-132">Consulte [escriba lista](../../../visual-basic/language-reference/statements/type-list.md).</span><span class="sxs-lookup"><span data-stu-id="e33d3-132">See [Type List](../../../visual-basic/language-reference/statements/type-list.md).</span></span>|  
|`Inherits`|<span data-ttu-id="e33d3-133">Opcional.</span><span class="sxs-lookup"><span data-stu-id="e33d3-133">Optional.</span></span> <span data-ttu-id="e33d3-134">Consulte [Inherits (instrucción)](../../../visual-basic/language-reference/statements/inherits-statement.md).</span><span class="sxs-lookup"><span data-stu-id="e33d3-134">See [Inherits Statement](../../../visual-basic/language-reference/statements/inherits-statement.md).</span></span>|  
|`classname`|<span data-ttu-id="e33d3-135">Obligatorio si se usa `Inherits`.</span><span class="sxs-lookup"><span data-stu-id="e33d3-135">Required if you use `Inherits`.</span></span> <span data-ttu-id="e33d3-136">El nombre de la clase o la interfaz de la que se deriva esta clase.</span><span class="sxs-lookup"><span data-stu-id="e33d3-136">The name of the class or interface from which this class derives.</span></span>|  
|`Implements`|<span data-ttu-id="e33d3-137">Opcional.</span><span class="sxs-lookup"><span data-stu-id="e33d3-137">Optional.</span></span> <span data-ttu-id="e33d3-138">Consulte [implementa instrucción](../../../visual-basic/language-reference/statements/implements-statement.md).</span><span class="sxs-lookup"><span data-stu-id="e33d3-138">See [Implements Statement](../../../visual-basic/language-reference/statements/implements-statement.md).</span></span>|  
|`interfacenames`|<span data-ttu-id="e33d3-139">Obligatorio si se usa `Implements`.</span><span class="sxs-lookup"><span data-stu-id="e33d3-139">Required if you use `Implements`.</span></span> <span data-ttu-id="e33d3-140">Los nombres de las interfaces que implementa este tipo.</span><span class="sxs-lookup"><span data-stu-id="e33d3-140">The names of the interfaces this type implements.</span></span>|  
|`variabledeclarations`|<span data-ttu-id="e33d3-141">Opcional.</span><span class="sxs-lookup"><span data-stu-id="e33d3-141">Optional.</span></span> <span data-ttu-id="e33d3-142">Instrucciones que declaran variables adicionales y eventos para el tipo.</span><span class="sxs-lookup"><span data-stu-id="e33d3-142">Statements which declare additional variables and events for the type.</span></span>|  
|`proceduredeclarations`|<span data-ttu-id="e33d3-143">Opcional.</span><span class="sxs-lookup"><span data-stu-id="e33d3-143">Optional.</span></span> <span data-ttu-id="e33d3-144">Instrucciones que declaran y definen procedimientos adicionales para el tipo.</span><span class="sxs-lookup"><span data-stu-id="e33d3-144">Statements which declare and define additional procedures for the type.</span></span>|  
|<span data-ttu-id="e33d3-145">`End Class` o `End Structure`</span><span class="sxs-lookup"><span data-stu-id="e33d3-145">`End Class` or `End Structure`</span></span>|<span data-ttu-id="e33d3-146">Finaliza esta definición `Class` o `Structure` parcial.</span><span class="sxs-lookup"><span data-stu-id="e33d3-146">Ends this partial `Class` or `Structure` definition.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e33d3-147">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e33d3-147">Remarks</span></span>  
 <span data-ttu-id="e33d3-148">Visual Basic usa definiciones de clase parcial para separar el código generado del código creado por el usuario en archivos de código fuente independientes.</span><span class="sxs-lookup"><span data-stu-id="e33d3-148">Visual Basic uses partial-class definitions to separate generated code from user-authored code in separate source files.</span></span> <span data-ttu-id="e33d3-149">Por ejemplo, el **Diseñador de Windows Forms<xref:System.Windows.Forms.Form> define clases parciales para controles como** .</span><span class="sxs-lookup"><span data-stu-id="e33d3-149">For example, the **Windows Form Designer** defines partial classes for controls such as <xref:System.Windows.Forms.Form>.</span></span> <span data-ttu-id="e33d3-150">No debe modificar el código generado en estos controles.</span><span class="sxs-lookup"><span data-stu-id="e33d3-150">You should not modify the generated code in these controls.</span></span>  
  
 <span data-ttu-id="e33d3-151">Todas las reglas para crear clases, estructuras, interfaces y módulos, como las reglas de uso y herencia de modificadores, se aplican al crear un tipo parcial.</span><span class="sxs-lookup"><span data-stu-id="e33d3-151">All the rules for class, structure, interface, and module creation, such as those for modifier usage and inheritance, apply when creating a partial type.</span></span>  
  
## <a name="best-practices"></a><span data-ttu-id="e33d3-152">Procedimientos recomendados</span><span class="sxs-lookup"><span data-stu-id="e33d3-152">Best Practices</span></span>  
  
-   <span data-ttu-id="e33d3-153">En circunstancias normales no debe dividir el desarrollo de un solo tipo en dos o más declaraciones.</span><span class="sxs-lookup"><span data-stu-id="e33d3-153">Under normal circumstances, you should not split the development of a single type across two or more declarations.</span></span> <span data-ttu-id="e33d3-154">Por lo tanto, en la mayoría de los casos no necesita la palabra clave `Partial`.</span><span class="sxs-lookup"><span data-stu-id="e33d3-154">Therefore, in most cases you do not need the `Partial` keyword.</span></span>  
  
-   <span data-ttu-id="e33d3-155">Para mejorar la legibilidad, cada declaración parcial de un tipo debe incluir la palabra clave `Partial`.</span><span class="sxs-lookup"><span data-stu-id="e33d3-155">For readability, every partial declaration of a type should include the `Partial` keyword.</span></span> <span data-ttu-id="e33d3-156">El compilador permite a lo sumo una declaración parcial para omitir la palabra clave; si hay dos o más que la omiten, el compilador señala un error.</span><span class="sxs-lookup"><span data-stu-id="e33d3-156">The compiler allows at most one partial declaration to omit the keyword; if two or more omit it the compiler signals an error.</span></span>  
  
## <a name="behavior"></a><span data-ttu-id="e33d3-157">Comportamiento</span><span class="sxs-lookup"><span data-stu-id="e33d3-157">Behavior</span></span>  
  
-   <span data-ttu-id="e33d3-158">**Unión de declaraciones.**</span><span class="sxs-lookup"><span data-stu-id="e33d3-158">**Union of Declarations.**</span></span> <span data-ttu-id="e33d3-159">El compilador trata el tipo como la unión de todas sus declaraciones parciales.</span><span class="sxs-lookup"><span data-stu-id="e33d3-159">The compiler treats the type as the union of all its partial declarations.</span></span> <span data-ttu-id="e33d3-160">Todos los modificadores de todas las definiciones parciales se aplican a todo el tipo; además, todos los miembros de todas las definiciones parciales están disponibles para todo el tipo.</span><span class="sxs-lookup"><span data-stu-id="e33d3-160">Every modifier from every partial definition applies to the entire type, and every member from every partial definition is available to the entire type.</span></span>  
  
-   <span data-ttu-id="e33d3-161">**Promoción de tipos no permitida para los tipos parciales en módulos.**</span><span class="sxs-lookup"><span data-stu-id="e33d3-161">**Type Promotion Not Allowed For Partial Types in Modules.**</span></span> <span data-ttu-id="e33d3-162">Si una definición parcial está dentro de un módulo, se rechaza automáticamente la promoción de tipos de ese tipo.</span><span class="sxs-lookup"><span data-stu-id="e33d3-162">If a partial definition is inside a module, type promotion of that type is automatically defeated.</span></span> <span data-ttu-id="e33d3-163">En este caso, un conjunto de definiciones parciales puede producir resultados inesperados e incluso errores del compilador.</span><span class="sxs-lookup"><span data-stu-id="e33d3-163">In such a case, a set of partial definitions can cause unexpected results and even compiler errors.</span></span> <span data-ttu-id="e33d3-164">Para obtener más información, consulte [promoción de tipos](../../../visual-basic/programming-guide/language-features/declared-elements/type-promotion.md).</span><span class="sxs-lookup"><span data-stu-id="e33d3-164">For more information, see [Type Promotion](../../../visual-basic/programming-guide/language-features/declared-elements/type-promotion.md).</span></span>  
  
     <span data-ttu-id="e33d3-165">El compilador solo combina las definiciones parciales cuando sus rutas de acceso completas son idénticas.</span><span class="sxs-lookup"><span data-stu-id="e33d3-165">The compiler merges partial definitions only when their fully qualified paths are identical.</span></span>  
  
 <span data-ttu-id="e33d3-166">La palabra clave `Partial` se puede usar en los siguientes contextos:</span><span class="sxs-lookup"><span data-stu-id="e33d3-166">The `Partial` keyword can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="e33d3-167">Class (instrucción)</span><span class="sxs-lookup"><span data-stu-id="e33d3-167">Class Statement</span></span>](../../../visual-basic/language-reference/statements/class-statement.md)  
  
 [<span data-ttu-id="e33d3-168">Structure (instrucción)</span><span class="sxs-lookup"><span data-stu-id="e33d3-168">Structure Statement</span></span>](../../../visual-basic/language-reference/statements/structure-statement.md)  
  
## <a name="example"></a><span data-ttu-id="e33d3-169">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e33d3-169">Example</span></span>  
 <span data-ttu-id="e33d3-170">En el ejemplo siguiente se divide la definición de la clase `sampleClass` en dos declaraciones, cada una de las cuales define otro procedimiento `Sub`.</span><span class="sxs-lookup"><span data-stu-id="e33d3-170">The following example splits the definition of class `sampleClass` into two declarations, each of which defines a different `Sub` procedure.</span></span>  
  
 [!code-vb[VbVbalrKeywords#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class1.vb#3)]  
  
 <span data-ttu-id="e33d3-171">Las dos definiciones parciales del ejemplo anterior podrían estar en el mismo archivo de origen o en dos archivos distintos.</span><span class="sxs-lookup"><span data-stu-id="e33d3-171">The two partial definitions in the preceding example could be in the same source file or in two different source files.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e33d3-172">Vea también</span><span class="sxs-lookup"><span data-stu-id="e33d3-172">See also</span></span>

- [<span data-ttu-id="e33d3-173">Class (instrucción)</span><span class="sxs-lookup"><span data-stu-id="e33d3-173">Class Statement</span></span>](../../../visual-basic/language-reference/statements/class-statement.md)
- [<span data-ttu-id="e33d3-174">Structure (instrucción)</span><span class="sxs-lookup"><span data-stu-id="e33d3-174">Structure Statement</span></span>](../../../visual-basic/language-reference/statements/structure-statement.md)
- [<span data-ttu-id="e33d3-175">Promoción de tipos</span><span class="sxs-lookup"><span data-stu-id="e33d3-175">Type Promotion</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/type-promotion.md)
- [<span data-ttu-id="e33d3-176">Shadows</span><span class="sxs-lookup"><span data-stu-id="e33d3-176">Shadows</span></span>](../../../visual-basic/language-reference/modifiers/shadows.md)
- [<span data-ttu-id="e33d3-177">Generic Types in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="e33d3-177">Generic Types in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)
- [<span data-ttu-id="e33d3-178">Métodos Partial</span><span class="sxs-lookup"><span data-stu-id="e33d3-178">Partial Methods</span></span>](../../../visual-basic/programming-guide/language-features/procedures/partial-methods.md)
