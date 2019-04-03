---
title: Solucionar problemas de controladores de eventos heredados en Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- troubleshooting events [Visual Basic]
- inherited events [Visual Basic]
- troubleshooting Visual Basic, event handlers
- event handling, troubleshooting
- event handlers, troubleshooting
ms.assetid: e1c8759f-5370-4308-8476-8c48b73509bf
ms.openlocfilehash: 704ca667a6d14ade7be0192e872f5e40791cb864
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2019
ms.locfileid: "58830193"
---
# <a name="troubleshooting-inherited-event-handlers-in-visual-basic"></a><span data-ttu-id="b2c63-102">Solucionar problemas de controladores de eventos heredados en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="b2c63-102">Troubleshooting Inherited Event Handlers in Visual Basic</span></span>
<span data-ttu-id="b2c63-103">En este tema se enumera problemas comunes que surgen con controladores de eventos en componentes heredados.</span><span class="sxs-lookup"><span data-stu-id="b2c63-103">This topic lists common issues that arise with event handlers in inherited components.</span></span>  
  
## <a name="procedures"></a><span data-ttu-id="b2c63-104">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="b2c63-104">Procedures</span></span>  
  
#### <a name="code-in-event-handler-executes-twice-for-every-call"></a><span data-ttu-id="b2c63-105">Código de controlador de eventos se ejecuta dos veces para todas las llamadas</span><span class="sxs-lookup"><span data-stu-id="b2c63-105">Code in Event Handler Executes Twice for Every Call</span></span>  
  
-   <span data-ttu-id="b2c63-106">Un controlador de eventos heredado no debe incluir un [controla](../../../../visual-basic/language-reference/statements/handles-clause.md) cláusula.</span><span class="sxs-lookup"><span data-stu-id="b2c63-106">An inherited event handler must not include a [Handles](../../../../visual-basic/language-reference/statements/handles-clause.md) clause.</span></span> <span data-ttu-id="b2c63-107">El método de la clase base ya está asociado con el evento y se activará en consecuencia.</span><span class="sxs-lookup"><span data-stu-id="b2c63-107">The method in the base class is already associated with the event and will fire accordingly.</span></span> <span data-ttu-id="b2c63-108">Quitar el `Handles` cláusula del método heredado.</span><span class="sxs-lookup"><span data-stu-id="b2c63-108">Remove the `Handles` clause from the inherited method.</span></span>  
  
     [!code-vb[VbVbalrEvents#32](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEvents/VB/Class1.vb#32)]  
  
-   <span data-ttu-id="b2c63-109">Si el método heredado no tiene un `Handles` palabra clave, compruebe que el código no contiene un archivo extra [AddHandler (instrucción)](../../../../visual-basic/language-reference/statements/addhandler-statement.md) o métodos adicionales que controlan el mismo evento.</span><span class="sxs-lookup"><span data-stu-id="b2c63-109">If the inherited method does not have a `Handles` keyword, verify that your code does not contain an extra [AddHandler Statement](../../../../visual-basic/language-reference/statements/addhandler-statement.md) or any additional methods that handle the same event.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b2c63-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="b2c63-110">See also</span></span>

- [<span data-ttu-id="b2c63-111">Eventos</span><span class="sxs-lookup"><span data-stu-id="b2c63-111">Events</span></span>](../../../../visual-basic/programming-guide/language-features/events/index.md)
