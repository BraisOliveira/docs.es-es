---
title: Variable de objeto o de bloque With no establecida
ms.date: 07/20/2015
f1_keywords:
- vbrID91
ms.assetid: 2f03e611-f0ed-465c-99a2-a816e034faa3
ms.openlocfilehash: 766b95163f164ec76135b964115069b6855ceebf
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64750677"
---
# <a name="object-variable-or-with-block-variable-not-set"></a><span data-ttu-id="72f05-102">Variable de objeto o de bloque With no establecida</span><span class="sxs-lookup"><span data-stu-id="72f05-102">Object variable or With block variable not set</span></span>
<span data-ttu-id="72f05-103">Se hace referencia a una variable de objeto no válido.</span><span class="sxs-lookup"><span data-stu-id="72f05-103">An invalid object variable is being referenced.</span></span>   <span data-ttu-id="72f05-104">Este error puede producirse por varias razones:</span><span class="sxs-lookup"><span data-stu-id="72f05-104">This error can occur for several reasons:</span></span>

- <span data-ttu-id="72f05-105">Se declaró una variable sin especificar un tipo.</span><span class="sxs-lookup"><span data-stu-id="72f05-105">A variable was declared without specifying a type.</span></span> <span data-ttu-id="72f05-106">Si se declara una variable sin especificar un tipo, el valor predeterminado es para que escriba `Object`.</span><span class="sxs-lookup"><span data-stu-id="72f05-106">If a variable is declared without specifying a type, it defaults to type `Object`.</span></span>

    <span data-ttu-id="72f05-107">Por ejemplo, una variable declarada con `Dim x` sería de tipo `Object;` una variable declarada con `Dim x As String` sería de tipo `String`.</span><span class="sxs-lookup"><span data-stu-id="72f05-107">For example, a variable declared with `Dim x` would be of type `Object;` a variable declared with `Dim x As String` would be of type `String`.</span></span>

    > [!TIP]
    >  <span data-ttu-id="72f05-108">El `Option Strict` instrucción no permite tipos implícitos que da como resultado un `Object` tipo.</span><span class="sxs-lookup"><span data-stu-id="72f05-108">The `Option Strict` statement disallows implicit typing that results in an `Object` type.</span></span> <span data-ttu-id="72f05-109">Si se omite el tipo, se producirá un error de tiempo de compilación.</span><span class="sxs-lookup"><span data-stu-id="72f05-109">If you omit the type, a compile-time error will occur.</span></span> <span data-ttu-id="72f05-110">Consulte [Option Strict (instrucción)](../../../visual-basic/language-reference/statements/option-strict-statement.md).</span><span class="sxs-lookup"><span data-stu-id="72f05-110">See [Option Strict Statement](../../../visual-basic/language-reference/statements/option-strict-statement.md).</span></span>

- <span data-ttu-id="72f05-111">Está intentando hacer referencia a un objeto que se ha establecido en `Nothing`.</span><span class="sxs-lookup"><span data-stu-id="72f05-111">You are attempting to reference an object that has been set to `Nothing`.</span></span>

- <span data-ttu-id="72f05-112">Está intentando obtener acceso a un elemento de una variable de matriz que no se ha declarado correctamente.</span><span class="sxs-lookup"><span data-stu-id="72f05-112">You are attempting to access an element of an array variable that wasn't properly declared.</span></span>

    <span data-ttu-id="72f05-113">Por ejemplo, se declara una matriz como `products() As String` desencadenará el error si intenta hacer referencia a un elemento de la matriz `products(3) = "Widget"`.</span><span class="sxs-lookup"><span data-stu-id="72f05-113">For example, an array declared as `products() As String` will trigger the error if you try to reference an element of the array `products(3) = "Widget"`.</span></span> <span data-ttu-id="72f05-114">La matriz no tiene elementos y se trata como un objeto.</span><span class="sxs-lookup"><span data-stu-id="72f05-114">The array has no elements and is treated as an object.</span></span>

- <span data-ttu-id="72f05-115">Está intentando código de acceso dentro de un `With...End With` bloquear antes de que el bloque se ha inicializado.</span><span class="sxs-lookup"><span data-stu-id="72f05-115">You are attempting to access code within a `With...End With` block before the block has been initialized.</span></span>   <span data-ttu-id="72f05-116">Un `With...End With` bloque debe inicializarse mediante la ejecución de la `With` punto de entrada de la instrucción.</span><span class="sxs-lookup"><span data-stu-id="72f05-116">A `With...End With` block must be initialized by executing the `With` statement entry point.</span></span>

