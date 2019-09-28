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
ms.openlocfilehash: acfe47f52ede289093b3554a7dd190ef3f0e2c80
ms.sourcegitcommit: 35da8fb45b4cca4e59cc99a5c56262c356977159
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/28/2019
ms.locfileid: "71592113"
---
# <a name="partial-visual-basic"></a><span data-ttu-id="73742-102">Partial (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="73742-102">Partial (Visual Basic)</span></span>
<span data-ttu-id="73742-103">Indica que una declaración de tipo es una definición parcial del tipo.</span><span class="sxs-lookup"><span data-stu-id="73742-103">Indicates that a type declaration is a partial definition of the type.</span></span>  
  
 <span data-ttu-id="73742-104">Puede dividir la definición de un tipo en varias declaraciones con la palabra clave `Partial`.</span><span class="sxs-lookup"><span data-stu-id="73742-104">You can divide the definition of a type among several declarations by using the `Partial` keyword.</span></span> <span data-ttu-id="73742-105">Puede usar todas las declaraciones parciales que quiera en todos los archivos de código fuente que desee,</span><span class="sxs-lookup"><span data-stu-id="73742-105">You can use as many partial declarations as you want, in as many different source files as you want.</span></span> <span data-ttu-id="73742-106">pero todas las declaraciones deben estar en el mismo ensamblado y en el mismo espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="73742-106">However, all the declarations must be in the same assembly and the same namespace.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="73742-107">Visual Basic admite *métodos parciales*, que normalmente se implementan en clases parciales.</span><span class="sxs-lookup"><span data-stu-id="73742-107">Visual Basic supports *partial methods*, which are typically implemented in partial classes.</span></span> <span data-ttu-id="73742-108">Para obtener más información, vea [métodos parciales](../../../visual-basic/programming-guide/language-features/procedures/partial-methods.md) y [Sub Statement](../../../visual-basic/language-reference/statements/sub-statement.md).</span><span class="sxs-lookup"><span data-stu-id="73742-108">For more information, see [Partial Methods](../../../visual-basic/programming-guide/language-features/procedures/partial-methods.md) and [Sub Statement](../../../visual-basic/language-reference/statements/sub-statement.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="73742-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="73742-109">Syntax</span></span>  
  
```vb  
[ <attrlist> ] [ accessmodifier ] [ Shadows ] [ MustInherit | NotInheritable ] _  
Partial { Class | Structure | Interface | Module } name [ (Of typelist) ]  
    [ Inherits classname ]  
    [ Implements interfacenames ]  
    [ variabledeclarations ]  
    [ proceduredeclarations ]  
{ End Class | End Structure }  
```  
  
## <a name="parts"></a><span data-ttu-id="73742-110">Elementos</span><span class="sxs-lookup"><span data-stu-id="73742-110">Parts</span></span>  
  
|<span data-ttu-id="73742-111">Término</span><span class="sxs-lookup"><span data-stu-id="73742-111">Term</span></span>|<span data-ttu-id="73742-112">Definición</span><span class="sxs-lookup"><span data-stu-id="73742-112">Definition</span></span>|  
|---|---|  
|`attrlist`|<span data-ttu-id="73742-113">Opcional.</span><span class="sxs-lookup"><span data-stu-id="73742-113">Optional.</span></span> <span data-ttu-id="73742-114">Lista de atributos que se aplican a este tipo.</span><span class="sxs-lookup"><span data-stu-id="73742-114">List of attributes that apply to this type.</span></span> <span data-ttu-id="73742-115">Debe incluir la [lista de atributos](../../../visual-basic/language-reference/statements/attribute-list.md) entre corchetes angulares (`< >`).</span><span class="sxs-lookup"><span data-stu-id="73742-115">You must enclose the [Attribute List](../../../visual-basic/language-reference/statements/attribute-list.md) in angle brackets (`< >`).</span></span>|  
|`accessmodifier`|<span data-ttu-id="73742-116">Opcional.</span><span class="sxs-lookup"><span data-stu-id="73742-116">Optional.</span></span> <span data-ttu-id="73742-117">Especifica qué código puede tener acceso a este tipo.</span><span class="sxs-lookup"><span data-stu-id="73742-117">Specifies what code can access this type.</span></span> <span data-ttu-id="73742-118">Vea [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="73742-118">See [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>|  
|`Shadows`|<span data-ttu-id="73742-119">Opcional.</span><span class="sxs-lookup"><span data-stu-id="73742-119">Optional.</span></span> <span data-ttu-id="73742-120">Vea [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md).</span><span class="sxs-lookup"><span data-stu-id="73742-120">See [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md).</span></span>|  
|`MustInherit`|<span data-ttu-id="73742-121">Opcional.</span><span class="sxs-lookup"><span data-stu-id="73742-121">Optional.</span></span> <span data-ttu-id="73742-122">Vea [MustInherit](../../../visual-basic/language-reference/modifiers/mustinherit.md).</span><span class="sxs-lookup"><span data-stu-id="73742-122">See [MustInherit](../../../visual-basic/language-reference/modifiers/mustinherit.md).</span></span>|  
|`NotInheritable`|<span data-ttu-id="73742-123">Opcional.</span><span class="sxs-lookup"><span data-stu-id="73742-123">Optional.</span></span> <span data-ttu-id="73742-124">Vea [NotInheritable](../../../visual-basic/language-reference/modifiers/notinheritable.md).</span><span class="sxs-lookup"><span data-stu-id="73742-124">See [NotInheritable](../../../visual-basic/language-reference/modifiers/notinheritable.md).</span></span>|  
|`name`|<span data-ttu-id="73742-125">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="73742-125">Required.</span></span> <span data-ttu-id="73742-126">Nombre de este tipo.</span><span class="sxs-lookup"><span data-stu-id="73742-126">Name of this type.</span></span> <span data-ttu-id="73742-127">Debe coincidir con el nombre definido en el resto de las declaraciones parciales del mismo tipo.</span><span class="sxs-lookup"><span data-stu-id="73742-127">Must match the name defined in all other partial declarations of the same type.</span></span>|  
|`Of`|<span data-ttu-id="73742-128">Opcional.</span><span class="sxs-lookup"><span data-stu-id="73742-128">Optional.</span></span> <span data-ttu-id="73742-129">Especifica que se trata de un tipo genérico.</span><span class="sxs-lookup"><span data-stu-id="73742-129">Specifies that this is a generic type.</span></span> <span data-ttu-id="73742-130">Vea [tipos genéricos en Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md).</span><span class="sxs-lookup"><span data-stu-id="73742-130">See [Generic Types in Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md).</span></span>|  
|`typelist`|<span data-ttu-id="73742-131">Obligatorio si se usa [de](../../../visual-basic/language-reference/statements/of-clause.md).</span><span class="sxs-lookup"><span data-stu-id="73742-131">Required if you use [Of](../../../visual-basic/language-reference/statements/of-clause.md).</span></span> <span data-ttu-id="73742-132">Consulte [lista de tipos](../../../visual-basic/language-reference/statements/type-list.md).</span><span class="sxs-lookup"><span data-stu-id="73742-132">See [Type List](../../../visual-basic/language-reference/statements/type-list.md).</span></span>|  
|`Inherits`|<span data-ttu-id="73742-133">Opcional.</span><span class="sxs-lookup"><span data-stu-id="73742-133">Optional.</span></span> <span data-ttu-id="73742-134">Vea [Inherits (instrucción](../../../visual-basic/language-reference/statements/inherits-statement.md)).</span><span class="sxs-lookup"><span data-stu-id="73742-134">See [Inherits Statement](../../../visual-basic/language-reference/statements/inherits-statement.md).</span></span>|  
|`classname`|<span data-ttu-id="73742-135">Obligatorio si se usa `Inherits`.</span><span class="sxs-lookup"><span data-stu-id="73742-135">Required if you use `Inherits`.</span></span> <span data-ttu-id="73742-136">El nombre de la clase o la interfaz de la que se deriva esta clase.</span><span class="sxs-lookup"><span data-stu-id="73742-136">The name of the class or interface from which this class derives.</span></span>|  
|`Implements`|<span data-ttu-id="73742-137">Opcional.</span><span class="sxs-lookup"><span data-stu-id="73742-137">Optional.</span></span> <span data-ttu-id="73742-138">Vea [Implements (instrucción](../../../visual-basic/language-reference/statements/implements-statement.md)).</span><span class="sxs-lookup"><span data-stu-id="73742-138">See [Implements Statement](../../../visual-basic/language-reference/statements/implements-statement.md).</span></span>|  
|`interfacenames`|<span data-ttu-id="73742-139">Obligatorio si se usa `Implements`.</span><span class="sxs-lookup"><span data-stu-id="73742-139">Required if you use `Implements`.</span></span> <span data-ttu-id="73742-140">Los nombres de las interfaces que implementa este tipo.</span><span class="sxs-lookup"><span data-stu-id="73742-140">The names of the interfaces this type implements.</span></span>|  
|`variabledeclarations`|<span data-ttu-id="73742-141">Opcional.</span><span class="sxs-lookup"><span data-stu-id="73742-141">Optional.</span></span> <span data-ttu-id="73742-142">Instrucciones que declaran variables adicionales y eventos para el tipo.</span><span class="sxs-lookup"><span data-stu-id="73742-142">Statements which declare additional variables and events for the type.</span></span>|  
|`proceduredeclarations`|<span data-ttu-id="73742-143">Opcional.</span><span class="sxs-lookup"><span data-stu-id="73742-143">Optional.</span></span> <span data-ttu-id="73742-144">Instrucciones que declaran y definen procedimientos adicionales para el tipo.</span><span class="sxs-lookup"><span data-stu-id="73742-144">Statements which declare and define additional procedures for the type.</span></span>|  
|<span data-ttu-id="73742-145">`End Class` o `End Structure`</span><span class="sxs-lookup"><span data-stu-id="73742-145">`End Class` or `End Structure`</span></span>|<span data-ttu-id="73742-146">Finaliza esta definición `Class` o `Structure` parcial.</span><span class="sxs-lookup"><span data-stu-id="73742-146">Ends this partial `Class` or `Structure` definition.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="73742-147">Comentarios</span><span class="sxs-lookup"><span data-stu-id="73742-147">Remarks</span></span>  
 <span data-ttu-id="73742-148">Visual Basic usa definiciones de clase parcial para separar el código generado del código creado por el usuario en archivos de código fuente independientes.</span><span class="sxs-lookup"><span data-stu-id="73742-148">Visual Basic uses partial-class definitions to separate generated code from user-authored code in separate source files.</span></span> <span data-ttu-id="73742-149">Por ejemplo, el **Diseñador de Windows Forms<xref:System.Windows.Forms.Form> define clases parciales para controles como** .</span><span class="sxs-lookup"><span data-stu-id="73742-149">For example, the **Windows Form Designer** defines partial classes for controls such as <xref:System.Windows.Forms.Form>.</span></span> <span data-ttu-id="73742-150">No debe modificar el código generado en estos controles.</span><span class="sxs-lookup"><span data-stu-id="73742-150">You should not modify the generated code in these controls.</span></span>  
  
 <span data-ttu-id="73742-151">Todas las reglas para crear clases, estructuras, interfaces y módulos, como las reglas de uso y herencia de modificadores, se aplican al crear un tipo parcial.</span><span class="sxs-lookup"><span data-stu-id="73742-151">All the rules for class, structure, interface, and module creation, such as those for modifier usage and inheritance, apply when creating a partial type.</span></span>  
  
## <a name="best-practices"></a><span data-ttu-id="73742-152">Procedimientos recomendados</span><span class="sxs-lookup"><span data-stu-id="73742-152">Best Practices</span></span>  
  
- <span data-ttu-id="73742-153">En circunstancias normales no debe dividir el desarrollo de un solo tipo en dos o más declaraciones.</span><span class="sxs-lookup"><span data-stu-id="73742-153">Under normal circumstances, you should not split the development of a single type across two or more declarations.</span></span> <span data-ttu-id="73742-154">Por lo tanto, en la mayoría de los casos no necesita la palabra clave `Partial`.</span><span class="sxs-lookup"><span data-stu-id="73742-154">Therefore, in most cases you do not need the `Partial` keyword.</span></span>  
  
- <span data-ttu-id="73742-155">Para mejorar la legibilidad, cada declaración parcial de un tipo debe incluir la palabra clave `Partial`.</span><span class="sxs-lookup"><span data-stu-id="73742-155">For readability, every partial declaration of a type should include the `Partial` keyword.</span></span> <span data-ttu-id="73742-156">El compilador permite a lo sumo una declaración parcial para omitir la palabra clave; si hay dos o más que la omiten, el compilador señala un error.</span><span class="sxs-lookup"><span data-stu-id="73742-156">The compiler allows at most one partial declaration to omit the keyword; if two or more omit it the compiler signals an error.</span></span>  
  
## <a name="behavior"></a><span data-ttu-id="73742-157">Comportamiento</span><span class="sxs-lookup"><span data-stu-id="73742-157">Behavior</span></span>  
  
- <span data-ttu-id="73742-158">**Unión de declaraciones.**</span><span class="sxs-lookup"><span data-stu-id="73742-158">**Union of Declarations.**</span></span> <span data-ttu-id="73742-159">El compilador trata el tipo como la unión de todas sus declaraciones parciales.</span><span class="sxs-lookup"><span data-stu-id="73742-159">The compiler treats the type as the union of all its partial declarations.</span></span> <span data-ttu-id="73742-160">Todos los modificadores de todas las definiciones parciales se aplican a todo el tipo; además, todos los miembros de todas las definiciones parciales están disponibles para todo el tipo.</span><span class="sxs-lookup"><span data-stu-id="73742-160">Every modifier from every partial definition applies to the entire type, and every member from every partial definition is available to the entire type.</span></span>  
  
- <span data-ttu-id="73742-161">**Promoción de tipos no permitida para tipos parciales en módulos.**</span><span class="sxs-lookup"><span data-stu-id="73742-161">**Type Promotion Not Allowed For Partial Types in Modules.**</span></span> <span data-ttu-id="73742-162">Si una definición parcial está dentro de un módulo, se rechaza automáticamente la promoción de tipos de ese tipo.</span><span class="sxs-lookup"><span data-stu-id="73742-162">If a partial definition is inside a module, type promotion of that type is automatically defeated.</span></span> <span data-ttu-id="73742-163">En este caso, un conjunto de definiciones parciales puede producir resultados inesperados e incluso errores del compilador.</span><span class="sxs-lookup"><span data-stu-id="73742-163">In such a case, a set of partial definitions can cause unexpected results and even compiler errors.</span></span> <span data-ttu-id="73742-164">Para obtener más información, consulte [promoción de tipos](../../../visual-basic/programming-guide/language-features/declared-elements/type-promotion.md).</span><span class="sxs-lookup"><span data-stu-id="73742-164">For more information, see [Type Promotion](../../../visual-basic/programming-guide/language-features/declared-elements/type-promotion.md).</span></span>  
  
     <span data-ttu-id="73742-165">El compilador solo combina las definiciones parciales cuando sus rutas de acceso completas son idénticas.</span><span class="sxs-lookup"><span data-stu-id="73742-165">The compiler merges partial definitions only when their fully qualified paths are identical.</span></span>  
  
 <span data-ttu-id="73742-166">La palabra clave `Partial` se puede usar en los siguientes contextos:</span><span class="sxs-lookup"><span data-stu-id="73742-166">The `Partial` keyword can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="73742-167">Class (instrucción)</span><span class="sxs-lookup"><span data-stu-id="73742-167">Class Statement</span></span>](../../../visual-basic/language-reference/statements/class-statement.md)  
  
 [<span data-ttu-id="73742-168">Structure (instrucción)</span><span class="sxs-lookup"><span data-stu-id="73742-168">Structure Statement</span></span>](../../../visual-basic/language-reference/statements/structure-statement.md)  
  
## <a name="example"></a><span data-ttu-id="73742-169">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="73742-169">Example</span></span>  
 <span data-ttu-id="73742-170">En el ejemplo siguiente se divide la definición de la clase `sampleClass` en dos declaraciones, cada una de las cuales define otro procedimiento `Sub`.</span><span class="sxs-lookup"><span data-stu-id="73742-170">The following example splits the definition of class `sampleClass` into two declarations, each of which defines a different `Sub` procedure.</span></span>  
  
 [!code-vb[VbVbalrKeywords#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class1.vb#3)]  
  
 <span data-ttu-id="73742-171">Las dos definiciones parciales del ejemplo anterior podrían estar en el mismo archivo de origen o en dos archivos distintos.</span><span class="sxs-lookup"><span data-stu-id="73742-171">The two partial definitions in the preceding example could be in the same source file or in two different source files.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="73742-172">Vea también</span><span class="sxs-lookup"><span data-stu-id="73742-172">See also</span></span>

- [<span data-ttu-id="73742-173">Class (instrucción)</span><span class="sxs-lookup"><span data-stu-id="73742-173">Class Statement</span></span>](../../../visual-basic/language-reference/statements/class-statement.md)
- [<span data-ttu-id="73742-174">Structure (instrucción)</span><span class="sxs-lookup"><span data-stu-id="73742-174">Structure Statement</span></span>](../../../visual-basic/language-reference/statements/structure-statement.md)
- [<span data-ttu-id="73742-175">Promoción de tipos</span><span class="sxs-lookup"><span data-stu-id="73742-175">Type Promotion</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/type-promotion.md)
- [<span data-ttu-id="73742-176">Shadows</span><span class="sxs-lookup"><span data-stu-id="73742-176">Shadows</span></span>](../../../visual-basic/language-reference/modifiers/shadows.md)
- [<span data-ttu-id="73742-177">Generic Types in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="73742-177">Generic Types in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)
- [<span data-ttu-id="73742-178">Métodos Partial</span><span class="sxs-lookup"><span data-stu-id="73742-178">Partial Methods</span></span>](../../../visual-basic/programming-guide/language-features/procedures/partial-methods.md)
