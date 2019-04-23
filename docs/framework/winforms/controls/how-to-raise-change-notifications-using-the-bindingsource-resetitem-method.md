---
title: Procedimiento para provocar notificaciones de cambios mediante el método ResetItem de BindingSource
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- change notifications [Windows Forms], raising
- data binding [Windows Forms], change notifications
- BindingSource component [Windows Forms], raising change notifications with
- data sources [Windows Forms], detecting changes
- change notifications
ms.assetid: ab8b4096-37ff-4e30-aabc-de79a2f2e972
ms.openlocfilehash: 68073f245e1a2eb18a277d7011ca0183dabb3724
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59085069"
---
# <a name="how-to-raise-change-notifications-using-the-bindingsource-resetitem-method"></a><span data-ttu-id="c29cb-102">Procedimiento para provocar notificaciones de cambios mediante el método ResetItem de BindingSource</span><span class="sxs-lookup"><span data-stu-id="c29cb-102">How to: Raise Change Notifications Using the BindingSource ResetItem Method</span></span>
<span data-ttu-id="c29cb-103">Algunos orígenes de datos para sus controles no provocan notificaciones de cambios cuando se cambian, agregan o eliminan elementos.</span><span class="sxs-lookup"><span data-stu-id="c29cb-103">Some data sources for your controls do not raise change notifications when items are changed, added, or deleted.</span></span> <span data-ttu-id="c29cb-104">Con el componente <xref:System.Windows.Forms.BindingSource>, puede enlazar a tales orígenes de datos y provocar una notificación de cambios desde el código.</span><span class="sxs-lookup"><span data-stu-id="c29cb-104">With the <xref:System.Windows.Forms.BindingSource> component, you can bind to such data sources and raise a change notification from your code.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c29cb-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c29cb-105">Example</span></span>  
 <span data-ttu-id="c29cb-106">Este formulario muestra cómo utilizar un componente <xref:System.Windows.Forms.BindingSource> para enlazar una lista a un control <xref:System.Windows.Forms.DataGridView>.</span><span class="sxs-lookup"><span data-stu-id="c29cb-106">This form demonstrates using a <xref:System.Windows.Forms.BindingSource> component to bind a list to a <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="c29cb-107">La lista no provoca notificaciones de cambios, por lo que se llama al método <xref:System.Windows.Forms.BindingSource.ResetItem%2A> en <xref:System.Windows.Forms.BindingSource> cuando se cambia un elemento en la lista.</span><span class="sxs-lookup"><span data-stu-id="c29cb-107">The list does not raise change notifications, so the <xref:System.Windows.Forms.BindingSource.ResetItem%2A> method on the <xref:System.Windows.Forms.BindingSource> is called when an item in the list is changed.</span></span> <span data-ttu-id="c29cb-108">.</span><span class="sxs-lookup"><span data-stu-id="c29cb-108">.</span></span>  
  
 [!code-cpp[System.Windows.Forms.DataConnector.ResetItem#1](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataConnector.ResetItem/CPP/form1.cpp#1)]
 [!code-csharp[System.Windows.Forms.DataConnector.ResetItem#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnector.ResetItem/CS/form1.cs#1)]
 [!code-vb[System.Windows.Forms.DataConnector.ResetItem#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnector.ResetItem/VB/form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="c29cb-109">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="c29cb-109">Compiling the Code</span></span>  
 <span data-ttu-id="c29cb-110">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="c29cb-110">This example requires:</span></span>  
  
-   <span data-ttu-id="c29cb-111">Referencias a los ensamblados System, System.Data, System.Drawing y System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="c29cb-111">References to the System, System.Data, System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="c29cb-112">Para obtener información sobre cómo compilar este ejemplo desde la línea de comandos para Visual Basic o Visual C#, vea [compilar desde la línea de comandos](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) o [de línea de comandos con csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="c29cb-112">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="c29cb-113">También puede compilar este ejemplo en Visual Studio pegando el código en un nuevo proyecto.</span><span class="sxs-lookup"><span data-stu-id="c29cb-113">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c29cb-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="c29cb-114">See also</span></span>

- <xref:System.Windows.Forms.BindingNavigator>
- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.BindingSource>
- [<span data-ttu-id="c29cb-115">Componente BindingSource</span><span class="sxs-lookup"><span data-stu-id="c29cb-115">BindingSource Component</span></span>](bindingsource-component.md)
- [<span data-ttu-id="c29cb-116">Cómo: Enlazar un Control de Windows Forms a un tipo</span><span class="sxs-lookup"><span data-stu-id="c29cb-116">How to: Bind a Windows Forms Control to a Type</span></span>](how-to-bind-a-windows-forms-control-to-a-type.md)
