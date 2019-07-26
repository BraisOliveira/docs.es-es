---
title: El tipo de la variable '<variablename>' no se inferirá porque está enlazado a un campo en un ámbito de inclusión
ms.date: 07/20/2015
f1_keywords:
- vbc42110
- bc42110
helpviewer_keywords:
- BC42110
ms.assetid: ef4442eb-08d1-434f-a03b-4aa2ed4e4414
ms.openlocfilehash: e56529919945558df178e18a83a895a79bfe4919
ms.sourcegitcommit: 463f3f050cecc0b6403e67f19a61f870fb8e7b7d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/26/2019
ms.locfileid: "68512721"
---
# <a name="the-type-for-variable-variablename-will-not-be-inferred-because-it-is-bound-to-a-field-in-an-enclosing-scope"></a><span data-ttu-id="6c511-102">El tipo de la variable\<' variablename > ' no se inferirá porque está enlazado a un campo en un ámbito de inclusión</span><span class="sxs-lookup"><span data-stu-id="6c511-102">The type for variable '\<variablename>' will not be inferred because it is bound to a field in an enclosing scope</span></span>

<span data-ttu-id="6c511-103">El tipo de la variable\<' variablename > ' no se inferirá porque está enlazado a un campo en un ámbito de inclusión.</span><span class="sxs-lookup"><span data-stu-id="6c511-103">The type for variable '\<variablename>' will not be inferred because it is bound to a field in an enclosing scope.</span></span> <span data-ttu-id="6c511-104">Cambie el nombre de '\<variablename > ' o use el nombre completo (por ejemplo, ' me. variablename ' o ' MyBase. variablename ').</span><span class="sxs-lookup"><span data-stu-id="6c511-104">Either change the name of '\<variablename>', or use the fully qualified name (for example, 'Me.variablename' or 'MyBase.variablename').</span></span>

<span data-ttu-id="6c511-105">Una variable de control de bucle en su código tiene el mismo nombre que un campo de la clase u otro ámbito de inclusión.</span><span class="sxs-lookup"><span data-stu-id="6c511-105">A loop control variable in your code has the same name as a field of the class or other enclosing scope.</span></span> <span data-ttu-id="6c511-106">Dado que la variable de control se utiliza sin una cláusula `As`, se enlaza al campo en el ámbito de inclusión y el compilador no crea una nueva variable para ella ni infiere su tipo.</span><span class="sxs-lookup"><span data-stu-id="6c511-106">Because the control variable is used without an `As` clause, it is bound to the field in the enclosing scope, and the compiler does not create a new variable for it or infer its type.</span></span>

<span data-ttu-id="6c511-107">En el ejemplo siguiente, `Index`, es decir, la variable de control en la instrucción `For`, se enlaza al campo `Index` de la clase `Customer`.</span><span class="sxs-lookup"><span data-stu-id="6c511-107">In the following example, `Index`, the control variable in the `For` statement, is bound to the `Index` field in the `Customer` class.</span></span> <span data-ttu-id="6c511-108">El compilador no crea una nueva variable para la variable de control `Index` ni infiere su tipo.</span><span class="sxs-lookup"><span data-stu-id="6c511-108">The compiler does not create a new variable for the control variable `Index` or infer its type.</span></span>

```vb
Class Customer

    ' The class has a field named Index.
    Private Index As Integer

    Sub Main()

    ' The following line will raise this warning.
        For Index = 1 To 10
            ' ...
        Next

    End Sub
End Class
```

<span data-ttu-id="6c511-109">De forma predeterminada, este mensaje es una advertencia.</span><span class="sxs-lookup"><span data-stu-id="6c511-109">By default, this message is a warning.</span></span> <span data-ttu-id="6c511-110">Para obtener información sobre cómo ocultar las advertencias o cómo tratarlas como errores, vea [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="6c511-110">For information about how to hide warnings or how to treat warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>

<span data-ttu-id="6c511-111">**IDENTIFICADOR de error:** BC42110</span><span class="sxs-lookup"><span data-stu-id="6c511-111">**Error ID:** BC42110</span></span>

### <a name="to-address-this-warning"></a><span data-ttu-id="6c511-112">Para resolver esta advertencia</span><span class="sxs-lookup"><span data-stu-id="6c511-112">To address this warning</span></span>

- <span data-ttu-id="6c511-113">Convierta la variable de control de bucle en local cambiando su nombre por un identificador que tampoco sea el nombre de un campo de la clase.</span><span class="sxs-lookup"><span data-stu-id="6c511-113">Make the loop control variable local by changing its name to an identifier that is not also the name of a field of the class.</span></span>

  ```vb
  For I = 1 To 10
  ```

- <span data-ttu-id="6c511-114">Asegúrese de que la variable de control de bucle se enlaza al campo de clase agregando el prefijo `Me.` al nombre de variable.</span><span class="sxs-lookup"><span data-stu-id="6c511-114">Clarify that the loop control variable binds to the class field by prefixing `Me.` to the variable name.</span></span>

  ```vb
  For Me.Index = 1 To 10
  ```

- <span data-ttu-id="6c511-115">En lugar de basarse en la inferencia de tipo local, use una cláusula `As` para especificar un tipo para la variable de control de bucle.</span><span class="sxs-lookup"><span data-stu-id="6c511-115">Instead of relying on local type inference, use an `As` clause to specify a type for the loop control variable.</span></span>

  ```vb
  For Index As Integer = 1 To 10
  ```

## <a name="example"></a><span data-ttu-id="6c511-116">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="6c511-116">Example</span></span>
 <span data-ttu-id="6c511-117">El código siguiente muestra el ejemplo anterior con la primera corrección en contexto.</span><span class="sxs-lookup"><span data-stu-id="6c511-117">The following code shows the earlier example with the first correction in place.</span></span>

```vb
Class Customer

    ' The class has a field named Index.
    Private Index As Integer

    Sub Main()

        For I = 1 To 10
            ' ...
        Next

    End Sub
End Class
```

## <a name="see-also"></a><span data-ttu-id="6c511-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="6c511-118">See also</span></span>

- [<span data-ttu-id="6c511-119">Option Infer (instrucción)</span><span class="sxs-lookup"><span data-stu-id="6c511-119">Option Infer Statement</span></span>](../../../visual-basic/language-reference/statements/option-infer-statement.md)
- [<span data-ttu-id="6c511-120">For Each...Next (instrucción)</span><span class="sxs-lookup"><span data-stu-id="6c511-120">For Each...Next Statement</span></span>](../../../visual-basic/language-reference/statements/for-each-next-statement.md)
- [<span data-ttu-id="6c511-121">For...Next (instrucción)</span><span class="sxs-lookup"><span data-stu-id="6c511-121">For...Next Statement</span></span>](../../../visual-basic/language-reference/statements/for-next-statement.md)
- [<span data-ttu-id="6c511-122">Procedimientos: Hacer referencia a la instancia actual de un objeto</span><span class="sxs-lookup"><span data-stu-id="6c511-122">How to: Refer to the Current Instance of an Object</span></span>](../../../visual-basic/programming-guide/language-features/variables/how-to-refer-to-the-current-instance-of-an-object.md)
- [<span data-ttu-id="6c511-123">Inferencia de tipo de variable local</span><span class="sxs-lookup"><span data-stu-id="6c511-123">Local Type Inference</span></span>](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
- [<span data-ttu-id="6c511-124">Me, My, MyBase y MyClass</span><span class="sxs-lookup"><span data-stu-id="6c511-124">Me, My, MyBase, and MyClass</span></span>](../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