> [!NOTE]
> <span data-ttu-id="72f05-117">En versiones anteriores de Visual Basic o VBA, este error también se desencadenó asignando un valor a una variable sin usar el `Set` palabra clave (`x = "name"` en lugar de `Set x = "name"`).</span><span class="sxs-lookup"><span data-stu-id="72f05-117">In earlier versions of Visual Basic or VBA this error was also triggered by assigning a value to a variable without using the `Set` keyword (`x = "name"` instead of `Set x = "name"`).</span></span> <span data-ttu-id="72f05-118">El `Set` palabra clave ya no es válido en Visual Basic. NET.</span><span class="sxs-lookup"><span data-stu-id="72f05-118">The `Set` keyword is no longer valid in Visual Basic .Net.</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="72f05-119">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="72f05-119">To correct this error</span></span>

1. <span data-ttu-id="72f05-120">Establecer `Option Strict` a `On` agregando el código siguiente al principio del archivo:</span><span class="sxs-lookup"><span data-stu-id="72f05-120">Set `Option Strict` to `On` by adding the following code to the beginning of the file:</span></span>

    ```vb
    Option Strict On
    ```

    <span data-ttu-id="72f05-121">Al ejecutar el proyecto, aparecerá un error del compilador en el **lista de errores** para cualquier variable que se especificó sin tipo.</span><span class="sxs-lookup"><span data-stu-id="72f05-121">When you run the project, a compiler error will appear in the **Error List** for any variable that was specified without a type.</span></span>

2. <span data-ttu-id="72f05-122">Si no desea habilitar `Option Strict`, busque el código para las variables que se especificaron sin tipo (`Dim x` en lugar de `Dim x As String`) y agregue el tipo deseado a la declaración.</span><span class="sxs-lookup"><span data-stu-id="72f05-122">If you don't want to enable `Option Strict`, search your code for any variables that were specified without a type (`Dim x` instead of `Dim x As String`) and add the intended type to the declaration.</span></span>

3. <span data-ttu-id="72f05-123">Asegúrese de que no está haciendo referencia a una variable de objeto que se ha establecido en `Nothing`.</span><span class="sxs-lookup"><span data-stu-id="72f05-123">Make sure you aren't referring to  an object variable that has been set to `Nothing`.</span></span>  <span data-ttu-id="72f05-124">Busque el código para la palabra clave `Nothing`y revise el código para que el objeto no está establecido en `Nothing` hasta que una vez haya hecho referencia.</span><span class="sxs-lookup"><span data-stu-id="72f05-124">Search your code for the keyword `Nothing`, and revise your code so that the object isn't set to `Nothing` until after you have referenced it.</span></span>

4. <span data-ttu-id="72f05-125">Asegúrese de que las variables de matriz están influenciadas antes de tener acceso a ellos.</span><span class="sxs-lookup"><span data-stu-id="72f05-125">Make sure that any array  variables are dimensioned before you access them.</span></span> <span data-ttu-id="72f05-126">Se puede asignar una dimensión cuando se crea la matriz (`Dim x(5) As String` en lugar de `Dim x() As String`), o usar el `ReDim` palabra clave para establecer las dimensiones de la matriz antes de que se acceda por primera vez.</span><span class="sxs-lookup"><span data-stu-id="72f05-126">You can either assign a dimension when you first create the array (`Dim x(5) As String` instead of `Dim x() As String`), or use the `ReDim` keyword to set the dimensions of the array before you first access it.</span></span>

5. <span data-ttu-id="72f05-127">Asegúrese de que su `With` bloque se inicializa mediante la ejecución de la `With` punto de entrada de la instrucción.</span><span class="sxs-lookup"><span data-stu-id="72f05-127">Make sure your `With` block is initialized by executing the `With` statement entry point.</span></span>

## <a name="see-also"></a><span data-ttu-id="72f05-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="72f05-128">See also</span></span>

- [<span data-ttu-id="72f05-129">Declaración de variables de objeto</span><span class="sxs-lookup"><span data-stu-id="72f05-129">Object Variable Declaration</span></span>](../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md)
- [<span data-ttu-id="72f05-130">ReDim (instrucción)</span><span class="sxs-lookup"><span data-stu-id="72f05-130">ReDim Statement</span></span>](../../../visual-basic/language-reference/statements/redim-statement.md)
- [<span data-ttu-id="72f05-131">With...End With (instrucción)</span><span class="sxs-lookup"><span data-stu-id="72f05-131">With...End With Statement</span></span>](../../../visual-basic/language-reference/statements/with-end-with-statement.md)
