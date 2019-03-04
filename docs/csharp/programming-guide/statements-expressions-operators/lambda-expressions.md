---
title: 'Expresiones lambda: Guía de programación de C#'
ms.custom: seodec18
ms.date: 03/03/2017
helpviewer_keywords:
- lambda expressions [C#]
- outer variables [C#]
- statement lambda [C#]
- expression lambda [C#]
- expressions [C#], lambda
ms.assetid: 57e3ba27-9a82-4067-aca7-5ca446b7bf93
ms.openlocfilehash: 77701653abacbe6d876c0890a11586f0840bad5d
ms.sourcegitcommit: 41c0637e894fbcd0713d46d6ef1866f08dc321a2
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/01/2019
ms.locfileid: "57200902"
---
# <a name="lambda-expressions-c-programming-guide"></a><span data-ttu-id="6dc70-102">Expresiones lambda (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="6dc70-102">Lambda expressions (C# Programming Guide)</span></span>

<span data-ttu-id="6dc70-103">Una expresión lambda es una [función anónima](anonymous-methods.md) que se puede usar para crear tipos [delegados](../delegates/using-delegates.md) o de [árbol de expresión](../concepts/expression-trees/index.md) .</span><span class="sxs-lookup"><span data-stu-id="6dc70-103">A lambda expression is an [anonymous function](anonymous-methods.md) that you can use to create [delegates](../delegates/using-delegates.md) or [expression tree](../concepts/expression-trees/index.md) types.</span></span> <span data-ttu-id="6dc70-104">Al utilizar expresiones lambda, puede escribir funciones locales que se pueden pasar como argumentos o devolverse como valor de llamadas de función.</span><span class="sxs-lookup"><span data-stu-id="6dc70-104">By using lambda expressions, you can write local functions that can be passed as arguments or returned as the value of function calls.</span></span> <span data-ttu-id="6dc70-105">Las expresiones lambda son especialmente útiles para escribir expresiones de consulta LINQ.</span><span class="sxs-lookup"><span data-stu-id="6dc70-105">Lambda expressions are particularly helpful for writing LINQ query expressions.</span></span>
  
<span data-ttu-id="6dc70-106">Para crear una expresión lambda, especifique los parámetros de entrada (si existen) a la izquierda del operador lambda [=>](../../../csharp/language-reference/operators/lambda-operator.md)y coloque el bloque de expresiones o de instrucciones en el otro lado.</span><span class="sxs-lookup"><span data-stu-id="6dc70-106">To create a lambda expression, you specify input parameters (if any) on the left side of the lambda operator [=>](../../../csharp/language-reference/operators/lambda-operator.md), and you put the expression or statement block on the other side.</span></span> <span data-ttu-id="6dc70-107">Por ejemplo, la expresión lambda `x => x * x` especifica un parámetro denominado `x` y devuelve el valor de `x` cuadrado.</span><span class="sxs-lookup"><span data-stu-id="6dc70-107">For example, the lambda expression `x => x * x` specifies a parameter that’s named `x` and returns the value of `x` squared.</span></span> <span data-ttu-id="6dc70-108">Puede asignar esta expresión a un tipo delegado, como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="6dc70-108">You can assign this expression to a delegate type, as the following example shows:</span></span>  
  
```csharp  
delegate int del(int i);  
static void Main(string[] args)  
{  
    del myDelegate = x => x * x;  
    int j = myDelegate(5); //j = 25  
}  
```  
  
 <span data-ttu-id="6dc70-109">Para crear un tipo de árbol de expresión:</span><span class="sxs-lookup"><span data-stu-id="6dc70-109">To create an expression tree type:</span></span>  
  
```csharp  
using System.Linq.Expressions;  
  
namespace ConsoleApplication1  
{  
    class Program  
    {  
        static void Main(string[] args)  
        {  
            Expression<del> myET = x => x * x;  
        }  
    }  
}  
```  
  
 <span data-ttu-id="6dc70-110">El operador `=>` tiene la misma prioridad que la asignación (`=`) y es [asociativa a la derecha](../../../csharp/programming-guide/statements-expressions-operators/operators.md) (vea la sección "Asociatividad" del artículo Operadores).</span><span class="sxs-lookup"><span data-stu-id="6dc70-110">The `=>` operator has the same precedence as assignment (`=`) and is [right associative](../../../csharp/programming-guide/statements-expressions-operators/operators.md) (see "Associativity" section of the Operators article).</span></span>  
  
 <span data-ttu-id="6dc70-111">Las lambdas se usan en consultas [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] basadas en métodos como argumentos de los métodos de operador de consulta estándar, tales como <xref:System.Linq.Enumerable.Where%2A>.</span><span class="sxs-lookup"><span data-stu-id="6dc70-111">Lambdas are used in method-based [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] queries as arguments to standard query operator methods such as <xref:System.Linq.Enumerable.Where%2A>.</span></span>  
  
 <span data-ttu-id="6dc70-112">Cuando se utiliza la sintaxis de método para llamar al método <xref:System.Linq.Enumerable.Where%2A> en la clase <xref:System.Linq.Enumerable> (como se hace en [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] to Objects y [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]), el parámetro es un tipo delegado <xref:System.Func%602?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="6dc70-112">When you use method-based syntax to call the <xref:System.Linq.Enumerable.Where%2A> method in the <xref:System.Linq.Enumerable> class (as you do in [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] to Objects and [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]) the parameter is a delegate type <xref:System.Func%602?displayProperty=nameWithType>.</span></span> <span data-ttu-id="6dc70-113">Una expresión lambda constituye la manera más práctica de crear ese delegado.</span><span class="sxs-lookup"><span data-stu-id="6dc70-113">A lambda expression is the most convenient way to create that delegate.</span></span> <span data-ttu-id="6dc70-114">Cuando se llama al mismo método en, por ejemplo, la clase <xref:System.Linq.Queryable?displayProperty=nameWithType> (como se hace en [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)]), el tipo de parámetro es <xref:System.Linq.Expressions.Expression?displayProperty=nameWithType><Func\>, donde Func es uno de los delegados de Func, que tiene hasta dieciséis parámetros de entrada.</span><span class="sxs-lookup"><span data-stu-id="6dc70-114">When you call the same method in, for example, the <xref:System.Linq.Queryable?displayProperty=nameWithType> class (as you do in [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)]) then the parameter type is an <xref:System.Linq.Expressions.Expression?displayProperty=nameWithType><Func\> where Func is any of the Func delegates with up to sixteen input parameters.</span></span> <span data-ttu-id="6dc70-115">De nuevo, una expresión lambda constituye una manera muy concisa de construir ese árbol de expresión.</span><span class="sxs-lookup"><span data-stu-id="6dc70-115">Again, a lambda expression is just a very concise way to construct that expression tree.</span></span> <span data-ttu-id="6dc70-116">Las lambdas permiten que las llamadas a `Where` tengan un aspecto similar, aunque, de hecho, el tipo de objeto creado a partir de la lambda sea diferente.</span><span class="sxs-lookup"><span data-stu-id="6dc70-116">The lambdas allow the `Where` calls to look similar although in fact the type of object created from the lambda is different.</span></span>  
  
 <span data-ttu-id="6dc70-117">En el ejemplo anterior, observe que la signatura de delegado tiene un parámetro de entrada con tipo implícito `int`y devuelve un `int`.</span><span class="sxs-lookup"><span data-stu-id="6dc70-117">In the previous example, notice that the delegate signature has one implicitly-typed input parameter of type `int`, and returns an `int`.</span></span> <span data-ttu-id="6dc70-118">La expresión lambda se puede convertir en un delegado de ese tipo porque también tiene un parámetro de entrada (`x`) y un valor devuelto que el compilador puede convertir implícitamente al tipo `int`.</span><span class="sxs-lookup"><span data-stu-id="6dc70-118">The lambda expression can be converted to a delegate of that type because it also has one input parameter (`x`) and a return value that the compiler can implicitly convert to type `int`.</span></span> <span data-ttu-id="6dc70-119">(La inferencia de tipos se analiza con más detalle en las secciones siguientes). Cuando el delegado se invoca mediante un parámetro de entrada de 5, devuelve un resultado de 25.</span><span class="sxs-lookup"><span data-stu-id="6dc70-119">(Type inference is discussed in more detail in the following sections.) When the delegate is invoked by using an input parameter of 5, it returns a result of 25.</span></span>  
  
 <span data-ttu-id="6dc70-120">Las lambdas no se permiten en el lado izquierdo del operador [is](../../../csharp/language-reference/keywords/is.md) o [as](../../../csharp/language-reference/keywords/as.md).</span><span class="sxs-lookup"><span data-stu-id="6dc70-120">Lambdas are not allowed on the left side of the [is](../../../csharp/language-reference/keywords/is.md) or [as](../../../csharp/language-reference/keywords/as.md) operator.</span></span>  
  
 <span data-ttu-id="6dc70-121">Todas las restricciones que se aplican a los métodos anónimos también se aplican a las expresiones lambda.</span><span class="sxs-lookup"><span data-stu-id="6dc70-121">All restrictions that apply to anonymous methods also apply to lambda expressions.</span></span> <span data-ttu-id="6dc70-122">Para obtener más información, vea [Métodos anónimos](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md).</span><span class="sxs-lookup"><span data-stu-id="6dc70-122">For more information, see [Anonymous Methods](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md).</span></span>  
  
## <a name="expression-lambdas"></a><span data-ttu-id="6dc70-123">Lambdas de expresión</span><span class="sxs-lookup"><span data-stu-id="6dc70-123">Expression lambdas</span></span>

 <span data-ttu-id="6dc70-124">Una expresión lambda con una expresión en el lado derecho del operador => se denomina *lambda de expresión*.</span><span class="sxs-lookup"><span data-stu-id="6dc70-124">A lambda expression with an expression on the right side of the => operator is called an *expression lambda*.</span></span> <span data-ttu-id="6dc70-125">Las lambdas de expresión se usan ampliamente en la construcción de [árboles de expresión](../concepts/expression-trees/index.md).</span><span class="sxs-lookup"><span data-stu-id="6dc70-125">Expression lambdas are used extensively in the construction of [Expression Trees](../concepts/expression-trees/index.md).</span></span> <span data-ttu-id="6dc70-126">Una expresión lambda devuelve el resultado de evaluar la condición y tiene la siguiente forma:</span><span class="sxs-lookup"><span data-stu-id="6dc70-126">An expression lambda returns the result of the expression and takes the following basic form:</span></span>
  
```csharp
(input-parameters) => expression
```

 <span data-ttu-id="6dc70-127">Los paréntesis solo son opcionales si la lambda tiene un parámetro de entrada; de lo contrario, son obligatorios.</span><span class="sxs-lookup"><span data-stu-id="6dc70-127">The parentheses are optional only if the lambda has one input parameter; otherwise they are required.</span></span> <span data-ttu-id="6dc70-128">Dos o más parámetros de entrada se separan por comas y se encierran entre paréntesis:</span><span class="sxs-lookup"><span data-stu-id="6dc70-128">Two or more input parameters are separated by commas enclosed in parentheses:</span></span>  
  
```csharp
(x, y) => x == y
```

 <span data-ttu-id="6dc70-129">A veces, es difícil o imposible que el compilador deduzca los tipos de entrada.</span><span class="sxs-lookup"><span data-stu-id="6dc70-129">Sometimes it is difficult or impossible for the compiler to infer the input types.</span></span> <span data-ttu-id="6dc70-130">Cuando ocurre esto, los tipos se pueden especificar explícitamente como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="6dc70-130">When this occurs, you can specify the types explicitly as shown in the following example:</span></span>  
  
```csharp
(int x, string s) => s.Length > x
```
 <span data-ttu-id="6dc70-131">Los tipos de parámetro de entrada deben ser todos explícitos o todos implícitos; de lo contrario, C# genera un error del compilador [CS0748](../../misc/cs0748.md).</span><span class="sxs-lookup"><span data-stu-id="6dc70-131">Input parameter types must be all explicit or all implicit; otherwise, C# generates a [CS0748](../../misc/cs0748.md) compiler error.</span></span>

 <span data-ttu-id="6dc70-132">Para especificar cero parámetros de entrada, utilice paréntesis vacíos:</span><span class="sxs-lookup"><span data-stu-id="6dc70-132">Specify zero input parameters with empty parentheses:</span></span>  
  
```csharp
() => SomeMethod()
```

 <span data-ttu-id="6dc70-133">Observe en el ejemplo anterior que el cuerpo de una lambda de expresión puede estar compuesto de una llamada a método.</span><span class="sxs-lookup"><span data-stu-id="6dc70-133">Note in the previous example that the body of an expression lambda can consist of a method call.</span></span> <span data-ttu-id="6dc70-134">Sin embargo, si crea árboles de expresiones que se evalúan fuera de .NET Framework, por ejemplo en SQL Server, no debe utilizar llamadas a métodos en expresiones lambda.</span><span class="sxs-lookup"><span data-stu-id="6dc70-134">However, if you are creating expression trees that are evaluated outside of the .NET Framework, such as in SQL Server, you should not use method calls in lambda expressions.</span></span> <span data-ttu-id="6dc70-135">Los métodos no tendrán ningún significado fuera del contexto de .NET Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="6dc70-135">The methods will have no meaning outside the context of the .NET common language runtime.</span></span>  
  
## <a name="statement-lambdas"></a><span data-ttu-id="6dc70-136">Lambdas de instrucción</span><span class="sxs-lookup"><span data-stu-id="6dc70-136">Statement lambdas</span></span>

 <span data-ttu-id="6dc70-137">Una lambda de instrucción es similar a un lambda de expresión, salvo que las instrucciones se encierran entre llaves:</span><span class="sxs-lookup"><span data-stu-id="6dc70-137">A statement lambda resembles an expression lambda except that the statement(s) is enclosed in braces:</span></span>  
  
<span data-ttu-id="6dc70-138">(parámetros de entrada) => { instrucción; }</span><span class="sxs-lookup"><span data-stu-id="6dc70-138">(input-parameters) => { statement; }</span></span>

 <span data-ttu-id="6dc70-139">El cuerpo de una lambda de instrucción puede estar compuesto de cualquier número de instrucciones; sin embargo, en la práctica, generalmente no hay más de dos o tres.</span><span class="sxs-lookup"><span data-stu-id="6dc70-139">The body of a statement lambda can consist of any number of statements; however, in practice there are typically no more than two or three.</span></span>  
  
[!code-csharp[StatementLambda#1](~/samples/snippets/csharp/programming-guide/lambda-expressions/statements.cs#1)]

[!code-csharp[StatementLambda#2](~/samples/snippets/csharp/programming-guide/lambda-expressions/statements.cs#2)]

 <span data-ttu-id="6dc70-140">Las lambdas de instrucción, como los métodos anónimos, no se pueden utilizar para crear árboles de expresión.</span><span class="sxs-lookup"><span data-stu-id="6dc70-140">Statement lambdas, like anonymous methods, cannot be used to create expression trees.</span></span>  
  
## <a name="async-lambdas"></a><span data-ttu-id="6dc70-141">Lambdas asincrónicas</span><span class="sxs-lookup"><span data-stu-id="6dc70-141">Async lambdas</span></span>

 <span data-ttu-id="6dc70-142">Puede crear fácilmente expresiones e instrucciones lambda que incorporen el procesamiento asincrónico mediante las palabras clave [async](../../../csharp/language-reference/keywords/async.md) y [await](../../../csharp/language-reference/keywords/await.md) .</span><span class="sxs-lookup"><span data-stu-id="6dc70-142">You can easily create lambda expressions and statements that incorporate asynchronous processing by using the [async](../../../csharp/language-reference/keywords/async.md) and [await](../../../csharp/language-reference/keywords/await.md) keywords.</span></span> <span data-ttu-id="6dc70-143">Por ejemplo, en el siguiente ejemplo de formularios Windows Forms se incluye un controlador de eventos que llama y espera un método asincrónico, `ExampleMethodAsync`.</span><span class="sxs-lookup"><span data-stu-id="6dc70-143">For example, the following Windows Forms example contains an event handler that calls and awaits an async method, `ExampleMethodAsync`.</span></span>  
  
```csharp
public partial class Form1 : Form  
{  
    public Form1()  
    {  
        InitializeComponent();  
    }  
  
    private async void button1_Click(object sender, EventArgs e)  
    {  
        // ExampleMethodAsync returns a Task.  
        await ExampleMethodAsync();  
        textBox1.Text += "\r\nControl returned to Click event handler.\n";  
    }  
  
    async Task ExampleMethodAsync()  
    {  
        // The following line simulates a task-returning asynchronous process.  
        await Task.Delay(1000);  
    }  
}  
```

 <span data-ttu-id="6dc70-144">Puede agregar el mismo controlador de eventos utilizando una lambda asincrónica.</span><span class="sxs-lookup"><span data-stu-id="6dc70-144">You can add the same event handler by using an async lambda.</span></span> <span data-ttu-id="6dc70-145">Para agregar este controlador, agregue un modificador `async` antes de la lista de parámetros lambda, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="6dc70-145">To add this handler, add an `async` modifier before the lambda parameter list, as the following example shows.</span></span>  
  
```csharp  
public partial class Form1 : Form  
{  
    public Form1()  
    {  
        InitializeComponent();  
        button1.Click += async (sender, e) =>  
        {  
            // ExampleMethodAsync returns a Task.  
            await ExampleMethodAsync();  
            textBox1.Text += "\nControl returned to Click event handler.\n";  
        };  
    }  
  
    async Task ExampleMethodAsync()  
    {  
        // The following line simulates a task-returning asynchronous process.  
        await Task.Delay(1000);  
    }  
}  
```  

 <span data-ttu-id="6dc70-146">Para obtener más información sobre cómo crear y usar métodos asincrónicos, vea [Programación asincrónica con async y await](../../../csharp/programming-guide/concepts/async/index.md).</span><span class="sxs-lookup"><span data-stu-id="6dc70-146">For more information about how to create and use async methods, see [Asynchronous Programming with async and await](../../../csharp/programming-guide/concepts/async/index.md).</span></span>  
  
## <a name="lambdas-with-the-standard-query-operators"></a><span data-ttu-id="6dc70-147">Lambdas con los operadores de consulta estándar</span><span class="sxs-lookup"><span data-stu-id="6dc70-147">Lambdas with the standard query operators</span></span>

 <span data-ttu-id="6dc70-148">Muchos operadores de consulta estándar tienen un parámetro de entrada cuyo tipo es uno de la familia <xref:System.Func%602> de delegados genéricos.</span><span class="sxs-lookup"><span data-stu-id="6dc70-148">Many standard query operators have an input parameter whose type is one of the <xref:System.Func%602> family of generic delegates.</span></span> <span data-ttu-id="6dc70-149">Estos delegados usan parámetros de tipo para definir el número y los tipos de los parámetros de entrada y el tipo de valor devuelto del delegado.</span><span class="sxs-lookup"><span data-stu-id="6dc70-149">These delegates use type parameters to define the number and types of input parameters, and the return type of the delegate.</span></span> <span data-ttu-id="6dc70-150">Los delegados`Func` son muy útiles para encapsular expresiones definidas por el usuario que se aplican a cada elemento en un conjunto de datos de origen.</span><span class="sxs-lookup"><span data-stu-id="6dc70-150">`Func` delegates are very useful for encapsulating user-defined expressions that are applied to each element in a set of source data.</span></span> <span data-ttu-id="6dc70-151">Por ejemplo, considere el siguiente tipo delegado:</span><span class="sxs-lookup"><span data-stu-id="6dc70-151">For example, consider the following delegate type:</span></span>  
  
```csharp  
public delegate TResult Func<TArg0, TResult>(TArg0 arg0)  
```  
  
 <span data-ttu-id="6dc70-152">Se pueden crear instancias del delegado como `Func<int,bool> myFunc` , donde `int` es un parámetro de entrada y `bool` es el valor devuelto.</span><span class="sxs-lookup"><span data-stu-id="6dc70-152">The delegate can be instantiated as `Func<int,bool> myFunc` where `int` is an input parameter and `bool` is the return value.</span></span> <span data-ttu-id="6dc70-153">El valor devuelto siempre se especifica en el último parámetro de tipo.</span><span class="sxs-lookup"><span data-stu-id="6dc70-153">The return value is always specified in the last type parameter.</span></span> <span data-ttu-id="6dc70-154">`Func<int, string, bool>` define un delegado con dos parámetros de entrada, `int` y `string`, y un tipo de valor devuelto de `bool`.</span><span class="sxs-lookup"><span data-stu-id="6dc70-154">`Func<int, string, bool>` defines a delegate with two input parameters, `int` and `string`, and a return type of `bool`.</span></span> <span data-ttu-id="6dc70-155">El siguiente delegado `Func` , cuando se invoca, devolverá true o false para indicar si el parámetro de entrada es igual a 5:</span><span class="sxs-lookup"><span data-stu-id="6dc70-155">The following `Func` delegate, when it is invoked, will return true or false to indicate whether the input parameter is equal to 5:</span></span>  
  
```csharp  
Func<int, bool> myFunc = x => x == 5;  
bool result = myFunc(4); // returns false of course  
```  
  
 <span data-ttu-id="6dc70-156">También puede proporcionar una expresión lambda cuando el tipo de argumento es `Expression<Func>`, por ejemplo, en los operadores de consulta estándar que se definen en System.Linq.Queryable.</span><span class="sxs-lookup"><span data-stu-id="6dc70-156">You can also supply a lambda expression when the argument type is an `Expression<Func>`, for example in the standard query operators that are defined in System.Linq.Queryable.</span></span> <span data-ttu-id="6dc70-157">Al especificar un argumento `Expression<Func>` , la lambda se compilará en un árbol de expresión.</span><span class="sxs-lookup"><span data-stu-id="6dc70-157">When you specify an `Expression<Func>` argument, the lambda will be compiled to an expression tree.</span></span>  
  
 <span data-ttu-id="6dc70-158">A continuación, se muestra un operador de consulta estándar, el método <xref:System.Linq.Enumerable.Count%2A> :</span><span class="sxs-lookup"><span data-stu-id="6dc70-158">A standard query operator, the <xref:System.Linq.Enumerable.Count%2A> method, is shown here:</span></span>  
  
```csharp  
int[] numbers = { 5, 4, 1, 3, 9, 8, 6, 7, 2, 0 };  
int oddNumbers = numbers.Count(n => n % 2 == 1);  
```  
  
 <span data-ttu-id="6dc70-159">El compilador puede deducir el tipo del parámetro de entrada o también se puede especificar explícitamente.</span><span class="sxs-lookup"><span data-stu-id="6dc70-159">The compiler can infer the type of the input parameter, or you can also specify it explicitly.</span></span> <span data-ttu-id="6dc70-160">Esta expresión lambda particular cuenta aquellos enteros (`n`) que divididos por dos dan como resto 1.</span><span class="sxs-lookup"><span data-stu-id="6dc70-160">This particular lambda expression counts those integers (`n`) which when divided by two have a remainder of 1.</span></span>  
  
 <span data-ttu-id="6dc70-161">La siguiente línea de código produce una secuencia que contiene todos los elementos de la matriz `numbers` que aparecen a la izquierda del 9, ya que ese es el primer número de la secuencia que no cumple la condición:</span><span class="sxs-lookup"><span data-stu-id="6dc70-161">The following line of code produces a sequence that contains all elements in the `numbers` array that are to the left side of the 9 because that's the first number in the sequence that doesn't meet the condition:</span></span>  
  
```csharp  
var firstNumbersLessThan6 = numbers.TakeWhile(n => n < 6);  
```  
  
 <span data-ttu-id="6dc70-162">En este ejemplo se muestra cómo especificar varios parámetros de entrada encerrándolos entre paréntesis.</span><span class="sxs-lookup"><span data-stu-id="6dc70-162">This example shows how to specify multiple input parameters by enclosing them in parentheses.</span></span> <span data-ttu-id="6dc70-163">El método devuelve todos los elementos de la matriz de números hasta encontrar un número cuyo valor sea menor que su posición.</span><span class="sxs-lookup"><span data-stu-id="6dc70-163">The method returns all the elements in the numbers array until a number is encountered whose value is less than its position.</span></span> <span data-ttu-id="6dc70-164">No confunda el operador lambda (`=>`) con el operador mayor o igual que (`>=`).</span><span class="sxs-lookup"><span data-stu-id="6dc70-164">Do not confuse the lambda operator (`=>`) with the greater than or equal operator (`>=`).</span></span>  
  
```csharp  
var firstSmallNumbers = numbers.TakeWhile((n, index) => n >= index);  
```  
  
## <a name="type-inference-in-lambdas"></a><span data-ttu-id="6dc70-165">Inferencia de tipos en las lambdas</span><span class="sxs-lookup"><span data-stu-id="6dc70-165">Type inference in lambdas</span></span>

 <span data-ttu-id="6dc70-166">Al escribir lambdas, no tiene por qué especificar un tipo para los parámetros de entrada, ya que el compilador puede deducir el tipo según el cuerpo de lambda, el tipo de delegado del parámetro y otros factores que se describen en la especificación del lenguaje C#.</span><span class="sxs-lookup"><span data-stu-id="6dc70-166">When writing lambdas, you often do not have to specify a type for the input parameters because the compiler can infer the type based on the lambda body, the parameter’s delegate type, and other factors as described in the C# Language Specification.</span></span> <span data-ttu-id="6dc70-167">Para la mayoría de los operadores de consulta estándar, la primera entrada es el tipo de los elementos en la secuencia de origen.</span><span class="sxs-lookup"><span data-stu-id="6dc70-167">For most of the standard query operators, the first input is the type of the elements in the source sequence.</span></span> <span data-ttu-id="6dc70-168">Por consiguiente, si está realizando una consulta sobre un `IEnumerable<Customer>`, se deducirá que la variable de entrada será un objeto `Customer` , lo cual significa que se podrá tener acceso a sus métodos y propiedades:</span><span class="sxs-lookup"><span data-stu-id="6dc70-168">So if you are querying an `IEnumerable<Customer>`, then the input variable is inferred to be a `Customer` object, which means you have access to its methods and properties:</span></span>  
  
```csharp  
customers.Where(c => c.City == "London");  
```  
  
 <span data-ttu-id="6dc70-169">Las reglas generales para las lambdas son las siguientes:</span><span class="sxs-lookup"><span data-stu-id="6dc70-169">The general rules for lambdas are as follows:</span></span>  
  
-   <span data-ttu-id="6dc70-170">La lambda debe contener el mismo número de parámetros que el tipo delegado.</span><span class="sxs-lookup"><span data-stu-id="6dc70-170">The lambda must contain the same number of parameters as the delegate type.</span></span>  
  
-   <span data-ttu-id="6dc70-171">Cada parámetro de entrada de la lambda debe poder convertirse implícitamente a su parámetro de delegado correspondiente.</span><span class="sxs-lookup"><span data-stu-id="6dc70-171">Each input parameter in the lambda must be implicitly convertible to its corresponding delegate parameter.</span></span>  
  
-   <span data-ttu-id="6dc70-172">El valor devuelto de la lambda (si existe) debe poder convertirse implícitamente al tipo de valor devuelto del delegado.</span><span class="sxs-lookup"><span data-stu-id="6dc70-172">The return value of the lambda (if any) must be implicitly convertible to the delegate's return type.</span></span>  
  
 <span data-ttu-id="6dc70-173">Observe que las expresiones lambda, en sí mismas, no tienen tipo, ya que el sistema de tipos comunes no tiene ningún concepto intrínseco de "expresión lambda".</span><span class="sxs-lookup"><span data-stu-id="6dc70-173">Note that lambda expressions in themselves do not have a type because the common type system has no intrinsic concept of "lambda expression."</span></span> <span data-ttu-id="6dc70-174">Sin embargo, a veces resulta práctico hablar coloquialmente del "tipo" de una expresión lambda.</span><span class="sxs-lookup"><span data-stu-id="6dc70-174">However, it is sometimes convenient to speak informally of the "type" of a lambda expression.</span></span> <span data-ttu-id="6dc70-175">En estos casos, el tipo hace referencia al tipo del delegado o el tipo de <xref:System.Linq.Expressions.Expression> en el que se convierte la expresión lambda.</span><span class="sxs-lookup"><span data-stu-id="6dc70-175">In these cases the type refers to the delegate type or <xref:System.Linq.Expressions.Expression> type to which the lambda expression is converted.</span></span>  
  
## <a name="variable-scope-in-lambda-expressions"></a><span data-ttu-id="6dc70-176">Ámbito de las variables en las expresiones lambda</span><span class="sxs-lookup"><span data-stu-id="6dc70-176">Variable scope in lambda expressions</span></span>

 <span data-ttu-id="6dc70-177">Las lambdas pueden hacer referencia a las *variables externas* (vea [Métodos anónimos](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md)) que están en el ámbito del método que define la función lambda o en el ámbito del tipo que contiene la expresión lambda.</span><span class="sxs-lookup"><span data-stu-id="6dc70-177">Lambdas can refer to *outer variables* (see [Anonymous Methods](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md)) that are in scope in the method that defines the lambda function, or in scope in the type that contains the lambda expression.</span></span> <span data-ttu-id="6dc70-178">Las variables que se capturan de esta manera se almacenan para su uso en la expresión lambda, cuando de otro modo quedarían fuera de ámbito y serían eliminadas por la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="6dc70-178">Variables that are captured in this manner are stored for use in the lambda expression even if the variables would otherwise go out of scope and be garbage collected.</span></span> <span data-ttu-id="6dc70-179">Para poder utilizar una variable externa en una expresión lambda, debe estar previamente asignada.</span><span class="sxs-lookup"><span data-stu-id="6dc70-179">An outer variable must be definitely assigned before it can be consumed in a lambda expression.</span></span> <span data-ttu-id="6dc70-180">En el ejemplo siguiente se muestran estas reglas:</span><span class="sxs-lookup"><span data-stu-id="6dc70-180">The following example demonstrates these rules:</span></span>  
  
```csharp  
delegate bool D();  
delegate bool D2(int i);  
  
class Test  
{  
    D del;  
    D2 del2;  
    public void TestMethod(int input)  
    {  
        int j = 0;  
        // Initialize the delegates with lambda expressions.  
        // Note access to 2 outer variables.  
        // del will be invoked within this method.  
        del = () => { j = 10;  return j > input; };  
  
        // del2 will be invoked after TestMethod goes out of scope.  
        del2 = (x) => {return x == j; };  
  
        // Demonstrate value of j:  
        // Output: j = 0   
        // The delegate has not been invoked yet.  
        Console.WriteLine("j = {0}", j);        // Invoke the delegate.  
        bool boolResult = del();  
  
        // Output: j = 10 b = True  
        Console.WriteLine("j = {0}. b = {1}", j, boolResult);  
    }  
  
    static void Main()  
    {  
        Test test = new Test();  
        test.TestMethod(5);  
  
        // Prove that del2 still has a copy of  
        // local variable j from TestMethod.  
        bool result = test.del2(10);  
  
        // Output: True  
        Console.WriteLine(result);  
  
        Console.ReadKey();  
    }  
}  
```  
  
 <span data-ttu-id="6dc70-181">Las reglas siguientes se aplican al ámbito de las variables en las expresiones lambda:</span><span class="sxs-lookup"><span data-stu-id="6dc70-181">The following rules apply to variable scope in lambda expressions:</span></span>  
  
-   <span data-ttu-id="6dc70-182">Una variable capturada no se recolectará como elemento no utilizado hasta que el delegado que hace referencia a ella sea elegible para la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="6dc70-182">A variable that is captured will not be garbage-collected until the delegate that references it becomes eligible for garbage collection.</span></span>  
  
-   <span data-ttu-id="6dc70-183">Las variables introducidas en una expresión lambda no son visibles en el método externo.</span><span class="sxs-lookup"><span data-stu-id="6dc70-183">Variables introduced within a lambda expression are not visible in the outer method.</span></span>  
  
-   <span data-ttu-id="6dc70-184">Una expresión lambda no puede capturar directamente un parámetro `in`, `ref` o `out` desde un método que la englobe.</span><span class="sxs-lookup"><span data-stu-id="6dc70-184">A lambda expression cannot directly capture an `in`, `ref`, or `out` parameter from an enclosing method.</span></span>  
  
-   <span data-ttu-id="6dc70-185">Una instrucción return en una expresión lambda no hace que el método que la engloba devuelva un valor.</span><span class="sxs-lookup"><span data-stu-id="6dc70-185">A return statement in a lambda expression does not cause the enclosing method to return.</span></span>  
  
-   <span data-ttu-id="6dc70-186">Una expresión lambda no puede contener una instrucción `goto` , `break` o `continue` que esté dentro de la función lambda si el destino de la instrucción de salto está fuera del bloque.</span><span class="sxs-lookup"><span data-stu-id="6dc70-186">A lambda expression cannot contain a `goto` statement, `break` statement, or `continue` statement that is inside the lambda function if the jump statement’s target is outside the block.</span></span> <span data-ttu-id="6dc70-187">También es un error utilizar una instrucción de salto fuera del bloque de la función lambda si el destino está dentro del bloque.</span><span class="sxs-lookup"><span data-stu-id="6dc70-187">It is also an error to have a jump statement outside the lambda function block if the target is inside the block.</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="6dc70-188">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="6dc70-188">C# language specification</span></span>

 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="featured-book-chapter"></a><span data-ttu-id="6dc70-189">Capítulo destacado del libro</span><span class="sxs-lookup"><span data-stu-id="6dc70-189">Featured book chapter</span></span>

 <span data-ttu-id="6dc70-190">[Delegates, Events, and Lambda Expressions](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/ff518994%28v=orm.10%29) (Delegados, eventos y expresiones lambda) en [C# 3.0 Cookbook, Tercera edición: More than 250 solutions for C# 3.0 programmers](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/ff518995%28v=orm.10%29) (Más de 250 soluciones para programadores de C# 3.0)</span><span class="sxs-lookup"><span data-stu-id="6dc70-190">[Delegates, Events, and Lambda Expressions](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/ff518994%28v=orm.10%29) in [C# 3.0 Cookbook, Third Edition: More than 250 solutions for C# 3.0 programmers](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/ff518995%28v=orm.10%29)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6dc70-191">Vea también</span><span class="sxs-lookup"><span data-stu-id="6dc70-191">See also</span></span>

- [<span data-ttu-id="6dc70-192">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="6dc70-192">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="6dc70-193">LINQ (Language Integrated Query)</span><span class="sxs-lookup"><span data-stu-id="6dc70-193">LINQ (Language-Integrated Query)</span></span>](../../../csharp/programming-guide/concepts/linq/index.md)
- [<span data-ttu-id="6dc70-194">Métodos anónimos</span><span class="sxs-lookup"><span data-stu-id="6dc70-194">Anonymous Methods</span></span>](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md)
- [<span data-ttu-id="6dc70-195">is</span><span class="sxs-lookup"><span data-stu-id="6dc70-195">is</span></span>](../../../csharp/language-reference/keywords/is.md)
- [<span data-ttu-id="6dc70-196">Árboles de expresión</span><span class="sxs-lookup"><span data-stu-id="6dc70-196">Expression Trees</span></span>](../../../csharp/programming-guide/concepts/expression-trees/index.md)
- [<span data-ttu-id="6dc70-197">Ejemplos de C# de Visual Studio 2008 (vea los archivos de ejemplos de consultas LINQ y el programa XQuery)</span><span class="sxs-lookup"><span data-stu-id="6dc70-197">Visual Studio 2008 C# Samples (see LINQ Sample Queries files and XQuery program)</span></span>](https://code.msdn.microsoft.com/Visual-Studio-2008-C-d295cdba)
- [<span data-ttu-id="6dc70-198">Expresiones lambda recursivas</span><span class="sxs-lookup"><span data-stu-id="6dc70-198">Recursive lambda expressions</span></span>](https://blogs.msdn.microsoft.com/madst/2007/05/11/recursive-lambda-expressions/)
