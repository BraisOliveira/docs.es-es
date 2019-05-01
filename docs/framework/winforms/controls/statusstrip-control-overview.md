---
title: Información general del control StatusStrip
ms.date: 03/30/2017
f1_keywords:
- StatusStrip
helpviewer_keywords:
- StatusStrip control [Windows Forms], about StatusStrip control
- status bars [Windows Forms], about status bars
ms.assetid: c0d9bcbb-f8b8-46ef-bae2-4146b8c8ce99
ms.openlocfilehash: f6f2d4b19b7ec91c964c72e3aca85e0253c7cc22
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62009648"
---
# <a name="statusstrip-control-overview"></a><span data-ttu-id="9600a-102">Información general del control StatusStrip</span><span class="sxs-lookup"><span data-stu-id="9600a-102">StatusStrip Control Overview</span></span>
<span data-ttu-id="9600a-103">Un control <xref:System.Windows.Forms.StatusStrip> muestra información sobre un objeto que se visualiza en <xref:System.Windows.Forms.Form>, componentes del objeto o información contextual relativa a esa operación del objeto en la aplicación.</span><span class="sxs-lookup"><span data-stu-id="9600a-103">A <xref:System.Windows.Forms.StatusStrip> control displays information about an object being viewed on a <xref:System.Windows.Forms.Form>, the object's components, or contextual information that relates to that object's operation within your application.</span></span> <span data-ttu-id="9600a-104">Normalmente, un control <xref:System.Windows.Forms.StatusStrip> está formado por objetos <xref:System.Windows.Forms.ToolStripStatusLabel>, cada uno de los cuales muestra texto, un icono o ambos.</span><span class="sxs-lookup"><span data-stu-id="9600a-104">Typically, a <xref:System.Windows.Forms.StatusStrip> control consists of <xref:System.Windows.Forms.ToolStripStatusLabel> objects, each of which displays text, an icon, or both.</span></span> <span data-ttu-id="9600a-105">El control <xref:System.Windows.Forms.StatusStrip> también puede contener los controles <xref:System.Windows.Forms.ToolStripDropDownButton>, <xref:System.Windows.Forms.ToolStripSplitButton> y <xref:System.Windows.Forms.ToolStripProgressBar>.</span><span class="sxs-lookup"><span data-stu-id="9600a-105">The <xref:System.Windows.Forms.StatusStrip> can also contain <xref:System.Windows.Forms.ToolStripDropDownButton>, <xref:System.Windows.Forms.ToolStripSplitButton>, and <xref:System.Windows.Forms.ToolStripProgressBar> controls.</span></span>  
  
 <span data-ttu-id="9600a-106">El control <xref:System.Windows.Forms.StatusStrip> predeterminado no tiene paneles.</span><span class="sxs-lookup"><span data-stu-id="9600a-106">The default <xref:System.Windows.Forms.StatusStrip> has no panels.</span></span> <span data-ttu-id="9600a-107">Para agregar paneles a <xref:System.Windows.Forms.StatusStrip>, utilice el método <xref:System.Windows.Forms.ToolStripItemCollection.AddRange%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="9600a-107">To add panels to a <xref:System.Windows.Forms.StatusStrip>, use the <xref:System.Windows.Forms.ToolStripItemCollection.AddRange%2A?displayProperty=nameWithType> method.</span></span>  
  
 <span data-ttu-id="9600a-108">Hay una amplia compatibilidad para controlar elementos <xref:System.Windows.Forms.StatusStrip> y comandos comunes en Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="9600a-108">There is extensive support for handling <xref:System.Windows.Forms.StatusStrip> items and common commands in Visual Studio.</span></span>  
  
 <span data-ttu-id="9600a-109">Consulte también [Editor de colección de elementos StatusStrip](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/ms233631(v=vs.100)) y [cuadro de diálogo de tareas de StatusStrip](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/ms233642(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="9600a-109">Also see [StatusStrip Items Collection Editor](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/ms233631(v=vs.100)) and [StatusStrip Tasks Dialog Box](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/ms233642(v=vs.100)).</span></span>  
  
 <span data-ttu-id="9600a-110">Aunque el control <xref:System.Windows.Forms.StatusStrip> reemplaza y amplía el control <xref:System.Windows.Forms.StatusBar> de versiones anteriores, <xref:System.Windows.Forms.StatusBar> se conserva a efectos de compatibilidad con versiones anteriores y uso futuro, según sea el caso.</span><span class="sxs-lookup"><span data-stu-id="9600a-110">Although <xref:System.Windows.Forms.StatusStrip> replaces and extends the <xref:System.Windows.Forms.StatusBar> control of previous versions, <xref:System.Windows.Forms.StatusBar> is retained for both backward compatibility and future use if you choose.</span></span>  
  
### <a name="important-statusstrip-members"></a><span data-ttu-id="9600a-111">Miembros de StatusStrip importantes</span><span class="sxs-lookup"><span data-stu-id="9600a-111">Important StatusStrip Members</span></span>  
  
|<span data-ttu-id="9600a-112">Name</span><span class="sxs-lookup"><span data-stu-id="9600a-112">Name</span></span>|<span data-ttu-id="9600a-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="9600a-113">Description</span></span>|  
|----------|-----------------|  
|<xref:System.Windows.Forms.StatusStrip.CanOverflow%2A>|<span data-ttu-id="9600a-114">Obtiene o establece un valor que indica si <xref:System.Windows.Forms.StatusStrip> admite la funcionalidad del desbordamiento.</span><span class="sxs-lookup"><span data-stu-id="9600a-114">Gets or sets a value indicating whether the <xref:System.Windows.Forms.StatusStrip> supports overflow functionality.</span></span>|  
|<xref:System.Windows.Forms.StatusStrip.Stretch%2A>|<span data-ttu-id="9600a-115">Obtiene o establece un valor que indica si <xref:System.Windows.Forms.StatusStrip> se expande de punto de conexión a punto de conexión en <xref:System.Windows.Forms.ToolStripContainer>.</span><span class="sxs-lookup"><span data-stu-id="9600a-115">Gets or sets a value indicating whether the <xref:System.Windows.Forms.StatusStrip> stretches from end to end in its <xref:System.Windows.Forms.ToolStripContainer>.</span></span>|  
  
### <a name="important-statusstrip-companion-classes"></a><span data-ttu-id="9600a-116">Clases complementarias importantes de StatusStrip</span><span class="sxs-lookup"><span data-stu-id="9600a-116">Important StatusStrip Companion Classes</span></span>  
  
|<span data-ttu-id="9600a-117">Name</span><span class="sxs-lookup"><span data-stu-id="9600a-117">Name</span></span>|<span data-ttu-id="9600a-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="9600a-118">Description</span></span>|  
|----------|-----------------|  
|<xref:System.Windows.Forms.ToolStripStatusLabel>|<span data-ttu-id="9600a-119">Representa un panel de un control <xref:System.Windows.Forms.StatusStrip>.</span><span class="sxs-lookup"><span data-stu-id="9600a-119">Represents a panel in a <xref:System.Windows.Forms.StatusStrip> control.</span></span>|  
|<xref:System.Windows.Forms.ToolStripDropDownButton>|<span data-ttu-id="9600a-120">Muestra un <xref:System.Windows.Forms.ToolStripDropDown> asociado en el que el usuario puede seleccionar un elemento único.</span><span class="sxs-lookup"><span data-stu-id="9600a-120">Displays an associated <xref:System.Windows.Forms.ToolStripDropDown> from which the user can select a single item.</span></span>|  
|<xref:System.Windows.Forms.ToolStripSplitButton>|<span data-ttu-id="9600a-121">Representa un control de dos elementos que son un botón estándar y un menú desplegable.</span><span class="sxs-lookup"><span data-stu-id="9600a-121">Represents a two-part control that is a standard button and a drop-down menu.</span></span>|  
|<xref:System.Windows.Forms.ToolStripProgressBar>|<span data-ttu-id="9600a-122">Muestra el estado de finalización de un proceso.</span><span class="sxs-lookup"><span data-stu-id="9600a-122">Displays the completion state of a process.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9600a-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="9600a-123">See also</span></span>

- <xref:System.Windows.Forms.StatusStrip>
- <xref:System.Windows.Forms.ToolStripStatusLabel>
- <xref:System.Windows.Forms.ToolStripStatusLabel.Spring%2A>
