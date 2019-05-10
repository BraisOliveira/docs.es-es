---
title: Los métodos no compartidos no pueden controlar los eventos de variables WithEvents compartidas
ms.date: 07/20/2015
f1_keywords:
- bc30594
- vbc30594
helpviewer_keywords:
- BC30594
ms.assetid: 5b9fceb4-ab11-41bb-ad3b-6f1a9da8ae7e
ms.openlocfilehash: d6067c75835ecd14f1dd796c20ae3f29f456e541
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64642939"
---
# <a name="events-of-shared-withevents-variables-cannot-be-handled-by-non-shared-methods"></a><span data-ttu-id="6a3a3-102">Los métodos no compartidos no pueden controlar los eventos de variables WithEvents compartidas</span><span class="sxs-lookup"><span data-stu-id="6a3a3-102">Events of shared WithEvents variables cannot be handled by non-shared methods</span></span>
<span data-ttu-id="6a3a3-103">Una variable declarada con el `Shared` modificador es una variable compartida.</span><span class="sxs-lookup"><span data-stu-id="6a3a3-103">A variable declared with the `Shared` modifier is a shared variable.</span></span> <span data-ttu-id="6a3a3-104">Una variable compartida identifica exactamente una ubicación de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="6a3a3-104">A shared variable identifies exactly one storage location.</span></span> <span data-ttu-id="6a3a3-105">Una variable declarada con el `WithEvents` modificador afirma que el tipo al que pertenece la variable controla el conjunto de eventos que provoca la variable.</span><span class="sxs-lookup"><span data-stu-id="6a3a3-105">A variable declared with the `WithEvents` modifier asserts that the type to which the variable belongs handles the set of events the variable raises.</span></span> <span data-ttu-id="6a3a3-106">Cuando se asigna un valor a la variable, la propiedad creada por el `WithEvents` declaración modo se desenlaza cualquier controlador de eventos existente y enlaza el nuevo controlador de eventos a través de la `Add` método.</span><span class="sxs-lookup"><span data-stu-id="6a3a3-106">When a value is assigned to the variable, the property created by the `WithEvents` declaration unhooks any existing event handler and hooks up the new event handler via the `Add` method.</span></span>  
  
 <span data-ttu-id="6a3a3-107">**Identificador de error:** BC30594</span><span class="sxs-lookup"><span data-stu-id="6a3a3-107">**Error ID:** BC30594</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="6a3a3-108">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="6a3a3-108">To correct this error</span></span>  
  
- <span data-ttu-id="6a3a3-109">Declare el controlador de eventos `Shared`.</span><span class="sxs-lookup"><span data-stu-id="6a3a3-109">Declare your event handler `Shared`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6a3a3-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="6a3a3-110">See also</span></span>

- [<span data-ttu-id="6a3a3-111">Shared</span><span class="sxs-lookup"><span data-stu-id="6a3a3-111">Shared</span></span>](../../../visual-basic/language-reference/modifiers/shared.md)
- [<span data-ttu-id="6a3a3-112">WithEvents</span><span class="sxs-lookup"><span data-stu-id="6a3a3-112">WithEvents</span></span>](../../../visual-basic/language-reference/modifiers/withevents.md)
