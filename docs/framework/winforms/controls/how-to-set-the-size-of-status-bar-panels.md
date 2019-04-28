---
title: Procedimiento para establecer el tamaño de los paneles de la barra de estado
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- StatusBar control [Windows Forms], panel size
- status bars [Windows Forms], setting panel size
- panels [Windows Forms], setting size in status bars
ms.assetid: a01bee43-d9eb-4954-84e6-45a93532d08d
ms.openlocfilehash: efd3074aaf018e7226c484061cbacb2eac0be820
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62013249"
---
# <a name="how-to-set-the-size-of-status-bar-panels"></a><span data-ttu-id="2311e-102">Procedimiento para establecer el tamaño de los paneles de la barra de estado</span><span class="sxs-lookup"><span data-stu-id="2311e-102">How to: Set the Size of Status-Bar Panels</span></span>
> [!NOTE]
>  <span data-ttu-id="2311e-103">El control <xref:System.Windows.Forms.ToolStripStatusLabel> reemplaza y agrega funcionalidad al control <xref:System.Windows.Forms.StatusBar>; sin embargo, el control <xref:System.Windows.Forms.StatusBar> se conserva a efectos de compatibilidad con versiones anteriores y uso futuro, en su caso.</span><span class="sxs-lookup"><span data-stu-id="2311e-103">The <xref:System.Windows.Forms.ToolStripStatusLabel> control replaces and adds functionality to the <xref:System.Windows.Forms.StatusBar> control; however, the <xref:System.Windows.Forms.StatusBar> control is retained for both backward compatibility and future use, if you choose.</span></span>  
  
 <span data-ttu-id="2311e-104">Cada instancia de la <xref:System.Windows.Forms.StatusBarPanel> clase dentro de un [StatusBar Control](statusbar-control-windows-forms.md) control tiene un número de propiedades dinámicas que determinan su ancho y cambiar el tamaño de comportamiento en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="2311e-104">Each instance of the <xref:System.Windows.Forms.StatusBarPanel> class within a [StatusBar Control](statusbar-control-windows-forms.md) control has a number of dynamic properties that determine its width and resize behavior at run time.</span></span>  
  
### <a name="to-set-the-size-of-a-panel"></a><span data-ttu-id="2311e-105">Para establecer el tamaño de un panel</span><span class="sxs-lookup"><span data-stu-id="2311e-105">To set the size of a panel</span></span>  
  
1. <span data-ttu-id="2311e-106">En un procedimiento, establezca la <xref:System.Windows.Forms.StatusBarPanel.AutoSize%2A>, <xref:System.Windows.Forms.StatusBarPanel.MinWidth%2A>, y <xref:System.Windows.Forms.StatusBarPanel.Width%2A> propiedades (o cualquier subconjunto en ellos) para la barra de estado paneles utilizando su índice se pasan a través de la <xref:System.Windows.Forms.StatusBar.Panels%2A> propiedad de la <xref:System.Windows.Forms.StatusBarPanel> colección.</span><span class="sxs-lookup"><span data-stu-id="2311e-106">In a procedure, set the <xref:System.Windows.Forms.StatusBarPanel.AutoSize%2A>, <xref:System.Windows.Forms.StatusBarPanel.MinWidth%2A>, and <xref:System.Windows.Forms.StatusBarPanel.Width%2A> properties (or any subset therein) for the status-bar panels using their index passed through the <xref:System.Windows.Forms.StatusBar.Panels%2A> property of the <xref:System.Windows.Forms.StatusBarPanel> collection.</span></span>  
  
    ```vb  
    Public Sub SetStatusBarPanelSize()  
    ' Create panel and set text property.  
       StatusBar1.Panels.Add("One")  
    ' Set properties of panels.  
       StatusBar1.Panels(0).AutoSize = StatusBarPanelAutoSize.Spring  
       StatusBar1.Panels(0).Width = 200  
    ' Enable the StatusBar control to display panels.  
       StatusBar1.ShowPanels = True  
        End Sub  
    ```  
  
    ```csharp  
    public void SetStatusBarPanelSize()  
    {  
       // Create panel and set text property.  
       statusBar1.Panels.Add("One");  
       // Set properties of panels.  
       statusBar1.Panels[0].AutoSize = StatusBarPanelAutoSize.Spring;  
       statusBar1.Panels[0].Width = 200;  
       statusBar1.ShowPanels = true;  
    }  
    ```  
  
    ```cpp  
    public:  
       void SetStatusBarPanelSize()  
       {  
          // Create panel and set text property.  
          statusBar1->Panels->Add("One");  
          // Set properties of panels.  
          statusBar1->Panels[0]->AutoSize =  
             StatusBarPanelAutoSize::Spring;  
          statusBar1->Panels[0]->Width = 200;  
          statusBar1->ShowPanels = true;  
       }  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="2311e-107">Vea también</span><span class="sxs-lookup"><span data-stu-id="2311e-107">See also</span></span>

- <xref:System.Windows.Forms.StatusBar>
- <xref:System.Windows.Forms.ToolStripStatusLabel>
- [<span data-ttu-id="2311e-108">Tutorial: Actualizar la información de la barra de estado en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="2311e-108">Walkthrough: Updating Status Bar Information at Run Time</span></span>](walkthrough-updating-status-bar-information-at-run-time.md)
- [<span data-ttu-id="2311e-109">Cómo: Determinar qué Panel de Control StatusBar de formularios Windows Forms se hizo clic</span><span class="sxs-lookup"><span data-stu-id="2311e-109">How to: Determine Which Panel in the Windows Forms StatusBar Control Was Clicked</span></span>](determine-which-panel-wf-statusbar-control-was-clicked.md)
- [<span data-ttu-id="2311e-110">Información general sobre StatusBar (Control)</span><span class="sxs-lookup"><span data-stu-id="2311e-110">StatusBar Control Overview</span></span>](statusbar-control-overview-windows-forms.md)
