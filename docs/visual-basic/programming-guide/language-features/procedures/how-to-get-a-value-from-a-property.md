---
title: Filtrar Obtener un valor de una propiedad (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- property values [Visual Basic]
- Visual Basic code, procedures
- values [Visual Basic], properties
- Visual Basic code, properties
- properties [Visual Basic], values
ms.assetid: 3954423e-6ab7-4a4c-b55c-a8d27be47891
ms.openlocfilehash: 7dbc9d926ae937dd032c0c054bde440037ab9f0d
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2019
ms.locfileid: "58842920"
---
# <a name="how-to-get-a-value-from-a-property-visual-basic"></a><span data-ttu-id="48ed6-102">Filtrar Obtener un valor de una propiedad (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="48ed6-102">How to: Get a Value from a Property (Visual Basic)</span></span>
<span data-ttu-id="48ed6-103">Para recuperar un valor de propiedad, incluido el nombre de propiedad en una expresión.</span><span class="sxs-lookup"><span data-stu-id="48ed6-103">You retrieve a property's value by including the property name in an expression.</span></span>  
  
 <span data-ttu-id="48ed6-104">La propiedad `Get` procedimiento recupera el valor, pero no llamar explícitamente a él por su nombre.</span><span class="sxs-lookup"><span data-stu-id="48ed6-104">The property's `Get` procedure retrieves the value, but you do not explicitly call it by name.</span></span> <span data-ttu-id="48ed6-105">Use la propiedad igual que usaría una variable.</span><span class="sxs-lookup"><span data-stu-id="48ed6-105">You use the property just as you would use a variable.</span></span> <span data-ttu-id="48ed6-106">Visual Basic realiza las llamadas a procedimientos de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="48ed6-106">Visual Basic makes the calls to the property's procedures.</span></span>  
  
### <a name="to-retrieve-a-value-from-a-property"></a><span data-ttu-id="48ed6-107">Para recuperar un valor de una propiedad</span><span class="sxs-lookup"><span data-stu-id="48ed6-107">To retrieve a value from a property</span></span>  
  
1.  <span data-ttu-id="48ed6-108">Utilice el nombre de propiedad en una expresión de la misma manera que utilizaría un nombre de variable.</span><span class="sxs-lookup"><span data-stu-id="48ed6-108">Use the property name in an expression the same way you would use a variable name.</span></span> <span data-ttu-id="48ed6-109">Puede usar una propiedad en cualquier lugar puede usar una variable o una constante.</span><span class="sxs-lookup"><span data-stu-id="48ed6-109">You can use a property anywhere you can use a variable or a constant.</span></span>  
  
     <span data-ttu-id="48ed6-110">-o bien-</span><span class="sxs-lookup"><span data-stu-id="48ed6-110">-or-</span></span>  
  
     <span data-ttu-id="48ed6-111">Utilice el nombre de propiedad tras la igual (`=`) inicie sesión en una instrucción de asignación.</span><span class="sxs-lookup"><span data-stu-id="48ed6-111">Use the property name following the equal (`=`) sign in an assignment statement.</span></span>  
  
     <span data-ttu-id="48ed6-112">El ejemplo siguiente lee el valor de Visual Basic `Now` propiedad, se llama implícitamente a su `Get` procedimiento.</span><span class="sxs-lookup"><span data-stu-id="48ed6-112">The following example reads the value of the Visual Basic `Now` property, implicitly calling its `Get` procedure.</span></span>  
  
     [!code-vb[VbVbalrDateProperties#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDateProperties/VB/Module1.vb#4)]  
  
2.  <span data-ttu-id="48ed6-113">Si la propiedad toma argumentos, siga el nombre de propiedad entre paréntesis para delimitar la lista de argumentos.</span><span class="sxs-lookup"><span data-stu-id="48ed6-113">If the property takes arguments, follow the property name with parentheses to enclose the argument list.</span></span> <span data-ttu-id="48ed6-114">Si no hay ningún argumento, opcionalmente, puede omitir los paréntesis.</span><span class="sxs-lookup"><span data-stu-id="48ed6-114">If there are no arguments, you can optionally omit the parentheses.</span></span>  
  
3.  <span data-ttu-id="48ed6-115">Coloque los argumentos en la lista de argumentos entre paréntesis, separados por comas.</span><span class="sxs-lookup"><span data-stu-id="48ed6-115">Place the arguments in the argument list within the parentheses, separated by commas.</span></span> <span data-ttu-id="48ed6-116">Asegúrese de que proporcionar los argumentos en el mismo orden que la propiedad define los parámetros correspondientes.</span><span class="sxs-lookup"><span data-stu-id="48ed6-116">Be sure you supply the arguments in the same order that the property defines the corresponding parameters.</span></span>  
  
 <span data-ttu-id="48ed6-117">El valor de la propiedad participa en la expresión igual que una variable o constante, o se almacena en la variable o propiedad en el lado izquierdo de la instrucción de asignación.</span><span class="sxs-lookup"><span data-stu-id="48ed6-117">The value of the property participates in the expression just as a variable or constant would, or it is stored in the variable or property on the left side of the assignment statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="48ed6-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="48ed6-118">See also</span></span>

- [<span data-ttu-id="48ed6-119">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="48ed6-119">Procedures</span></span>](./index.md)
- [<span data-ttu-id="48ed6-120">Procedimientos de propiedades</span><span class="sxs-lookup"><span data-stu-id="48ed6-120">Property Procedures</span></span>](./property-procedures.md)
- [<span data-ttu-id="48ed6-121">Argumentos y parámetros de procedimiento</span><span class="sxs-lookup"><span data-stu-id="48ed6-121">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="48ed6-122">Property (instrucción)</span><span class="sxs-lookup"><span data-stu-id="48ed6-122">Property Statement</span></span>](../../../../visual-basic/language-reference/statements/property-statement.md)
- [<span data-ttu-id="48ed6-123">Diferencias entre propiedades y Variables en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="48ed6-123">Differences Between Properties and Variables in Visual Basic</span></span>](./differences-between-properties-and-variables.md)
- [<span data-ttu-id="48ed6-124">Cómo: Crear una propiedad</span><span class="sxs-lookup"><span data-stu-id="48ed6-124">How to: Create a Property</span></span>](./how-to-create-a-property.md)
- [<span data-ttu-id="48ed6-125">Cómo: Declarar una propiedad con niveles de acceso mixtos</span><span class="sxs-lookup"><span data-stu-id="48ed6-125">How to: Declare a Property with Mixed Access Levels</span></span>](./how-to-declare-a-property-with-mixed-access-levels.md)
- [<span data-ttu-id="48ed6-126">Cómo: Llamar a un procedimiento de propiedad</span><span class="sxs-lookup"><span data-stu-id="48ed6-126">How to: Call a Property Procedure</span></span>](./how-to-call-a-property-procedure.md)
- [<span data-ttu-id="48ed6-127">Cómo: Declarar y llamar a una propiedad predeterminada en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="48ed6-127">How to: Declare and Call a Default Property in Visual Basic</span></span>](./how-to-declare-and-call-a-default-property.md)
- [<span data-ttu-id="48ed6-128">Cómo: Establecer un valor en una propiedad</span><span class="sxs-lookup"><span data-stu-id="48ed6-128">How to: Put a Value in a Property</span></span>](./how-to-put-a-value-in-a-property.md)
