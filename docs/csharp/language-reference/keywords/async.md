---
title: 'async: Referencia de C#'
ms.custom: seodec18
ms.date: 05/22/2017
f1_keywords:
- async_CSharpKeyword
helpviewer_keywords:
- async keyword [C#]
- async method [C#]
- async [C#]
ms.assetid: 16f14f09-b2ce-42c7-a875-e4eca5d50674
ms.openlocfilehash: 346cfccd076866e9c321974aaa8c8ddd367a17ea
ms.sourcegitcommit: 83ecdf731dc1920bca31f017b1556c917aafd7a0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/12/2019
ms.locfileid: "67859576"
---
# <a name="async-c-reference"></a><span data-ttu-id="a7a5d-102">async (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="a7a5d-102">async (C# Reference)</span></span>
<span data-ttu-id="a7a5d-103">Use el modificador `async` para especificar que un método, una [expresión lambda](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md) o un [método anónimo](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md) es asincrónico.</span><span class="sxs-lookup"><span data-stu-id="a7a5d-103">Use the `async` modifier to specify that a method, [lambda expression](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md), or [anonymous method](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md) is asynchronous.</span></span> <span data-ttu-id="a7a5d-104">Si usa este modificador en un método o una expresión, se hace referencia al mismo como un *método asincrónico*.</span><span class="sxs-lookup"><span data-stu-id="a7a5d-104">If you use this modifier on a method or expression, it's referred to as an *async method*.</span></span> <span data-ttu-id="a7a5d-105">En el ejemplo siguiente se define un método asincrónico denominado `ExampleMethodAsync`:</span><span class="sxs-lookup"><span data-stu-id="a7a5d-105">The following example defines an async method named `ExampleMethodAsync`:</span></span> 
  
```csharp  
public async Task<int> ExampleMethodAsync()  
{  
    // . . . .  
}  
```  
 
<span data-ttu-id="a7a5d-106">Si no está familiarizado con la programación asincrónica o no entiende cómo un método asincrónico usa la palabra clave `await` para hacer el trabajo de larga duración sin bloquear el subproceso del autor de la llamada, lea la introducción de [Programación asincrónica con async y await](../../../csharp/programming-guide/concepts/async/index.md).</span><span class="sxs-lookup"><span data-stu-id="a7a5d-106">If you're new to asynchronous programming or do not understand how an async method uses the `await` keyword to do potentially long-running work without blocking the caller’s thread, read the introduction in [Asynchronous Programming with async and await](../../../csharp/programming-guide/concepts/async/index.md).</span></span> <span data-ttu-id="a7a5d-107">El siguiente código se encuentra dentro de un método asincrónico y llama al método <xref:System.Net.Http.HttpClient.GetStringAsync%2a?displayProperty=nameWithType>:</span><span class="sxs-lookup"><span data-stu-id="a7a5d-107">The following code is found inside an async method and calls the <xref:System.Net.Http.HttpClient.GetStringAsync%2a?displayProperty=nameWithType> method:</span></span> 
  
```csharp  
string contents = await httpClient.GetStringAsync(requestUrl);  
```  
  
<span data-ttu-id="a7a5d-108">Un método asincrónico se ejecuta sincrónicamente hasta alcanzar la primera expresión `await`, en la que se suspende el método hasta que se complete la tarea en espera.</span><span class="sxs-lookup"><span data-stu-id="a7a5d-108">An async method runs synchronously until it reaches its first `await` expression, at which point the method is suspended until the awaited task is complete.</span></span> <span data-ttu-id="a7a5d-109">Mientras tanto, el control vuelve al llamador del método, como se muestra en el ejemplo de la sección siguiente.</span><span class="sxs-lookup"><span data-stu-id="a7a5d-109">In the meantime, control returns to the caller of the method, as the example in the next section shows.</span></span>  
  
<span data-ttu-id="a7a5d-110">Si el método que la palabra clave `async` modifica no contiene una expresión o instrucción `await`, el método se ejecuta de forma sincrónica.</span><span class="sxs-lookup"><span data-stu-id="a7a5d-110">If the method that the `async` keyword modifies doesn't contain an `await` expression or statement, the method executes synchronously.</span></span> <span data-ttu-id="a7a5d-111">Una advertencia del compilador alerta de cualquier método asincrónico que no contenga instrucciones de `await`, porque esa situación podría indicar un error.</span><span class="sxs-lookup"><span data-stu-id="a7a5d-111">A compiler warning alerts you to any async methods that don't contain `await` statements, because that situation might indicate an error.</span></span> <span data-ttu-id="a7a5d-112">Vea [Compiler Warning (level 1) CS4014](../../../csharp/language-reference/compiler-messages/cs4014.md) (Advertencia del compilador (nivel 1) CS4014).</span><span class="sxs-lookup"><span data-stu-id="a7a5d-112">See [Compiler Warning (level 1) CS4014](../../../csharp/language-reference/compiler-messages/cs4014.md).</span></span>  
  
 <span data-ttu-id="a7a5d-113">La palabra clave `async` es contextual en el sentido de que es una palabra clave cuando modifica un método, una expresión lambda o un método anónimo.</span><span class="sxs-lookup"><span data-stu-id="a7a5d-113">The `async` keyword is contextual in that it's a keyword only when it modifies a method, a lambda expression, or an anonymous method.</span></span> <span data-ttu-id="a7a5d-114">En todos los demás contextos, se interpreta como identificador.</span><span class="sxs-lookup"><span data-stu-id="a7a5d-114">In all other contexts, it's interpreted as an identifier.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a7a5d-115">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a7a5d-115">Example</span></span>  
<span data-ttu-id="a7a5d-116">En el ejemplo siguiente se muestra la estructura y el flujo de control entre un controlador de eventos asincrónicos, `StartButton_Click`, y un método asincrónico, `ExampleMethodAsync`.</span><span class="sxs-lookup"><span data-stu-id="a7a5d-116">The following example shows the structure and flow of control between an async event handler, `StartButton_Click`, and an async method, `ExampleMethodAsync`.</span></span> <span data-ttu-id="a7a5d-117">El resultado del método asincrónico es el número de caracteres de una página web.</span><span class="sxs-lookup"><span data-stu-id="a7a5d-117">The result from the async method is the number of characters of a web page.</span></span> <span data-ttu-id="a7a5d-118">El código es adecuado para una aplicación Windows Presentation Foundation (WPF) o de la Tienda Windows creada en Visual Studio; vea los comentarios del código para configurar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="a7a5d-118">The code is suitable for a Windows Presentation Foundation (WPF) app or Windows Store app that you create in Visual Studio; see the code comments for setting up the app.</span></span>  

<span data-ttu-id="a7a5d-119">Puede ejecutar este código en Visual Studio como una aplicación Windows Presentation Foundation (WPF) o una aplicación de la Tienda Windows.</span><span class="sxs-lookup"><span data-stu-id="a7a5d-119">You can run this code in Visual Studio as a Windows Presentation Foundation (WPF) app or a Windows Store app.</span></span> <span data-ttu-id="a7a5d-120">Necesita un control de botón denominado `StartButton` y un control de cuadro de texto denominado `ResultsTextBox`.</span><span class="sxs-lookup"><span data-stu-id="a7a5d-120">You need a Button control named `StartButton` and a Textbox control named `ResultsTextBox`.</span></span> <span data-ttu-id="a7a5d-121">Recuerde establecer los nombres y el controlador de manera que tenga algo similar a esto:</span><span class="sxs-lookup"><span data-stu-id="a7a5d-121">Remember to set the names and handler so that you have something like this:</span></span>  

```xaml
<Button Content="Button" HorizontalAlignment="Left" Margin="88,77,0,0" VerticalAlignment="Top" Width="75"  
        Click="StartButton_Click" Name="StartButton"/>  
<TextBox HorizontalAlignment="Left" Height="137" Margin="88,140,0,0" TextWrapping="Wrap"   
         Text="&lt;Enter a URL&gt;" VerticalAlignment="Top" Width="310" Name="ResultsTextBox"/>  
```
  
<span data-ttu-id="a7a5d-122">Para ejecutar el código como una aplicación WPF:</span><span class="sxs-lookup"><span data-stu-id="a7a5d-122">To run the code as a WPF app:</span></span>  

- <span data-ttu-id="a7a5d-123">Pegue este código en la clase `MainWindow` en MainWindow.xaml.cs.</span><span class="sxs-lookup"><span data-stu-id="a7a5d-123">Paste this code into the `MainWindow` class in MainWindow.xaml.cs.</span></span>  
- <span data-ttu-id="a7a5d-124">Agregue una referencia a System.Net.Http.</span><span class="sxs-lookup"><span data-stu-id="a7a5d-124">Add a reference to System.Net.Http.</span></span>  
- <span data-ttu-id="a7a5d-125">Agregue una directiva `using` a System.Net.Http.</span><span class="sxs-lookup"><span data-stu-id="a7a5d-125">Add a `using` directive for System.Net.Http.</span></span>  
  
<span data-ttu-id="a7a5d-126">Para ejecutar el código como una aplicación de la Tienda Windows:</span><span class="sxs-lookup"><span data-stu-id="a7a5d-126">To run the code as a Windows Store app:</span></span>  
- <span data-ttu-id="a7a5d-127">Pegue este código en la clase `MainPage` en MainPage.xaml.cs.</span><span class="sxs-lookup"><span data-stu-id="a7a5d-127">Paste this code into the `MainPage` class in MainPage.xaml.cs.</span></span>  
- <span data-ttu-id="a7a5d-128">Agregue directivas using para System.Net.Http y System.Threading.Tasks.</span><span class="sxs-lookup"><span data-stu-id="a7a5d-128">Add using directives for System.Net.Http and System.Threading.Tasks.</span></span>  
  
[!code-csharp[wpf-async](../../../../samples/snippets/csharp/language-reference/keywords/async/wpf/mainwindow.xaml.cs#1)]
  
> [!IMPORTANT]
>  <span data-ttu-id="a7a5d-129">Para más información sobre las tareas y el código que se ejecuta mientras se espera la finalización por una tarea, vea [Programación asincrónica con async y await](../../../csharp/programming-guide/concepts/async/index.md).</span><span class="sxs-lookup"><span data-stu-id="a7a5d-129">For more information about tasks and the code that executes while waiting for a task, see [Asynchronous Programming with async and await](../../../csharp/programming-guide/concepts/async/index.md).</span></span> <span data-ttu-id="a7a5d-130">Para obtener un ejemplo completo de WPF en el que se usan elementos similares, vea [Tutorial: Acceso a la Web usando async y await](../../../csharp/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md).</span><span class="sxs-lookup"><span data-stu-id="a7a5d-130">For a full WPF example that uses similar elements, see [Walkthrough: Accessing the Web by Using Async and Await](../../../csharp/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md).</span></span>  
  
## <a name="return-types"></a><span data-ttu-id="a7a5d-131">Tipos de valor devueltos</span><span class="sxs-lookup"><span data-stu-id="a7a5d-131">Return Types</span></span>  
<span data-ttu-id="a7a5d-132">Un método asincrónico puede tener los siguientes tipos de valor devuelto:</span><span class="sxs-lookup"><span data-stu-id="a7a5d-132">An async method can have the following return types:</span></span>

- <xref:System.Threading.Tasks.Task>
- <xref:System.Threading.Tasks.Task%601>
- <span data-ttu-id="a7a5d-133">[void](../../../csharp/language-reference/keywords/void.md).</span><span class="sxs-lookup"><span data-stu-id="a7a5d-133">[void](../../../csharp/language-reference/keywords/void.md).</span></span> <span data-ttu-id="a7a5d-134">Los métodos `async void` no suelen ser recomendables para código que no sea controladores de eventos dado que los autores de la llamada no pueden usar `await` con esos métodos y deben implementar otro mecanismo para informar sobre la finalización correcta o condiciones de error.</span><span class="sxs-lookup"><span data-stu-id="a7a5d-134">`async void` methods are generally discouraged for code other than event handlers because callers cannot `await` those methods and must implement a different mechanism to report successful completion or error conditions.</span></span>
- <span data-ttu-id="a7a5d-135">A partir de C# 7.0, cualquier tipo que tenga un método `GetAwaiter` accesible.</span><span class="sxs-lookup"><span data-stu-id="a7a5d-135">Starting with C# 7.0, any type that has an accessible `GetAwaiter` method.</span></span> <span data-ttu-id="a7a5d-136">El tipo `System.Threading.Tasks.ValueTask<TResult>` es una implementación de ese tipo.</span><span class="sxs-lookup"><span data-stu-id="a7a5d-136">The `System.Threading.Tasks.ValueTask<TResult>` type is one such implementation.</span></span> <span data-ttu-id="a7a5d-137">Está disponible agregando el paquete NuGet `System.Threading.Tasks.Extensions`.</span><span class="sxs-lookup"><span data-stu-id="a7a5d-137">It is available by adding the NuGet package `System.Threading.Tasks.Extensions`.</span></span> 

<span data-ttu-id="a7a5d-138">El método asincrónico no puede declarar ningún parámetro [in](../../../csharp/language-reference/keywords/in-parameter-modifier.md), [ref](../../../csharp/language-reference/keywords/ref.md) o [out](../../../csharp/language-reference/keywords/out-parameter-modifier.md), ni puede tener un [valor devuelto de referencia](../../programming-guide/classes-and-structs/ref-returns.md), pero puede llamar a los métodos que tienen estos parámetros.</span><span class="sxs-lookup"><span data-stu-id="a7a5d-138">The async method can't declare any [in](../../../csharp/language-reference/keywords/in-parameter-modifier.md), [ref](../../../csharp/language-reference/keywords/ref.md) or [out](../../../csharp/language-reference/keywords/out-parameter-modifier.md) parameters, nor can it have a [reference return value](../../programming-guide/classes-and-structs/ref-returns.md), but it can call methods that have such parameters.</span></span>  
  
<span data-ttu-id="a7a5d-139">Se puede especificar `Task<TResult>` como el tipo de valor devuelto de un método asincrónico si la instrucción [return](../../../csharp/language-reference/keywords/return.md) del método especifica un operando de tipo `TResult`.</span><span class="sxs-lookup"><span data-stu-id="a7a5d-139">You specify `Task<TResult>` as the return type of an async method if the [return](../../../csharp/language-reference/keywords/return.md) statement of the method specifies an operand of type `TResult`.</span></span> <span data-ttu-id="a7a5d-140">Utilice `Task` si no se devuelve ningún valor significativo al completarse el método.</span><span class="sxs-lookup"><span data-stu-id="a7a5d-140">You use `Task` if no meaningful value is returned when the method is completed.</span></span> <span data-ttu-id="a7a5d-141">Es decir, una llamada al método devuelve `Task`, pero cuando se completa `Task`, las expresiones `await` que esperan a que `Task` finalice se evalúan como `void`.</span><span class="sxs-lookup"><span data-stu-id="a7a5d-141">That is, a call to the method returns a `Task`, but when the `Task` is completed, any `await` expression that's awaiting the `Task` evaluates to `void`.</span></span>  
  
<span data-ttu-id="a7a5d-142">El tipo devuelto `void` se utiliza principalmente para definir controladores de eventos, que requieren ese tipo devuelto.</span><span class="sxs-lookup"><span data-stu-id="a7a5d-142">You use the `void` return type primarily to define event handlers, which require that return type.</span></span> <span data-ttu-id="a7a5d-143">El llamador de un método asincrónico que devuelva `void` no puede esperar a que finalice y no puede detectar las excepciones que el método inicia.</span><span class="sxs-lookup"><span data-stu-id="a7a5d-143">The caller of a `void`-returning async method can't await it and can't catch exceptions that the method throws.</span></span>  

<span data-ttu-id="a7a5d-144">A partir de C# 7.0, devuelve otro tipo, normalmente un tipo de valor, que tiene un método `GetAwaiter` para minimizar las asignaciones de memoria en secciones críticas de rendimiento del código.</span><span class="sxs-lookup"><span data-stu-id="a7a5d-144">Starting with C# 7.0, you return another type, typically a value type, that has a `GetAwaiter` method to minimize memory allocations in performance-critical sections of code.</span></span> 

<span data-ttu-id="a7a5d-145">Para más información y ejemplos, vea [Tipos de valor devueltos asincrónicos](../../../csharp/programming-guide/concepts/async/async-return-types.md).</span><span class="sxs-lookup"><span data-stu-id="a7a5d-145">For more information and examples, see [Async Return Types](../../../csharp/programming-guide/concepts/async/async-return-types.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a7a5d-146">Vea también</span><span class="sxs-lookup"><span data-stu-id="a7a5d-146">See also</span></span>

- <xref:System.Runtime.CompilerServices.AsyncStateMachineAttribute>
- [<span data-ttu-id="a7a5d-147">await</span><span class="sxs-lookup"><span data-stu-id="a7a5d-147">await</span></span>](../../../csharp/language-reference/keywords/await.md)
- [<span data-ttu-id="a7a5d-148">Tutorial: Acceso a la Web usando async y await</span><span class="sxs-lookup"><span data-stu-id="a7a5d-148">Walkthrough: Accessing the Web by Using Async and Await</span></span>](../../../csharp/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md)
- [<span data-ttu-id="a7a5d-149">Programación asincrónica con Async y Await</span><span class="sxs-lookup"><span data-stu-id="a7a5d-149">Asynchronous Programming with async and await</span></span>](../../../csharp/programming-guide/concepts/async/index.md)
