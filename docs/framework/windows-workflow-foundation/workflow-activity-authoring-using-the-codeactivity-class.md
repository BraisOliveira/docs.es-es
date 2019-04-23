---
title: Crear actividad de flujo de trabajo mediante la clase CodeActivity
ms.date: 03/30/2017
ms.assetid: cfe315c1-f86d-43ec-b9ce-2f8c469b1106
ms.openlocfilehash: 549acec8b8101312d48bd20e63a4a988b798ff38
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59767401"
---
# <a name="workflow-activity-authoring-using-the-codeactivity-class"></a><span data-ttu-id="b89de-102">Crear actividad de flujo de trabajo mediante la clase CodeActivity</span><span class="sxs-lookup"><span data-stu-id="b89de-102">Workflow Activity Authoring Using the CodeActivity Class</span></span>
<span data-ttu-id="b89de-103">Las actividades creadas al heredar de <xref:System.Activities.CodeActivity> pueden implementar el comportamiento imperativo básico al invalidar el método <xref:System.Activities.CodeActivity.Execute%2A>.</span><span class="sxs-lookup"><span data-stu-id="b89de-103">Activities created by inheriting from <xref:System.Activities.CodeActivity> can implement basic imperative behavior by overriding the <xref:System.Activities.CodeActivity.Execute%2A> method.</span></span>

## <a name="using-codeactivitycontext"></a><span data-ttu-id="b89de-104">Usar CodeActivityContext</span><span class="sxs-lookup"><span data-stu-id="b89de-104">Using CodeActivityContext</span></span>
 <span data-ttu-id="b89de-105">Se puede tener acceso a las características del tiempo de ejecución del flujo de trabajo desde dentro del método <xref:System.Activities.CodeActivity.Execute%2A> usando los miembros del parámetro `context`, del tipo <xref:System.Activities.CodeActivityContext>.</span><span class="sxs-lookup"><span data-stu-id="b89de-105">Features of the workflow runtime can be accessed from within the <xref:System.Activities.CodeActivity.Execute%2A> method by using members of the `context` parameter, of type <xref:System.Activities.CodeActivityContext>.</span></span> <span data-ttu-id="b89de-106">Las características disponibles mediante <xref:System.Activities.CodeActivityContext> incluyen lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="b89de-106">The features available through <xref:System.Activities.CodeActivityContext> include the following:</span></span>

-   <span data-ttu-id="b89de-107">Obtener y establecer los valores de variables y argumentos.</span><span class="sxs-lookup"><span data-stu-id="b89de-107">Getting and setting the values of variables and arguments.</span></span>

-   <span data-ttu-id="b89de-108">Características de seguimiento personalizadas con <xref:System.Activities.CodeActivityContext.Track%2A>.</span><span class="sxs-lookup"><span data-stu-id="b89de-108">Custom tracking features using <xref:System.Activities.CodeActivityContext.Track%2A>.</span></span>

-   <span data-ttu-id="b89de-109">Obtenga acceso a las propiedades de ejecución de la actividad con <xref:System.Activities.CodeActivityContext.GetProperty%2A>.</span><span class="sxs-lookup"><span data-stu-id="b89de-109">Access to the activity’s execution properties using <xref:System.Activities.CodeActivityContext.GetProperty%2A>.</span></span>

#### <a name="to-create-a-custom-activity-that-inherits-from-codeactivity"></a><span data-ttu-id="b89de-110">Para crear una actividad personalizada que herede de CodeActivity</span><span class="sxs-lookup"><span data-stu-id="b89de-110">To create a custom activity that inherits from CodeActivity</span></span>

1. <span data-ttu-id="b89de-111">Abra Visual Studio 2010.</span><span class="sxs-lookup"><span data-stu-id="b89de-111">Open Visual Studio 2010.</span></span>

2. <span data-ttu-id="b89de-112">Seleccione **archivo**, **nueva**y, a continuación, **proyecto**.</span><span class="sxs-lookup"><span data-stu-id="b89de-112">Select **File**, **New**, and then **Project**.</span></span> <span data-ttu-id="b89de-113">Seleccione **Workflow 4.0** en **Visual C#** en el **tipos de proyecto** ventana y seleccione el **v2010** nodo.</span><span class="sxs-lookup"><span data-stu-id="b89de-113">Select **Workflow 4.0** under **Visual C#** in the **Project Types** window, and select the **v2010** node.</span></span> <span data-ttu-id="b89de-114">Seleccione **biblioteca de actividades** en el **plantillas** ventana.</span><span class="sxs-lookup"><span data-stu-id="b89de-114">Select **Activity Library** in the **Templates** window.</span></span> <span data-ttu-id="b89de-115">Dé al nuevo proyecto el nombre "HelloActivity".</span><span class="sxs-lookup"><span data-stu-id="b89de-115">Name the new project HelloActivity.</span></span>

3. <span data-ttu-id="b89de-116">Haga clic en Activity1.xaml en el proyecto HelloActivity y seleccione **eliminar**.</span><span class="sxs-lookup"><span data-stu-id="b89de-116">Right-click Activity1.xaml in the HelloActivity project and select **Delete**.</span></span>

4. <span data-ttu-id="b89de-117">Haga clic en el proyecto HelloActivity y seleccione **agregar** y, a continuación, **clase**.</span><span class="sxs-lookup"><span data-stu-id="b89de-117">Right-click the HelloActivity project and select **Add** , and then **Class**.</span></span> <span data-ttu-id="b89de-118">Dé a la nueva clase el nombre "HelloActivity.cs".</span><span class="sxs-lookup"><span data-stu-id="b89de-118">Name the new class HelloActivity.cs.</span></span>

5. <span data-ttu-id="b89de-119">En el archivo HelloActivity.cs, agregue las siguientes directivas `using`.</span><span class="sxs-lookup"><span data-stu-id="b89de-119">In the HelloActivity.cs file, add the following `using` directives.</span></span>

    ```csharp
    using System.Activities;
    using System.Activities.Statements;
    ```

6. <span data-ttu-id="b89de-120">Haga que la nueva clase herede de <xref:System.Activities.CodeActivity> al agregar una clase base a la declaración de clase.</span><span class="sxs-lookup"><span data-stu-id="b89de-120">Make the new class inherit from <xref:System.Activities.CodeActivity> by adding a base class to the class declaration.</span></span>

    ```csharp
    class HelloActivity : CodeActivity
    ```

7. <span data-ttu-id="b89de-121">Agregue la funcionalidad a la clase agregando un método <xref:System.Activities.CodeActivity.Execute%2A>.</span><span class="sxs-lookup"><span data-stu-id="b89de-121">Add functionality to the class by adding an <xref:System.Activities.CodeActivity.Execute%2A> method.</span></span>

    ```csharp
    protected override void Execute(CodeActivityContext context)
    {
        Console.WriteLine("Hello World!");
    }
    ```

8. <span data-ttu-id="b89de-122">Use <xref:System.Activities.CodeActivityContext> para crear un registro de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="b89de-122">Use the <xref:System.Activities.CodeActivityContext> to create a tracking record.</span></span>

    ```csharp
    protected override void Execute(CodeActivityContext context)
    {
        Console.WriteLine("Hello World!");
        CustomTrackingRecord record = new CustomTrackingRecord("MyRecord");
        record.Data.Add(new KeyValuePair<String, Object>("ExecutionTime", DateTime.Now));
        context.Track(record);
    }
    ```
