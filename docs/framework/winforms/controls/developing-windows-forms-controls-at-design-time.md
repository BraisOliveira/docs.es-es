---
title: Desarrollar controles de formularios Windows Forms en tiempo de diseño
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms controls [Windows Forms]
- Windows Forms controls, creating
- controls [Windows Forms]
- controls [Windows Forms], creating
- user controls [Windows Forms]
- custom controls [Windows Forms]
ms.assetid: e5a8e088-7ec8-4fd9-bcb3-9078fd134829
ms.openlocfilehash: 11c3d9d6e7faa4741365316339d38f9fda69d059
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69965705"
---
# <a name="developing-windows-forms-controls-at-design-time"></a><span data-ttu-id="c80d7-102">Desarrollar controles de formularios Windows Forms en tiempo de diseño</span><span class="sxs-lookup"><span data-stu-id="c80d7-102">Developing Windows Forms Controls at Design Time</span></span>
<span data-ttu-id="c80d7-103">Para los autores de controles, .NET Framework proporciona una gran cantidad de tecnologías de creación de controles.</span><span class="sxs-lookup"><span data-stu-id="c80d7-103">For control authors, the .NET Framework provides a wealth of control authoring technology.</span></span> <span data-ttu-id="c80d7-104">Los creadores ya no están limitados al diseño de controles compuestos que actúan como una colección de controles preexistentes.</span><span class="sxs-lookup"><span data-stu-id="c80d7-104">Authors are no longer limited to designing composite controls that act as a collection of preexisting controls.</span></span> <span data-ttu-id="c80d7-105">A través de la herencia, puede crear sus propios controles a partir de controles compuestos preexistentes o de controles de Windows Forms preexistentes.</span><span class="sxs-lookup"><span data-stu-id="c80d7-105">Through inheritance, you can create your own controls from preexisting composite controls or preexisting Windows Forms controls.</span></span> <span data-ttu-id="c80d7-106">También puede diseñar sus propios controles que implementen el dibujo personalizado.</span><span class="sxs-lookup"><span data-stu-id="c80d7-106">You can also design your own controls that implement custom painting.</span></span> <span data-ttu-id="c80d7-107">Estas opciones permiten una gran flexibilidad en el diseño y la funcionalidad de la interfaz visual.</span><span class="sxs-lookup"><span data-stu-id="c80d7-107">These options enable a great deal of flexibility to the design and functionality of the visual interface.</span></span> <span data-ttu-id="c80d7-108">Para aprovechar estas características, debe estar familiarizado con conceptos de programación basada en objetos.</span><span class="sxs-lookup"><span data-stu-id="c80d7-108">To take advantage of these features, you should be familiar with object-based programming concepts.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c80d7-109">No es necesario tener un conocimiento exhaustivo de la herencia, pero puede que le resulte útil hacer referencia a los [conceptos básicos de la herencia (Visual Basic)](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md).</span><span class="sxs-lookup"><span data-stu-id="c80d7-109">It is not necessary to have a thorough understanding of inheritance, but you may find it useful to refer to [Inheritance basics (Visual Basic)](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md).</span></span>  
  
 <span data-ttu-id="c80d7-110">Si quiere crear controles personalizados para usarlos en formularios Web Forms, consulte [Desarrollar controles de servidor ASP.NET personalizados](https://docs.microsoft.com/previous-versions/aspnet/zt27tfhy(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="c80d7-110">If you want to create custom controls to use on Web Forms, see [Developing Custom ASP.NET Server Controls](https://docs.microsoft.com/previous-versions/aspnet/zt27tfhy(v=vs.100)).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c80d7-111">En esta sección</span><span class="sxs-lookup"><span data-stu-id="c80d7-111">In This Section</span></span>  
 [<span data-ttu-id="c80d7-112">Tutorial: Crear un control compuesto con Visual Basic</span><span class="sxs-lookup"><span data-stu-id="c80d7-112">Walkthrough: Authoring a Composite Control with Visual Basic</span></span>](walkthrough-authoring-a-composite-control-with-visual-basic.md)  
 <span data-ttu-id="c80d7-113">Muestra cómo crear un control compuesto simple en Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="c80d7-113">Shows how to create a simple composite control in Visual Basic.</span></span>  
  
 [<span data-ttu-id="c80d7-114">Tutorial: Crear un control compuesto con VisualC#</span><span class="sxs-lookup"><span data-stu-id="c80d7-114">Walkthrough: Authoring a Composite Control with Visual C#</span></span>](walkthrough-authoring-a-composite-control-with-visual-csharp.md)  
 <span data-ttu-id="c80d7-115">Muestra cómo crear un control compuesto simple en C#.</span><span class="sxs-lookup"><span data-stu-id="c80d7-115">Shows how to create a simple composite control in C#.</span></span>  
  
 [<span data-ttu-id="c80d7-116">Tutorial: Heredar de un control Windows Forms con Visual Basic</span><span class="sxs-lookup"><span data-stu-id="c80d7-116">Walkthrough: Inheriting from a Windows Forms Control with Visual Basic</span></span>](walkthrough-inheriting-from-a-windows-forms-control-with-visual-basic.md)  
 <span data-ttu-id="c80d7-117">Muestra cómo crear un control de Windows Forms simple utilizando la herencia en Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="c80d7-117">Shows how to create a simple Windows Forms control using inheritance in Visual Basic.</span></span>  
  
 [<span data-ttu-id="c80d7-118">Tutorial: Heredar de un control Windows Forms con VisualC#</span><span class="sxs-lookup"><span data-stu-id="c80d7-118">Walkthrough: Inheriting from a Windows Forms Control with Visual C#</span></span>](walkthrough-inheriting-from-a-windows-forms-control-with-visual-csharp.md)  
 <span data-ttu-id="c80d7-119">Muestra cómo crear un control de Windows Forms simple utilizando la herencia en C#.</span><span class="sxs-lookup"><span data-stu-id="c80d7-119">Shows how to create a simple Windows Forms control using inheritance in C#.</span></span>  
  
 [<span data-ttu-id="c80d7-120">Tutorial: Realizar tareas comunes utilizando etiquetas inteligentes en controles de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="c80d7-120">Walkthrough: Performing Common Tasks Using Smart Tags on Windows Forms Controls</span></span>](performing-common-tasks-using-smart-tags-on-wf-controls.md)  
 <span data-ttu-id="c80d7-121">Muestra cómo usar la característica de etiquetas inteligentes en controles de Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="c80d7-121">Shows how to use the smart tag feature on Windows Forms controls.</span></span>  
  
 [<span data-ttu-id="c80d7-122">Tutorial: Serializar colecciones de tipos estándar con DesignerSerializationVisibilityAttribute</span><span class="sxs-lookup"><span data-stu-id="c80d7-122">Walkthrough: Serializing Collections of Standard Types with the DesignerSerializationVisibilityAttribute</span></span>](serializing-collections-designerserializationvisibilityattribute.md)  
 <span data-ttu-id="c80d7-123">Muestra cómo utilizar el <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute.Content?displayProperty=nameWithType> atributo para serializar una colección.</span><span class="sxs-lookup"><span data-stu-id="c80d7-123">Shows how to use the <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute.Content?displayProperty=nameWithType> attribute to serialize a collection.</span></span>  
  
 [<span data-ttu-id="c80d7-124">Tutorial: Depurar controles personalizados de Windows Forms en tiempo de diseño</span><span class="sxs-lookup"><span data-stu-id="c80d7-124">Walkthrough: Debugging Custom Windows Forms Controls at Design Time</span></span>](walkthrough-debugging-custom-windows-forms-controls-at-design-time.md)  
 <span data-ttu-id="c80d7-125">Muestra cómo depurar el comportamiento en tiempo de diseño de un control de Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="c80d7-125">Shows how to debug the design-time behavior of a Windows Forms control.</span></span>  
  
 [<span data-ttu-id="c80d7-126">Tutorial: Crear un control de Windows Forms que aprovecha las características en tiempo de diseño de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="c80d7-126">Walkthrough: Creating a Windows Forms Control That Takes Advantage of Visual Studio Design-Time Features</span></span>](creating-a-wf-control-design-time-features.md)  
 <span data-ttu-id="c80d7-127">Muestra cómo integrar estrechamente un control compuesto en el entorno de diseño.</span><span class="sxs-lookup"><span data-stu-id="c80d7-127">Shows how to tightly integrate a composite control into the design environment.</span></span>  
  
 [<span data-ttu-id="c80d7-128">Cómo: Controles de autor para Windows Forms</span><span class="sxs-lookup"><span data-stu-id="c80d7-128">How to: Author Controls for Windows Forms</span></span>](how-to-author-controls-for-windows-forms.md)  
 <span data-ttu-id="c80d7-129">Proporciona información general sobre consideraciones para implementar un control de Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="c80d7-129">Provides an overview of considerations for implementing a Windows Forms control.</span></span>  
  
 [<span data-ttu-id="c80d7-130">Cómo: Crear controles compuestos</span><span class="sxs-lookup"><span data-stu-id="c80d7-130">How to: Author Composite Controls</span></span>](how-to-author-composite-controls.md)  
 <span data-ttu-id="c80d7-131">Muestra cómo crear un control al heredar de un control compuesto.</span><span class="sxs-lookup"><span data-stu-id="c80d7-131">Shows how to create a control by inheriting from a composite control.</span></span>  
  
 [<span data-ttu-id="c80d7-132">Procedimientos: Heredar de la clase UserControl</span><span class="sxs-lookup"><span data-stu-id="c80d7-132">How to: Inherit from the UserControl Class</span></span>](how-to-inherit-from-the-usercontrol-class.md)  
 <span data-ttu-id="c80d7-133">Proporciona información general sobre el procedimiento para crear un control compuesto.</span><span class="sxs-lookup"><span data-stu-id="c80d7-133">Provides an overview of the procedure for creating a composite control.</span></span>  
  
 [<span data-ttu-id="c80d7-134">Cómo: Heredar de controles de Windows Forms existentes</span><span class="sxs-lookup"><span data-stu-id="c80d7-134">How to: Inherit from Existing Windows Forms Controls</span></span>](how-to-inherit-from-existing-windows-forms-controls.md)  
 <span data-ttu-id="c80d7-135">Muestra cómo crear un control extendido heredando de la <xref:System.Windows.Forms.Button> clase control.</span><span class="sxs-lookup"><span data-stu-id="c80d7-135">Shows how to create an extended control by inheriting from the <xref:System.Windows.Forms.Button> control class.</span></span>  
  
 [<span data-ttu-id="c80d7-136">Procedimientos: Heredar de la clase control</span><span class="sxs-lookup"><span data-stu-id="c80d7-136">How to: Inherit from the Control Class</span></span>](how-to-inherit-from-the-control-class.md)  
 <span data-ttu-id="c80d7-137">Proporciona información general sobre la creación de un control extendido.</span><span class="sxs-lookup"><span data-stu-id="c80d7-137">Provides an overview of creating an extended control.</span></span>  
  
 [<span data-ttu-id="c80d7-138">Procedimientos: Alinear un control con los bordes de los formularios en tiempo de diseño</span><span class="sxs-lookup"><span data-stu-id="c80d7-138">How to: Align a Control to the Edges of Forms at Design Time</span></span>](how-to-align-a-control-to-the-edges-of-forms-at-design-time.md)  
 <span data-ttu-id="c80d7-139">Muestra cómo usar la <xref:System.Windows.Forms.Control.Dock%2A> propiedad para alinear el control con el borde del formulario que ocupa.</span><span class="sxs-lookup"><span data-stu-id="c80d7-139">Shows how to use the <xref:System.Windows.Forms.Control.Dock%2A> property to align your control to the edge of the form it occupies.</span></span>  
  
 [<span data-ttu-id="c80d7-140">Cómo: Mostrar un control en el cuadro de diálogo Elegir elementos del cuadro de herramientas</span><span class="sxs-lookup"><span data-stu-id="c80d7-140">How to: Display a Control in the Choose Toolbox Items Dialog Box</span></span>](how-to-display-a-control-in-the-choose-toolbox-items-dialog-box.md)  
 <span data-ttu-id="c80d7-141">Muestra el procedimiento para instalar el control de modo que aparezca en el cuadro de diálogo **Customize Toolbox** (Personalizar cuadro de herramientas).</span><span class="sxs-lookup"><span data-stu-id="c80d7-141">Shows the procedure for installing your control so that it appears in the **Customize Toolbox** dialog box.</span></span>  
  
 [<span data-ttu-id="c80d7-142">Cómo: Proporcionar un mapa de bits del cuadro de herramientas para un control</span><span class="sxs-lookup"><span data-stu-id="c80d7-142">How to: Provide a Toolbox Bitmap for a Control</span></span>](how-to-provide-a-toolbox-bitmap-for-a-control.md)  
 <span data-ttu-id="c80d7-143">Muestra cómo utilizar <xref:System.Drawing.ToolboxBitmapAttribute> para mostrar un icono junto al control personalizado en el **cuadro de herramientas**.</span><span class="sxs-lookup"><span data-stu-id="c80d7-143">Shows how to use the <xref:System.Drawing.ToolboxBitmapAttribute> to display an icon next to your custom control in the **Toolbox**.</span></span>  
  
 [<span data-ttu-id="c80d7-144">Cómo: Probar el comportamiento en tiempo de ejecución de un control UserControl</span><span class="sxs-lookup"><span data-stu-id="c80d7-144">How to: Test the Run-Time Behavior of a UserControl</span></span>](how-to-test-the-run-time-behavior-of-a-usercontrol.md)  
 <span data-ttu-id="c80d7-145">Muestra cómo utilizar **UserControl Test Container** para probar el comportamiento de un control compuesto.</span><span class="sxs-lookup"><span data-stu-id="c80d7-145">Shows how to use the **UserControl Test Container** to test the behavior of a composite control.</span></span>  
  
 [<span data-ttu-id="c80d7-146">Errores en tiempo de diseño en el Diseñador de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="c80d7-146">Design-Time Errors in the Windows Forms Designer</span></span>](design-time-errors-in-the-windows-forms-designer.md)  
 <span data-ttu-id="c80d7-147">Explica el significado y el uso de la lista de errores de tiempo de diseño que aparece en Microsoft Visual Studio cuando no se puede cargar el Diseñador de Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="c80d7-147">Explains the meaning and use of the Design-Time Error List that appears in Microsoft Visual Studio when the Windows Forms designer fails to load.</span></span>  
  
 [<span data-ttu-id="c80d7-148">Solución de problemas relacionados con la creación de controles y componentes</span><span class="sxs-lookup"><span data-stu-id="c80d7-148">Troubleshooting Control and Component Authoring</span></span>](troubleshooting-control-and-component-authoring.md)  
 <span data-ttu-id="c80d7-149">Muestra cómo diagnosticar y corregir los problemas comunes que pueden producirse al crear un componente o control personalizados.</span><span class="sxs-lookup"><span data-stu-id="c80d7-149">Shows how to diagnose and fix common issues that can occur when you author a custom component or control.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="c80d7-150">Referencia</span><span class="sxs-lookup"><span data-stu-id="c80d7-150">Reference</span></span>  
 <xref:System.Windows.Forms.Control?displayProperty=nameWithType>  
 <span data-ttu-id="c80d7-151">Describe esta clase y contiene vínculos a todos sus miembros.</span><span class="sxs-lookup"><span data-stu-id="c80d7-151">Describes this class and has links to all of its members.</span></span>  
  
 <xref:System.Windows.Forms.UserControl?displayProperty=nameWithType>  
 <span data-ttu-id="c80d7-152">Describe esta clase y contiene vínculos a todos sus miembros.</span><span class="sxs-lookup"><span data-stu-id="c80d7-152">Describes this class and has links to all of its members.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="c80d7-153">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="c80d7-153">Related Sections</span></span>  
 [<span data-ttu-id="c80d7-154">Desarrollar controles personalizados de Windows Forms con .NET Framework</span><span class="sxs-lookup"><span data-stu-id="c80d7-154">Developing Custom Windows Forms Controls with the .NET Framework</span></span>](developing-custom-windows-forms-controls.md)  
 <span data-ttu-id="c80d7-155">Describe cómo crear sus propios controles personalizados con .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="c80d7-155">Discusses how to create your own custom controls with the .NET Framework.</span></span>  
  
 [<span data-ttu-id="c80d7-156">Independencia del lenguaje y componentes independientes del lenguaje</span><span class="sxs-lookup"><span data-stu-id="c80d7-156">Language Independence and Language-Independent Components</span></span>](../../../standard/language-independence-and-language-independent-components.md)  
 <span data-ttu-id="c80d7-157">Presenta Common Language Runtime, que está diseñado para simplificar la creación y el uso de componentes.</span><span class="sxs-lookup"><span data-stu-id="c80d7-157">Introduces the common language runtime, which is designed to simplify the creation and use of components.</span></span> <span data-ttu-id="c80d7-158">Un aspecto importante de esta simplificación es la interoperabilidad mejorada entre los componentes escritos con diferentes lenguajes de programación.</span><span class="sxs-lookup"><span data-stu-id="c80d7-158">An important aspect of this simplification is enhanced interoperability between components written using different programming languages.</span></span> <span data-ttu-id="c80d7-159">Common Language Specification (CLS) hace posible crear herramientas y componentes que funcionen con varios lenguajes de programación.</span><span class="sxs-lookup"><span data-stu-id="c80d7-159">The Common Language Specification (CLS) makes it possible to create tools and components that work with multiple programming languages.</span></span>  
  
 [<span data-ttu-id="c80d7-160">Tutorial: Rellenar automáticamente el cuadro de herramientas con componentes personalizados</span><span class="sxs-lookup"><span data-stu-id="c80d7-160">Walkthrough: Automatically Populating the Toolbox with Custom Components</span></span>](walkthrough-automatically-populating-the-toolbox-with-custom-components.md)  
 <span data-ttu-id="c80d7-161">Describe cómo habilitar que el componente o el control se muestren en el cuadro de diálogo **Customize Toolbox** (Personalizar cuadro de herramientas).</span><span class="sxs-lookup"><span data-stu-id="c80d7-161">Describes how to enable your component or control to be displayed in the **Customize Toolbox** dialog box.</span></span>
