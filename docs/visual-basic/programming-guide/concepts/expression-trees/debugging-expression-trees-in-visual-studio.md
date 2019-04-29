---
title: Depuración de árboles de expresión en Visual Studio (Visual Basic)
ms.date: 07/20/2015
ms.assetid: 492cc28f-b7a2-4c47-b582-b3c437b8a5d5
ms.openlocfilehash: fb5905c3c1124dd64371216bddda0a17235abdce
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61787197"
---
# <a name="debugging-expression-trees-in-visual-studio-visual-basic"></a><span data-ttu-id="fd953-102">Depuración de árboles de expresión en Visual Studio (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fd953-102">Debugging Expression Trees in Visual Studio (Visual Basic)</span></span>

<span data-ttu-id="fd953-103">Se puede analizar la estructura y el contenido de los árboles de expresión cuando se depuran las aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="fd953-103">You can analyze the structure and content of expression trees when you debug your applications.</span></span> <span data-ttu-id="fd953-104">Para obtener una introducción rápida de la estructura de árbol de expresión, puede usar la propiedad `DebugView`, que solo está disponible en modo de depuración.</span><span class="sxs-lookup"><span data-stu-id="fd953-104">To get a quick overview of the expression tree structure, you can use the `DebugView` property, which is available only in debug mode.</span></span> <span data-ttu-id="fd953-105">Para más información sobre la depuración, vea [Debugging in Visual Studio](/visualstudio/debugger/debugging-in-visual-studio) (Depuración en Visual Studio).</span><span class="sxs-lookup"><span data-stu-id="fd953-105">For more information about debugging, see [Debugging in Visual Studio](/visualstudio/debugger/debugging-in-visual-studio).</span></span>

<span data-ttu-id="fd953-106">Para representar mejor el contenido de árboles de expresión, la propiedad `DebugView` usa los visualizadores de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="fd953-106">To better represent the content of expression trees, the `DebugView` property uses Visual Studio visualizers.</span></span> <span data-ttu-id="fd953-107">Para obtener más información, vea [Create Custom Visualizers](/visualstudio/debugger/create-custom-visualizers-of-data) (Crear visualizadores personalizados).</span><span class="sxs-lookup"><span data-stu-id="fd953-107">For more information, see [Create Custom Visualizers](/visualstudio/debugger/create-custom-visualizers-of-data).</span></span>

### <a name="to-open-a-visualizer-for-an-expression-tree"></a><span data-ttu-id="fd953-108">Para abrir un visualizador para un árbol de expresión</span><span class="sxs-lookup"><span data-stu-id="fd953-108">To open a visualizer for an expression tree</span></span>

1. <span data-ttu-id="fd953-109">Haga clic en el icono de lupa que aparece junto a la propiedad `DebugView` de un árbol de expresión en **Información sobre datos**, en una ventana **Inspección** o en las ventanas **Automático** o **Variables locales**.</span><span class="sxs-lookup"><span data-stu-id="fd953-109">Click the magnifying glass icon that appears next to the `DebugView` property of an expression tree in **DataTips**, a **Watch** window, the **Autos** window, or the **Locals** window.</span></span>

    <span data-ttu-id="fd953-110">Se mostrará una lista de visualizadores.</span><span class="sxs-lookup"><span data-stu-id="fd953-110">A list of visualizers is displayed.</span></span>

2. <span data-ttu-id="fd953-111">Haga clic en el visualizador que desee usar.</span><span class="sxs-lookup"><span data-stu-id="fd953-111">Click the visualizer you want to use.</span></span>

<span data-ttu-id="fd953-112">Cada tipo de expresión se muestra en el visualizador como se describe en las secciones siguientes.</span><span class="sxs-lookup"><span data-stu-id="fd953-112">Each expression type is displayed in the visualizer as described in the following sections.</span></span>

## <a name="parameterexpressions"></a><span data-ttu-id="fd953-113">ParameterExpressions</span><span class="sxs-lookup"><span data-stu-id="fd953-113">ParameterExpressions</span></span>

