---
title: Procedimiento para crear un control con enlace simple en formularios Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- data binding [Windows Forms], simple data binding
- Windows Forms controls, data binding
ms.assetid: 3bcaded8-0f1a-4cc0-8830-f59be253bf4e
ms.openlocfilehash: 5c92b7bfd5026b0569397dc05cca216fbdab0753
ms.sourcegitcommit: d8ebe0ee198f5d38387a80ba50f395386779334f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/05/2019
ms.locfileid: "66689306"
---
# <a name="how-to-create-a-simple-bound-control-on-a-windows-form"></a><span data-ttu-id="9a86c-102">Procedimiento para crear un control con enlace simple en formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="9a86c-102">How to: Create a Simple-Bound Control on a Windows Form</span></span>

<span data-ttu-id="9a86c-103">Con *enlace simple*, puede mostrar un elemento de datos único, como un valor de columna de una tabla de conjunto de datos en un control.</span><span class="sxs-lookup"><span data-stu-id="9a86c-103">With *simple binding*, you can display a single data element, such as a column value from a dataset table, in a control.</span></span> <span data-ttu-id="9a86c-104">Puede enlazar cualquier propiedad de un control de forma sencilla en un valor de datos.</span><span class="sxs-lookup"><span data-stu-id="9a86c-104">You can simple-bind any property of a control to a data value.</span></span>

> [!NOTE]
> <span data-ttu-id="9a86c-105">Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos.</span><span class="sxs-lookup"><span data-stu-id="9a86c-105">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="9a86c-106">Para cambiar la configuración, elija la opción **Importar y exportar configuraciones** del menú **Herramientas** .</span><span class="sxs-lookup"><span data-stu-id="9a86c-106">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="9a86c-107">Para más información, vea [Personalizar el IDE de Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).</span><span class="sxs-lookup"><span data-stu-id="9a86c-107">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>

### <a name="to-simple-bind-a-control"></a><span data-ttu-id="9a86c-108">Para enlazar un control simple</span><span class="sxs-lookup"><span data-stu-id="9a86c-108">To simple-bind a control</span></span>

1. <span data-ttu-id="9a86c-109">Conéctese a un origen de datos.</span><span class="sxs-lookup"><span data-stu-id="9a86c-109">Connect to a data source.</span></span> <span data-ttu-id="9a86c-110">Para obtener más información, consulte [conectarse a un origen de datos](../data/adonet/connecting-to-a-data-source.md).</span><span class="sxs-lookup"><span data-stu-id="9a86c-110">For more information, see [Connecting to a Data Source](../data/adonet/connecting-to-a-data-source.md).</span></span>

2. <span data-ttu-id="9a86c-111">En el formulario, seleccione el control y mostrar el **propiedades** ventana.</span><span class="sxs-lookup"><span data-stu-id="9a86c-111">In the form, select the control and display the **Properties** window.</span></span>

3. <span data-ttu-id="9a86c-112">Expanda el **(DataBindings)** propiedad.</span><span class="sxs-lookup"><span data-stu-id="9a86c-112">Expand the **(DataBindings)** property.</span></span>

     <span data-ttu-id="9a86c-113">Las propiedades enlazadas con más frecuencia se muestran bajo el **(DataBindings)** propiedad.</span><span class="sxs-lookup"><span data-stu-id="9a86c-113">The properties most often bound are displayed underneath the **(DataBindings)** property.</span></span> <span data-ttu-id="9a86c-114">Por ejemplo, en la mayoría de los controles, el **texto** propiedad está enlazada con más frecuencia.</span><span class="sxs-lookup"><span data-stu-id="9a86c-114">For example, in most controls, the **Text** property is most frequently bound.</span></span>

