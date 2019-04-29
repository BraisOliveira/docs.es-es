---
title: El nombre de una variable de rango sólo se puede inferir a partir de un nombre simple o completo sin argumentos
ms.date: 07/20/2015
f1_keywords:
- vbc36599
- bc36599
helpviewer_keywords:
- BC36599
ms.assetid: 17763dbe-f74f-4ccb-8086-cb7e45ec4d12
ms.openlocfilehash: a0b5633bb0efb3c67f73810552ef9a14ac3d0c70
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61934282"
---
# <a name="range-variable-name-can-be-inferred-only-from-a-simple-or-qualified-name-with-no-arguments"></a><span data-ttu-id="89abc-102">El nombre de una variable de rango sólo se puede inferir a partir de un nombre simple o completo sin argumentos</span><span class="sxs-lookup"><span data-stu-id="89abc-102">Range variable name can be inferred only from a simple or qualified name with no arguments</span></span>
<span data-ttu-id="89abc-103">Se incluye un elemento de programación que toma uno o más argumentos en una consulta LINQ.</span><span class="sxs-lookup"><span data-stu-id="89abc-103">A programming element that takes one or more arguments is included in a LINQ query.</span></span> <span data-ttu-id="89abc-104">El compilador no puede inferir una variable de rango de ese elemento de programación.</span><span class="sxs-lookup"><span data-stu-id="89abc-104">The compiler is unable to infer a range variable from that programming element.</span></span>  
  
 <span data-ttu-id="89abc-105">**Identificador de error:** BC36599</span><span class="sxs-lookup"><span data-stu-id="89abc-105">**Error ID:** BC36599</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="89abc-106">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="89abc-106">To correct this error</span></span>  
  
1. <span data-ttu-id="89abc-107">Proporcione un nombre de variable explícito para el elemento de programación, como se muestra en el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="89abc-107">Supply an explicit variable name for the programming element, as shown in the following code:</span></span>  
  
```  
Dim query = From var1 In collection1   
            Select VariableAlias= SampleFunction(var1), var1  
```  
  
## <a name="see-also"></a><span data-ttu-id="89abc-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="89abc-108">See also</span></span>

- [<span data-ttu-id="89abc-109">Introducción a LINQ en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="89abc-109">Introduction to LINQ in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [<span data-ttu-id="89abc-110">Select (cláusula)</span><span class="sxs-lookup"><span data-stu-id="89abc-110">Select Clause</span></span>](../../../visual-basic/language-reference/queries/select-clause.md)
