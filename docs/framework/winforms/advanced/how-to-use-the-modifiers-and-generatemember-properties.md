---
title: Procedimiento para usar las propiedades Modifiers y GenerateMember
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
ms.openlocfilehash: 3fbaaae53aa60f6356c3a8daa0513de86ef2dacb
ms.sourcegitcommit: 0d0a6e96737dfe24d3257b7c94f25d9500f383ea
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2019
ms.locfileid: "65211299"
---
# <a name="how-to-use-the-modifiers-and-generatemember-properties"></a><span data-ttu-id="4641c-102">Procedimiento para usar las propiedades Modifiers y GenerateMember</span><span class="sxs-lookup"><span data-stu-id="4641c-102">How to: Use the Modifiers and GenerateMember Properties</span></span>

<span data-ttu-id="4641c-103">Cuando se coloca un componente en un formulario de Windows, el entorno de diseño proporciona dos propiedades: `GenerateMember` y `Modifiers`.</span><span class="sxs-lookup"><span data-stu-id="4641c-103">When you place a component on a Windows Form, two properties are provided by the design environment: `GenerateMember` and `Modifiers`.</span></span> <span data-ttu-id="4641c-104">El `GenerateMember` propiedad especifica que cuando el Diseñador de Windows Forms genera una variable miembro para un componente.</span><span class="sxs-lookup"><span data-stu-id="4641c-104">The `GenerateMember` property specifies when the Windows Forms Designer generates a member variable for a component.</span></span> <span data-ttu-id="4641c-105">El `Modifiers` propiedad es el modificador de acceso asignado a esa variable de miembro.</span><span class="sxs-lookup"><span data-stu-id="4641c-105">The `Modifiers` property is the access modifier assigned to that member variable.</span></span> <span data-ttu-id="4641c-106">Si el valor de la `GenerateMember` propiedad es `false`, el valor de la `Modifiers` propiedad no tiene ningún efecto.</span><span class="sxs-lookup"><span data-stu-id="4641c-106">If the value of the `GenerateMember` property is `false`, the value of the `Modifiers` property has no effect.</span></span>

## <a name="specify-whether-a-component-is-a-member-of-the-form"></a><span data-ttu-id="4641c-107">Especificar si un componente es un miembro del formulario</span><span class="sxs-lookup"><span data-stu-id="4641c-107">Specify whether a component is a member of the form</span></span>

1. <span data-ttu-id="4641c-108">En Visual Studio, en el Diseñador de formularios de Windows, abra el formulario.</span><span class="sxs-lookup"><span data-stu-id="4641c-108">In Visual Studio, in the Windows Forms Designer, open your form.</span></span>

2. <span data-ttu-id="4641c-109">Abra el **cuadro de herramientas**y en el formulario, coloque tres <xref:System.Windows.Forms.Button> controles.</span><span class="sxs-lookup"><span data-stu-id="4641c-109">Open the **Toolbox**, and on the form, place three <xref:System.Windows.Forms.Button> controls.</span></span>

3. <span data-ttu-id="4641c-110">Establecer el `GenerateMember` y `Modifiers` propiedades para cada <xref:System.Windows.Forms.Button> control según la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="4641c-110">Set the `GenerateMember` and `Modifiers` properties for each <xref:System.Windows.Forms.Button> control according to the following table.</span></span>

    |<span data-ttu-id="4641c-111">Nombre del botón</span><span class="sxs-lookup"><span data-stu-id="4641c-111">Button name</span></span>|<span data-ttu-id="4641c-112">Valor de GenerateMember</span><span class="sxs-lookup"><span data-stu-id="4641c-112">GenerateMember value</span></span>|<span data-ttu-id="4641c-113">Valor de modificadores</span><span class="sxs-lookup"><span data-stu-id="4641c-113">Modifiers value</span></span>|
    |-----------------|--------------------------|---------------------|
    |`button1`|`true`|`private`|
    |`button2`|`true`|`protected`|
    |`button3`|`false`|<span data-ttu-id="4641c-114">Sin cambios</span><span class="sxs-lookup"><span data-stu-id="4641c-114">No change</span></span>|