4. <span data-ttu-id="9a86c-115">Si la propiedad que desea enlazar no es una de las propiedades enlazadas con frecuencia, haga clic en el **puntos suspensivos** botón (![los puntos suspensivos (...) en la ventana Propiedades de Visual Studio.](./media/how-to-create-a-simple-bound-control-on-a-windows-form/visual-studio-ellipsis-button.png)) en el **() Opciones avanzadas)** cuadro para mostrar el **formato y enlace de datos avanzado** cuadro de diálogo con una lista completa de propiedades para ese control.</span><span class="sxs-lookup"><span data-stu-id="9a86c-115">If the property you want to bind is not one of the commonly bound properties, click the **Ellipsis** button (![The Ellipsis button (...) in the Properties window of Visual Studio.](./media/how-to-create-a-simple-bound-control-on-a-windows-form/visual-studio-ellipsis-button.png)) in the **(Advanced)** box to display the **Formatting and Advanced Binding** dialog box with a complete list of properties for that control.</span></span>

5. <span data-ttu-id="9a86c-116">Seleccione la propiedad que desea enlazar y haga clic en la flecha desplegable situada debajo **enlace**.</span><span class="sxs-lookup"><span data-stu-id="9a86c-116">Select the property you want to bind and click the drop-down arrow under **Binding**.</span></span>

     <span data-ttu-id="9a86c-117">Se muestra una lista de los orígenes de datos disponibles.</span><span class="sxs-lookup"><span data-stu-id="9a86c-117">A list of available data sources is displayed.</span></span>

6. <span data-ttu-id="9a86c-118">Expanda el origen de datos al que desea enlazar hasta que encuentre el elemento de datos que desea.</span><span class="sxs-lookup"><span data-stu-id="9a86c-118">Expand the data source you want to bind to until you find the single data element you want.</span></span> <span data-ttu-id="9a86c-119">Por ejemplo, si va a enlazar a un valor de columna en la tabla de un conjunto de datos, expanda el nombre del conjunto de datos y, después, expanda el nombre de la tabla para mostrar los nombres de columna.</span><span class="sxs-lookup"><span data-stu-id="9a86c-119">For example, if you are binding to a column value in a dataset's table, expand the name of the dataset, and then expand the table name to display column names.</span></span>

7. <span data-ttu-id="9a86c-120">Haga clic en el nombre del elemento al que se va a enlazar.</span><span class="sxs-lookup"><span data-stu-id="9a86c-120">Click the name of an element to bind to.</span></span>

8. <span data-ttu-id="9a86c-121">Si estuviera trabajando la **formato y enlace de datos avanzado** cuadro de diálogo, haga clic en **Aceptar** para volver a la **propiedades** ventana.</span><span class="sxs-lookup"><span data-stu-id="9a86c-121">If you were working in the **Formatting and Advanced Binding** dialog box, click **OK** to return to the **Properties** window.</span></span>

9. <span data-ttu-id="9a86c-122">Si desea enlazar propiedades adicionales del control, repita los pasos del 3 al 7.</span><span class="sxs-lookup"><span data-stu-id="9a86c-122">If you want to bind additional properties of the control, repeat steps 3 through 7.</span></span>

    > [!NOTE]
    > <span data-ttu-id="9a86c-123">Dado que los controles de enlace simple muestran solo un único elemento de datos, es muy habitual incluir lógica de navegación en un formulario de Windows con controles de enlace simple.</span><span class="sxs-lookup"><span data-stu-id="9a86c-123">Because simple-bound controls show only a single data element, it is very typical to include navigation logic in a Windows Form with simple-bound controls.</span></span>

## <a name="see-also"></a><span data-ttu-id="9a86c-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="9a86c-124">See also</span></span>

- <xref:System.Windows.Forms.Binding>
- [<span data-ttu-id="9a86c-125">Enlace de datos en Windows Forms</span><span class="sxs-lookup"><span data-stu-id="9a86c-125">Windows Forms Data Binding</span></span>](windows-forms-data-binding.md)
- [<span data-ttu-id="9a86c-126">Enlace de datos y Windows Forms</span><span class="sxs-lookup"><span data-stu-id="9a86c-126">Data Binding and Windows Forms</span></span>](data-binding-and-windows-forms.md)
