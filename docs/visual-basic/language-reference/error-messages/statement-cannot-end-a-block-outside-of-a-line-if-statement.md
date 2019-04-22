---
title: La instrucción no puede terminar un bloque fuera de una línea de la instrucción 'If'
ms.date: 07/20/2015
f1_keywords:
- vbc32005
- bc32005
helpviewer_keywords:
- BC32005
ms.assetid: 4039f51b-e0ee-4789-a89b-45d06de06b5d
ms.openlocfilehash: 85573099ec0a3f8a23c17bdf384c4c105f9157df
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "58825799"
---
# <a name="statement-cannot-end-a-block-outside-of-a-line-if-statement"></a><span data-ttu-id="5b7c6-102">La instrucción no puede terminar un bloque fuera de una línea de la instrucción 'If'</span><span class="sxs-lookup"><span data-stu-id="5b7c6-102">Statement cannot end a block outside of a line 'If' statement</span></span>
<span data-ttu-id="5b7c6-103">Una sola línea `If` instrucción contiene varias instrucciones separadas por dos puntos (:), uno de los cuales es un `End` declaración de un bloque de control fuera de la línea `If`.</span><span class="sxs-lookup"><span data-stu-id="5b7c6-103">A single-line `If` statement contains several statements separated by colons (:), one of which is an `End` statement for a control block outside the single-line `If`.</span></span> <span data-ttu-id="5b7c6-104">Línea `If` instrucciones no utilizan el `End If` instrucción.</span><span class="sxs-lookup"><span data-stu-id="5b7c6-104">Single-line `If` statements do not use the `End If` statement.</span></span>  
  
 <span data-ttu-id="5b7c6-105">**Identificador de error:** BC32005</span><span class="sxs-lookup"><span data-stu-id="5b7c6-105">**Error ID:** BC32005</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="5b7c6-106">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="5b7c6-106">To correct this error</span></span>  
  
-   <span data-ttu-id="5b7c6-107">Mover la línea `If` instrucción fuera del bloque de control que contiene el `End If` instrucción.</span><span class="sxs-lookup"><span data-stu-id="5b7c6-107">Move the single-line `If` statement outside the control block that contains the `End If` statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5b7c6-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="5b7c6-108">See also</span></span>

- [<span data-ttu-id="5b7c6-109">If...Then...Else (instrucción)</span><span class="sxs-lookup"><span data-stu-id="5b7c6-109">If...Then...Else Statement</span></span>](../../../visual-basic/language-reference/statements/if-then-else-statement.md)
