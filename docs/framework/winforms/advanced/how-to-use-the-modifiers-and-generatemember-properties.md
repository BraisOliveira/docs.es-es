---
title: Filtrar para usar las propiedades Modifiers y GenerateMember
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
f1_keywords:
- Designer_GenerateMember
- Designer_Modifiers
helpviewer_keywords:
- base forms
- inheritance [Windows Forms], forms
- inherited forms [Windows Forms], Windows Forms
- inherited forms
- form inheritance
- Windows Forms, inheritance
ms.assetid: 3381a5e4-e1a3-44e2-a765-a0b758937b85
ms.openlocfilehash: 612d323305c2dbd4698c6d687fb19ec36983bde4
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59143915"
---
# <a name="how-to-use-the-modifiers-and-generatemember-properties"></a><span data-ttu-id="71a39-102">Filtrar para usar las propiedades Modifiers y GenerateMember</span><span class="sxs-lookup"><span data-stu-id="71a39-102">How to: Use the Modifiers and GenerateMember Properties</span></span>
<span data-ttu-id="71a39-103">Cuando se coloca un componente en un formulario de Windows, el entorno de diseño proporciona dos propiedades: `GenerateMember` y `Modifiers`.</span><span class="sxs-lookup"><span data-stu-id="71a39-103">When you place a component on a Windows Form, two properties are provided by the design environment: `GenerateMember` and `Modifiers`.</span></span> <span data-ttu-id="71a39-104">El `GenerateMember` propiedad especifica que cuando el Diseñador de Windows Forms genera una variable miembro para un componente.</span><span class="sxs-lookup"><span data-stu-id="71a39-104">The `GenerateMember` property specifies when the Windows Forms Designer generates a member variable for a component.</span></span> <span data-ttu-id="71a39-105">El `Modifiers` propiedad es el modificador de acceso asignado a esa variable de miembro.</span><span class="sxs-lookup"><span data-stu-id="71a39-105">The `Modifiers` property is the access modifier assigned to that member variable.</span></span> <span data-ttu-id="71a39-106">Si el valor de la `GenerateMember` propiedad es `false`, el valor de la `Modifiers` propiedad no tiene ningún efecto.</span><span class="sxs-lookup"><span data-stu-id="71a39-106">If the value of the `GenerateMember` property is `false`, the value of the `Modifiers` property has no effect.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="71a39-107">Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos.</span><span class="sxs-lookup"><span data-stu-id="71a39-107">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="71a39-108">Para cambiar la configuración, elija la opción **Importar y exportar configuraciones** del menú **Herramientas** .</span><span class="sxs-lookup"><span data-stu-id="71a39-108">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="71a39-109">Para más información, vea [Personalizar el IDE de Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).</span><span class="sxs-lookup"><span data-stu-id="71a39-109">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-specify-whether-a-component-is-a-member-of-the-form"></a><span data-ttu-id="71a39-110">Para especificar si un componente es un miembro del formulario</span><span class="sxs-lookup"><span data-stu-id="71a39-110">To specify whether a component is a member of the form</span></span>  
  
1.  <span data-ttu-id="71a39-111">En el Diseñador de formularios de Windows, abra el formulario.</span><span class="sxs-lookup"><span data-stu-id="71a39-111">In the Windows Forms Designer, open your form.</span></span>  
  
2.  <span data-ttu-id="71a39-112">Abra el **cuadro de herramientas**y en el formulario, coloque tres <xref:System.Windows.Forms.Button> controles.</span><span class="sxs-lookup"><span data-stu-id="71a39-112">Open the **Toolbox**, and on the form, place three <xref:System.Windows.Forms.Button> controls.</span></span>  
  
3.  <span data-ttu-id="71a39-113">Establecer el `GenerateMember` y `Modifiers` propiedades para cada <xref:System.Windows.Forms.Button> control según la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="71a39-113">Set the `GenerateMember` and `Modifiers` properties for each <xref:System.Windows.Forms.Button> control according to the following table.</span></span>  
  
    |<span data-ttu-id="71a39-114">Nombre del botón</span><span class="sxs-lookup"><span data-stu-id="71a39-114">Button name</span></span>|<span data-ttu-id="71a39-115">Valor de GenerateMember</span><span class="sxs-lookup"><span data-stu-id="71a39-115">GenerateMember value</span></span>|<span data-ttu-id="71a39-116">Valor de modificadores</span><span class="sxs-lookup"><span data-stu-id="71a39-116">Modifiers value</span></span>|  
    |-----------------|--------------------------|---------------------|  
    |`button1`|`true`|`private`|  
    |`button2`|`true`|`protected`|  
    |`button3`|`false`|<span data-ttu-id="71a39-117">Sin cambios</span><span class="sxs-lookup"><span data-stu-id="71a39-117">No change</span></span>|  
  
