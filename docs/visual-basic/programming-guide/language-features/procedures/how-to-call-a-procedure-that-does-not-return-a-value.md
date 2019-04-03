---
title: Filtrar Llamar a un procedimiento que no devuelve un valor (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- procedure calls [Visual Basic], returning values
- Visual Basic code, procedures
- procedures [Visual Basic], calling
ms.assetid: 259b49a3-a3c1-4254-ba8c-73cdc4127703
ms.openlocfilehash: 05b4b1cb29abff97c44c33d462375fc4d5ab159d
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2019
ms.locfileid: "58818584"
---
# <a name="how-to-call-a-procedure-that-does-not-return-a-value-visual-basic"></a><span data-ttu-id="ce16c-102">Filtrar Llamar a un procedimiento que no devuelve un valor (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ce16c-102">How to: Call a Procedure that Does Not Return a Value (Visual Basic)</span></span>
<span data-ttu-id="ce16c-103">Un `Sub` procedimiento no devuelve un valor al código de llamada.</span><span class="sxs-lookup"><span data-stu-id="ce16c-103">A `Sub` procedure does not return a value to the calling code.</span></span> <span data-ttu-id="ce16c-104">Llama de forma explícita con una instrucción independiente que realiza la llamada.</span><span class="sxs-lookup"><span data-stu-id="ce16c-104">You call it explicitly with a stand-alone calling statement.</span></span> <span data-ttu-id="ce16c-105">No se puede llamar a simplemente utilizando su nombre dentro de una expresión.</span><span class="sxs-lookup"><span data-stu-id="ce16c-105">You cannot call it by simply using its name within an expression.</span></span>  
  
### <a name="to-call-a-sub-procedure"></a><span data-ttu-id="ce16c-106">Para llamar a un procedimiento Sub</span><span class="sxs-lookup"><span data-stu-id="ce16c-106">To call a Sub procedure</span></span>  
  
1.  <span data-ttu-id="ce16c-107">Especifique el nombre de la `Sub` procedimiento.</span><span class="sxs-lookup"><span data-stu-id="ce16c-107">Specify the name of the `Sub` procedure.</span></span>  
  
2.  <span data-ttu-id="ce16c-108">Siga el nombre del procedimiento con paréntesis para delimitar la lista de argumentos.</span><span class="sxs-lookup"><span data-stu-id="ce16c-108">Follow the procedure name with parentheses to enclose the argument list.</span></span> <span data-ttu-id="ce16c-109">Si no hay ningún argumento, opcionalmente, puede omitir los paréntesis.</span><span class="sxs-lookup"><span data-stu-id="ce16c-109">If there are no arguments, you can optionally omit the parentheses.</span></span> <span data-ttu-id="ce16c-110">Sin embargo, el uso de los paréntesis hace que el código más fácil de leer.</span><span class="sxs-lookup"><span data-stu-id="ce16c-110">However, using the parentheses makes your code easier to read.</span></span>  
  
3.  <span data-ttu-id="ce16c-111">Coloque los argumentos en la lista de argumentos entre paréntesis, separados por comas.</span><span class="sxs-lookup"><span data-stu-id="ce16c-111">Place the arguments in the argument list within the parentheses, separated by commas.</span></span> <span data-ttu-id="ce16c-112">Asegúrese de proporcionar los argumentos en el mismo orden que el `Sub` procedimiento define los parámetros correspondientes.</span><span class="sxs-lookup"><span data-stu-id="ce16c-112">Be sure you supply the arguments in the same order that the `Sub` procedure defines the corresponding parameters.</span></span>  
  
     <span data-ttu-id="ce16c-113">El ejemplo siguiente se llama a la de Visual Basic <xref:Microsoft.VisualBasic.Interaction.AppActivate%2A> función para activar una ventana de aplicación.</span><span class="sxs-lookup"><span data-stu-id="ce16c-113">The following example calls the Visual Basic <xref:Microsoft.VisualBasic.Interaction.AppActivate%2A> function to activate an application window.</span></span> <span data-ttu-id="ce16c-114"><xref:Microsoft.VisualBasic.Interaction.AppActivate%2A> toma el título de ventana como único argumento.</span><span class="sxs-lookup"><span data-stu-id="ce16c-114"><xref:Microsoft.VisualBasic.Interaction.AppActivate%2A> takes the window title as its sole argument.</span></span> <span data-ttu-id="ce16c-115">No se devuelve un valor al código de llamada.</span><span class="sxs-lookup"><span data-stu-id="ce16c-115">It does not return a value to the calling code.</span></span> <span data-ttu-id="ce16c-116">Si no se está ejecutando un proceso de Bloc de notas, en el ejemplo se produce un <xref:System.ArgumentException>.</span><span class="sxs-lookup"><span data-stu-id="ce16c-116">If a Notepad process is not running, the example throws an <xref:System.ArgumentException>.</span></span> <span data-ttu-id="ce16c-117">El `Shell` procedimiento se da por supuesto que las aplicaciones están en las rutas de acceso especificadas.</span><span class="sxs-lookup"><span data-stu-id="ce16c-117">The `Shell` procedure assumes the applications are in the paths specified.</span></span>  
  
     [!code-vb[VbVbalrCatRef#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCatRef/VB/Class1.vb#11)]  
  
## <a name="see-also"></a><span data-ttu-id="ce16c-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="ce16c-118">See also</span></span>

- <xref:Microsoft.VisualBasic.Interaction.Shell%2A>
- <xref:System.ArgumentException>
- [<span data-ttu-id="ce16c-119">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="ce16c-119">Procedures</span></span>](./index.md)
- [<span data-ttu-id="ce16c-120">Subprocedimientos</span><span class="sxs-lookup"><span data-stu-id="ce16c-120">Sub Procedures</span></span>](./sub-procedures.md)
- [<span data-ttu-id="ce16c-121">Argumentos y parámetros de procedimiento</span><span class="sxs-lookup"><span data-stu-id="ce16c-121">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="ce16c-122">Sub (instrucción)</span><span class="sxs-lookup"><span data-stu-id="ce16c-122">Sub Statement</span></span>](../../../../visual-basic/language-reference/statements/sub-statement.md)
- [<span data-ttu-id="ce16c-123">Cómo: Crear un procedimiento</span><span class="sxs-lookup"><span data-stu-id="ce16c-123">How to: Create a Procedure</span></span>](./how-to-create-a-procedure.md)
- [<span data-ttu-id="ce16c-124">Cómo: Llamar a un procedimiento que devuelve un valor</span><span class="sxs-lookup"><span data-stu-id="ce16c-124">How to: Call a Procedure That Returns a Value</span></span>](./how-to-call-a-procedure-that-returns-a-value.md)
- [<span data-ttu-id="ce16c-125">Cómo: Llamar a un controlador de eventos en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="ce16c-125">How to: Call an Event Handler in Visual Basic</span></span>](./how-to-call-an-event-handler.md)
