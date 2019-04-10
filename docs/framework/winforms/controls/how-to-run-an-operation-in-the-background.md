---
title: Filtrar para ejecutar una operación en segundo plano
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- background tasks
- forms [Windows Forms], multithreading
- forms [Windows Forms], background operations
- background threads
- BackgroundWorker class [Windows Forms], examples
- threading [Windows Forms], background operations
- background operations
ms.assetid: 5b56e2aa-dc05-444f-930c-2d7b23f9ad5b
ms.openlocfilehash: 5ccbb6e4c09f5417f6c2766824ec7ed9722eed52
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59217996"
---
# <a name="how-to-run-an-operation-in-the-background"></a><span data-ttu-id="00d4a-102">Filtrar para ejecutar una operación en segundo plano</span><span class="sxs-lookup"><span data-stu-id="00d4a-102">How to: Run an Operation in the Background</span></span>
<span data-ttu-id="00d4a-103">Si tiene una operación que tarda mucho tiempo en completarse y no desea causar retrasos en la interfaz de usuario, puede utilizar la clase <xref:System.ComponentModel.BackgroundWorker> para ejecutar la operación en otro subproceso.</span><span class="sxs-lookup"><span data-stu-id="00d4a-103">If you have an operation that will take a long time to complete, and you do not want to cause delays in your user interface, you can use the <xref:System.ComponentModel.BackgroundWorker> class to run the operation on another thread.</span></span>  
  
 <span data-ttu-id="00d4a-104">El ejemplo de código siguiente muestra cómo ejecutar en segundo plano una operación que consume mucho tiempo.</span><span class="sxs-lookup"><span data-stu-id="00d4a-104">The following code example shows how to run a time-consuming operation in the background.</span></span> <span data-ttu-id="00d4a-105">El formulario cuenta con los botones **Iniciar** y **Cancelar**.</span><span class="sxs-lookup"><span data-stu-id="00d4a-105">The form has **Start** and **Cancel** buttons.</span></span> <span data-ttu-id="00d4a-106">Haga clic en el botón **Iniciar** para ejecutar una operación asincrónica.</span><span class="sxs-lookup"><span data-stu-id="00d4a-106">Click the **Start** button to run an asynchronous operation.</span></span> <span data-ttu-id="00d4a-107">Haga clic en el botón **Cancelar** para detener una operación asincrónica.</span><span class="sxs-lookup"><span data-stu-id="00d4a-107">Click the **Cancel** button to stop a running asynchronous operation.</span></span> <span data-ttu-id="00d4a-108">El resultado de cada operación se muestra en un elemento <xref:System.Windows.Forms.MessageBox>.</span><span class="sxs-lookup"><span data-stu-id="00d4a-108">The outcome of each operation is displayed in a <xref:System.Windows.Forms.MessageBox>.</span></span>  
  
 <span data-ttu-id="00d4a-109">Visual Studio es altamente compatible con esta tarea.</span><span class="sxs-lookup"><span data-stu-id="00d4a-109">There is extensive support for this task in Visual Studio.</span></span>  
  
 <span data-ttu-id="00d4a-110">Consulte también [Tutorial: Ejecución de una operación en segundo plano](walkthrough-running-an-operation-in-the-background.md).</span><span class="sxs-lookup"><span data-stu-id="00d4a-110">Also see [Walkthrough: Running an Operation in the Background](walkthrough-running-an-operation-in-the-background.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="00d4a-111">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="00d4a-111">Example</span></span>  
 [!code-csharp[System.ComponentModel.BackgroundWorker.Example#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/CS/Form1.cs#1)]
 [!code-vb[System.ComponentModel.BackgroundWorker.Example#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="00d4a-112">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="00d4a-112">Compiling the Code</span></span>  
 <span data-ttu-id="00d4a-113">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="00d4a-113">This example requires:</span></span>  
  
-   <span data-ttu-id="00d4a-114">Referencias a los ensamblados System, System.Drawing y System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="00d4a-114">References to the System, System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="00d4a-115">Para obtener información sobre cómo compilar este ejemplo desde la línea de comandos para Visual Basic o Visual C#, vea [compilar desde la línea de comandos](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) o [de línea de comandos con csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="00d4a-115">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="00d4a-116">También puede compilar este ejemplo en Visual Studio pegando el código en un nuevo proyecto.</span><span class="sxs-lookup"><span data-stu-id="00d4a-116">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="00d4a-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="00d4a-117">See also</span></span>

- <xref:System.ComponentModel.BackgroundWorker>
- <xref:System.ComponentModel.DoWorkEventArgs>
- [<span data-ttu-id="00d4a-118">Filtrar para implementar un formulario que usa una operación en segundo plano</span><span class="sxs-lookup"><span data-stu-id="00d4a-118">How to: Implement a Form That Uses a Background Operation</span></span>](how-to-implement-a-form-that-uses-a-background-operation.md)
- [<span data-ttu-id="00d4a-119">BackgroundWorker (Componente)</span><span class="sxs-lookup"><span data-stu-id="00d4a-119">BackgroundWorker Component</span></span>](backgroundworker-component.md)