4.  <span data-ttu-id="71a39-118">Compile la solución.</span><span class="sxs-lookup"><span data-stu-id="71a39-118">Build the solution.</span></span>  
  
5.  <span data-ttu-id="71a39-119">En el **Explorador de soluciones**, haga clic en el botón **Mostrar todos los archivos**.</span><span class="sxs-lookup"><span data-stu-id="71a39-119">In **Solution Explorer**, click the **Show All Files** button.</span></span>  
  
6.  <span data-ttu-id="71a39-120">Abra el **Form1** nodo y en el **Editor de código**, abra el **Form1.Designer.vb** o **Form1.Designer.cs** archivo.</span><span class="sxs-lookup"><span data-stu-id="71a39-120">Open the **Form1** node, and in the **Code Editor**,open the **Form1.Designer.vb** or **Form1.Designer.cs** file.</span></span> <span data-ttu-id="71a39-121">Este archivo contiene el código emitido por el Diseñador de formularios de Windows.</span><span class="sxs-lookup"><span data-stu-id="71a39-121">This file contains the code emitted by the Windows Forms Designer.</span></span>  
  
7.  <span data-ttu-id="71a39-122">Busque las declaraciones de los tres botones.</span><span class="sxs-lookup"><span data-stu-id="71a39-122">Find the declarations for the three buttons.</span></span> <span data-ttu-id="71a39-123">El ejemplo de código siguiente muestra las diferencias especificadas por el `GenerateMember` y `Modifiers` propiedades.</span><span class="sxs-lookup"><span data-stu-id="71a39-123">The following code example shows the differences specified by the `GenerateMember` and `Modifiers` properties.</span></span>  
  
     [!code-csharp[System.Windows.Forms.GenerateMember#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.GenerateMember/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.GenerateMember#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.GenerateMember/VB/Form1.vb#3)]  
  
     [!code-csharp[System.Windows.Forms.GenerateMember#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.GenerateMember/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.GenerateMember#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.GenerateMember/VB/Form1.vb#2)]  
  
> [!NOTE]
>  <span data-ttu-id="71a39-124">De forma predeterminada, el Diseñador de formularios de Windows asigna el `private` (`Friend` en Visual Basic) a los controles de contenedor como modificador de <xref:System.Windows.Forms.Panel>.</span><span class="sxs-lookup"><span data-stu-id="71a39-124">By default, the Windows Forms Designer assigns the `private` (`Friend` in Visual Basic) modifier to container controls like <xref:System.Windows.Forms.Panel>.</span></span> <span data-ttu-id="71a39-125">Si la base de <xref:System.Windows.Forms.UserControl> o <xref:System.Windows.Forms.Form> tiene un control contenedor, no se aceptarán nuevos objetos secundarios en controles y formularios heredados.</span><span class="sxs-lookup"><span data-stu-id="71a39-125">If your base <xref:System.Windows.Forms.UserControl> or <xref:System.Windows.Forms.Form> has a container control, it will not accept new children in inherited controls and forms.</span></span> <span data-ttu-id="71a39-126">La solución es cambiar el modificador del control contenedor base para `protected` o `public`.</span><span class="sxs-lookup"><span data-stu-id="71a39-126">The solution is to change the modifier of the base container control to `protected` or `public`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="71a39-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="71a39-127">See also</span></span>

- <xref:System.Windows.Forms.Button>
- [<span data-ttu-id="71a39-128">Herencia visual de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="71a39-128">Windows Forms Visual Inheritance</span></span>](windows-forms-visual-inheritance.md)
- [<span data-ttu-id="71a39-129">Tutorial: Demostración de la herencia visual</span><span class="sxs-lookup"><span data-stu-id="71a39-129">Walkthrough: Demonstrating Visual Inheritance</span></span>](walkthrough-demonstrating-visual-inheritance.md)
- [<span data-ttu-id="71a39-130">Filtrar para heredar formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="71a39-130">How to: Inherit Windows Forms</span></span>](how-to-inherit-windows-forms.md)
