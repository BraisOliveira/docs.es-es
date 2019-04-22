---
title: Operadores de concatenación en Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- '& operator [Visual Basic], concatenation'
- concatenation operators [Visual Basic]
- operators [Visual Basic], concatenation
- Visual Basic code, operators
- + operator [Visual Basic], concatenation
- concatenation operators [Visual Basic]
ms.assetid: e59908c3-89e0-41ae-933d-3e8826c16a04
ms.openlocfilehash: 124f0ca0cd01d7fd218fd89dfb78e70fe8aad9e4
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "58835731"
---
# <a name="concatenation-operators-in-visual-basic"></a><span data-ttu-id="9b1c0-102">Operadores de concatenación en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="9b1c0-102">Concatenation Operators in Visual Basic</span></span>
<span data-ttu-id="9b1c0-103">Los operadores de concatenación unen varias cadenas en una sola.</span><span class="sxs-lookup"><span data-stu-id="9b1c0-103">Concatenation operators join multiple strings into a single string.</span></span> <span data-ttu-id="9b1c0-104">Existen dos operadores de concatenación: `+` y `&`.</span><span class="sxs-lookup"><span data-stu-id="9b1c0-104">There are two concatenation operators, `+` and `&`.</span></span> <span data-ttu-id="9b1c0-105">Ambos efectúan la operación de concatenación básica, como se aprecia en el siguiente ejemplo.</span><span class="sxs-lookup"><span data-stu-id="9b1c0-105">Both carry out the basic concatenation operation, as the following example shows.</span></span>  
  
```vb
Dim x As String = "Mic" & "ro" & "soft" 
Dim y As String = "Mic" + "ro" + "soft" 
' The preceding statements set both x and y to "Microsoft".
```  
  
 <span data-ttu-id="9b1c0-106">Estos operadores también concatenan variables de `String`, como indica el siguiente ejemplo.</span><span class="sxs-lookup"><span data-stu-id="9b1c0-106">These operators can also concatenate `String` variables, as the following example shows.</span></span>  
  
 [!code-vb[VbVbalrOperators#76](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#76)]  
  
## <a name="differences-between-the-two-concatenation-operators"></a><span data-ttu-id="9b1c0-107">Diferencias entre los dos operadores de concatenación</span><span class="sxs-lookup"><span data-stu-id="9b1c0-107">Differences Between the Two Concatenation Operators</span></span>  
 <span data-ttu-id="9b1c0-108">El [operador +](../../../../visual-basic/language-reference/operators/addition-operator.md) tiene el propósito principal de sumar dos números.</span><span class="sxs-lookup"><span data-stu-id="9b1c0-108">The [+ Operator](../../../../visual-basic/language-reference/operators/addition-operator.md) has the primary purpose of adding two numbers.</span></span> <span data-ttu-id="9b1c0-109">aunque también puede concatenar operandos numéricos con operandos de cadena.</span><span class="sxs-lookup"><span data-stu-id="9b1c0-109">However, it can also concatenate numeric operands with string operands.</span></span> <span data-ttu-id="9b1c0-110">El operador `+` posee un conjunto de reglas complejo que establecen si hay que sumar, concatenar, señalar un error de compilador o generar una excepción <xref:System.InvalidCastException> en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="9b1c0-110">The `+` operator has a complex set of rules that determine whether to add, concatenate, signal a compiler error, or throw a run-time <xref:System.InvalidCastException> exception.</span></span>  
  
 <span data-ttu-id="9b1c0-111">El [& operador](../../../../visual-basic/language-reference/operators/concatenation-operator.md) sólo se define para `String` operandos y siempre amplía sus operandos a `String`, independientemente de la configuración de `Option Strict`.</span><span class="sxs-lookup"><span data-stu-id="9b1c0-111">The [& Operator](../../../../visual-basic/language-reference/operators/concatenation-operator.md) is defined only for `String` operands, and it always widens its operands to `String`, regardless of the setting of `Option Strict`.</span></span> <span data-ttu-id="9b1c0-112">El uso del operador `&` es recomendable para concatenar cadenas, ya que se está expresamente definido para cadenas y reduce las probabilidades de generar una conversión inintencionada.</span><span class="sxs-lookup"><span data-stu-id="9b1c0-112">The `&` operator is recommended for string concatenation because it is defined exclusively for strings and reduces your chances of generating an unintended conversion.</span></span>  
  
## <a name="performance-string-and-stringbuilder"></a><span data-ttu-id="9b1c0-113">Rendimiento: String y StringBuilder</span><span class="sxs-lookup"><span data-stu-id="9b1c0-113">Performance: String and StringBuilder</span></span>  
 <span data-ttu-id="9b1c0-114">Si realiza una cantidad considerable de manipulaciones en una cadena (como concatenaciones, eliminaciones y reemplazos), el rendimiento puede verse beneficiado si usa la clase <xref:System.Text.StringBuilder> del espacio de nombres <xref:System.Text>.</span><span class="sxs-lookup"><span data-stu-id="9b1c0-114">If you do a significant number of manipulations on a string, such as concatenations, deletions, and replacements, your performance might profit from the <xref:System.Text.StringBuilder> class in the <xref:System.Text> namespace.</span></span> <span data-ttu-id="9b1c0-115">Esta clase toma una instrucción extra para crear e inicializar un objeto <xref:System.Text.StringBuilder>, así como otra instrucción para convertir su valor final a una `String`, pero este tiempo se puede recuperar, ya que el rendimiento de <xref:System.Text.StringBuilder> es más rápido.</span><span class="sxs-lookup"><span data-stu-id="9b1c0-115">It takes an extra instruction to create and initialize a <xref:System.Text.StringBuilder> object, and another instruction to convert its final value to a `String`, but you might recover this time because <xref:System.Text.StringBuilder> can perform faster.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9b1c0-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="9b1c0-116">See also</span></span>

- [<span data-ttu-id="9b1c0-117">Option Strict (instrucción)</span><span class="sxs-lookup"><span data-stu-id="9b1c0-117">Option Strict Statement</span></span>](../../../../visual-basic/language-reference/statements/option-strict-statement.md)
- [<span data-ttu-id="9b1c0-118">Tipos de métodos de manipulación de cadenas en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="9b1c0-118">Types of String Manipulation Methods in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/strings/types-of-string-manipulation-methods.md)
- [<span data-ttu-id="9b1c0-119">Operadores aritméticos en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="9b1c0-119">Arithmetic Operators in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
- [<span data-ttu-id="9b1c0-120">Operadores de comparación en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="9b1c0-120">Comparison Operators in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)
- [<span data-ttu-id="9b1c0-121">Operadores lógicos y bit a bit en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="9b1c0-121">Logical and Bitwise Operators in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
