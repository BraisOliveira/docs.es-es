---
title: Filtrar Enlazar un Control de Windows Forms a un objeto Factory
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- controls [Windows Forms], binding
- factory objects [Windows Forms], binding to
- BindingSource component [Windows Forms], binding to a factory object
- BindingSource component [Windows Forms], examples
ms.assetid: 7d59af89-ff82-41d8-a48a-f1fbae788b0d
ms.openlocfilehash: 57fab57896c4b122f96cea72a5af637c5f5d268a
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2019
ms.locfileid: "57717328"
---
# <a name="how-to-bind-a-windows-forms-control-to-a-factory-object"></a><span data-ttu-id="1c770-102">Procedimiento Enlazar un Control de Windows Forms a un objeto Factory</span><span class="sxs-lookup"><span data-stu-id="1c770-102">How to: Bind a Windows Forms Control to a Factory Object</span></span>
<span data-ttu-id="1c770-103">Al crear controles que interactúan con datos, a veces considerará necesario enlazar un control a un objeto o un método que genere otros objetos.</span><span class="sxs-lookup"><span data-stu-id="1c770-103">When you are building controls that interact with data, you will sometimes find it necessary to bind a control to an object or method that generates other objects.</span></span> <span data-ttu-id="1c770-104">Este tipo de objetos o métodos se denomina generador.</span><span class="sxs-lookup"><span data-stu-id="1c770-104">Such an object or method is called a factory.</span></span> <span data-ttu-id="1c770-105">El origen de datos podría ser, por ejemplo, el valor devuelto de una llamada al método, en lugar de un objeto en la memoria o un tipo.</span><span class="sxs-lookup"><span data-stu-id="1c770-105">Your data source might be, for example, the return value from a method call, instead of an object in memory or a type.</span></span> <span data-ttu-id="1c770-106">Puede enlazar un control a este tipo de origen de datos mientras el origen devuelve una colección.</span><span class="sxs-lookup"><span data-stu-id="1c770-106">You can bind a control to this kind of data source as long as the source returns a collection.</span></span>  
  
 <span data-ttu-id="1c770-107">Puede enlazar fácilmente un control a un objeto de generador utilizando el control <xref:System.Windows.Forms.BindingSource>.</span><span class="sxs-lookup"><span data-stu-id="1c770-107">You can easily bind a control to a factory object by using the <xref:System.Windows.Forms.BindingSource> control.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1c770-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="1c770-108">Example</span></span>  
 <span data-ttu-id="1c770-109">El ejemplo siguiente muestra cómo enlazar un control <xref:System.Windows.Forms.DataGridView> a un método de generador mediante el uso de un control <xref:System.Windows.Forms.BindingSource>.</span><span class="sxs-lookup"><span data-stu-id="1c770-109">The following example demonstrates how to bind a <xref:System.Windows.Forms.DataGridView> control to a factory method by using a <xref:System.Windows.Forms.BindingSource> control.</span></span> <span data-ttu-id="1c770-110">El método de generador se denomina `GetOrdersByCustomerId` y devuelve todos los pedidos de un cliente determinado en la base de datos Northwind.</span><span class="sxs-lookup"><span data-stu-id="1c770-110">The factory method is named `GetOrdersByCustomerId`, and it returns all the orders for a given customer in the Northwind database.</span></span>  
  
 [!code-cpp[System.Windows.Forms.DataConnector.BindToFactory#1](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataConnector.BindToFactory/CPP/form1.cpp#1)]
 [!code-csharp[System.Windows.Forms.DataConnector.BindToFactory#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnector.BindToFactory/CS/form1.cs#1)]
 [!code-vb[System.Windows.Forms.DataConnector.BindToFactory#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnector.BindToFactory/VB/form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="1c770-111">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="1c770-111">Compiling the Code</span></span>  
 <span data-ttu-id="1c770-112">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="1c770-112">This example requires:</span></span>  
  
-   <span data-ttu-id="1c770-113">Referencias a los ensamblados System, System.Data, System.Drawing y System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="1c770-113">References to the System, System.Data, System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="1c770-114">Para obtener información sobre cómo compilar este ejemplo desde la línea de comandos para Visual Basic o Visual C#, vea [compilar desde la línea de comandos](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) o [de línea de comandos con csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="1c770-114">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="1c770-115">También puede compilar este ejemplo en Visual Studio pegando el código en un nuevo proyecto.</span><span class="sxs-lookup"><span data-stu-id="1c770-115">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1c770-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="1c770-116">See also</span></span>
- <xref:System.Windows.Forms.BindingNavigator>
- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.BindingSource>
- [<span data-ttu-id="1c770-117">Componente BindingSource</span><span class="sxs-lookup"><span data-stu-id="1c770-117">BindingSource Component</span></span>](bindingsource-component.md)
- [<span data-ttu-id="1c770-118">Cómo: Enlazar un Control de Windows Forms a un tipo</span><span class="sxs-lookup"><span data-stu-id="1c770-118">How to: Bind a Windows Forms Control to a Type</span></span>](how-to-bind-a-windows-forms-control-to-a-type.md)
