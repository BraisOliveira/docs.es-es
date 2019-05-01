---
title: 'Tutoriales: Crear un botón animado personalizado'
ms.date: 03/30/2017
helpviewer_keywords:
- custom animated buttons [WPF]
- buttons [WPF]
- animation [WPF], buttons [WPF]
ms.assetid: e9532c72-460f-4898-9332-613fa21d746a
ms.openlocfilehash: 3c601641a0eb1024722b4f449f0ab23e54fe93dd
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62024474"
---
# <a name="walkthroughs-create-a-custom-animated-button"></a><span data-ttu-id="ef2b9-102">Tutoriales: Crear un botón animado personalizado</span><span class="sxs-lookup"><span data-stu-id="ef2b9-102">Walkthroughs: Create a Custom Animated Button</span></span>
<span data-ttu-id="ef2b9-103">Como sugiere su nombre, Windows Presentation Foundation (WPF) es magnífico para crear experiencias de presentación rico para los clientes.</span><span class="sxs-lookup"><span data-stu-id="ef2b9-103">As its name suggests, Windows Presentation Foundation (WPF) is great for making rich presentation experiences for customers.</span></span> <span data-ttu-id="ef2b9-104">Estos tutoriales muestra cómo personalizar la apariencia y comportamiento de un botón (incluyendo animaciones).</span><span class="sxs-lookup"><span data-stu-id="ef2b9-104">These walkthroughs show you how to customize the look and behavior of a button (including animations).</span></span> <span data-ttu-id="ef2b9-105">Esta personalización se realiza mediante un estilo y una plantilla para que pueda aplicar fácilmente este botón personalizado a los botones en la aplicación.</span><span class="sxs-lookup"><span data-stu-id="ef2b9-105">This customization is done using a style and template so that you can apply this custom button easily to any buttons in your application.</span></span> <span data-ttu-id="ef2b9-106">La siguiente ilustración muestra el botón personalizado que va a crear.</span><span class="sxs-lookup"><span data-stu-id="ef2b9-106">The following illustration shows the customized button that you will create.</span></span>  
  
 <span data-ttu-id="ef2b9-107">![Botón personalizado que va a crear](./media/custom-button-blend-intro.jpg "custom_button_blend_Intro")</span><span class="sxs-lookup"><span data-stu-id="ef2b9-107">![The customized button that you will create](./media/custom-button-blend-intro.jpg "custom_button_blend_Intro")</span></span>  
  
 <span data-ttu-id="ef2b9-108">Los gráficos vectoriales que constituyen la apariencia del botón se crean mediante [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ef2b9-108">The vector graphics that make up the appearance of the button are created by using [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].</span></span> [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] <span data-ttu-id="ef2b9-109">es similar a HTML, salvo que es más eficaz y extensible.</span><span class="sxs-lookup"><span data-stu-id="ef2b9-109">is similar to HTML except it is more powerful and extensible.</span></span> [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] <span data-ttu-id="ef2b9-110">se pueden escribir en forma manual mediante Microsoft Visual Studio o el Bloc de notas, o puede usar una herramienta de diseño visual como Microsoft Expression Blend.</span><span class="sxs-lookup"><span data-stu-id="ef2b9-110">can be typed in manually using Microsoft Visual Studio or Notepad, or you can use a visual design tool such as Microsoft Expression Blend.</span></span> <span data-ttu-id="ef2b9-111">Expression Blend funciona creando subyacente [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] de código, por lo que ambos métodos crean los mismos gráficos.</span><span class="sxs-lookup"><span data-stu-id="ef2b9-111">Expression Blend works by creating underlying [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] code, so both methods create the same graphics.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="ef2b9-112">En esta sección</span><span class="sxs-lookup"><span data-stu-id="ef2b9-112">In This Section</span></span>  
 [<span data-ttu-id="ef2b9-113">Crear un botón mediante Microsoft Expression Blend</span><span class="sxs-lookup"><span data-stu-id="ef2b9-113">Create a Button by Using Microsoft Expression Blend</span></span>](walkthrough-create-a-button-by-using-microsoft-expression-blend.md)  
 <span data-ttu-id="ef2b9-114">Muestra cómo crear botones con comportamiento personalizado mediante las características del Diseñador de Expression Blend.</span><span class="sxs-lookup"><span data-stu-id="ef2b9-114">Demonstrates how to create buttons with custom behavior by using the designer features of Expression Blend.</span></span>  
  
 [<span data-ttu-id="ef2b9-115">Crear un botón mediante el uso de XAML</span><span class="sxs-lookup"><span data-stu-id="ef2b9-115">Create a Button by Using XAML</span></span>](walkthrough-create-a-button-by-using-xaml.md)  
 <span data-ttu-id="ef2b9-116">Muestra cómo crear botones con comportamiento personalizado mediante [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] y Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="ef2b9-116">Demonstrates how to create buttons with custom behavior by using [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] and Visual Studio.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="ef2b9-117">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="ef2b9-117">Related Sections</span></span>  
 [<span data-ttu-id="ef2b9-118">Aplicar estilos y plantillas</span><span class="sxs-lookup"><span data-stu-id="ef2b9-118">Styling and Templating</span></span>](styling-and-templating.md)  
 <span data-ttu-id="ef2b9-119">Describe cómo se pueden utilizar los estilos y plantillas para determinar la apariencia y comportamiento de los controles.</span><span class="sxs-lookup"><span data-stu-id="ef2b9-119">Describes how styles and templates can be used to determine the appearance and behavior of controls.</span></span>  
  
 [<span data-ttu-id="ef2b9-120">Información general sobre animaciones</span><span class="sxs-lookup"><span data-stu-id="ef2b9-120">Animation Overview</span></span>](../graphics-multimedia/animation-overview.md)  
 <span data-ttu-id="ef2b9-121">Describe cómo se pueden animar objetos mediante el uso de la [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] sistema de temporización y animación.</span><span class="sxs-lookup"><span data-stu-id="ef2b9-121">Describes how objects can be animated by using the [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] animation and timing system.</span></span>  
  
 [<span data-ttu-id="ef2b9-122">Información general sobre el dibujo con colores sólidos y degradados</span><span class="sxs-lookup"><span data-stu-id="ef2b9-122">Painting with Solid Colors and Gradients Overview</span></span>](../graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md)  
 <span data-ttu-id="ef2b9-123">Describe cómo utilizar objetos de pincel para pintar con colores sólidos, degradados lineales y degradados radiales.</span><span class="sxs-lookup"><span data-stu-id="ef2b9-123">Describes how to use brush objects to paint with solid colors, linear gradients, and radial gradients.</span></span>  
  
 [<span data-ttu-id="ef2b9-124">Información general sobre efectos de imagen</span><span class="sxs-lookup"><span data-stu-id="ef2b9-124">Bitmap Effects Overview</span></span>](../graphics-multimedia/bitmap-effects-overview.md)  
 <span data-ttu-id="ef2b9-125">Describe los efectos de imagen compatibles con [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] y explica cómo aplicarlos.</span><span class="sxs-lookup"><span data-stu-id="ef2b9-125">Describes the bitmap effects supported by [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] and explains how to apply them.</span></span>
