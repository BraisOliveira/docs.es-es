---
title: 'Tarea 1: Crear una nueva aplicación de Windows Presentation Foundation'
ms.date: 03/30/2017
ms.assetid: 270eaeba-9492-4532-af9f-403ce5c9935b
ms.openlocfilehash: 533b4a1030ab5f47eb96ca62dc2805eae7933b9b
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2019
ms.locfileid: "57711903"
---
# <a name="task-1-create-a-new-windows-presentation-foundation-application"></a><span data-ttu-id="47575-102">Tarea 1: Crear una nueva aplicación de Windows Presentation Foundation</span><span class="sxs-lookup"><span data-stu-id="47575-102">Task 1: Create a New Windows Presentation Foundation Application</span></span>
<span data-ttu-id="47575-103">En esta tarea, creará una aplicación vacía de Windows Presentation Foundation (WPF) mediante la plantilla de aplicaciones de WPF de Visual Studio y agregue referencias a adecuado [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] ensamblados de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="47575-103">In this task, you will create an empty Windows Presentation Foundation (WPF) application by using the WPF Application Visual Studio template and add references to the appropriate [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] workflow assemblies.</span></span>  
  
### <a name="to-create-the-wpf-application-project"></a><span data-ttu-id="47575-104">Para crear el proyecto de aplicación WPF</span><span class="sxs-lookup"><span data-stu-id="47575-104">To create the WPF Application project</span></span>  
  
1.  <span data-ttu-id="47575-105">Abra Visual Studio y en el **archivo** menú, elija **New**y, a continuación, haga clic en **proyecto**.</span><span class="sxs-lookup"><span data-stu-id="47575-105">Open Visual Studio and on the **File** menu, point to **New**, and then click **Project**.</span></span>  
  
2.  <span data-ttu-id="47575-106">En el **nuevo proyecto** cuadro de diálogo, seleccione **Visual C#**  o **Visual Basic** desde el **plantillas instaladas** panel de la izquierda lado del cuadro.</span><span class="sxs-lookup"><span data-stu-id="47575-106">In the **New Project** dialog box, select either **Visual C#** or **Visual Basic** from the **Installed Templates** pane on the left side of the box.</span></span> <span data-ttu-id="47575-107">Si el idioma que prefiera no aparece, mire en **otros lenguajes**.</span><span class="sxs-lookup"><span data-stu-id="47575-107">If the language of your choice does not appear, look under **Other Languages**.</span></span>  
  
3.  <span data-ttu-id="47575-108">Seleccione **Windows** en el **plantillas instaladas** panel.</span><span class="sxs-lookup"><span data-stu-id="47575-108">Select **Windows** in the **Installed Templates** pane.</span></span>  
  
4.  <span data-ttu-id="47575-109">En el panel superior, confirme que (el valor predeterminado) **.NET Framework 4** se ha seleccionado en el cuadro de lista desplegable y, a continuación, seleccione **aplicación WPF**.</span><span class="sxs-lookup"><span data-stu-id="47575-109">In the top pane, confirm that (the default value) **.NET Framework 4** has been selected in the drop-down list box, and then select **WPF Application**.</span></span>  
  
5.  <span data-ttu-id="47575-110">Establezca el nombre del proyecto a **HostingApplication** en la parte inferior de la ventana.</span><span class="sxs-lookup"><span data-stu-id="47575-110">Set the name of the project to **HostingApplication** at the bottom of the window.</span></span>  
  
6.  <span data-ttu-id="47575-111">Establece el nombre de la solución en **"rehostingthedesigner"**.</span><span class="sxs-lookup"><span data-stu-id="47575-111">Set the solution name to **RehostingTheDesigner**.</span></span>  
  
7.  <span data-ttu-id="47575-112">Haga clic en **Aceptar** para crear el proyecto de aplicación.</span><span class="sxs-lookup"><span data-stu-id="47575-112">Click **OK** to create the application project.</span></span> <span data-ttu-id="47575-113">Visual Studio crea una UI WPF básica para la aplicación e incluye el XAML adecuado y los archivos de código subyacente.</span><span class="sxs-lookup"><span data-stu-id="47575-113">Visual Studio creates a basic WPF UI for your application and includes the appropriate XAML and code-behind files.</span></span>  
  
8.  <span data-ttu-id="47575-114">Agregue referencias a **WorkflowModel** ensamblados.</span><span class="sxs-lookup"><span data-stu-id="47575-114">Add references to **WorkflowModel** assemblies.</span></span> <span data-ttu-id="47575-115">Para ello, en **el Explorador de soluciones**, haga clic en el **HostingApplication** del proyecto y seleccione **Agregar referencia**.</span><span class="sxs-lookup"><span data-stu-id="47575-115">To do this, in **Solution Explorer**, right-click the **HostingApplication** project and select **Add Reference**.</span></span>  
  
9. <span data-ttu-id="47575-116">En el **Agregar referencia** cuadro de diálogo, haga clic en el **.NET** , mantenga presionada la tecla CTRL, seleccione los ensamblados siguientes y, a continuación, haga clic en **Aceptar**:</span><span class="sxs-lookup"><span data-stu-id="47575-116">In the **Add Reference** dialog box, click the **.NET** tab, hold down the CTRL key, select the following assemblies, and then click **OK**:</span></span>  
  
    -   <span data-ttu-id="47575-117">System.Activities</span><span class="sxs-lookup"><span data-stu-id="47575-117">System.Activities</span></span>  
  
    -   <span data-ttu-id="47575-118">System.Activities.Presentation</span><span class="sxs-lookup"><span data-stu-id="47575-118">System.Activities.Presentation</span></span>  
  
    -   <span data-ttu-id="47575-119">System.Activities.Core.Presentation</span><span class="sxs-lookup"><span data-stu-id="47575-119">System.Activities.Core.Presentation</span></span>  
  
10. <span data-ttu-id="47575-120">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="47575-120">Click **OK**.</span></span>  
  
11. <span data-ttu-id="47575-121">Consulte [tarea 2: Hospedar el Diseñador de flujo de trabajo](task-2-host-the-workflow-designer.md) para aprender a hospedar el lienzo de diseño del Diseñador de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="47575-121">See [Task 2: Host the Workflow Designer](task-2-host-the-workflow-designer.md) to learn how to host the workflow designer design canvas.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="47575-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="47575-122">See also</span></span>
- [<span data-ttu-id="47575-123">Rehospedaje del Diseñador de flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="47575-123">Rehosting the Workflow Designer</span></span>](rehosting-the-workflow-designer.md)
- [<span data-ttu-id="47575-124">Tarea 2: Hospedar el Diseñador de flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="47575-124">Task 2: Host the Workflow Designer</span></span>](task-2-host-the-workflow-designer.md)
