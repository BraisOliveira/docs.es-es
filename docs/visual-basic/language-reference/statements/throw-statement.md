---
title: Throw (Instrucción, Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Throw
helpviewer_keywords:
- structured exception handling, throw statements
- try-catch exception handling, throw statements
- throw statement [Visual Basic], about throw statements
- throwing exceptions, throw statement
- exception handling, throw statement
- On Error statement [Visual Basic], throwing exceptions
- throwing exceptions
- exception handling, unstructured
- throw statement [Visual Basic]
ms.assetid: a6e07406-5c8a-4498-87a2-8339f3651d62
ms.openlocfilehash: 2494eac2f61f112f3ba6321ada7404f8cd618049
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2019
ms.locfileid: "58821397"
---
# <a name="throw-statement-visual-basic"></a><span data-ttu-id="2b78e-102">Throw (Instrucción, Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2b78e-102">Throw Statement (Visual Basic)</span></span>
<span data-ttu-id="2b78e-103">Se produce una excepción dentro de un procedimiento.</span><span class="sxs-lookup"><span data-stu-id="2b78e-103">Throws an exception within a procedure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2b78e-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2b78e-104">Syntax</span></span>  
  
```  
Throw [ expression ]  
```  
  
## <a name="part"></a><span data-ttu-id="2b78e-105">Parte</span><span class="sxs-lookup"><span data-stu-id="2b78e-105">Part</span></span>  
 `expression`  
 <span data-ttu-id="2b78e-106">Proporciona información sobre la excepción que se produzca.</span><span class="sxs-lookup"><span data-stu-id="2b78e-106">Provides information about the exception to be thrown.</span></span> <span data-ttu-id="2b78e-107">Opcional si se encuentra en un `Catch` instrucción, de lo contrario requerido.</span><span class="sxs-lookup"><span data-stu-id="2b78e-107">Optional when residing in a `Catch` statement, otherwise required.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2b78e-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="2b78e-108">Remarks</span></span>  
 <span data-ttu-id="2b78e-109">El `Throw` instrucción produce una excepción que se puede controlar con código de control de excepciones estructurado (`Try`... `Catch`... `Finally`) o el código de control de excepciones no estructurado (`On Error GoTo`).</span><span class="sxs-lookup"><span data-stu-id="2b78e-109">The `Throw` statement throws an exception that you can handle with structured exception-handling code (`Try`...`Catch`...`Finally`) or unstructured exception-handling code (`On Error GoTo`).</span></span> <span data-ttu-id="2b78e-110">Puede usar el `Throw` instrucción para interceptar errores dentro del código porque Visual Basic asciende por la pila de llamadas hasta que encuentra el código de control de excepciones adecuado.</span><span class="sxs-lookup"><span data-stu-id="2b78e-110">You can use the `Throw` statement to trap errors within your code because Visual Basic moves up the call stack until it finds the appropriate exception-handling code.</span></span>  
  
 <span data-ttu-id="2b78e-111">Un `Throw` instrucción sin una expresión solo se puede usar en un `Catch` instrucción, en el que la instrucción case, vuelve a producir la excepción que se controla actualmente por el `Catch` instrucción.</span><span class="sxs-lookup"><span data-stu-id="2b78e-111">A `Throw` statement with no expression can only be used in a `Catch` statement, in which case the statement rethrows the exception currently being handled by the `Catch` statement.</span></span>  
  
 <span data-ttu-id="2b78e-112">El `Throw` instrucción restablece la pila de llamadas para el `expression` excepción.</span><span class="sxs-lookup"><span data-stu-id="2b78e-112">The `Throw` statement resets the call stack for the `expression` exception.</span></span> <span data-ttu-id="2b78e-113">Si `expression` no se proporciona, la pila de llamadas permanece inalterado.</span><span class="sxs-lookup"><span data-stu-id="2b78e-113">If `expression` is not provided, the call stack is left unchanged.</span></span> <span data-ttu-id="2b78e-114">Puede tener acceso a la pila de llamadas para la excepción a través de la <xref:System.Exception.StackTrace%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="2b78e-114">You can access the call stack for the exception through the <xref:System.Exception.StackTrace%2A> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2b78e-115">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="2b78e-115">Example</span></span>  
 <span data-ttu-id="2b78e-116">El siguiente código utiliza el `Throw` instrucción para producir una excepción:</span><span class="sxs-lookup"><span data-stu-id="2b78e-116">The following code uses the `Throw` statement to throw an exception:</span></span>  
  
 [!code-vb[VbVbalrStatements#84](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#84)]  
  
## <a name="requirements"></a><span data-ttu-id="2b78e-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2b78e-117">Requirements</span></span>  
 <span data-ttu-id="2b78e-118">**Espacio de nombres**: [Microsoft.VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)</span><span class="sxs-lookup"><span data-stu-id="2b78e-118">**Namespace:** [Microsoft.VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)</span></span>  
  
 <span data-ttu-id="2b78e-119">**Módulo:** `Interaction`</span><span class="sxs-lookup"><span data-stu-id="2b78e-119">**Module:** `Interaction`</span></span>  
  
 <span data-ttu-id="2b78e-120">**Ensamblado:** Biblioteca en tiempo de ejecución de Visual Basic (en Microsoft.VisualBasic.dll)</span><span class="sxs-lookup"><span data-stu-id="2b78e-120">**Assembly:** Visual Basic Runtime Library (in Microsoft.VisualBasic.dll)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2b78e-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="2b78e-121">See also</span></span>

- [<span data-ttu-id="2b78e-122">Try...Catch...Finally (instrucción)</span><span class="sxs-lookup"><span data-stu-id="2b78e-122">Try...Catch...Finally Statement</span></span>](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
- [<span data-ttu-id="2b78e-123">On Error (instrucción)</span><span class="sxs-lookup"><span data-stu-id="2b78e-123">On Error Statement</span></span>](../../../visual-basic/language-reference/statements/on-error-statement.md)
