---
title: Propiedades de los controles de formularios Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- custom controls [Windows Forms], properties overview (using code)
- controls [Windows Forms], properties
- properties [Windows Forms]
ms.assetid: 2785279b-fb57-4937-8f6b-2050e475db6f
ms.openlocfilehash: e531b80cffabb94d2589383936a425b740c9cc07
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2019
ms.locfileid: "57708917"
---
# <a name="properties-in-windows-forms-controls"></a><span data-ttu-id="c9c66-102">Propiedades de los controles de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="c9c66-102">Properties in Windows Forms Controls</span></span>
<span data-ttu-id="c9c66-103">Un control de Windows Forms hereda muchas formulario de propiedades de la clase base <xref:System.Windows.Forms.Control?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="c9c66-103">A Windows Forms control inherits many properties form the base class <xref:System.Windows.Forms.Control?displayProperty=nameWithType>.</span></span> <span data-ttu-id="c9c66-104">Estos incluyen propiedades como <xref:System.Windows.Forms.Control.Font%2A>, <xref:System.Windows.Forms.Control.ForeColor%2A>, <xref:System.Windows.Forms.Control.BackColor%2A>, <xref:System.Windows.Forms.Control.Bounds%2A>, <xref:System.Windows.Forms.Control.ClientRectangle%2A>, <xref:System.Windows.Forms.Control.DisplayRectangle%2A>, <xref:System.Windows.Forms.Control.Enabled%2A>, <xref:System.Windows.Forms.Control.Focused%2A>, <xref:System.Windows.Forms.Control.Height%2A>, <xref:System.Windows.Forms.Control.Width%2A>, <xref:System.Windows.Forms.Control.Visible%2A>, <xref:System.Windows.Forms.Control.AutoSize%2A>y muchos otros.</span><span class="sxs-lookup"><span data-stu-id="c9c66-104">These include properties such as <xref:System.Windows.Forms.Control.Font%2A>, <xref:System.Windows.Forms.Control.ForeColor%2A>, <xref:System.Windows.Forms.Control.BackColor%2A>, <xref:System.Windows.Forms.Control.Bounds%2A>, <xref:System.Windows.Forms.Control.ClientRectangle%2A>, <xref:System.Windows.Forms.Control.DisplayRectangle%2A>, <xref:System.Windows.Forms.Control.Enabled%2A>, <xref:System.Windows.Forms.Control.Focused%2A>, <xref:System.Windows.Forms.Control.Height%2A>, <xref:System.Windows.Forms.Control.Width%2A>, <xref:System.Windows.Forms.Control.Visible%2A>, <xref:System.Windows.Forms.Control.AutoSize%2A>, and many others.</span></span> <span data-ttu-id="c9c66-105">Para obtener más información acerca de las propiedades heredadas, vea <xref:System.Windows.Forms.Control?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="c9c66-105">For details about inherited properties, see <xref:System.Windows.Forms.Control?displayProperty=nameWithType>.</span></span>  
  
 <span data-ttu-id="c9c66-106">Se pueden reemplazar las propiedades heredadas en un control, así como definir propiedades nuevas.</span><span class="sxs-lookup"><span data-stu-id="c9c66-106">You can override inherited properties in your control as well as define new properties.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c9c66-107">En esta sección</span><span class="sxs-lookup"><span data-stu-id="c9c66-107">In This Section</span></span>  
 [<span data-ttu-id="c9c66-108">Definir una propiedad</span><span class="sxs-lookup"><span data-stu-id="c9c66-108">Defining a Property</span></span>](defining-a-property-in-windows-forms-controls.md)  
 <span data-ttu-id="c9c66-109">Muestra cómo implementar una propiedad para un control o componente personalizado y cómo integrar la propiedad en el entorno de diseño.</span><span class="sxs-lookup"><span data-stu-id="c9c66-109">Shows how to implement a property for a custom control or component and shows how to integrate the property into the design environment.</span></span>  
  
 [<span data-ttu-id="c9c66-110">Definir valores predeterminados con los métodos ShouldSerialize y Reset</span><span class="sxs-lookup"><span data-stu-id="c9c66-110">Defining Default Values with the ShouldSerialize and Reset Methods</span></span>](defining-default-values-with-the-shouldserialize-and-reset-methods.md)  
 <span data-ttu-id="c9c66-111">Muestra cómo definir valores de propiedad predeterminados de un control o componente personalizado.</span><span class="sxs-lookup"><span data-stu-id="c9c66-111">Shows how to define default property values for a custom control or component.</span></span>  
  
 [<span data-ttu-id="c9c66-112">Eventos de cambio de propiedades</span><span class="sxs-lookup"><span data-stu-id="c9c66-112">Property-Changed Events</span></span>](property-changed-events.md)  
 <span data-ttu-id="c9c66-113">Describe cómo habilitar notificaciones de cambio de propiedad cuando cambia un valor de propiedad.</span><span class="sxs-lookup"><span data-stu-id="c9c66-113">Describes how to enable property-change notifications when a property value changes.</span></span>  
  
 [<span data-ttu-id="c9c66-114">Cómo: Exponer propiedades de controles constituyentes</span><span class="sxs-lookup"><span data-stu-id="c9c66-114">How to: Expose Properties of Constituent Controls</span></span>](how-to-expose-properties-of-constituent-controls.md)  
 <span data-ttu-id="c9c66-115">Muestra cómo exponer propiedades de controles constituyentes en un control compuesto personalizado.</span><span class="sxs-lookup"><span data-stu-id="c9c66-115">Shows how to expose properties of constituent controls in a custom composite control.</span></span>  
  
 [<span data-ttu-id="c9c66-116">Implementación de métodos en controles personalizados</span><span class="sxs-lookup"><span data-stu-id="c9c66-116">Method Implementation in Custom Controls</span></span>](method-implementation-in-custom-controls.md)  
 <span data-ttu-id="c9c66-117">Describe cómo implementar métodos en controles y componentes personalizados.</span><span class="sxs-lookup"><span data-stu-id="c9c66-117">Describes how to implement methods in custom controls and components.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="c9c66-118">Referencia</span><span class="sxs-lookup"><span data-stu-id="c9c66-118">Reference</span></span>  
 <xref:System.Windows.Forms.UserControl>  
 <span data-ttu-id="c9c66-119">Documenta la clase base para implementar controles compuestos.</span><span class="sxs-lookup"><span data-stu-id="c9c66-119">Documents the base class for implementing composite controls.</span></span>  
  
 <xref:System.ComponentModel.TypeConverterAttribute>  
 <span data-ttu-id="c9c66-120">Documenta el atributo que especifica el <xref:System.ComponentModel.TypeConverter> que se usará para un tipo de propiedad personalizada.</span><span class="sxs-lookup"><span data-stu-id="c9c66-120">Documents the attribute that specifies the <xref:System.ComponentModel.TypeConverter> to use for a custom property type.</span></span>  
  
 <xref:System.ComponentModel.EditorAttribute>  
 <span data-ttu-id="c9c66-121">Documenta el atributo que especifica el <xref:System.Drawing.Design.UITypeEditor> que se usará para una propiedad personalizada.</span><span class="sxs-lookup"><span data-stu-id="c9c66-121">Documents the attribute that specifies the <xref:System.Drawing.Design.UITypeEditor> to use for a custom property.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="c9c66-122">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="c9c66-122">Related Sections</span></span>  
 [<span data-ttu-id="c9c66-123">Atributos en controles de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="c9c66-123">Attributes in Windows Forms Controls</span></span>](attributes-in-windows-forms-controls.md)  
 <span data-ttu-id="c9c66-124">Describe los atributos que se puede aplicar a propiedades u otros miembros de los controles y componentes personalizados.</span><span class="sxs-lookup"><span data-stu-id="c9c66-124">Describes the attributes you can apply to properties or other members of your custom controls and components.</span></span>  
  
 <span data-ttu-id="c9c66-125">[Atributos en tiempo de diseño para componentes](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/tk67c2t8(v=vs.120))</span><span class="sxs-lookup"><span data-stu-id="c9c66-125">[Design-Time Attributes for Components](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/tk67c2t8(v=vs.120))</span></span>  
 <span data-ttu-id="c9c66-126">Enumera los atributos de metadatos que se deben aplicar a componentes y controles para que se muestren correctamente en tiempo de diseño en diseñadores visuales.</span><span class="sxs-lookup"><span data-stu-id="c9c66-126">Lists metadata attributes to apply to components and controls so that they are displayed correctly at design time in visual designers.</span></span>  
  
 <span data-ttu-id="c9c66-127">[Ampliar compatibilidad en tiempo de diseño](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/37899azc(v=vs.120))</span><span class="sxs-lookup"><span data-stu-id="c9c66-127">[Extending Design-Time Support](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/37899azc(v=vs.120))</span></span>  
 <span data-ttu-id="c9c66-128">Describe cómo implementar clases, como editores y diseñadores, que proporcionan compatibilidad en tiempo de diseño.</span><span class="sxs-lookup"><span data-stu-id="c9c66-128">Describes how to implement classes such as editors and designers that provide design-time support.</span></span>
