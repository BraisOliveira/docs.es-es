---
title: Procedimiento para modificar la entrada de teclado en un control estándar
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- keyboard input [Windows Forms], modifying
- modifying keyboard input
- Windows Forms, modifying keyboard input
- keyboards [Windows Forms], keyboard input
ms.assetid: 626d3712-d866-4988-bcda-a2d5b36ec0ba
ms.openlocfilehash: 81d33234670fb8ae5445cc86a79f5c3b6a647a03
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61802341"
---
# <a name="how-to-modify-keyboard-input-to-a-standard-control"></a><span data-ttu-id="53ab1-102">Procedimiento para modificar la entrada de teclado en un control estándar</span><span class="sxs-lookup"><span data-stu-id="53ab1-102">How to: Modify Keyboard Input to a Standard Control</span></span>
<span data-ttu-id="53ab1-103">Windows Forms permite consumir y modificar la entrada de teclado.</span><span class="sxs-lookup"><span data-stu-id="53ab1-103">Windows Forms provides the ability to consume and modify keyboard input.</span></span> <span data-ttu-id="53ab1-104">Consumir una tecla es controlar una tecla dentro de un método o controlador de eventos para que otros métodos y eventos más abajo en la cola de mensajes no reciban el valor de la tecla.</span><span class="sxs-lookup"><span data-stu-id="53ab1-104">Consuming a key refers to handling a key within a method or event handler so that other methods and events further down the message queue do not receive the key value.</span></span> <span data-ttu-id="53ab1-105">Modificar una tecla es modificar el valor de una tecla para que los métodos y controladores de eventos más abajo en la cola de mensajes reciban un valor de tecla diferente.</span><span class="sxs-lookup"><span data-stu-id="53ab1-105">Modifying a key refers to modifying the value of a key so that methods and event handlers further down the message queue receive a different key value.</span></span> <span data-ttu-id="53ab1-106">En este tema se muestra cómo realizar estas tareas.</span><span class="sxs-lookup"><span data-stu-id="53ab1-106">This topic shows how to accomplish these tasks.</span></span>  
  
### <a name="to-consume-a-key"></a><span data-ttu-id="53ab1-107">Para consumir una tecla</span><span class="sxs-lookup"><span data-stu-id="53ab1-107">To consume a key</span></span>  
  
