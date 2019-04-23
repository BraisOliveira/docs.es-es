---
title: Suscribirse a eventos de UI Automation
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- UI Automation, subscribing to events
- subscribing to UI Automation events
- events, subscribing to
- listening for events
ms.assetid: b688effa-b3e8-4b05-944d-05ed89a245aa
ms.openlocfilehash: 9c5308192ca122e9c25fa8e845f2b8f89345dda8
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59168472"
---
# <a name="subscribe-to-ui-automation-events"></a><span data-ttu-id="3909a-102">Suscribirse a eventos de UI Automation</span><span class="sxs-lookup"><span data-stu-id="3909a-102">Subscribe to UI Automation Events</span></span>
> [!NOTE]
>  <span data-ttu-id="3909a-103">Esta documentación está dirigida a los desarrolladores de .NET Framework que quieran usar las clases [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] administradas definidas en el espacio de nombres <xref:System.Windows.Automation>.</span><span class="sxs-lookup"><span data-stu-id="3909a-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="3909a-104">Para obtener información más reciente sobre [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], consulte [Windows Automation API: Automatización de interfaz de usuario](https://go.microsoft.com/fwlink/?LinkID=156746).</span><span class="sxs-lookup"><span data-stu-id="3909a-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](https://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="3909a-105">En este tema se muestra cómo suscribirse a eventos generados por los proveedores de UI Automation.</span><span class="sxs-lookup"><span data-stu-id="3909a-105">This topic shows how to subscribe to events raised by UI Automation providers.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3909a-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="3909a-106">Example</span></span>  
 <span data-ttu-id="3909a-107">El ejemplo de código siguiente registra un controlador de eventos para el evento que se desencadena cuando se invoca un control como un botón y lo quita cuando se cierra el formulario de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="3909a-107">The following example code registers an event handler for the event that is raised when a control such as a button is invoked, and removes it when the application form closes.</span></span> <span data-ttu-id="3909a-108">El evento se identifica mediante un elemento <xref:System.Windows.Automation.AutomationEvent> que se pasa como parámetro a <xref:System.Windows.Automation.Automation.AddAutomationEventHandler%2A>.</span><span class="sxs-lookup"><span data-stu-id="3909a-108">The event is identified by an <xref:System.Windows.Automation.AutomationEvent> passed as a parameter to <xref:System.Windows.Automation.Automation.AddAutomationEventHandler%2A>.</span></span>  
  
 [!code-csharp[UIAClient_snip#101](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClient_snip/CSharp/ClientForm.cs#101)]
 [!code-vb[UIAClient_snip#101](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClient_snip/VisualBasic/ClientForm.vb#101)]  
  
## <a name="example"></a><span data-ttu-id="3909a-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="3909a-109">Example</span></span>  
 <span data-ttu-id="3909a-110">En el ejemplo siguiente se muestra cómo utilizar [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] para suscribirse a un evento que se genera cuando cambia el foco.</span><span class="sxs-lookup"><span data-stu-id="3909a-110">The following example shows how to use [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] to subscribe to an event that is raised when the focus changes.</span></span> <span data-ttu-id="3909a-111">Se anula el registro del controlador de eventos en un método al que se puede llamar al cerrar la aplicación o cuando ya no se requiere la notificación de eventos de la interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="3909a-111">The event handler is unregistered in a method that could be called on application shutdown, or when notification of UI events is no longer required.</span></span>  
  
 [!code-csharp[UIAClient_snip#102](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClient_snip/CSharp/ClientForm.cs#102)]
 [!code-vb[UIAClient_snip#102](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClient_snip/VisualBasic/ClientForm.vb#102)]  
  
## <a name="see-also"></a><span data-ttu-id="3909a-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="3909a-112">See also</span></span>

- <xref:System.Windows.Automation.Automation.AddAutomationEventHandler%2A>
- <xref:System.Windows.Automation.Automation.RemoveAllEventHandlers%2A>
- <xref:System.Windows.Automation.Automation.RemoveAutomationEventHandler%2A>
- [<span data-ttu-id="3909a-113">Información general sobre eventos de la Automatización de la interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="3909a-113">UI Automation Events Overview</span></span>](../../../docs/framework/ui-automation/ui-automation-events-overview.md)
