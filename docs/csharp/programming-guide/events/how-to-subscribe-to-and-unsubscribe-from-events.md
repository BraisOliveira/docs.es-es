---
title: 'Procedimiento Suscribir y cancelar la suscripción a eventos: Guía de programación de C#'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- event handlers [C#], creating
- Code Editor, event handlers
- events [C#], creating using the IDE
ms.assetid: 6319f39f-282c-4173-8a62-6c4657cf51cd
ms.openlocfilehash: 4d06899303110d0b06729f2a02c47b9096bec724
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2019
ms.locfileid: "56981808"
---
# <a name="how-to-subscribe-to-and-unsubscribe-from-events-c-programming-guide"></a><span data-ttu-id="9abc3-102">Procedimiento Suscribir y cancelar la suscripción a eventos (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="9abc3-102">How to: Subscribe to and Unsubscribe from Events (C# Programming Guide)</span></span>
<span data-ttu-id="9abc3-103">La suscripción a un evento publicado por otra clase se realiza cuando quiere escribir código personalizado al que se llama cuando se produce ese evento.</span><span class="sxs-lookup"><span data-stu-id="9abc3-103">You subscribe to an event that is published by another class when you want to write custom code that is called when that event is raised.</span></span> <span data-ttu-id="9abc3-104">Por ejemplo, puede suscribirse al evento `click` de un botón para que la aplicación realice alguna operación cuando el usuario haga clic en el botón.</span><span class="sxs-lookup"><span data-stu-id="9abc3-104">For example, you might subscribe to a button's `click` event in order to make your application do something useful when the user clicks the button.</span></span>  
  
### <a name="to-subscribe-to-events-by-using-the-visual-studio-ide"></a><span data-ttu-id="9abc3-105">Para suscribirse a eventos mediante el IDE de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="9abc3-105">To subscribe to events by using the Visual Studio IDE</span></span>  
  
1.  <span data-ttu-id="9abc3-106">Si no puede ver la ventana **Propiedades**, en la vista **Diseño** haga clic con el botón derecho en el formulario o control para el que quiere crear un controlador de eventos y seleccione **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="9abc3-106">If you cannot see the **Properties** window, in **Design** view, right-click the form or control for which you want to create an event handler, and select **Properties**.</span></span>  
  
2.  <span data-ttu-id="9abc3-107">En la parte superior de la ventana **Propiedades**, haga clic en el icono **Eventos**.</span><span class="sxs-lookup"><span data-stu-id="9abc3-107">On top of the **Properties** window, click the **Events** icon.</span></span>  
  
3.  <span data-ttu-id="9abc3-108">Haga doble clic en el evento que quiera crear, por ejemplo, el evento `Load`.</span><span class="sxs-lookup"><span data-stu-id="9abc3-108">Double-click the event that you want to create, for example the `Load` event.</span></span>  
  
     <span data-ttu-id="9abc3-109">Visual C# crea un método de controlador de eventos vacío y lo agrega al código.</span><span class="sxs-lookup"><span data-stu-id="9abc3-109">Visual C# creates an empty event handler method and adds it to your code.</span></span> <span data-ttu-id="9abc3-110">También puede agregar manualmente el código en la vista **Código**.</span><span class="sxs-lookup"><span data-stu-id="9abc3-110">Alternatively you can add the code manually in **Code** view.</span></span> <span data-ttu-id="9abc3-111">Por ejemplo, las líneas siguientes de código declaran un método de controlador de eventos al que se llamará cuando la clase `Form` genere el evento `Load`.</span><span class="sxs-lookup"><span data-stu-id="9abc3-111">For example, the following lines of code declare an event handler method that will be called when the `Form` class raises the `Load` event.</span></span>  
  
     [!code-csharp[csProgGuideEvents#11](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideEvents/CS/Events.cs#11)]  
  
     <span data-ttu-id="9abc3-112">La línea de código que es necesaria para suscribirse al evento también se genera automáticamente con el método `InitializeComponent` en el archivo Form1.Designer.cs del proyecto.</span><span class="sxs-lookup"><span data-stu-id="9abc3-112">The line of code that is required to subscribe to the event is also automatically generated in the `InitializeComponent` method in the Form1.Designer.cs file in your project.</span></span> <span data-ttu-id="9abc3-113">Se parece a lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="9abc3-113">It resembles this:</span></span>  
  
    ```csharp
    this.Load += new System.EventHandler(this.Form1_Load);  
    ```  
  
### <a name="to-subscribe-to-events-programmatically"></a><span data-ttu-id="9abc3-114">Para suscribirse a eventos mediante programación</span><span class="sxs-lookup"><span data-stu-id="9abc3-114">To subscribe to events programmatically</span></span>  
  
1.  <span data-ttu-id="9abc3-115">Defina un método de controlador de eventos cuya firma coincida con la firma de delegado del evento.</span><span class="sxs-lookup"><span data-stu-id="9abc3-115">Define an event handler method whose signature matches the delegate signature for the event.</span></span> <span data-ttu-id="9abc3-116">Por ejemplo, si el evento se basa en el tipo de delegado <xref:System.EventHandler>, el siguiente código representa el código auxiliar del método:</span><span class="sxs-lookup"><span data-stu-id="9abc3-116">For example, if the event is based on the <xref:System.EventHandler> delegate type, the following code represents the method stub:</span></span>  
  
    ```csharp
    void HandleCustomEvent(object sender, CustomEventArgs a)  
    {  
       // Do something useful here.  
    }  
    ```  
  
2.  <span data-ttu-id="9abc3-117">Use el operador de suma y asignación (`+=`) para asociar el controlador de eventos al evento.</span><span class="sxs-lookup"><span data-stu-id="9abc3-117">Use the addition assignment operator (`+=`) to attach your event handler to the event.</span></span> <span data-ttu-id="9abc3-118">En el ejemplo siguiente, se asume que un objeto denominado `publisher` tiene un evento denominado `RaiseCustomEvent`.</span><span class="sxs-lookup"><span data-stu-id="9abc3-118">In the following example, assume that an object named `publisher` has an event named `RaiseCustomEvent`.</span></span> <span data-ttu-id="9abc3-119">Observe que la clase de suscriptor necesita una referencia a la clase de editor para suscribirse a sus eventos.</span><span class="sxs-lookup"><span data-stu-id="9abc3-119">Note that the subscriber class needs a reference to the publisher class in order to subscribe to its events.</span></span>  
  
    ```csharp
    publisher.RaiseCustomEvent += HandleCustomEvent;  
    ```  
  
     <span data-ttu-id="9abc3-120">Observe que la sintaxis anterior es nueva en C# 2.0.</span><span class="sxs-lookup"><span data-stu-id="9abc3-120">Note that the previous syntax is new in C# 2.0.</span></span> <span data-ttu-id="9abc3-121">Al igual que en la sintaxis de C# 1.0, el delegado encapsulador debe crearse explícitamente mediante la palabra clave `new`:</span><span class="sxs-lookup"><span data-stu-id="9abc3-121">It is exactly equivalent to the C# 1.0 syntax in which the encapsulating delegate must be explicitly created by using the `new` keyword:</span></span>  
  
    ```csharp
    publisher.RaiseCustomEvent += new CustomEventHandler(HandleCustomEvent);  
    ```  
  
     <span data-ttu-id="9abc3-122">También puede agregarse un controlador de eventos usando una expresión lambda:</span><span class="sxs-lookup"><span data-stu-id="9abc3-122">An event handler can also be added by using a lambda expression:</span></span>  
  
    ```csharp
    public Form1()  
    {  
        InitializeComponent();  
        // Use a lambda expression to define an event handler.  
        this.Click += (s,e) => { MessageBox.Show(  
           ((MouseEventArgs)e).Location.ToString());};  
    }  
    ```  
  
     <span data-ttu-id="9abc3-123">Para obtener más información, vea [Cómo: Usar expresiones lambda fuera de LINQ](../../../csharp/programming-guide/statements-expressions-operators/how-to-use-lambda-expressions-outside-linq.md).</span><span class="sxs-lookup"><span data-stu-id="9abc3-123">For more information, see [How to: Use Lambda Expressions Outside LINQ](../../../csharp/programming-guide/statements-expressions-operators/how-to-use-lambda-expressions-outside-linq.md).</span></span>  
  
### <a name="to-subscribe-to-events-by-using-an-anonymous-method"></a><span data-ttu-id="9abc3-124">Para suscribirse a eventos mediante un método anónimo</span><span class="sxs-lookup"><span data-stu-id="9abc3-124">To subscribe to events by using an anonymous method</span></span>  
  
-   <span data-ttu-id="9abc3-125">Si no tiene que cancelar la suscripción a un evento más adelante, puede usar el operador de suma y asignación (`+=`) para asociar un método anónimo al evento.</span><span class="sxs-lookup"><span data-stu-id="9abc3-125">If you will not have to unsubscribe to an event later, you can use the addition assignment operator (`+=`) to attach an anonymous method to the event.</span></span> <span data-ttu-id="9abc3-126">En el ejemplo siguiente, se presupone que un objeto denominado `publisher` tiene un evento denominado `RaiseCustomEvent` y que se ha definido una clase `CustomEventArgs` para proporcionar algún tipo de información específica del evento.</span><span class="sxs-lookup"><span data-stu-id="9abc3-126">In the following example, assume that an object named `publisher` has an event named `RaiseCustomEvent` and that a `CustomEventArgs` class has also been defined to carry some kind of specialized event information.</span></span> <span data-ttu-id="9abc3-127">Observe que la clase de suscriptor necesita una referencia a `publisher` para suscribirse a sus eventos.</span><span class="sxs-lookup"><span data-stu-id="9abc3-127">Note that the subscriber class needs a reference to `publisher` in order to subscribe to its events.</span></span>  
  
    ```csharp
    publisher.RaiseCustomEvent += delegate(object o, CustomEventArgs e)  
    {  
      string s = o.ToString() + " " + e.ToString();  
      Console.WriteLine(s);  
    };  
    ```  
  
     <span data-ttu-id="9abc3-128">Es importante tener en cuenta que puede no resultar fácil cancelar la suscripción a un evento si se ha usado una función anónima para suscribirse a él.</span><span class="sxs-lookup"><span data-stu-id="9abc3-128">It is important to notice that you cannot easily unsubscribe from an event if you used an anonymous function to subscribe to it.</span></span> <span data-ttu-id="9abc3-129">Para cancelar la suscripción en esta situación, es necesario regresar al código donde se ha suscrito al evento, almacenar el método anónimo en una variable de delegado y, después, agregar el delegado al evento.</span><span class="sxs-lookup"><span data-stu-id="9abc3-129">To unsubscribe in this scenario, it is necessary to go back to the code where you subscribe to the event, store the anonymous method in a delegate variable, and then add the delegate to the event.</span></span> <span data-ttu-id="9abc3-130">En general, se recomienda que no use funciones anónimas para suscribirse a eventos si va a tener que cancelar la suscripción al evento en el código más adelante.</span><span class="sxs-lookup"><span data-stu-id="9abc3-130">In general, we recommend that you do not use anonymous functions to subscribe to events if you will have to unsubscribe from the event at some later point in your code.</span></span> <span data-ttu-id="9abc3-131">Para obtener más información sobre las funciones anónimas, vea [Funciones anónimas](../../../csharp/programming-guide/statements-expressions-operators/anonymous-functions.md).</span><span class="sxs-lookup"><span data-stu-id="9abc3-131">For more information about anonymous functions, see [Anonymous Functions](../../../csharp/programming-guide/statements-expressions-operators/anonymous-functions.md).</span></span>  
  
## <a name="unsubscribing"></a><span data-ttu-id="9abc3-132">Cancelar una suscripción</span><span class="sxs-lookup"><span data-stu-id="9abc3-132">Unsubscribing</span></span>  
 <span data-ttu-id="9abc3-133">Para impedir que se invoque el controlador de eventos cuando se produce el evento, puede cancelar la suscripción al evento.</span><span class="sxs-lookup"><span data-stu-id="9abc3-133">To prevent your event handler from being invoked when the event is raised, unsubscribe from the event.</span></span> <span data-ttu-id="9abc3-134">Para evitar que se pierdan recursos, debe cancelar la suscripción a los eventos antes de eliminar un objeto suscriptor.</span><span class="sxs-lookup"><span data-stu-id="9abc3-134">In order to prevent resource leaks, you should unsubscribe from events before you dispose of a subscriber object.</span></span> <span data-ttu-id="9abc3-135">Hasta que se cancela la suscripción a un evento, el delegado multidifusión subyacente al evento en el objeto de publicación tiene una referencia al delegado que encapsula el controlador de eventos del suscriptor.</span><span class="sxs-lookup"><span data-stu-id="9abc3-135">Until you unsubscribe from an event, the multicast delegate that underlies the event in the publishing object has a reference to the delegate that encapsulates the subscriber's event handler.</span></span> <span data-ttu-id="9abc3-136">Mientras el objeto de publicación mantenga esa referencia, la recolección de elementos no utilizados no eliminará el objeto suscriptor.</span><span class="sxs-lookup"><span data-stu-id="9abc3-136">As long as the publishing object holds that reference, garbage collection will not delete your subscriber object.</span></span>  
  
#### <a name="to-unsubscribe-from-an-event"></a><span data-ttu-id="9abc3-137">Para cancelar la suscripción a un evento</span><span class="sxs-lookup"><span data-stu-id="9abc3-137">To unsubscribe from an event</span></span>  
  
-   <span data-ttu-id="9abc3-138">Use el operador de resta y asignación (`-=`) para cancelar la suscripción a un evento:</span><span class="sxs-lookup"><span data-stu-id="9abc3-138">Use the subtraction assignment operator (`-=`) to unsubscribe from an event:</span></span>  
  
    ```csharp
    publisher.RaiseCustomEvent -= HandleCustomEvent;  
    ```  
  
     <span data-ttu-id="9abc3-139">Cuando se haya cancelado la suscripción a un evento de todos los suscriptores, la instancia del evento en la clase de editor se establecerá en `null`.</span><span class="sxs-lookup"><span data-stu-id="9abc3-139">When all subscribers have unsubscribed from an event, the event instance in the publisher class is set to `null`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9abc3-140">Vea también</span><span class="sxs-lookup"><span data-stu-id="9abc3-140">See also</span></span>

- [<span data-ttu-id="9abc3-141">Eventos</span><span class="sxs-lookup"><span data-stu-id="9abc3-141">Events</span></span>](../../../csharp/programming-guide/events/index.md)
- [<span data-ttu-id="9abc3-142">event</span><span class="sxs-lookup"><span data-stu-id="9abc3-142">event</span></span>](../../../csharp/language-reference/keywords/event.md)
- [<span data-ttu-id="9abc3-143">Cómo: Publicar eventos que cumplan las directrices de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="9abc3-143">How to: Publish Events that Conform to .NET Framework Guidelines</span></span>](../../../csharp/programming-guide/events/how-to-publish-events-that-conform-to-net-framework-guidelines.md)
- [<span data-ttu-id="9abc3-144">Operador -= (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="9abc3-144">-= Operator (C# Reference)</span></span>](../../language-reference/operators/subtraction-assignment-operator.md)
- [<span data-ttu-id="9abc3-145">Operador +=</span><span class="sxs-lookup"><span data-stu-id="9abc3-145">+= Operator</span></span>](../../../csharp/language-reference/operators/addition-assignment-operator.md)