- <span data-ttu-id="53ab1-108">En un controlador de eventos <xref:System.Windows.Forms.Control.KeyPress>, establezca la propiedad <xref:System.Windows.Forms.KeyPressEventArgs.Handled%2A> de la clase <xref:System.Windows.Forms.KeyPressEventArgs> en `true`.</span><span class="sxs-lookup"><span data-stu-id="53ab1-108">In a <xref:System.Windows.Forms.Control.KeyPress> event handler, set the <xref:System.Windows.Forms.KeyPressEventArgs.Handled%2A> property of the <xref:System.Windows.Forms.KeyPressEventArgs> class to `true`.</span></span>  
  
     <span data-ttu-id="53ab1-109">-o bien-</span><span class="sxs-lookup"><span data-stu-id="53ab1-109">-or-</span></span>  
  
     <span data-ttu-id="53ab1-110">En un controlador de eventos <xref:System.Windows.Forms.Control.KeyDown>, establezca la propiedad <xref:System.Windows.Forms.KeyEventArgs.Handled%2A> de la clase <xref:System.Windows.Forms.KeyEventArgs> en `true`.</span><span class="sxs-lookup"><span data-stu-id="53ab1-110">In a <xref:System.Windows.Forms.Control.KeyDown> event handler, set the <xref:System.Windows.Forms.KeyEventArgs.Handled%2A> property of the <xref:System.Windows.Forms.KeyEventArgs> class to `true`.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="53ab1-111">Establecer la propiedad <xref:System.Windows.Forms.KeyEventArgs.Handled%2A> en el controlador de eventos <xref:System.Windows.Forms.Control.KeyDown> no impide que los eventos <xref:System.Windows.Forms.Control.KeyPress> y <xref:System.Windows.Forms.Control.KeyUp> se generen para la pulsación de tecla actual.</span><span class="sxs-lookup"><span data-stu-id="53ab1-111">Setting the <xref:System.Windows.Forms.KeyEventArgs.Handled%2A> property in the <xref:System.Windows.Forms.Control.KeyDown> event handler does not prevent the <xref:System.Windows.Forms.Control.KeyPress> and <xref:System.Windows.Forms.Control.KeyUp> events from being raised for the current keystroke.</span></span> <span data-ttu-id="53ab1-112">Use la propiedad <xref:System.Windows.Forms.KeyEventArgs.SuppressKeyPress%2A> para este propósito.</span><span class="sxs-lookup"><span data-stu-id="53ab1-112">Use the <xref:System.Windows.Forms.KeyEventArgs.SuppressKeyPress%2A> property for this purpose.</span></span>  
  
     <span data-ttu-id="53ab1-113">El ejemplo siguiente es un extracto de una instrucción `switch` que examina la propiedad <xref:System.Windows.Forms.KeyPressEventArgs.KeyChar%2A> de <xref:System.Windows.Forms.KeyPressEventArgs> recibido por un controlador de eventos <xref:System.Windows.Forms.Control.KeyPress>.</span><span class="sxs-lookup"><span data-stu-id="53ab1-113">The following example is an excerpt from a `switch` statement that examines the <xref:System.Windows.Forms.KeyPressEventArgs.KeyChar%2A> property of the <xref:System.Windows.Forms.KeyPressEventArgs> received by a <xref:System.Windows.Forms.Control.KeyPress> event handler.</span></span> <span data-ttu-id="53ab1-114">Este código consume las teclas de caracteres 'A' y 'a'.</span><span class="sxs-lookup"><span data-stu-id="53ab1-114">This code consumes the 'A' and 'a' character keys.</span></span>  
  
     [!code-csharp[System.Windows.Forms.KeyBoardInput#6](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.KeyboardInput/CS/form1.cs#6)]
     [!code-vb[System.Windows.Forms.KeyBoardInput#6](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.KeyboardInput/VB/form1.vb#6)]  
  
### <a name="to-modify-a-standard-character-key"></a><span data-ttu-id="53ab1-115">Para modificar una tecla de carácter estándar</span><span class="sxs-lookup"><span data-stu-id="53ab1-115">To modify a standard character key</span></span>  
  
- <span data-ttu-id="53ab1-116">En un controlador de eventos <xref:System.Windows.Forms.Control.KeyPress>, establezca la propiedad <xref:System.Windows.Forms.KeyPressEventArgs.KeyChar%2A> de la clase <xref:System.Windows.Forms.KeyPressEventArgs> en el valor de la nueva tecla de carácter.</span><span class="sxs-lookup"><span data-stu-id="53ab1-116">In a <xref:System.Windows.Forms.Control.KeyPress> event handler, set the <xref:System.Windows.Forms.KeyPressEventArgs.KeyChar%2A> property of the <xref:System.Windows.Forms.KeyPressEventArgs> class to the value of the new character key.</span></span>  
  
     <span data-ttu-id="53ab1-117">El ejemplo siguiente es un extracto de una instrucción `switch` que modifica 'B' por 'A' y 'b' por 'a'.</span><span class="sxs-lookup"><span data-stu-id="53ab1-117">The following example is an excerpt from a `switch` statement that modifies 'B' to 'A' and 'b' to 'a'.</span></span> <span data-ttu-id="53ab1-118">Tenga en cuenta que la propiedad <xref:System.Windows.Forms.KeyPressEventArgs.Handled%2A> del parámetro <xref:System.Windows.Forms.KeyPressEventArgs> está establecida en `false`, por lo que el nuevo valor de tecla se propaga a otros métodos y eventos de la cola de mensajes.</span><span class="sxs-lookup"><span data-stu-id="53ab1-118">Note that the <xref:System.Windows.Forms.KeyPressEventArgs.Handled%2A> property of the <xref:System.Windows.Forms.KeyPressEventArgs> parameter is set to `false`, so that the new key value is propagated to other methods and events in the message queue.</span></span>  
  
     [!code-csharp[System.Windows.Forms.KeyBoardInput#7](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.KeyboardInput/CS/form1.cs#7)]
     [!code-vb[System.Windows.Forms.KeyBoardInput#7](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.KeyboardInput/VB/form1.vb#7)]  
  
### <a name="to-modify-a-noncharacter-key"></a><span data-ttu-id="53ab1-119">Para modificar una tecla que no es de carácter</span><span class="sxs-lookup"><span data-stu-id="53ab1-119">To modify a noncharacter key</span></span>  
  
- <span data-ttu-id="53ab1-120">Invalide un método <xref:System.Windows.Forms.Control> que procesa los mensajes de Windows, detecte el mensaje WM_KEYDOWN o WM_SYSKEYDOWN y establezca la propiedad <xref:System.Windows.Forms.Message.WParam%2A> del parámetro <xref:System.Windows.Forms.Message> en el valor <xref:System.Windows.Forms.Keys> que representa la nueva tecla que no es de carácter.</span><span class="sxs-lookup"><span data-stu-id="53ab1-120">Override a <xref:System.Windows.Forms.Control> method that processes Windows messages, detect the WM_KEYDOWN or WM_SYSKEYDOWN message, and set the <xref:System.Windows.Forms.Message.WParam%2A> property of the <xref:System.Windows.Forms.Message> parameter to the <xref:System.Windows.Forms.Keys> value that represents the new noncharacter key.</span></span>  
  
     <span data-ttu-id="53ab1-121">En el ejemplo de código siguiente se muestra cómo invalidar el método <xref:System.Windows.Forms.Control.PreProcessMessage%2A> de un control para detectar las teclas F1 a F9 y modificar cualquier pulsación de tecla de F3 por F1.</span><span class="sxs-lookup"><span data-stu-id="53ab1-121">The following code example demonstrates how to override the <xref:System.Windows.Forms.Control.PreProcessMessage%2A> method of a control to detect keys F1 through F9 and modify any F3 key press to F1.</span></span> <span data-ttu-id="53ab1-122">Para obtener más información sobre <xref:System.Windows.Forms.Control> métodos que se pueden invalidar para interceptar los mensajes del teclado, vea [entrada del usuario en una aplicación de Windows Forms](user-input-in-a-windows-forms-application.md) y [cómo funciona la entrada de teclado](how-keyboard-input-works.md).</span><span class="sxs-lookup"><span data-stu-id="53ab1-122">For more information on <xref:System.Windows.Forms.Control> methods that you can override to intercept keyboard messages, see [User Input in a Windows Forms Application](user-input-in-a-windows-forms-application.md) and [How Keyboard Input Works](how-keyboard-input-works.md).</span></span>  
  
     [!code-csharp[System.Windows.Forms.KeyBoardInput#12](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.KeyboardInput/CS/form1.cs#12)]
     [!code-vb[System.Windows.Forms.KeyBoardInput#12](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.KeyboardInput/VB/form1.vb#12)]  
  
## <a name="example"></a><span data-ttu-id="53ab1-123">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="53ab1-123">Example</span></span>  
 <span data-ttu-id="53ab1-124">El ejemplo de código siguiente es la aplicación completa de los ejemplos de código de las secciones anteriores.</span><span class="sxs-lookup"><span data-stu-id="53ab1-124">The following code example is the complete application for the code examples in the previous sections.</span></span> <span data-ttu-id="53ab1-125">La aplicación usa un control personalizado derivado de la clase <xref:System.Windows.Forms.TextBox> para consumir y modificar la entrada de teclado.</span><span class="sxs-lookup"><span data-stu-id="53ab1-125">The application uses a custom control derived from the <xref:System.Windows.Forms.TextBox> class to consume and modify keyboard input.</span></span>  
  
 [!code-csharp[System.Windows.Forms.KeyBoardInput#0](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.KeyboardInput/CS/form1.cs#0)]
 [!code-vb[System.Windows.Forms.KeyBoardInput#0](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.KeyboardInput/VB/form1.vb#0)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="53ab1-126">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="53ab1-126">Compiling the Code</span></span>  
 <span data-ttu-id="53ab1-127">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="53ab1-127">This example requires:</span></span>  
  
- <span data-ttu-id="53ab1-128">Referencias a los ensamblados System, System.Drawing y System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="53ab1-128">References to the System, System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="53ab1-129">Para obtener información sobre cómo compilar este ejemplo desde la línea de comandos para Visual Basic o Visual C#, vea [compilar desde la línea de comandos](../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) o [de línea de comandos con csc.exe](../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="53ab1-129">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="53ab1-130">También puede compilar este ejemplo en Visual Studio pegando el código en un nuevo proyecto.</span><span class="sxs-lookup"><span data-stu-id="53ab1-130">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="53ab1-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="53ab1-131">See also</span></span>

- [<span data-ttu-id="53ab1-132">Entradas mediante teclado en una aplicación de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="53ab1-132">Keyboard Input in a Windows Forms Application</span></span>](keyboard-input-in-a-windows-forms-application.md)
- [<span data-ttu-id="53ab1-133">Datos introducidos por el usuario en una aplicación de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="53ab1-133">User Input in a Windows Forms Application</span></span>](user-input-in-a-windows-forms-application.md)
- [<span data-ttu-id="53ab1-134">Funcionamiento de las entradas mediante teclado</span><span class="sxs-lookup"><span data-stu-id="53ab1-134">How Keyboard Input Works</span></span>](how-keyboard-input-works.md)