<span data-ttu-id="fd953-114">Los nombres de variable <xref:System.Linq.Expressions.ParameterExpression> se muestran con un símbolo "$" al principio.</span><span class="sxs-lookup"><span data-stu-id="fd953-114"><xref:System.Linq.Expressions.ParameterExpression> variable names are displayed with a "$" symbol at the beginning.</span></span>

<span data-ttu-id="fd953-115">Si un parámetro no tiene un nombre, se le asigna un nombre generado automáticamente, como `$var1` o `$var2`.</span><span class="sxs-lookup"><span data-stu-id="fd953-115">If a parameter does not have a name, it is assigned an automatically generated name, such as `$var1` or `$var2`.</span></span>

### <a name="examples"></a><span data-ttu-id="fd953-116">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="fd953-116">Examples</span></span>

- `Expression`

    ```vb
    Dim numParam As ParameterExpression =
    Expression.Parameter(GetType(Integer), "num")
    ```

    <span data-ttu-id="fd953-117">Propiedad `DebugView`</span><span class="sxs-lookup"><span data-stu-id="fd953-117">`DebugView` property</span></span>

    `$num`

- `Expression`

    ```vb
    Dim numParam As ParameterExpression =
    Expression.Parameter(GetType(Integer))
    ```

    <span data-ttu-id="fd953-118">Propiedad `DebugView`</span><span class="sxs-lookup"><span data-stu-id="fd953-118">`DebugView` property</span></span>

    `$var1`

## <a name="constantexpressions"></a><span data-ttu-id="fd953-119">ConstantExpressions</span><span class="sxs-lookup"><span data-stu-id="fd953-119">ConstantExpressions</span></span>
 <span data-ttu-id="fd953-120">Para los objetos <xref:System.Linq.Expressions.ConstantExpression> que representan valores enteros, cadenas y `null`, se muestra el valor de la constante.</span><span class="sxs-lookup"><span data-stu-id="fd953-120">For <xref:System.Linq.Expressions.ConstantExpression> objects that represent integer values, strings, and `null`, the value of the constant is displayed.</span></span>

### <a name="examples"></a><span data-ttu-id="fd953-121">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="fd953-121">Examples</span></span>

- `Expression`

    ```vb
    Dim num as Integer= 10
    Dim expr As ConstantExpression = Expression.Constant(num)
    ```

    <span data-ttu-id="fd953-122">Propiedad `DebugView`</span><span class="sxs-lookup"><span data-stu-id="fd953-122">`DebugView` property</span></span>

    <span data-ttu-id="fd953-123">10</span><span class="sxs-lookup"><span data-stu-id="fd953-123">10</span></span>

- `Expression`

    ```vb
    Dim num As Double = 10
    Dim expr As ConstantExpression = Expression.Constant(num)
    ```

    <span data-ttu-id="fd953-124">Propiedad `DebugView`</span><span class="sxs-lookup"><span data-stu-id="fd953-124">`DebugView` property</span></span>

    <span data-ttu-id="fd953-125">10D</span><span class="sxs-lookup"><span data-stu-id="fd953-125">10D</span></span>

## <a name="blockexpression"></a><span data-ttu-id="fd953-126">BlockExpression</span><span class="sxs-lookup"><span data-stu-id="fd953-126">BlockExpression</span></span>

<span data-ttu-id="fd953-127">Si el tipo de un objeto <xref:System.Linq.Expressions.BlockExpression> difiere del tipo de la última expresión del bloque, el tipo se muestra en la propiedad `DebugInfo` entre corchetes angulares (\< y >).</span><span class="sxs-lookup"><span data-stu-id="fd953-127">If the type of a <xref:System.Linq.Expressions.BlockExpression> object differs from the type of the last expression in the block, the type is displayed in the `DebugInfo` property in angle brackets (\< and >).</span></span> <span data-ttu-id="fd953-128">De otro modo, el tipo del objeto <xref:System.Linq.Expressions.BlockExpression> no se muestra.</span><span class="sxs-lookup"><span data-stu-id="fd953-128">Otherwise, the type of the <xref:System.Linq.Expressions.BlockExpression> object is not displayed.</span></span>

