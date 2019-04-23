---
title: Procedimiento para descargar un archivo en segundo plano
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- BackgroundWorker component
- background tasks
- Asynchronous Pattern
- forms [Windows Forms], multithreading
- components [Windows Forms], asynchronous
- forms [Windows Forms], background operations
- threading [Windows Forms], background operations
- background operations
ms.assetid: 9b7bc5ae-051c-4904-9720-18f6667388bd
ms.openlocfilehash: af5a607b4800635d096e83b55a5bd5a912c8538d
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59128783"
---
# <a name="how-to-download-a-file-in-the-background"></a><span data-ttu-id="240d3-102">Procedimiento para descargar un archivo en segundo plano</span><span class="sxs-lookup"><span data-stu-id="240d3-102">How to: Download a File in the Background</span></span>
<span data-ttu-id="240d3-103">Descargar un archivo es una tarea común y, por lo general, resulta útil ejecutar esta operación que puede requerir mucho tiempo en un subproceso independiente.</span><span class="sxs-lookup"><span data-stu-id="240d3-103">Downloading a file is a common task, and it is often useful to run this potentially time-consuming operation on a separate thread.</span></span> <span data-ttu-id="240d3-104">Use el componente <xref:System.ComponentModel.BackgroundWorker> para realizar esta tarea con muy poco código.</span><span class="sxs-lookup"><span data-stu-id="240d3-104">Use the <xref:System.ComponentModel.BackgroundWorker> component to accomplish this task with very little code.</span></span>  
  
