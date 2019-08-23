---
title: Información general sobre StatusBar (Control, formularios Windows Forms)
ms.date: 03/30/2017
f1_keywords:
- StatusBar
helpviewer_keywords:
- StatusBar control [Windows Forms], about StatusBar control
- status bars
ms.assetid: b7b9852c-633d-4416-bb2e-94852b989c6c
ms.openlocfilehash: bd58d4c70e3a3c88e57fe242957f669d1944fd71
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69964435"
---
# <a name="statusbar-control-overview-windows-forms"></a><span data-ttu-id="be320-102">Información general sobre StatusBar (Control, formularios Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="be320-102">StatusBar Control Overview (Windows Forms)</span></span>
> [!IMPORTANT]
> <span data-ttu-id="be320-103">Los <xref:System.Windows.Forms.StatusStrip> controles <xref:System.Windows.Forms.ToolStripStatusLabel> y reemplazan y agregan funcionalidad <xref:System.Windows.Forms.StatusBar> a <xref:System.Windows.Forms.StatusBarPanel> los controles y; sin <xref:System.Windows.Forms.StatusBar> embargo <xref:System.Windows.Forms.StatusBarPanel> , los controles y se conservan por compatibilidad con versiones anteriores y uso futuro, si Elija.</span><span class="sxs-lookup"><span data-stu-id="be320-103">The <xref:System.Windows.Forms.StatusStrip> and <xref:System.Windows.Forms.ToolStripStatusLabel> controls replace and add functionality to the <xref:System.Windows.Forms.StatusBar> and <xref:System.Windows.Forms.StatusBarPanel> controls; however, the <xref:System.Windows.Forms.StatusBar> and <xref:System.Windows.Forms.StatusBarPanel> controls are retained for both backward compatibility and future use, if you choose.</span></span>  
  
 <span data-ttu-id="be320-104">El Windows Forms [control StatusBar](statusbar-control-windows-forms.md) se usa en los formularios como un área, que normalmente se muestra en la parte inferior de una ventana, en la que una aplicación puede mostrar diversos tipos de información de estado.</span><span class="sxs-lookup"><span data-stu-id="be320-104">The Windows Forms [StatusBar Control](statusbar-control-windows-forms.md) is used on forms as an area, usually displayed at the bottom of a window, in which an application can display various kinds of status information.</span></span> <span data-ttu-id="be320-105"><xref:System.Windows.Forms.StatusBar>los controles pueden tener paneles de barra de estado en los que se muestre texto o iconos para indicar el estado o una serie de iconos de una animación que indiquen que un proceso está funcionando; por ejemplo, Microsoft Word indica que el documento se está guardando.</span><span class="sxs-lookup"><span data-stu-id="be320-105"><xref:System.Windows.Forms.StatusBar> controls can have status bar panels on them that display text or icons to indicate state, or a series of icons in an animation that indicate a process is working; for example, Microsoft Word indicating that the document is being saved.</span></span>  
  
## <a name="using-the-statusbar-control"></a><span data-ttu-id="be320-106">Usar el control StatusBar</span><span class="sxs-lookup"><span data-stu-id="be320-106">Using the StatusBar Control</span></span>  
 <span data-ttu-id="be320-107">Internet Explorer usa una barra de estado para indicar la dirección URL de una página cuando el mouse se sitúa sobre el hipervínculo; Microsoft Word le proporciona información sobre la ubicación de la página, la ubicación de la sección y los modos de edición como sobreescribir y seguimiento de la revisión. y Visual Studio usa la barra de estado para proporcionar información contextual, como indicar cómo manipular las ventanas acoplables como acopladas o flotantes.</span><span class="sxs-lookup"><span data-stu-id="be320-107">Internet Explorer uses a status bar to indicate the URL of a page when the mouse rolls over the hyperlink; Microsoft Word gives you information on page location, section location, and editing modes such as overtype and revision tracking; and Visual Studio uses the status bar to give context-sensitive information, such as telling you how to manipulate dockable windows as either docked or floating.</span></span>  
  
 <span data-ttu-id="be320-108">Puede mostrar un solo mensaje en la barra de estado si establece la <xref:System.Windows.Forms.StatusBar.ShowPanels%2A> propiedad en `false` (valor predeterminado) y establece la <xref:System.Windows.Forms.StatusBar.Text%2A> propiedad de la barra de estado en el texto que desea que aparezca en la barra de estado.</span><span class="sxs-lookup"><span data-stu-id="be320-108">You can display a single message on the status bar by setting the <xref:System.Windows.Forms.StatusBar.ShowPanels%2A> property to `false` (the default) and setting the <xref:System.Windows.Forms.StatusBar.Text%2A> property of the status bar to the text you want to appear in the status bar.</span></span> <span data-ttu-id="be320-109">Puede dividir la barra de estado en paneles para mostrar más de un tipo de <xref:System.Windows.Forms.StatusBar.ShowPanels%2A> información estableciendo la propiedad en `true` y usando el <xref:System.Windows.Forms.StatusBar.StatusBarPanelCollection.Add%2A> método de <xref:System.Windows.Forms.StatusBar.StatusBarPanelCollection>.</span><span class="sxs-lookup"><span data-stu-id="be320-109">You can divide the status bar into panels to display more than one type of information by setting the <xref:System.Windows.Forms.StatusBar.ShowPanels%2A> property to `true` and using the <xref:System.Windows.Forms.StatusBar.StatusBarPanelCollection.Add%2A> method of <xref:System.Windows.Forms.StatusBar.StatusBarPanelCollection>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="be320-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="be320-110">See also</span></span>

- <xref:System.Windows.Forms.StatusBar>
- <xref:System.Windows.Forms.ToolStripStatusLabel>
- [<span data-ttu-id="be320-111">Cómo: Determinar en qué panel del control Windows Forms StatusBar se hizo clic</span><span class="sxs-lookup"><span data-stu-id="be320-111">How to: Determine Which Panel in the Windows Forms StatusBar Control Was Clicked</span></span>](determine-which-panel-wf-statusbar-control-was-clicked.md)