### <a name="examples"></a><span data-ttu-id="fd953-129">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="fd953-129">Examples</span></span>

- `Expression`

    ```vb
    Dim block As BlockExpression = Expression.Block(Expression.Constant("test"))
    ```

    <span data-ttu-id="fd953-130">Propiedad `DebugView`</span><span class="sxs-lookup"><span data-stu-id="fd953-130">`DebugView` property</span></span>

    `.Block() {`

    `"test"`

    `}`

- `Expression`

    ```vb
    Dim block As BlockExpression =
    Expression.Block(GetType(Object), Expression.Constant("test"))
    ```

    <span data-ttu-id="fd953-131">Propiedad `DebugView`</span><span class="sxs-lookup"><span data-stu-id="fd953-131">`DebugView` property</span></span>

    `.Block<System.Object>() {`

    `"test"`

    `}`

## <a name="lambdaexpression"></a><span data-ttu-id="fd953-132">LambdaExpression</span><span class="sxs-lookup"><span data-stu-id="fd953-132">LambdaExpression</span></span>

<span data-ttu-id="fd953-133">Los objetos <xref:System.Linq.Expressions.LambdaExpression> se muestran junto con sus tipos delegados.</span><span class="sxs-lookup"><span data-stu-id="fd953-133"><xref:System.Linq.Expressions.LambdaExpression> objects are displayed together with their delegate types.</span></span>

<span data-ttu-id="fd953-134">Si una expresión lambda no tiene un nombre, se le asigna un nombre generado automáticamente, como `#Lambda1` o `#Lambda2`.</span><span class="sxs-lookup"><span data-stu-id="fd953-134">If a lambda expression does not have a name, it is assigned an automatically generated name, such as `#Lambda1` or `#Lambda2`.</span></span>

### <a name="examples"></a><span data-ttu-id="fd953-135">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="fd953-135">Examples</span></span>

- `Expression`

    ```vb
    Dim lambda As LambdaExpression =
    Expression.Lambda(Of Func(Of Integer))(Expression.Constant(1))
    ```

    <span data-ttu-id="fd953-136">Propiedad `DebugView`</span><span class="sxs-lookup"><span data-stu-id="fd953-136">`DebugView` property</span></span>

    `.Lambda #Lambda1<System.Func'1[System.Int32]>() {`

    `1`

    `}`

- `Expression`

    ```vb
    Dim lambda As LambdaExpression =
    Expression.Lambda(Of Func(Of Integer))(Expression.Constant(1), "SampleLambda", Nothing)
    ```

    <span data-ttu-id="fd953-137">Propiedad `DebugView`</span><span class="sxs-lookup"><span data-stu-id="fd953-137">`DebugView` property</span></span>

    `.Lambda SampleLambda<System.Func'1[System.Int32]>() {`

    `1`

    `}`

## <a name="labelexpression"></a><span data-ttu-id="fd953-138">LabelExpression</span><span class="sxs-lookup"><span data-stu-id="fd953-138">LabelExpression</span></span>

<span data-ttu-id="fd953-139">Si especifica un valor predeterminado para el objeto <xref:System.Linq.Expressions.LabelExpression>, este valor se muestra antes del objeto <xref:System.Linq.Expressions.LabelTarget>.</span><span class="sxs-lookup"><span data-stu-id="fd953-139">If you specify a default value for the <xref:System.Linq.Expressions.LabelExpression> object, this value is displayed before the <xref:System.Linq.Expressions.LabelTarget> object.</span></span>

<span data-ttu-id="fd953-140">El token `.Label` indica el inicio de la etiqueta.</span><span class="sxs-lookup"><span data-stu-id="fd953-140">The `.Label` token indicates the start of the label.</span></span> <span data-ttu-id="fd953-141">El token `.LabelTarget` indica el destino al que se va a saltar.</span><span class="sxs-lookup"><span data-stu-id="fd953-141">The `.LabelTarget` token indicates the destination of the target to jump to.</span></span>

