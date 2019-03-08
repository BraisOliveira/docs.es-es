---
title: Propiedades sobrecargadas y métodos (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- properties [Visual Basic], overloading
- methods [Visual Basic], overloading
- shadowing
- names [Visual Basic], multiple procedures with same
- procedures [Visual Basic], multiples with same name
- classes [Visual Basic], properties
- classes [Visual Basic], methods
- method overloading
- Overloads keyword [Visual Basic], overloaded members
ms.assetid: b686fb97-e7d7-4001-afaa-6650cba08f0d
ms.openlocfilehash: 8d7341370d9770d2e57f786ac7c68277e66a9bbd
ms.sourcegitcommit: 58fc0e6564a37fa1b9b1b140a637e864c4cf696e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/08/2019
ms.locfileid: "57677401"
---
# <a name="overloaded-properties-and-methods-visual-basic"></a><span data-ttu-id="dd03c-102">Propiedades sobrecargadas y métodos (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="dd03c-102">Overloaded properties and methods (Visual Basic)</span></span>

<span data-ttu-id="dd03c-103">La sobrecarga es la creación de más de un procedimiento, constructor de instancia o propiedad en una clase con el mismo nombre pero con distintos tipos de argumento.</span><span class="sxs-lookup"><span data-stu-id="dd03c-103">Overloading is the creation of more than one procedure, instance constructor, or property in a class with the same name but different argument types.</span></span>

## <a name="overloading-usage"></a><span data-ttu-id="dd03c-104">Uso de la sobrecarga</span><span class="sxs-lookup"><span data-stu-id="dd03c-104">Overloading usage</span></span>

<span data-ttu-id="dd03c-105">Sobrecarga es especialmente útil cuando el modelo de objeto exige el uso de nombres idénticos para los procedimientos que operan en distintos tipos de datos.</span><span class="sxs-lookup"><span data-stu-id="dd03c-105">Overloading is especially useful when your object model dictates that you employ identical names for procedures that operate on different data types.</span></span> <span data-ttu-id="dd03c-106">Por ejemplo, podría tener una clase que puede mostrar diferentes tipos de datos `Display` procedimientos que tienen un aspecto similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="dd03c-106">For example, a class that can display several different data types could have `Display` procedures that look like this:</span></span>

[!code-vb[VbVbalrOOP#64](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#64)]

<span data-ttu-id="dd03c-107">Sin sobrecarga, sería necesario crear nombres distintos para cada procedimiento, aunque lo hacen lo mismo, tal como se muestra a continuación:</span><span class="sxs-lookup"><span data-stu-id="dd03c-107">Without overloading, you would need to create distinct names for each procedure, even though they do the same thing, as shown next:</span></span>

[!code-vb[VbVbalrOOP#65](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#65)]

<span data-ttu-id="dd03c-108">Sobrecarga hace más fácil de usar los métodos o propiedades porque proporciona una opción de tipos de datos que se puede usar.</span><span class="sxs-lookup"><span data-stu-id="dd03c-108">Overloading makes it easier to use properties or methods because it provides a choice of data types that can be used.</span></span> <span data-ttu-id="dd03c-109">Por ejemplo, el sobrecargado `Display` método descrito anteriormente se puede llamar con cualquiera de las siguientes líneas de código:</span><span class="sxs-lookup"><span data-stu-id="dd03c-109">For example, the overloaded `Display` method discussed previously can be called with any of the following lines of code:</span></span>

[!code-vb[VbVbalrOOP#66](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#66)]

<span data-ttu-id="dd03c-110">En tiempo de ejecución, Visual Basic llama al procedimiento correcto basándose en los tipos de datos de los parámetros especificados.</span><span class="sxs-lookup"><span data-stu-id="dd03c-110">At run time, Visual Basic calls the correct procedure based on the data types of the parameters you specify.</span></span>

## <a name="overloading-rules"></a><span data-ttu-id="dd03c-111">Reglas de sobrecarga</span><span class="sxs-lookup"><span data-stu-id="dd03c-111">Overloading rules</span></span>

 <span data-ttu-id="dd03c-112">Crear a un miembro sobrecargado para una clase mediante la adición de dos o más propiedades o métodos con el mismo nombre.</span><span class="sxs-lookup"><span data-stu-id="dd03c-112">You create an overloaded member for a class by adding two or more properties or methods with the same name.</span></span> <span data-ttu-id="dd03c-113">Excepto para los miembros derivados sobrecargados, cada miembro sobrecargado debe tener distintas listas de parámetros y los elementos siguientes no se puede usar como una característica distintiva cuando sobrecargue un procedimiento o propiedad:</span><span class="sxs-lookup"><span data-stu-id="dd03c-113">Except for overloaded derived members, each overloaded member must have different parameter lists, and the following items cannot be used as a differentiating feature when overloading a property or procedure:</span></span>

- <span data-ttu-id="dd03c-114">Modificadores, como `ByVal` o `ByRef`, que se aplican a un miembro o los parámetros del miembro.</span><span class="sxs-lookup"><span data-stu-id="dd03c-114">Modifiers, such as `ByVal` or `ByRef`, that apply to a member, or parameters of the member.</span></span>

- <span data-ttu-id="dd03c-115">Nombres de parámetros</span><span class="sxs-lookup"><span data-stu-id="dd03c-115">Names of parameters</span></span>

- <span data-ttu-id="dd03c-116">Tipos de valor devuelto de procedimientos</span><span class="sxs-lookup"><span data-stu-id="dd03c-116">Return types of procedures</span></span>

<span data-ttu-id="dd03c-117">El `Overloads` palabra clave es opcional cuando sobrecargue un procedimiento, pero si alguna sobrecarga miembro usa la `Overloads` palabra clave y, a continuación, todos los demás miembros sobrecargados con el mismo nombre también deben especificar esta palabra clave.</span><span class="sxs-lookup"><span data-stu-id="dd03c-117">The `Overloads` keyword is optional when overloading, but if any overloaded member uses the `Overloads` keyword, then all other overloaded members with the same name must also specify this keyword.</span></span>

<span data-ttu-id="dd03c-118">Las clases derivadas pueden sobrecargar los miembros heredados con miembros que tienen parámetros idénticos y los tipos de parámetro, un proceso conocido como *sombrear por nombre y firma*.</span><span class="sxs-lookup"><span data-stu-id="dd03c-118">Derived classes can overload inherited members with members that have identical parameters and parameter types, a process known as *shadowing by name and signature*.</span></span> <span data-ttu-id="dd03c-119">Si el `Overloads` palabra clave se usa cuando el sombreado por nombre y firma, implementación de la clase derivada del miembro se usará en lugar de la implementación de la clase base y todas las demás sobrecargas para ese miembro estará disponibles para las instancias de la clase derivada.</span><span class="sxs-lookup"><span data-stu-id="dd03c-119">If the `Overloads` keyword is used when shadowing by name and signature, the derived class's implementation of the member will be used instead of the implementation in the base class, and all other overloads for that member will be available to instances of the derived class.</span></span>

<span data-ttu-id="dd03c-120">Si el `Overloads` se omite la palabra clave cuando sobrecargue un miembro heredado con un miembro que tiene parámetros y tipos de parámetro idénticos, a continuación, la sobrecarga se denomina *sombrear por nombre*.</span><span class="sxs-lookup"><span data-stu-id="dd03c-120">If the `Overloads` keyword is omitted when overloading an inherited member with a member that has identical parameters and parameter types, then the overloading is called *shadowing by name*.</span></span> <span data-ttu-id="dd03c-121">Sombrear por nombre reemplaza la implementación heredada de un miembro y hace que todas las demás sobrecargas que no están disponibles para las instancias de la clase derivada y sus descendientes.</span><span class="sxs-lookup"><span data-stu-id="dd03c-121">Shadowing by name replaces the inherited implementation of a member, and it makes all other overloads unavailable to instances of the derived class and its decedents.</span></span>

<span data-ttu-id="dd03c-122">El `Overloads` y `Shadows` modificadores no pueden utilizarse con la misma propiedad o método.</span><span class="sxs-lookup"><span data-stu-id="dd03c-122">The `Overloads` and `Shadows` modifiers cannot both be used with the same property or method.</span></span>

### <a name="example"></a><span data-ttu-id="dd03c-123">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="dd03c-123">Example</span></span>

<span data-ttu-id="dd03c-124">En el ejemplo siguiente se crea métodos sobrecargados que aceptan un `String` o `Decimal` representación de una cantidad en dólares y devuelven una cadena que contiene los impuestos.</span><span class="sxs-lookup"><span data-stu-id="dd03c-124">The following example creates overloaded methods that accept either a `String` or `Decimal` representation of a dollar amount and return a string containing the sales tax.</span></span>

#### <a name="to-use-this-example-to-create-an-overloaded-method"></a><span data-ttu-id="dd03c-125">Para usar este ejemplo para crear un método sobrecargado</span><span class="sxs-lookup"><span data-stu-id="dd03c-125">To use this example to create an overloaded method</span></span>

1. <span data-ttu-id="dd03c-126">Abra un nuevo proyecto y agregue una clase denominada `TaxClass`.</span><span class="sxs-lookup"><span data-stu-id="dd03c-126">Open a new project and add a class named `TaxClass`.</span></span>

2. <span data-ttu-id="dd03c-127">Agregue el código siguiente a la clase `TaxClass` .</span><span class="sxs-lookup"><span data-stu-id="dd03c-127">Add the following code to the `TaxClass` class.</span></span>

    [!code-vb[VbVbalrOOP#67](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#67)]

3. <span data-ttu-id="dd03c-128">Agregue el siguiente procedimiento para el formulario.</span><span class="sxs-lookup"><span data-stu-id="dd03c-128">Add the following procedure to your form.</span></span>

    [!code-vb[VbVbalrOOP#68](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#68)]

4. <span data-ttu-id="dd03c-129">Agregar un botón a su formulario y llame a la `ShowTax` procedimiento desde el `Button1_Click` eventos del botón.</span><span class="sxs-lookup"><span data-stu-id="dd03c-129">Add a button to your form and call the `ShowTax` procedure from the `Button1_Click` event of the button.</span></span>

5. <span data-ttu-id="dd03c-130">Ejecute el proyecto y haga clic en el botón del formulario para probar sobrecargado `ShowTax` procedimiento.</span><span class="sxs-lookup"><span data-stu-id="dd03c-130">Run the project and click the button on the form to test the overloaded `ShowTax` procedure.</span></span>

<span data-ttu-id="dd03c-131">En tiempo de ejecución, el compilador elige la función sobrecargada adecuada que coincida con los parámetros que se va a usar.</span><span class="sxs-lookup"><span data-stu-id="dd03c-131">At run time, the compiler chooses the appropriate overloaded function that matches the parameters being used.</span></span> <span data-ttu-id="dd03c-132">Al hacer clic en el botón, se llama primero al método sobrecargado con un `Price` parámetro que es una cadena y el mensaje, "precio es una cadena.</span><span class="sxs-lookup"><span data-stu-id="dd03c-132">When you click the button, the overloaded method is called first with a `Price` parameter that is a string and the message, "Price is a String.</span></span> <span data-ttu-id="dd03c-133">Impuestos es $5.12" se muestra.</span><span class="sxs-lookup"><span data-stu-id="dd03c-133">Tax is $5.12" is displayed.</span></span> <span data-ttu-id="dd03c-134">`TaxAmount` se llama con un `Decimal` valor de la segunda vez y el mensaje, "precio es un Decimal.</span><span class="sxs-lookup"><span data-stu-id="dd03c-134">`TaxAmount` is called with a `Decimal` value the second time and the message, "Price is a Decimal.</span></span> <span data-ttu-id="dd03c-135">Impuestos es $5.12" se muestra.</span><span class="sxs-lookup"><span data-stu-id="dd03c-135">Tax is $5.12" is displayed.</span></span>

## <a name="see-also"></a><span data-ttu-id="dd03c-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="dd03c-136">See also</span></span>

- [<span data-ttu-id="dd03c-137">Objetos y clases</span><span class="sxs-lookup"><span data-stu-id="dd03c-137">Objects and Classes</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
- [<span data-ttu-id="dd03c-138">Sombrear en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="dd03c-138">Shadowing in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)
- [<span data-ttu-id="dd03c-139">Sub (instrucción)</span><span class="sxs-lookup"><span data-stu-id="dd03c-139">Sub Statement</span></span>](../../../../visual-basic/language-reference/statements/sub-statement.md)
- [<span data-ttu-id="dd03c-140">Fundamentos de la herencia</span><span class="sxs-lookup"><span data-stu-id="dd03c-140">Inheritance Basics</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
- [<span data-ttu-id="dd03c-141">Shadows</span><span class="sxs-lookup"><span data-stu-id="dd03c-141">Shadows</span></span>](../../../../visual-basic/language-reference/modifiers/shadows.md)
- [<span data-ttu-id="dd03c-142">ByVal</span><span class="sxs-lookup"><span data-stu-id="dd03c-142">ByVal</span></span>](../../../../visual-basic/language-reference/modifiers/byval.md)
- [<span data-ttu-id="dd03c-143">ByRef</span><span class="sxs-lookup"><span data-stu-id="dd03c-143">ByRef</span></span>](../../../../visual-basic/language-reference/modifiers/byref.md)
- [<span data-ttu-id="dd03c-144">Sobrecargas</span><span class="sxs-lookup"><span data-stu-id="dd03c-144">Overloads</span></span>](../../../../visual-basic/language-reference/modifiers/overloads.md)
- [<span data-ttu-id="dd03c-145">Shadows</span><span class="sxs-lookup"><span data-stu-id="dd03c-145">Shadows</span></span>](../../../../visual-basic/language-reference/modifiers/shadows.md)
