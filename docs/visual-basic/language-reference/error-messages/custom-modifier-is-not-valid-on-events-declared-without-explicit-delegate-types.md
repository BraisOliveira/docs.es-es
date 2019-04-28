---
title: El modificador 'Custom' no es válido en eventos declarados sin tipos de delegado explícitos
ms.date: 07/20/2015
f1_keywords:
- vbc31122
- bc31122
helpviewer_keywords:
- BC31122
ms.assetid: 6911f0d1-641a-473b-906d-8ee5681194be
ms.openlocfilehash: 169cb49cc5abc76b7c52785392d0083b81a99450
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61803888"
---
# <a name="custom-modifier-is-not-valid-on-events-declared-without-explicit-delegate-types"></a><span data-ttu-id="7a7d6-102">El modificador 'Custom' no es válido en eventos declarados sin tipos de delegado explícitos</span><span class="sxs-lookup"><span data-stu-id="7a7d6-102">'Custom' modifier is not valid on events declared without explicit delegate types</span></span>
<span data-ttu-id="7a7d6-103">A diferencia de un evento no personalizado, un `Custom Event` declaración requiere un `As` cláusula después del nombre de evento que se especifica explícitamente el tipo de delegado para el evento.</span><span class="sxs-lookup"><span data-stu-id="7a7d6-103">Unlike a non-custom event, a `Custom Event` declaration requires an `As` clause following the event name that explicitly specifies the delegate type for the event.</span></span>  
  
 <span data-ttu-id="7a7d6-104">Los eventos no personalizados pueden ser definido con un `As` cláusula y explícita el tipo delegado, o con un parámetro de lista inmediatamente después del nombre de evento.</span><span class="sxs-lookup"><span data-stu-id="7a7d6-104">Non-custom events can be defined either with an `As` clause and an explicit delegate type, or with a parameter list immediately following the event name.</span></span>  
  
 <span data-ttu-id="7a7d6-105">**Identificador de error:** BC31122</span><span class="sxs-lookup"><span data-stu-id="7a7d6-105">**Error ID:** BC31122</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="7a7d6-106">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="7a7d6-106">To correct this error</span></span>  
  
1. <span data-ttu-id="7a7d6-107">Defina a un delegado con la misma lista de parámetros como el evento personalizado.</span><span class="sxs-lookup"><span data-stu-id="7a7d6-107">Define a delegate with the same parameter list as the custom event.</span></span>  
  
     <span data-ttu-id="7a7d6-108">Por ejemplo, si la `Custom Event` se ha definido por `Custom Event Test(ByVal sender As Object, ByVal i As Integer)`, a continuación, el delegado correspondiente sería la siguiente.</span><span class="sxs-lookup"><span data-stu-id="7a7d6-108">For example, if the `Custom Event` was defined by `Custom Event Test(ByVal sender As Object, ByVal i As Integer)`, then the corresponding delegate would be the following.</span></span>  
  
     [!code-vb[VbVbalrEventError#18](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEventError/VB/VbVbalrEventError.vb#18)]  
  
2. <span data-ttu-id="7a7d6-109">Reemplazar la lista de parámetros del evento personalizado con un `As` cláusula que especifica el tipo de delegado.</span><span class="sxs-lookup"><span data-stu-id="7a7d6-109">Replace the parameter list of the custom event with an `As` clause specifying the delegate type.</span></span>  
  
     <span data-ttu-id="7a7d6-110">Continuando con el ejemplo, `Custom Event` declaración se volvería como sigue.</span><span class="sxs-lookup"><span data-stu-id="7a7d6-110">Continuing with the example, `Custom Event` declaration would be rewritten as follows.</span></span>  
  
     [!code-vb[VbVbalrEventError#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEventError/VB/VbVbalrEventError.vb#19)]  
  
## <a name="example"></a><span data-ttu-id="7a7d6-111">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="7a7d6-111">Example</span></span>  
 <span data-ttu-id="7a7d6-112">Este ejemplo se declara un `Custom Event` y especifica los `As` cláusula con un tipo de delegado.</span><span class="sxs-lookup"><span data-stu-id="7a7d6-112">This example declares a `Custom Event` and specifies the required `As` clause with a delegate type.</span></span>  
  
 [!code-vb[VbVbalrEventError#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEventError/VB/VbVbalrEventError.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="7a7d6-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="7a7d6-113">See also</span></span>

- [<span data-ttu-id="7a7d6-114">Event (instrucción)</span><span class="sxs-lookup"><span data-stu-id="7a7d6-114">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)
- [<span data-ttu-id="7a7d6-115">Delegate (instrucción)</span><span class="sxs-lookup"><span data-stu-id="7a7d6-115">Delegate Statement</span></span>](../../../visual-basic/language-reference/statements/delegate-statement.md)
- [<span data-ttu-id="7a7d6-116">Eventos</span><span class="sxs-lookup"><span data-stu-id="7a7d6-116">Events</span></span>](../../../visual-basic/programming-guide/language-features/events/index.md)
