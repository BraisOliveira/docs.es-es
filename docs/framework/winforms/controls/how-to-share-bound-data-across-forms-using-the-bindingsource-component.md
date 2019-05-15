---
title: Procedimiento para compartir datos enlazados entre formularios mediante el componente BindingSource
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- examples [Windows Forms], BindingSource component
- data binding [Windows Forms], sharing data across forms
- BindingSource component [Windows Forms], examples
- BindingSource [Windows Forms], using with multiple forms
ms.assetid: a1a49630-db9c-4485-b888-1f62a373a4f7
ms.openlocfilehash: 28eceaec72053d70885d54bc09179cff743ff71c
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/14/2019
ms.locfileid: "65591440"
---
# <a name="how-to-share-bound-data-across-forms-using-the-bindingsource-component"></a><span data-ttu-id="feab3-102">Procedimiento para compartir datos enlazados entre formularios mediante el componente BindingSource</span><span class="sxs-lookup"><span data-stu-id="feab3-102">How to: Share Bound Data Across Forms Using the BindingSource Component</span></span>
<span data-ttu-id="feab3-103">Puede compartir datos fácilmente entre formularios con el componente <xref:System.Windows.Forms.BindingSource>.</span><span class="sxs-lookup"><span data-stu-id="feab3-103">You can easily share data across forms using the <xref:System.Windows.Forms.BindingSource> component.</span></span> <span data-ttu-id="feab3-104">Por ejemplo, quizás quiera mostrar un formulario de solo lectura que resume los datos del origen de datos y otro formulario editable que contiene información detallada sobre el elemento seleccionado actualmente en el origen de datos.</span><span class="sxs-lookup"><span data-stu-id="feab3-104">For example, you may want to display one read-only form that summarizes the data-source data and another editable form that contains detailed information about the currently selected item in the data source.</span></span> <span data-ttu-id="feab3-105">Este ejemplo muestra este escenario.</span><span class="sxs-lookup"><span data-stu-id="feab3-105">This example demonstrates this scenario.</span></span>  
  
## <a name="example"></a><span data-ttu-id="feab3-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="feab3-106">Example</span></span>  
 <span data-ttu-id="feab3-107">En el ejemplo de código siguiente se muestra cómo compartir un <xref:System.Windows.Forms.BindingSource> y sus datos enlazados entre formularios.</span><span class="sxs-lookup"><span data-stu-id="feab3-107">The following code example demonstrates how to share a <xref:System.Windows.Forms.BindingSource> and its bound data across forms.</span></span> <span data-ttu-id="feab3-108">En este ejemplo, el <xref:System.Windows.Forms.BindingSource> compartido se pasa al constructor del formulario secundario.</span><span class="sxs-lookup"><span data-stu-id="feab3-108">In this example, the shared <xref:System.Windows.Forms.BindingSource> is passed to the constructor of the child form.</span></span> <span data-ttu-id="feab3-109">El formulario secundario permite al usuario editar los datos del elemento actualmente seleccionado en el formulario principal.</span><span class="sxs-lookup"><span data-stu-id="feab3-109">The child form allows the user to edit the data for the currently selected item in the main form.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="feab3-110">El evento <xref:System.Windows.Forms.BindingSource.BindingComplete> del componente <xref:System.Windows.Forms.BindingSource> se controla en el ejemplo para asegurarse de que los dos formularios permanecen sincronizadas.</span><span class="sxs-lookup"><span data-stu-id="feab3-110">The <xref:System.Windows.Forms.BindingSource.BindingComplete> event for the <xref:System.Windows.Forms.BindingSource> component is handled in the example to ensure that the two forms remain synchronized.</span></span> <span data-ttu-id="feab3-111">Para obtener más información acerca de por qué se hace esto, vea [Cómo: Garantizar que varios controles enlazados al mismo origen de datos permanezcan sincronizados](../multiple-controls-bound-to-data-source-synchronized.md).</span><span class="sxs-lookup"><span data-stu-id="feab3-111">For more information about why this is done, see [How to: Ensure Multiple Controls Bound to the Same Data Source Remain Synchronized](../multiple-controls-bound-to-data-source-synchronized.md).</span></span>  
  
 [!code-csharp[System.Windows.Forms.BindingSourceMultipleForms#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.BindingSourceMultipleForms/CS/Form1.cs#1)]
 [!code-vb[System.Windows.Forms.BindingSourceMultipleForms#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.BindingSourceMultipleForms/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="feab3-112">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="feab3-112">Compiling the Code</span></span>  
 <span data-ttu-id="feab3-113">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="feab3-113">This example requires:</span></span>  
  
- <span data-ttu-id="feab3-114">Referencias a los ensamblados System, System.Windows.Forms, System.Drawing, System.Data y System.Xml.</span><span class="sxs-lookup"><span data-stu-id="feab3-114">References to the System, System.Windows.Forms, System.Drawing, System.Data, and System.Xml assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="feab3-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="feab3-115">See also</span></span>

- [<span data-ttu-id="feab3-116">Componente BindingSource</span><span class="sxs-lookup"><span data-stu-id="feab3-116">BindingSource Component</span></span>](bindingsource-component.md)
- [<span data-ttu-id="feab3-117">Enlace de datos en Windows Forms</span><span class="sxs-lookup"><span data-stu-id="feab3-117">Windows Forms Data Binding</span></span>](../windows-forms-data-binding.md)
- [<span data-ttu-id="feab3-118">Cómo: Controlar errores y excepciones que se producen con el enlace de datos</span><span class="sxs-lookup"><span data-stu-id="feab3-118">How to: Handle Errors and Exceptions that Occur with Databinding</span></span>](how-to-handle-errors-and-exceptions-that-occur-with-databinding.md)