4. <span data-ttu-id="4641c-115">Compile la solución.</span><span class="sxs-lookup"><span data-stu-id="4641c-115">Build the solution.</span></span>

5. <span data-ttu-id="4641c-116">En el **Explorador de soluciones**, haga clic en el botón **Mostrar todos los archivos**.</span><span class="sxs-lookup"><span data-stu-id="4641c-116">In **Solution Explorer**, click the **Show All Files** button.</span></span>

6. <span data-ttu-id="4641c-117">Abra el **Form1** nodo y en el **Editor de código**, abra el **Form1.Designer.vb** o **Form1.Designer.cs** archivo.</span><span class="sxs-lookup"><span data-stu-id="4641c-117">Open the **Form1** node, and in the **Code Editor**,open the **Form1.Designer.vb** or **Form1.Designer.cs** file.</span></span> <span data-ttu-id="4641c-118">Este archivo contiene el código emitido por el Diseñador de formularios de Windows.</span><span class="sxs-lookup"><span data-stu-id="4641c-118">This file contains the code emitted by the Windows Forms Designer.</span></span>

7. <span data-ttu-id="4641c-119">Busque las declaraciones de los tres botones.</span><span class="sxs-lookup"><span data-stu-id="4641c-119">Find the declarations for the three buttons.</span></span> <span data-ttu-id="4641c-120">El ejemplo de código siguiente muestra las diferencias especificadas por el `GenerateMember` y `Modifiers` propiedades.</span><span class="sxs-lookup"><span data-stu-id="4641c-120">The following code example shows the differences specified by the `GenerateMember` and `Modifiers` properties.</span></span>

     [!code-csharp[System.Windows.Forms.GenerateMember#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.GenerateMember/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.GenerateMember#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.GenerateMember/VB/Form1.vb#3)]

     [!code-csharp[System.Windows.Forms.GenerateMember#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.GenerateMember/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.GenerateMember#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.GenerateMember/VB/Form1.vb#2)]

> [!NOTE]
> <span data-ttu-id="4641c-121">De forma predeterminada, el Diseñador de formularios de Windows asigna el `private` (`Friend` en Visual Basic) a los controles de contenedor como modificador de <xref:System.Windows.Forms.Panel>.</span><span class="sxs-lookup"><span data-stu-id="4641c-121">By default, the Windows Forms Designer assigns the `private` (`Friend` in Visual Basic) modifier to container controls like <xref:System.Windows.Forms.Panel>.</span></span> <span data-ttu-id="4641c-122">Si la base de <xref:System.Windows.Forms.UserControl> o <xref:System.Windows.Forms.Form> tiene un control contenedor, no se aceptarán nuevos objetos secundarios en controles y formularios heredados.</span><span class="sxs-lookup"><span data-stu-id="4641c-122">If your base <xref:System.Windows.Forms.UserControl> or <xref:System.Windows.Forms.Form> has a container control, it will not accept new children in inherited controls and forms.</span></span> <span data-ttu-id="4641c-123">La solución es cambiar el modificador del control contenedor base para `protected` o `public`.</span><span class="sxs-lookup"><span data-stu-id="4641c-123">The solution is to change the modifier of the base container control to `protected` or `public`.</span></span>

## <a name="see-also"></a><span data-ttu-id="4641c-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="4641c-124">See also</span></span>

- <xref:System.Windows.Forms.Button>
- [<span data-ttu-id="4641c-125">Herencia visual de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="4641c-125">Windows Forms Visual Inheritance</span></span>](windows-forms-visual-inheritance.md)
- [<span data-ttu-id="4641c-126">Tutorial: Demostración de la herencia Visual</span><span class="sxs-lookup"><span data-stu-id="4641c-126">Walkthrough: Demonstrating Visual Inheritance</span></span>](walkthrough-demonstrating-visual-inheritance.md)
- [<span data-ttu-id="4641c-127">Cómo: Heredar Windows Forms</span><span class="sxs-lookup"><span data-stu-id="4641c-127">How to: Inherit Windows Forms</span></span>](how-to-inherit-windows-forms.md)