<span data-ttu-id="fd953-142">Si una etiqueta no tiene un nombre, se le asigna un nombre generado automáticamente, como `#Label1` o `#Label2`.</span><span class="sxs-lookup"><span data-stu-id="fd953-142">If a label does not have a name, it is assigned an automatically generated name, such as `#Label1` or `#Label2`.</span></span>

### <a name="examples"></a><span data-ttu-id="fd953-143">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="fd953-143">Examples</span></span>

- `Expression`

    ```vb
    Dim target As LabelTarget = Expression.Label(GetType(Integer), "SampleLabel")
    Dim label1 As BlockExpression = Expression.Block(
    Expression.Goto(target, Expression.Constant(0)),
    Expression.Label(target, Expression.Constant(-1)))
    ```

    <span data-ttu-id="fd953-144">Propiedad `DebugView`</span><span class="sxs-lookup"><span data-stu-id="fd953-144">`DebugView` property</span></span>

    `.Block() {`

    `.Goto SampleLabel { 0 };`

    `.Label`

    `-1`

    `.LabelTarget SampleLabel:`

    `}`

- `Expression`

    ```vb
    Dim target As LabelTarget = Expression.Label()
    Dim block As BlockExpression = Expression.Block(
    Expression.Goto(target), Expression.Label(target))
    ```

    <span data-ttu-id="fd953-145">Propiedad `DebugView`</span><span class="sxs-lookup"><span data-stu-id="fd953-145">`DebugView` property</span></span>

    `.Block() {`

    `.Goto #Label1 { };`

    `.Label`

    `.LabelTarget #Label1:`

    `}`

## <a name="checked-operators"></a><span data-ttu-id="fd953-146">Operadores activados</span><span class="sxs-lookup"><span data-stu-id="fd953-146">Checked Operators</span></span>

<span data-ttu-id="fd953-147">Los operadores activados se muestran con el símbolo "#" delante del operador.</span><span class="sxs-lookup"><span data-stu-id="fd953-147">Checked operators are displayed with the "#" symbol in front of the operator.</span></span> <span data-ttu-id="fd953-148">Por ejemplo, el operador de adición activado se muestra como `#+`.</span><span class="sxs-lookup"><span data-stu-id="fd953-148">For example, the checked addition operator is displayed as `#+`.</span></span>

### <a name="examples"></a><span data-ttu-id="fd953-149">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="fd953-149">Examples</span></span>

- `Expression`

    ```vb
    Dim expr As Expression = Expression.AddChecked(
    Expression.Constant(1), Expression.Constant(2))
    ```

    <span data-ttu-id="fd953-150">Propiedad `DebugView`</span><span class="sxs-lookup"><span data-stu-id="fd953-150">`DebugView` property</span></span>

    `1 #+ 2`

- `Expression`

    ```vb
    Dim expr As Expression = Expression.ConvertChecked(
    Expression.Constant(10.0), GetType(Integer))
    ```

    <span data-ttu-id="fd953-151">Propiedad `DebugView`</span><span class="sxs-lookup"><span data-stu-id="fd953-151">`DebugView` property</span></span>

    `#(System.Int32)10D`

## <a name="see-also"></a><span data-ttu-id="fd953-152">Vea también</span><span class="sxs-lookup"><span data-stu-id="fd953-152">See also</span></span>

- [<span data-ttu-id="fd953-153">Árboles de expresión (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fd953-153">Expression Trees (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/expression-trees/index.md)
- [<span data-ttu-id="fd953-154">Depurar en Visual Studio</span><span class="sxs-lookup"><span data-stu-id="fd953-154">Debugging in Visual Studio</span></span>](/visualstudio/debugger/debugging-in-visual-studio)
- <span data-ttu-id="fd953-155">[Create Custom Visualizers](/visualstudio/debugger/create-custom-visualizers-of-data) (Crear visualizadores personalizados)</span><span class="sxs-lookup"><span data-stu-id="fd953-155">[Create Custom Visualizers](/visualstudio/debugger/create-custom-visualizers-of-data)</span></span>
