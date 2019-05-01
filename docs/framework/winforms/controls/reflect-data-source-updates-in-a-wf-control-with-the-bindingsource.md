---
title: Procedimiento para reflejar las actualizaciones de los orígenes de datos en un control de formularios Windows Forms con BindingSource
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- data binding [Windows Forms], updating
- BindingSource component [Windows Forms], updating data binding
- examples [Windows Forms], BindingSource component
- data sources [Windows Forms], updating
- BindingSource component [Windows Forms], examples
ms.assetid: bd8bd9b2-af8a-4f11-a3d5-54eecbe2400b
ms.openlocfilehash: 16dbe4da1efecd120d4da4d66c3d79ec907b92a6
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61947997"
---
# <a name="how-to-reflect-data-source-updates-in-a-windows-forms-control-with-the-bindingsource"></a><span data-ttu-id="efdaa-102">Procedimiento para reflejar las actualizaciones de los orígenes de datos en un control de formularios Windows Forms con BindingSource</span><span class="sxs-lookup"><span data-stu-id="efdaa-102">How to: Reflect Data Source Updates in a Windows Forms Control with the BindingSource</span></span>
<span data-ttu-id="efdaa-103">Cuando utilice controles enlazados a datos, a veces tendrá que responder a los cambios del origen de datos cuando el origen de datos no provoque eventos cambiados en la lista.</span><span class="sxs-lookup"><span data-stu-id="efdaa-103">When you use data-bound controls, you sometimes have to respond to changes in the data source when the data source does not raise list-changed events.</span></span> <span data-ttu-id="efdaa-104">Cuando utiliza el componente <xref:System.Windows.Forms.BindingSource> para enlazar el origen de datos a un control de Windows Forms, se puede notificar al control que el origen de datos ha cambiado llamando al método <xref:System.Windows.Forms.BindingSource.ResetBindings%2A>.</span><span class="sxs-lookup"><span data-stu-id="efdaa-104">When you use the <xref:System.Windows.Forms.BindingSource> component to bind your data source to a Windows Forms control, you can notify the control that your data source has changed by calling the <xref:System.Windows.Forms.BindingSource.ResetBindings%2A> method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="efdaa-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="efdaa-105">Example</span></span>  
 <span data-ttu-id="efdaa-106">El ejemplo de código siguiente muestra cómo utilizar el método <xref:System.Windows.Forms.BindingSource.ResetBindings%2A> para notificar a un control enlazado una actualización del origen de datos.</span><span class="sxs-lookup"><span data-stu-id="efdaa-106">The following code example demonstrates using the <xref:System.Windows.Forms.BindingSource.ResetBindings%2A> method to notify a bound control about an update in the data source.</span></span>  
  
 [!code-cpp[System.Windows.Forms.DataConnector.ResetBindings#1](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataConnector.ResetBindings/CPP/form1.cpp#1)]
 [!code-csharp[System.Windows.Forms.DataConnector.ResetBindings#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnector.ResetBindings/CS/form1.cs#1)]
 [!code-vb[System.Windows.Forms.DataConnector.ResetBindings#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnector.ResetBindings/VB/form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="efdaa-107">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="efdaa-107">Compiling the Code</span></span>  
 <span data-ttu-id="efdaa-108">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="efdaa-108">This example requires:</span></span>  
  
- <span data-ttu-id="efdaa-109">Referencias a los ensamblados System, System.Drawing y System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="efdaa-109">References to the System, System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="efdaa-110">Para obtener información sobre cómo compilar este ejemplo desde la línea de comandos para Visual Basic o Visual C#, vea [compilar desde la línea de comandos](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) o [de línea de comandos con csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="efdaa-110">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="efdaa-111">También puede compilar este ejemplo en Visual Studio pegando el código en un nuevo proyecto.</span><span class="sxs-lookup"><span data-stu-id="efdaa-111">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="efdaa-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="efdaa-112">See also</span></span>

- <xref:System.Windows.Forms.BindingNavigator>
- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.BindingSource>
- [<span data-ttu-id="efdaa-113">Componente BindingSource</span><span class="sxs-lookup"><span data-stu-id="efdaa-113">BindingSource Component</span></span>](bindingsource-component.md)
- [<span data-ttu-id="efdaa-114">Cómo: Enlazar un Control de Windows Forms a un tipo</span><span class="sxs-lookup"><span data-stu-id="efdaa-114">How to: Bind a Windows Forms Control to a Type</span></span>](how-to-bind-a-windows-forms-control-to-a-type.md)
