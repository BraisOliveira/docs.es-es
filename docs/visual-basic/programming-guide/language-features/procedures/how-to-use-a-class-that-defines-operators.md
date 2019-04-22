---
title: Procedimiento Usar una clase que define operadores (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- operator procedures [Visual Basic], calling
- procedures [Visual Basic], operator
- procedures [Visual Basic], calling
- examples [Visual Basic], CType
- syntax [Visual Basic], Operator procedures
- operators [Visual Basic], overloading
- return values [Visual Basic], Operator procedures
- operator overloading
ms.assetid: 7ccce94a-6ca0-47d1-9f3f-13385d34f5d5
ms.openlocfilehash: bd512adf2f06ed0fbd3d36ed3175a0928bf1c57c
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "58829413"
---
# <a name="how-to-use-a-class-that-defines-operators-visual-basic"></a><span data-ttu-id="c0f54-102">Procedimiento Usar una clase que define operadores (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c0f54-102">How to: Use a Class that Defines Operators (Visual Basic)</span></span>
<span data-ttu-id="c0f54-103">Si utiliza una clase o estructura que define sus propios operadores, puede tener acceso a esos operadores desde Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="c0f54-103">If you are using a class or structure that defines its own operators, you can access those operators from Visual Basic.</span></span>  
  
 <span data-ttu-id="c0f54-104">Definir un operador en una clase o estructura también se denomina *sobrecarga* el operador.</span><span class="sxs-lookup"><span data-stu-id="c0f54-104">Defining an operator on a class or structure is also called *overloading* the operator.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c0f54-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c0f54-105">Example</span></span>  
 <span data-ttu-id="c0f54-106">El ejemplo siguiente se obtiene acceso a la estructura SQL <xref:System.Data.SqlTypes.SqlString>, que define los operadores de conversión ([CType Function](../../../../visual-basic/language-reference/functions/ctype-function.md)) en ambas direcciones entre una cadena SQL y una cadena de Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="c0f54-106">The following example accesses the SQL structure <xref:System.Data.SqlTypes.SqlString>, which defines the conversion operators ([CType Function](../../../../visual-basic/language-reference/functions/ctype-function.md)) in both directions between a SQL string and a Visual Basic string.</span></span> <span data-ttu-id="c0f54-107">Use `CType(` *expresión de cadena SQL*, `String)` para convertir una cadena SQL en una cadena de Visual Basic y `CType(` *expresión de cadena de Visual Basic*, <xref:System.Data.SqlTypes.SqlString> `)` para convertir en la otra dirección.</span><span class="sxs-lookup"><span data-stu-id="c0f54-107">Use `CType(`*SQL string expression*, `String)` to convert a SQL string to a Visual Basic string, and `CType(`*Visual Basic string expression*, <xref:System.Data.SqlTypes.SqlString>`)` to convert in the other direction.</span></span>  
  
 [!code-vb[VbVbcnProcedures#30](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#30)]  
  
 [!code-vb[VbVbcnProcedures#31](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#31)]  
  
 <span data-ttu-id="c0f54-108">El <xref:System.Data.SqlTypes.SqlString> estructura define un operador de conversión ([CType Function](../../../../visual-basic/language-reference/functions/ctype-function.md)) desde `String` a <xref:System.Data.SqlTypes.SqlString> y otro de <xref:System.Data.SqlTypes.SqlString> a `String`.</span><span class="sxs-lookup"><span data-stu-id="c0f54-108">The <xref:System.Data.SqlTypes.SqlString> structure defines a conversion operator ([CType Function](../../../../visual-basic/language-reference/functions/ctype-function.md)) from `String` to <xref:System.Data.SqlTypes.SqlString> and another from <xref:System.Data.SqlTypes.SqlString> to `String`.</span></span> <span data-ttu-id="c0f54-109">La instrucción que asigna `title` a `jobTitle` usa el primer operador y el <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A> llamada de función usa la segunda.</span><span class="sxs-lookup"><span data-stu-id="c0f54-109">The statement that assigns `title` to `jobTitle` makes use of the first operator, and the <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A> function call uses the second.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="c0f54-110">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="c0f54-110">Compiling the Code</span></span>  
 <span data-ttu-id="c0f54-111">Asegúrese de que la clase o estructura que está utilizando define el operador que desea usar.</span><span class="sxs-lookup"><span data-stu-id="c0f54-111">Be sure the class or structure you are using defines the operator you want to use.</span></span> <span data-ttu-id="c0f54-112">No suponga que la clase o estructura ha definido todos los operadores disponibles para la sobrecarga.</span><span class="sxs-lookup"><span data-stu-id="c0f54-112">Do not assume that the class or structure has defined every operator available for overloading.</span></span> <span data-ttu-id="c0f54-113">Para obtener una lista de operadores disponibles, vea [Operator (instrucción)](../../../../visual-basic/language-reference/statements/operator-statement.md).</span><span class="sxs-lookup"><span data-stu-id="c0f54-113">For a list of available operators, see [Operator Statement](../../../../visual-basic/language-reference/statements/operator-statement.md).</span></span>  
  
 <span data-ttu-id="c0f54-114">Incluir adecuado `Imports` instrucción para la cadena SQL al principio del archivo de origen (en este caso <xref:System.Data.SqlTypes>).</span><span class="sxs-lookup"><span data-stu-id="c0f54-114">Include the appropriate `Imports` statement for the SQL string at the beginning of your source file (in this case <xref:System.Data.SqlTypes>).</span></span>  
  
 <span data-ttu-id="c0f54-115">El proyecto debe tener referencias a System.Data y System.XML.</span><span class="sxs-lookup"><span data-stu-id="c0f54-115">Your project must have references to System.Data and System.XML.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c0f54-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="c0f54-116">See also</span></span>

- [<span data-ttu-id="c0f54-117">Procedimientos de operadores</span><span class="sxs-lookup"><span data-stu-id="c0f54-117">Operator Procedures</span></span>](./operator-procedures.md)
- [<span data-ttu-id="c0f54-118">Cómo: Definir un operador</span><span class="sxs-lookup"><span data-stu-id="c0f54-118">How to: Define an Operator</span></span>](./how-to-define-an-operator.md)
- [<span data-ttu-id="c0f54-119">Cómo: Definir un operador de conversión</span><span class="sxs-lookup"><span data-stu-id="c0f54-119">How to: Define a Conversion Operator</span></span>](./how-to-define-a-conversion-operator.md)
- [<span data-ttu-id="c0f54-120">Cómo: Llamar a un procedimiento de operador</span><span class="sxs-lookup"><span data-stu-id="c0f54-120">How to: Call an Operator Procedure</span></span>](./how-to-call-an-operator-procedure.md)
- [<span data-ttu-id="c0f54-121">Widening</span><span class="sxs-lookup"><span data-stu-id="c0f54-121">Widening</span></span>](../../../../visual-basic/language-reference/modifiers/widening.md)
- [<span data-ttu-id="c0f54-122">Narrowing</span><span class="sxs-lookup"><span data-stu-id="c0f54-122">Narrowing</span></span>](../../../../visual-basic/language-reference/modifiers/narrowing.md)
- [<span data-ttu-id="c0f54-123">Structure (instrucción)</span><span class="sxs-lookup"><span data-stu-id="c0f54-123">Structure Statement</span></span>](../../../../visual-basic/language-reference/statements/structure-statement.md)
- [<span data-ttu-id="c0f54-124">Cómo: Declarar una estructura</span><span class="sxs-lookup"><span data-stu-id="c0f54-124">How to: Declare a Structure</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)
- [<span data-ttu-id="c0f54-125">Conversiones implícitas y explícitas</span><span class="sxs-lookup"><span data-stu-id="c0f54-125">Implicit and Explicit Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
- [<span data-ttu-id="c0f54-126">Conversiones de ampliación y de restricción</span><span class="sxs-lookup"><span data-stu-id="c0f54-126">Widening and Narrowing Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
