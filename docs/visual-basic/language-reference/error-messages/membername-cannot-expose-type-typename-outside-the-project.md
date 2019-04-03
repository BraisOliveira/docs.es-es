---
title: "'<membername>' no puede exponer el tipo '<typename>' fuera del proyecto mediante <containertype> '<containertypename>'"
ms.date: 07/20/2015
f1_keywords:
- bc30909
- vbc30909
helpviewer_keywords:
- BC30909
ms.assetid: ffa7395d-e182-4087-8ce8-079810fdae54
ms.openlocfilehash: 16f579a05236ba8977a071cb08068be8e98799f8
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2019
ms.locfileid: "58818350"
---
# <a name="membername-cannot-expose-type-typename-outside-the-project-through-containertype-containertypename"></a><span data-ttu-id="d2795-102">'\<membername >' no puede exponer el tipo '\<typename >' fuera del proyecto mediante \<containertype > '\<containertypename >'</span><span class="sxs-lookup"><span data-stu-id="d2795-102">'\<membername>' cannot expose type '\<typename>' outside the project through \<containertype> '\<containertypename>'</span></span>
<span data-ttu-id="d2795-103">Una variable, parámetro de procedimiento o valor devuelto de función se expone fuera de su contenedor, pero se declara como un tipo que no se debe exponer fuera del contenedor.</span><span class="sxs-lookup"><span data-stu-id="d2795-103">A variable, procedure parameter, or function return is exposed outside its container, but it is declared as a type that must not be exposed outside the container.</span></span>  
  
 <span data-ttu-id="d2795-104">La estructura de código siguiente muestra una situación que genera este error.</span><span class="sxs-lookup"><span data-stu-id="d2795-104">The following skeleton code shows a situation that generates this error.</span></span>  
  
```  
Private Class privateClass  
End Class  
Public Class mainClass  
    Public exposedVar As New privateClass  
End Class  
```  
  
 <span data-ttu-id="d2795-105">Un tipo que se declara `Protected`, `Friend`, `Protected Friend`, o `Private` está diseñado para tener acceso limitado fuera de su contexto de declaración.</span><span class="sxs-lookup"><span data-stu-id="d2795-105">A type that is declared `Protected`, `Friend`, `Protected Friend`, or `Private` is intended to have limited access outside its declaration context.</span></span> <span data-ttu-id="d2795-106">Lo utilizan como los datos de tipo de una variable con acceso menos restringido iría con este fin.</span><span class="sxs-lookup"><span data-stu-id="d2795-106">Using it as the data type of a variable with less restricted access would defeat this purpose.</span></span> <span data-ttu-id="d2795-107">En el código anterior de esqueleto, `exposedVar` es `Public` y expondría `privateClass` al código que no debería tener acceso a él.</span><span class="sxs-lookup"><span data-stu-id="d2795-107">In the preceding skeleton code, `exposedVar` is `Public` and would expose `privateClass` to code that should not have access to it.</span></span>  
  
 <span data-ttu-id="d2795-108">**Identificador de error:** BC30909</span><span class="sxs-lookup"><span data-stu-id="d2795-108">**Error ID:** BC30909</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="d2795-109">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="d2795-109">To correct this error</span></span>  
  
-   <span data-ttu-id="d2795-110">Cambiar el nivel de acceso de la variable, parámetro de procedimiento o función que se devuelven para que sea al menos tan restrictiva como el nivel de acceso de su tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="d2795-110">Change the access level of the variable, procedure parameter, or function return to be at least as restrictive as the access level of its data type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d2795-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="d2795-111">See also</span></span>

- [<span data-ttu-id="d2795-112">Niveles de acceso en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="d2795-112">Access levels in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)
