---
title: Rehospedar el Diseñador de flujo de trabajo
ms.date: 03/30/2017
ms.assetid: bec1fc28-f902-4edb-86c5-436cec802c2b
ms.openlocfilehash: 98048ca58bf635f4e87241befa083dc240deaecf
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59206114"
---
# <a name="rehosting-the-workflow-designer"></a><span data-ttu-id="75abb-102">Rehospedar el Diseñador de flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="75abb-102">Rehosting the Workflow Designer</span></span>
<span data-ttu-id="75abb-103">El [!INCLUDE[wfd1](../../../includes/wfd1-md.md)] puede rehospedarse en entornos fuera de Visual Studio 2012 para los fines de crear, modificar y supervisar flujos de trabajo.</span><span class="sxs-lookup"><span data-stu-id="75abb-103">The [!INCLUDE[wfd1](../../../includes/wfd1-md.md)] can be rehosted in environments outside of Visual Studio 2012 for the purposes of creating, modifying, and monitoring workflows.</span></span>

 <span data-ttu-id="75abb-104">El tipo <xref:System.Activities.Presentation.WorkflowDesigner> es un contenedor del lienzo, cuadrícula de propiedad y otros elementos, y expone un modelo de programación básico para administrar la mayoría de escenarios de rehospedaje del diseñador.</span><span class="sxs-lookup"><span data-stu-id="75abb-104">The <xref:System.Activities.Presentation.WorkflowDesigner> type is a wrapper of the canvas, property grid, and other elements, and exposes a basic programming model to handle the majority of designer rehosting scenarios.</span></span> <span data-ttu-id="75abb-105">Hospedar el <xref:System.Activities.Presentation.WorkflowDesigner> dentro de Windows Presentation Foundation (WPF) aplicación es un escenario de rehospedaje común para [!INCLUDE[wfd2](../../../includes/wfd2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="75abb-105">Hosting the <xref:System.Activities.Presentation.WorkflowDesigner> inside a Windows Presentation Foundation (WPF) application is a common rehosting scenario for [!INCLUDE[wfd2](../../../includes/wfd2-md.md)].</span></span>

## <a name="in-this-section"></a><span data-ttu-id="75abb-106">En esta sección</span><span class="sxs-lookup"><span data-stu-id="75abb-106">In This Section</span></span>
 [<span data-ttu-id="75abb-107">Tarea 1: Crear una aplicación de Windows Presentation Foundation</span><span class="sxs-lookup"><span data-stu-id="75abb-107">Task 1: Create a New Windows Presentation Foundation Application</span></span>](task-1-create-a-new-wpf-app.md)

 [<span data-ttu-id="75abb-108">Tarea 2: Hospedar el diseñador de flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="75abb-108">Task 2: Host the Workflow Designer</span></span>](task-2-host-the-workflow-designer.md)

 [<span data-ttu-id="75abb-109">Tarea 3: Crear los paneles de Cuadro de herramientas y PropertyGrid</span><span class="sxs-lookup"><span data-stu-id="75abb-109">Task 3: Create the Toolbox and PropertyGrid Panes</span></span>](task-3-create-the-toolbox-and-propertygrid-panes.md)

 [<span data-ttu-id="75abb-110">Compatibilidad para las nuevas características de Workflow Foundation 4.5 en el diseñador de flujo de trabajo rehospedado</span><span class="sxs-lookup"><span data-stu-id="75abb-110">Support for New Workflow Foundation 4.5 Features in the Rehosted Workflow Designer</span></span>](wf-features-in-the-rehosted-workflow-designer.md)

## <a name="see-also"></a><span data-ttu-id="75abb-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="75abb-111">See also</span></span>

- [<span data-ttu-id="75abb-112">Personalizar la experiencia de diseño del flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="75abb-112">Customizing the Workflow Design Experience</span></span>](customizing-the-workflow-design-experience.md)
