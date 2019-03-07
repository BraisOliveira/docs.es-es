---
title: PasswordBox estilos y plantillas
ms.date: 03/30/2017
helpviewer_keywords:
- styles [WPF], PasswordBox
- templates [WPF], PasswordBox
- ControlTemplate [WPF], PasswordBox
- states [WPF], PasswordBox
- PasswordBox [WPF], styles and templates
- parts [WPF], PasswordBox
ms.assetid: deb52107-959f-4a60-b303-d21a0a933060
ms.openlocfilehash: 7783330dd56ec5b2759e783a6935761eb3587978
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57509534"
---
# <a name="passwordbox-styles-and-templates"></a><span data-ttu-id="4e1ab-102">PasswordBox estilos y plantillas</span><span class="sxs-lookup"><span data-stu-id="4e1ab-102">PasswordBox Styles and Templates</span></span>

<span data-ttu-id="4e1ab-103">En este tema se describe los estilos y plantillas para el <xref:System.Windows.Controls.PasswordBox> control.</span><span class="sxs-lookup"><span data-stu-id="4e1ab-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.PasswordBox> control.</span></span> <span data-ttu-id="4e1ab-104">Puede modificar el valor predeterminado <xref:System.Windows.Controls.ControlTemplate> para proporcionar el control una apariencia única.</span><span class="sxs-lookup"><span data-stu-id="4e1ab-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="4e1ab-105">Para más información, consulte [Personalización de la apariencia de un control existente mediante la creación de una clase ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span><span class="sxs-lookup"><span data-stu-id="4e1ab-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span></span>

## <a name="passwordbox-parts"></a><span data-ttu-id="4e1ab-106">Partes de PasswordBox</span><span class="sxs-lookup"><span data-stu-id="4e1ab-106">PasswordBox Parts</span></span>

<span data-ttu-id="4e1ab-107">En la tabla siguiente se enumera los elementos con nombre para el <xref:System.Windows.Controls.PasswordBox> control.</span><span class="sxs-lookup"><span data-stu-id="4e1ab-107">The following table lists the named parts for the <xref:System.Windows.Controls.PasswordBox> control.</span></span>

|<span data-ttu-id="4e1ab-108">Parte</span><span class="sxs-lookup"><span data-stu-id="4e1ab-108">Part</span></span>|<span data-ttu-id="4e1ab-109">Tipo</span><span class="sxs-lookup"><span data-stu-id="4e1ab-109">Type</span></span>|<span data-ttu-id="4e1ab-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="4e1ab-110">Description</span></span>|
|-|-|-|
|<span data-ttu-id="4e1ab-111">PART_ContentHost</span><span class="sxs-lookup"><span data-stu-id="4e1ab-111">PART_ContentHost</span></span>|<xref:System.Windows.FrameworkElement>|<span data-ttu-id="4e1ab-112">Un elemento visual que puede contener un <xref:System.Windows.FrameworkElement>.</span><span class="sxs-lookup"><span data-stu-id="4e1ab-112">A visual element that can contain a <xref:System.Windows.FrameworkElement>.</span></span> <span data-ttu-id="4e1ab-113">El texto de la <xref:System.Windows.Controls.PasswordBox> se muestra en este elemento.</span><span class="sxs-lookup"><span data-stu-id="4e1ab-113">The text of the <xref:System.Windows.Controls.PasswordBox> is displayed in this element.</span></span>|

## <a name="passwordbox-states"></a><span data-ttu-id="4e1ab-114">Estados de PasswordBox</span><span class="sxs-lookup"><span data-stu-id="4e1ab-114">PasswordBox States</span></span>

<span data-ttu-id="4e1ab-115">En la tabla siguiente se enumera los estados visuales para el <xref:System.Windows.Controls.PasswordBox> control.</span><span class="sxs-lookup"><span data-stu-id="4e1ab-115">The following table lists the visual states for the <xref:System.Windows.Controls.PasswordBox> control.</span></span>

|<span data-ttu-id="4e1ab-116">Nombre de VisualState</span><span class="sxs-lookup"><span data-stu-id="4e1ab-116">VisualState Name</span></span>|<span data-ttu-id="4e1ab-117">Nombre de VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="4e1ab-117">VisualStateGroup Name</span></span>|<span data-ttu-id="4e1ab-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="4e1ab-118">Description</span></span>|
|-|-|-|
|<span data-ttu-id="4e1ab-119">Normal</span><span class="sxs-lookup"><span data-stu-id="4e1ab-119">Normal</span></span>|<span data-ttu-id="4e1ab-120">CommonStates</span><span class="sxs-lookup"><span data-stu-id="4e1ab-120">CommonStates</span></span>|<span data-ttu-id="4e1ab-121">El estado predeterminado.</span><span class="sxs-lookup"><span data-stu-id="4e1ab-121">The default state.</span></span>|
|<span data-ttu-id="4e1ab-122">MouseOver</span><span class="sxs-lookup"><span data-stu-id="4e1ab-122">MouseOver</span></span>|<span data-ttu-id="4e1ab-123">CommonStates</span><span class="sxs-lookup"><span data-stu-id="4e1ab-123">CommonStates</span></span>|<span data-ttu-id="4e1ab-124">El puntero del mouse se coloca sobre el control.</span><span class="sxs-lookup"><span data-stu-id="4e1ab-124">The mouse pointer is positioned over the control.</span></span>|
|<span data-ttu-id="4e1ab-125">Deshabilitado</span><span class="sxs-lookup"><span data-stu-id="4e1ab-125">Disabled</span></span>|<span data-ttu-id="4e1ab-126">CommonStates</span><span class="sxs-lookup"><span data-stu-id="4e1ab-126">CommonStates</span></span>|<span data-ttu-id="4e1ab-127">El control está deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="4e1ab-127">The control is disabled.</span></span>|
|<span data-ttu-id="4e1ab-128">Con foco</span><span class="sxs-lookup"><span data-stu-id="4e1ab-128">Focused</span></span>|<span data-ttu-id="4e1ab-129">FocusStates</span><span class="sxs-lookup"><span data-stu-id="4e1ab-129">FocusStates</span></span>|<span data-ttu-id="4e1ab-130">El control tiene el foco.</span><span class="sxs-lookup"><span data-stu-id="4e1ab-130">The control has focus.</span></span>|
|<span data-ttu-id="4e1ab-131">Sin foco</span><span class="sxs-lookup"><span data-stu-id="4e1ab-131">Unfocused</span></span>|<span data-ttu-id="4e1ab-132">FocusStates</span><span class="sxs-lookup"><span data-stu-id="4e1ab-132">FocusStates</span></span>|<span data-ttu-id="4e1ab-133">El control no tiene el foco.</span><span class="sxs-lookup"><span data-stu-id="4e1ab-133">The control does not have focus.</span></span>|
|<span data-ttu-id="4e1ab-134">Válido</span><span class="sxs-lookup"><span data-stu-id="4e1ab-134">Valid</span></span>|<span data-ttu-id="4e1ab-135">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="4e1ab-135">ValidationStates</span></span>|<span data-ttu-id="4e1ab-136">El control utiliza el <xref:System.Windows.Controls.Validation> clase y el <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> propiedad adjunta es `false`.</span><span class="sxs-lookup"><span data-stu-id="4e1ab-136">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|
|<span data-ttu-id="4e1ab-137">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="4e1ab-137">InvalidFocused</span></span>|<span data-ttu-id="4e1ab-138">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="4e1ab-138">ValidationStates</span></span>|<span data-ttu-id="4e1ab-139">El <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> propiedad adjunta es `true` tiene el control tiene el foco.</span><span class="sxs-lookup"><span data-stu-id="4e1ab-139">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|
|<span data-ttu-id="4e1ab-140">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="4e1ab-140">InvalidUnfocused</span></span>|<span data-ttu-id="4e1ab-141">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="4e1ab-141">ValidationStates</span></span>|<span data-ttu-id="4e1ab-142">El <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> propiedad adjunta es `true` tiene el control no tiene el foco.</span><span class="sxs-lookup"><span data-stu-id="4e1ab-142">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|

## <a name="passwordbox-controltemplate-example"></a><span data-ttu-id="4e1ab-143">Ejemplo de ControlTemplate de PasswordBox</span><span class="sxs-lookup"><span data-stu-id="4e1ab-143">PasswordBox ControlTemplate Example</span></span>

<span data-ttu-id="4e1ab-144">El ejemplo siguiente muestra cómo definir un <xref:System.Windows.Controls.ControlTemplate> para el <xref:System.Windows.Controls.PasswordBox> control.</span><span class="sxs-lookup"><span data-stu-id="4e1ab-144">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.PasswordBox> control.</span></span>

[!code-xaml[ControlTemplateExamples#PasswordBox](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/textbox.xaml#passwordbox)]

<span data-ttu-id="4e1ab-145">En el ejemplo anterior se usa uno o varios de los recursos siguientes.</span><span class="sxs-lookup"><span data-stu-id="4e1ab-145">The preceding example uses one or more of the following resources.</span></span>

[!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]

<span data-ttu-id="4e1ab-146">Para ver un ejemplo completo, consulte [Aplicación de estilos con el ejemplo ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span><span class="sxs-lookup"><span data-stu-id="4e1ab-146">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>

## <a name="see-also"></a><span data-ttu-id="4e1ab-147">Vea también</span><span class="sxs-lookup"><span data-stu-id="4e1ab-147">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="4e1ab-148">Estilos y plantillas de controles</span><span class="sxs-lookup"><span data-stu-id="4e1ab-148">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- <span data-ttu-id="4e1ab-149">[Control Customization](control-customization.md) (Personalización de controles)</span><span class="sxs-lookup"><span data-stu-id="4e1ab-149">[Control Customization](control-customization.md)</span></span>
- [<span data-ttu-id="4e1ab-150">Aplicar estilos y plantillas</span><span class="sxs-lookup"><span data-stu-id="4e1ab-150">Styling and Templating</span></span>](styling-and-templating.md)
- [<span data-ttu-id="4e1ab-151">Personalización de la apariencia de un control existente mediante la creación de una clase ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="4e1ab-151">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](customizing-the-appearance-of-an-existing-control.md)