## <a name="example"></a><span data-ttu-id="240d3-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="240d3-105">Example</span></span>  
 <span data-ttu-id="240d3-106">En el ejemplo de código siguiente se muestra cómo usar un componente <xref:System.ComponentModel.BackgroundWorker> para cargar un archivo XML desde una dirección URL.</span><span class="sxs-lookup"><span data-stu-id="240d3-106">The following code example demonstrates how to use a <xref:System.ComponentModel.BackgroundWorker> component to load an XML file from a URL.</span></span> <span data-ttu-id="240d3-107">Cuando el usuario hace clic en el **descargar** botón, el <xref:System.Windows.Forms.Control.Click> llamadas del controlador de eventos el <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A> método de un <xref:System.ComponentModel.BackgroundWorker> componente para iniciar la operación de descarga.</span><span class="sxs-lookup"><span data-stu-id="240d3-107">When the user clicks the **Download** button, the <xref:System.Windows.Forms.Control.Click> event handler calls the <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A> method of a <xref:System.ComponentModel.BackgroundWorker> component to start the download operation.</span></span> <span data-ttu-id="240d3-108">El botón se deshabilita mientras dura la descarga y se vuelve a habilitar una vez completada la descarga.</span><span class="sxs-lookup"><span data-stu-id="240d3-108">The button is disabled for the duration of the download, and then enabled when the download is complete.</span></span> <span data-ttu-id="240d3-109">Un <xref:System.Windows.Forms.MessageBox> muestra el contenido del archivo.</span><span class="sxs-lookup"><span data-stu-id="240d3-109">A <xref:System.Windows.Forms.MessageBox> displays the contents of the file.</span></span>  
  
 [!code-csharp[System.ComponentModel.BackgroundWorker.IsBusy#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.IsBusy/CS/Form1.cs#1)]
 [!code-vb[System.ComponentModel.BackgroundWorker.IsBusy#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.IsBusy/VB/Form1.vb#1)]  
  
 <span data-ttu-id="240d3-110">**Descargar el archivo**</span><span class="sxs-lookup"><span data-stu-id="240d3-110">**Downloading the file**</span></span>  
  
 <span data-ttu-id="240d3-111">El archivo se descarga en el subproceso de trabajo del componente <xref:System.ComponentModel.BackgroundWorker>, que ejecuta el controlador de eventos <xref:System.ComponentModel.BackgroundWorker.DoWork>.</span><span class="sxs-lookup"><span data-stu-id="240d3-111">The file is downloaded on the <xref:System.ComponentModel.BackgroundWorker> component's worker thread, which runs the <xref:System.ComponentModel.BackgroundWorker.DoWork> event handler.</span></span> <span data-ttu-id="240d3-112">Este subproceso se inicia cuando el código llama al método <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A>.</span><span class="sxs-lookup"><span data-stu-id="240d3-112">This thread starts when your code calls the <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A> method.</span></span>  
  
 [!code-csharp[System.ComponentModel.BackgroundWorker.IsBusy#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.IsBusy/CS/Form1.cs#3)]
 [!code-vb[System.ComponentModel.BackgroundWorker.IsBusy#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.IsBusy/VB/Form1.vb#3)]  
  
 <span data-ttu-id="240d3-113">**Esperar a que BackgroundWorker termine**</span><span class="sxs-lookup"><span data-stu-id="240d3-113">**Waiting for a BackgroundWorker to finish**</span></span>  
  
 <span data-ttu-id="240d3-114">El controlador de eventos `downloadButton_Click` muestra cómo esperar a que un componente <xref:System.ComponentModel.BackgroundWorker> termine su tarea asincrónica.</span><span class="sxs-lookup"><span data-stu-id="240d3-114">The `downloadButton_Click` event handler demonstrates how to wait for a <xref:System.ComponentModel.BackgroundWorker> component to finish its asynchronous task.</span></span>  
  
 <span data-ttu-id="240d3-115">Si solo quiere que la aplicación responda a los eventos y no quiere hacer ningún trabajo en el subproceso principal mientras espera a que termine el subproceso en segundo plano, simplemente salga del controlador.</span><span class="sxs-lookup"><span data-stu-id="240d3-115">If you only want the application to respond to events and do not want to do any work in the main thread while you wait for the background thread to complete, just exit the handler.</span></span>  
  
 <span data-ttu-id="240d3-116">Si quiere continuar trabajando en el subproceso principal, use la propiedad <xref:System.ComponentModel.BackgroundWorker.IsBusy%2A> para determinar si el subproceso <xref:System.ComponentModel.BackgroundWorker> todavía se está ejecutando.</span><span class="sxs-lookup"><span data-stu-id="240d3-116">If you want to continue doing work in the main thread, use the <xref:System.ComponentModel.BackgroundWorker.IsBusy%2A> property to determine whether the <xref:System.ComponentModel.BackgroundWorker> thread is still running.</span></span> <span data-ttu-id="240d3-117">En el ejemplo, una barra de progreso se actualiza mientras la descarga se procesa.</span><span class="sxs-lookup"><span data-stu-id="240d3-117">In the example, a progress bar is updated while the download is processing.</span></span> <span data-ttu-id="240d3-118">No olvide llamar al método <xref:System.Windows.Forms.Application.DoEvents%2A?displayProperty=nameWithType> para mantener la capacidad de respuesta de la interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="240d3-118">Be sure to call the <xref:System.Windows.Forms.Application.DoEvents%2A?displayProperty=nameWithType> method to keep the UI responsive.</span></span>  
  
 [!code-csharp[System.ComponentModel.BackgroundWorker.IsBusy#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.IsBusy/CS/Form1.cs#2)]
 [!code-vb[System.ComponentModel.BackgroundWorker.IsBusy#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.IsBusy/VB/Form1.vb#2)]  
  
 <span data-ttu-id="240d3-119">**Mostrar el resultado**</span><span class="sxs-lookup"><span data-stu-id="240d3-119">**Displaying the result**</span></span>  
  
 <span data-ttu-id="240d3-120">El método `backgroundWorker1_RunWorkerCompleted` controla el evento <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> y se le llama cuando se completa la operación en segundo plano.</span><span class="sxs-lookup"><span data-stu-id="240d3-120">The `backgroundWorker1_RunWorkerCompleted` method handles the <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> event and is called when the background operation is completed.</span></span> <span data-ttu-id="240d3-121">Este método comprueba primero la propiedad <xref:System.ComponentModel.AsyncCompletedEventArgs.Error%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="240d3-121">This method first checks the <xref:System.ComponentModel.AsyncCompletedEventArgs.Error%2A?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="240d3-122">Si <xref:System.ComponentModel.AsyncCompletedEventArgs.Error%2A?displayProperty=nameWithType> es `null`, este método muestra el contenido del archivo.</span><span class="sxs-lookup"><span data-stu-id="240d3-122">If <xref:System.ComponentModel.AsyncCompletedEventArgs.Error%2A?displayProperty=nameWithType> is `null`, then this method displays the contents of the file.</span></span> <span data-ttu-id="240d3-123">Después, habilita el botón de descarga, que se deshabilitó cuando comenzó la descarga, y restablece la barra de progreso.</span><span class="sxs-lookup"><span data-stu-id="240d3-123">It then enables the download button, which was disabled when the download began, and it resets the progress bar.</span></span>  
  
 [!code-csharp[System.ComponentModel.BackgroundWorker.IsBusy#4](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.IsBusy/CS/Form1.cs#4)]
 [!code-vb[System.ComponentModel.BackgroundWorker.IsBusy#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.IsBusy/VB/Form1.vb#4)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="240d3-124">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="240d3-124">Compiling the Code</span></span>  
 <span data-ttu-id="240d3-125">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="240d3-125">This example requires:</span></span>  
  
-   <span data-ttu-id="240d3-126">Referencias a los ensamblados System.Drawing, System.Windows.Forms y System.Xml.</span><span class="sxs-lookup"><span data-stu-id="240d3-126">References to the System.Drawing, System.Windows.Forms, and System.Xml assemblies.</span></span>  
  
 <span data-ttu-id="240d3-127">Para obtener información sobre cómo compilar este ejemplo desde la línea de comandos para Visual Basic o Visual C#, vea [compilar desde la línea de comandos](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) o [de línea de comandos con csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="240d3-127">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="240d3-128">También puede compilar este ejemplo en Visual Studio pegando el código en un nuevo proyecto.</span><span class="sxs-lookup"><span data-stu-id="240d3-128">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="240d3-129">Programación sólida</span><span class="sxs-lookup"><span data-stu-id="240d3-129">Robust Programming</span></span>  
 <span data-ttu-id="240d3-130">Compruebe siempre la propiedad <xref:System.ComponentModel.AsyncCompletedEventArgs.Error%2A?displayProperty=nameWithType> en su controlador de eventos <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> antes de intentar acceder a la propiedad <xref:System.ComponentModel.RunWorkerCompletedEventArgs.Result%2A?displayProperty=nameWithType> o a cualquier otro objeto afectado por el controlador de eventos <xref:System.ComponentModel.BackgroundWorker.DoWork>.</span><span class="sxs-lookup"><span data-stu-id="240d3-130">Always check the <xref:System.ComponentModel.AsyncCompletedEventArgs.Error%2A?displayProperty=nameWithType> property in your <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> event handler before attempting to access the <xref:System.ComponentModel.RunWorkerCompletedEventArgs.Result%2A?displayProperty=nameWithType> property or any other object that may have been affected by the <xref:System.ComponentModel.BackgroundWorker.DoWork> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="240d3-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="240d3-131">See also</span></span>

- <xref:System.ComponentModel.BackgroundWorker>
- [<span data-ttu-id="240d3-132">Cómo: Ejecutar una operación en segundo plano</span><span class="sxs-lookup"><span data-stu-id="240d3-132">How to: Run an Operation in the Background</span></span>](how-to-run-an-operation-in-the-background.md)
- [<span data-ttu-id="240d3-133">Cómo: Implementar un formulario que usa una operación en segundo plano</span><span class="sxs-lookup"><span data-stu-id="240d3-133">How to: Implement a Form That Uses a Background Operation</span></span>](how-to-implement-a-form-that-uses-a-background-operation.md)
