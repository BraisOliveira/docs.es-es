---
title: No se puede convertir un tipo anónimo en un árbol de expresión porque contiene un campo que se usa en la inicialización de otro campo
ms.date: 07/20/2015
f1_keywords:
- bc36548
- vbc36548
helpviewer_keywords:
- BC36548
ms.assetid: 27de068f-080e-4160-86bf-1ec23fd1925a
ms.openlocfilehash: ba14c0cd8781b8771ac8b746e3efec29a457294a
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/01/2019
ms.locfileid: "71701189"
---
# <a name="cannot-convert-anonymous-type-to-expression-tree-because-it-contains-a-field-that-is-used-in-the-initialization-of-another-field"></a><span data-ttu-id="e127d-102">No se puede convertir un tipo anónimo en un árbol de expresión porque contiene un campo que se usa en la inicialización de otro campo</span><span class="sxs-lookup"><span data-stu-id="e127d-102">Cannot convert anonymous type to expression tree because it contains a field that is used in the initialization of another field</span></span>
<span data-ttu-id="e127d-103">El compilador no acepta la conversión de un anónimo en un árbol de expresión cuando se usa una propiedad del tipo anónimo para inicializar otra propiedad del tipo anónimo.</span><span class="sxs-lookup"><span data-stu-id="e127d-103">The compiler does not accept conversion of an anonymous to an expression tree when one property of the anonymous type is used to initialize another property of the anonymous type.</span></span> <span data-ttu-id="e127d-104">Por ejemplo, en el código siguiente, `Prop1` se declara en la lista de inicialización y, a continuación, se usa como el valor inicial de `Prop2`.</span><span class="sxs-lookup"><span data-stu-id="e127d-104">For example, in the following code, `Prop1` is declared in the initialization list and then used as the initial value for `Prop2`.</span></span>  
  
```vb  
Module M2  
  
    Sub ExpressionExample(Of T)(ByVal x As Expressions.Expression(Of Func(Of T)))  
    End Sub  
  
    Sub Main()  
        ' The following line causes the error.  
        ' ExpressionExample(Function() New With {.Prop1 = 2, .Prop2 = .Prop1})  
  
    End Sub  
End Module  
```  
  
 <span data-ttu-id="e127d-105">**IDENTIFICADOR de error:** BC36548</span><span class="sxs-lookup"><span data-stu-id="e127d-105">**Error ID:** BC36548</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="e127d-106">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="e127d-106">To correct this error</span></span>  
  
- <span data-ttu-id="e127d-107">Asigne el valor inicial de `Prop1` a una variable local.</span><span class="sxs-lookup"><span data-stu-id="e127d-107">Assign the initial value for `Prop1` to a local variable.</span></span> <span data-ttu-id="e127d-108">Asigne esa variable a `Prop1` y `Prop2`, tal y como se muestra en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="e127d-108">Assign that variable to both `Prop1` and `Prop2`, as shown in the following code.</span></span>  
  
    ```vb  
    Sub Main()  
  
        Dim temp = 2  
        ExpressionExample(Function() New With {.Prop1 = temp, .Prop2 = temp})  
  
    End Sub  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="e127d-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="e127d-109">See also</span></span>

- [<span data-ttu-id="e127d-110">Tipos anónimos (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e127d-110">Anonymous Types (Visual Basic)</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)
- [<span data-ttu-id="e127d-111">Árboles de expresión (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e127d-111">Expression Trees (Visual Basic)</span></span>](../../programming-guide/concepts/expression-trees/index.md)
- [<span data-ttu-id="e127d-112">Cómo: Usar árboles de expresión para generar consultas dinámicas (Visual Basic) </span><span class="sxs-lookup"><span data-stu-id="e127d-112">How to: Use Expression Trees to Build Dynamic Queries (Visual Basic)</span></span>](../../programming-guide/concepts/expression-trees/how-to-use-expression-trees-to-build-dynamic-queries.md)
