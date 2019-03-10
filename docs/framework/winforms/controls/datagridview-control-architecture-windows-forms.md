---
title: Arquitectura del control DataGridView (formularios Windows Forms)
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], architecture
ms.assetid: 1c6cabf0-02ee-4bbc-9574-b54bb7f5b19e
ms.openlocfilehash: d215eeaa367156c6228615a8f6e0a7f889efdf60
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2019
ms.locfileid: "57713818"
---
# <a name="datagridview-control-architecture-windows-forms"></a><span data-ttu-id="453fc-102">Arquitectura del control DataGridView (formularios Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="453fc-102">DataGridView Control Architecture (Windows Forms)</span></span>
<span data-ttu-id="453fc-103">El <xref:System.Windows.Forms.DataGridView> control y sus clases relacionadas están diseñadas para ser un sistema flexible y extensible para mostrar y editar datos tabulares.</span><span class="sxs-lookup"><span data-stu-id="453fc-103">The <xref:System.Windows.Forms.DataGridView> control and its related classes are designed to be a flexible, extensible system for displaying and editing tabular data.</span></span> <span data-ttu-id="453fc-104">Estas clases están incluidas en el <xref:System.Windows.Forms?displayProperty=nameWithType> espacio de nombres y se denominan con el prefijo "DataGridView".</span><span class="sxs-lookup"><span data-stu-id="453fc-104">These classes are all contained in the <xref:System.Windows.Forms?displayProperty=nameWithType> namespace, and they are all named with the "DataGridView" prefix.</span></span>  
  
## <a name="architecture-elements"></a><span data-ttu-id="453fc-105">Elementos de arquitectura</span><span class="sxs-lookup"><span data-stu-id="453fc-105">Architecture Elements</span></span>  
 <span data-ttu-id="453fc-106">La principal <xref:System.Windows.Forms.DataGridView> derivan clases complementarias <xref:System.Windows.Forms.DataGridViewElement>.</span><span class="sxs-lookup"><span data-stu-id="453fc-106">The primary <xref:System.Windows.Forms.DataGridView> companion classes derive from <xref:System.Windows.Forms.DataGridViewElement>.</span></span> <span data-ttu-id="453fc-107">El modelo de objetos siguiente ilustra la <xref:System.Windows.Forms.DataGridViewElement> jerarquía de herencia.</span><span class="sxs-lookup"><span data-stu-id="453fc-107">The following object model illustrates the <xref:System.Windows.Forms.DataGridViewElement> inheritance hierarchy.</span></span>  
  
 <span data-ttu-id="453fc-108">![Modelo de objetos DataGridViewElement](./media/datagridviewelement.gif "DataGridViewElement")</span><span class="sxs-lookup"><span data-stu-id="453fc-108">![DataGridViewElement Object Model](./media/datagridviewelement.gif "DataGridViewElement")</span></span>  
<span data-ttu-id="453fc-109">Modelo de objetos DataGridViewElement</span><span class="sxs-lookup"><span data-stu-id="453fc-109">DataGridViewElement object model</span></span>  
  
 <span data-ttu-id="453fc-110">El <xref:System.Windows.Forms.DataGridViewElement> clase proporciona una referencia al elemento primario <xref:System.Windows.Forms.DataGridView> controlar y tiene un <xref:System.Windows.Forms.DataGridViewElement.State%2A> propiedad, que contiene un valor que representa una combinación de valores de la <xref:System.Windows.Forms.DataGridViewElementStates> enumeración.</span><span class="sxs-lookup"><span data-stu-id="453fc-110">The <xref:System.Windows.Forms.DataGridViewElement> class provides a reference to the parent <xref:System.Windows.Forms.DataGridView> control and has a <xref:System.Windows.Forms.DataGridViewElement.State%2A> property, which holds a value that represents a combination of values from the <xref:System.Windows.Forms.DataGridViewElementStates> enumeration.</span></span>  
  
 <span data-ttu-id="453fc-111">Las secciones siguientes describen el <xref:System.Windows.Forms.DataGridView> clases con más detalle complementarias.</span><span class="sxs-lookup"><span data-stu-id="453fc-111">The following sections describe the <xref:System.Windows.Forms.DataGridView> companion classes in more detail.</span></span>  
  
### <a name="datagridviewelementstates"></a><span data-ttu-id="453fc-112">DataGridViewElementStates</span><span class="sxs-lookup"><span data-stu-id="453fc-112">DataGridViewElementStates</span></span>  
 <span data-ttu-id="453fc-113">El <xref:System.Windows.Forms.DataGridViewElementStates> enumeración contiene los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="453fc-113">The <xref:System.Windows.Forms.DataGridViewElementStates> enumeration contains the following values:</span></span>  
  
-   <xref:System.Windows.Forms.DataGridViewElementStates.None>  
  
-   <xref:System.Windows.Forms.DataGridViewElementStates.Frozen>  
  
-   <xref:System.Windows.Forms.DataGridViewElementStates.ReadOnly>  
  
-   <xref:System.Windows.Forms.DataGridViewElementStates.Resizable>  
  
-   <xref:System.Windows.Forms.DataGridViewElementStates.ResizableSet>  
  
-   <xref:System.Windows.Forms.DataGridViewElementStates.Selected>  
  
-   <xref:System.Windows.Forms.DataGridViewElementStates.Visible>  
  
 <span data-ttu-id="453fc-114">Los valores de esta enumeración se pueden combinar con los operadores lógicos bit a bit, por lo que el <xref:System.Windows.Forms.DataGridViewElement.State%2A> propiedad puede expresar en más de un estado a la vez.</span><span class="sxs-lookup"><span data-stu-id="453fc-114">The values of this enumeration can be combined with the bitwise logical operators, so the <xref:System.Windows.Forms.DataGridViewElement.State%2A> property can express more than one state at once.</span></span> <span data-ttu-id="453fc-115">Por ejemplo, un <xref:System.Windows.Forms.DataGridViewElement> puede ser simultáneamente <xref:System.Windows.Forms.DataGridViewElementStates.Frozen>, <xref:System.Windows.Forms.DataGridViewElementStates.Selected>, y <xref:System.Windows.Forms.DataGridViewElementStates.Visible>.</span><span class="sxs-lookup"><span data-stu-id="453fc-115">For example, a <xref:System.Windows.Forms.DataGridViewElement> can be simultaneously <xref:System.Windows.Forms.DataGridViewElementStates.Frozen>, <xref:System.Windows.Forms.DataGridViewElementStates.Selected>, and <xref:System.Windows.Forms.DataGridViewElementStates.Visible>.</span></span>  
  
### <a name="cells-and-bands"></a><span data-ttu-id="453fc-116">Las celdas y bandas</span><span class="sxs-lookup"><span data-stu-id="453fc-116">Cells and Bands</span></span>  
 <span data-ttu-id="453fc-117">El <xref:System.Windows.Forms.DataGridView> control consta de dos tipos fundamentales de objetos: celdas y bandas.</span><span class="sxs-lookup"><span data-stu-id="453fc-117">The <xref:System.Windows.Forms.DataGridView> control comprises two fundamental kinds of objects: cells and bands.</span></span> <span data-ttu-id="453fc-118">Todas las celdas que se derivan de la <xref:System.Windows.Forms.DataGridViewCell> clase base.</span><span class="sxs-lookup"><span data-stu-id="453fc-118">All cells derive from the <xref:System.Windows.Forms.DataGridViewCell> base class.</span></span> <span data-ttu-id="453fc-119">Los dos tipos de bandas, <xref:System.Windows.Forms.DataGridViewColumn> y <xref:System.Windows.Forms.DataGridViewRow>, ambos derivan de la <xref:System.Windows.Forms.DataGridViewBand> clase base.</span><span class="sxs-lookup"><span data-stu-id="453fc-119">The two kinds of bands, <xref:System.Windows.Forms.DataGridViewColumn> and <xref:System.Windows.Forms.DataGridViewRow>, both derive from the <xref:System.Windows.Forms.DataGridViewBand> base class.</span></span>  
  
 <span data-ttu-id="453fc-120">El <xref:System.Windows.Forms.DataGridView> control interopera con varias clases, pero son detectados con más frecuencia <xref:System.Windows.Forms.DataGridViewCell>, <xref:System.Windows.Forms.DataGridViewColumn>, y <xref:System.Windows.Forms.DataGridViewRow>.</span><span class="sxs-lookup"><span data-stu-id="453fc-120">The <xref:System.Windows.Forms.DataGridView> control interoperates with several classes, but the most commonly encountered are <xref:System.Windows.Forms.DataGridViewCell>, <xref:System.Windows.Forms.DataGridViewColumn>, and <xref:System.Windows.Forms.DataGridViewRow>.</span></span>  
  
### <a name="datagridviewcell"></a><span data-ttu-id="453fc-121">DataGridViewCell</span><span class="sxs-lookup"><span data-stu-id="453fc-121">DataGridViewCell</span></span>  
 <span data-ttu-id="453fc-122">La celda es la unidad fundamental de interacción para el <xref:System.Windows.Forms.DataGridView>.</span><span class="sxs-lookup"><span data-stu-id="453fc-122">The cell is the fundamental unit of interaction for the <xref:System.Windows.Forms.DataGridView>.</span></span> <span data-ttu-id="453fc-123">La presentación se centra en las celdas y entrada de datos a menudo se realiza a través de las celdas.</span><span class="sxs-lookup"><span data-stu-id="453fc-123">Display is centered on cells, and data entry is often performed through cells.</span></span> <span data-ttu-id="453fc-124">Puede acceder a las celdas mediante la <xref:System.Windows.Forms.DataGridViewRow.Cells%2A> colección de la <xref:System.Windows.Forms.DataGridViewRow> clase y se pueden acceder a las celdas seleccionadas mediante la <xref:System.Windows.Forms.DataGridView.SelectedCells%2A> colección de la <xref:System.Windows.Forms.DataGridView> control.</span><span class="sxs-lookup"><span data-stu-id="453fc-124">You can access cells by using the <xref:System.Windows.Forms.DataGridViewRow.Cells%2A> collection of the <xref:System.Windows.Forms.DataGridViewRow> class, and you can access the selected cells by using the <xref:System.Windows.Forms.DataGridView.SelectedCells%2A> collection of the <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="453fc-125">El modelo de objetos siguiente muestra este uso y muestra el <xref:System.Windows.Forms.DataGridViewCell> jerarquía de herencia.</span><span class="sxs-lookup"><span data-stu-id="453fc-125">The following object model illustrates this usage and shows the <xref:System.Windows.Forms.DataGridViewCell> inheritance hierarchy.</span></span>  
  
 <span data-ttu-id="453fc-126">![Modelo de objetos DataGridViewCell](./media/datagridviewcell.gif "DataGridViewCell")</span><span class="sxs-lookup"><span data-stu-id="453fc-126">![DataGridViewCell Object Model](./media/datagridviewcell.gif "DataGridViewCell")</span></span>  
<span data-ttu-id="453fc-127">Modelo de objetos DataGridViewCell</span><span class="sxs-lookup"><span data-stu-id="453fc-127">DataGridViewCell object model</span></span>  
  
 <span data-ttu-id="453fc-128">El <xref:System.Windows.Forms.DataGridViewCell> tipo es una clase base abstracta, de la que derivan todos los tipos de celda.</span><span class="sxs-lookup"><span data-stu-id="453fc-128">The <xref:System.Windows.Forms.DataGridViewCell> type is an abstract base class, from which all cell types derive.</span></span> <span data-ttu-id="453fc-129"><xref:System.Windows.Forms.DataGridViewCell> y sus tipos derivados no son controles de formularios Windows Forms, pero algunos controles de formularios de Windows de host.</span><span class="sxs-lookup"><span data-stu-id="453fc-129"><xref:System.Windows.Forms.DataGridViewCell> and its derived types are not Windows Forms controls, but some host Windows Forms controls.</span></span> <span data-ttu-id="453fc-130">Cualquier función de edición admitida por una celda normalmente se controla mediante un control hospedado.</span><span class="sxs-lookup"><span data-stu-id="453fc-130">Any editing functionality supported by a cell is typically handled by a hosted control.</span></span>  
  
 <span data-ttu-id="453fc-131"><xref:System.Windows.Forms.DataGridViewCell> objetos no controlan su propia apariencia y las características de dibujo de la misma manera como controles de formularios Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="453fc-131"><xref:System.Windows.Forms.DataGridViewCell> objects do not control their own appearance and painting features in the same way as Windows Forms controls.</span></span> <span data-ttu-id="453fc-132">En su lugar, el <xref:System.Windows.Forms.DataGridView> es responsable de la apariencia de su <xref:System.Windows.Forms.DataGridViewCell> objetos.</span><span class="sxs-lookup"><span data-stu-id="453fc-132">Instead, the <xref:System.Windows.Forms.DataGridView> is responsible for the appearance of its <xref:System.Windows.Forms.DataGridViewCell> objects.</span></span> <span data-ttu-id="453fc-133">Puede afectar significativamente a la apariencia y comportamiento de las celdas mediante la interacción con el <xref:System.Windows.Forms.DataGridView> eventos y propiedades del control.</span><span class="sxs-lookup"><span data-stu-id="453fc-133">You can significantly affect the appearance and behavior of cells by interacting with the <xref:System.Windows.Forms.DataGridView> control's properties and events.</span></span> <span data-ttu-id="453fc-134">Cuando tenga requisitos especiales para las personalizaciones que van más allá de las capacidades de la <xref:System.Windows.Forms.DataGridView> control, puede implementar su propia clase que derive de <xref:System.Windows.Forms.DataGridViewCell> o uno de sus clases secundarias.</span><span class="sxs-lookup"><span data-stu-id="453fc-134">When you have special requirements for customizations that are beyond the capabilities of the <xref:System.Windows.Forms.DataGridView> control, you can implement your own class that derives from <xref:System.Windows.Forms.DataGridViewCell> or one of its child classes.</span></span>  
  
 <span data-ttu-id="453fc-135">La siguiente lista muestra las clases derivadas de <xref:System.Windows.Forms.DataGridViewCell>:</span><span class="sxs-lookup"><span data-stu-id="453fc-135">The following list shows the classes derived from <xref:System.Windows.Forms.DataGridViewCell>:</span></span>  
  
-   <xref:System.Windows.Forms.DataGridViewTextBoxCell>  
  
-   <xref:System.Windows.Forms.DataGridViewButtonCell>  
  
-   <xref:System.Windows.Forms.DataGridViewLinkCell>  
  
-   <xref:System.Windows.Forms.DataGridViewCheckBoxCell>  
  
-   <xref:System.Windows.Forms.DataGridViewComboBoxCell>  
  
-   <xref:System.Windows.Forms.DataGridViewImageCell>  
  
-   <xref:System.Windows.Forms.DataGridViewHeaderCell>  
  
-   <xref:System.Windows.Forms.DataGridViewRowHeaderCell>  
  
-   <xref:System.Windows.Forms.DataGridViewColumnHeaderCell>  
  
-   <xref:System.Windows.Forms.DataGridViewTopLeftHeaderCell>  
  
-   <span data-ttu-id="453fc-136">Tipos de celda personalizados</span><span class="sxs-lookup"><span data-stu-id="453fc-136">Your custom cell types</span></span>  
  
### <a name="datagridviewcolumn"></a><span data-ttu-id="453fc-137">DataGridViewColumn</span><span class="sxs-lookup"><span data-stu-id="453fc-137">DataGridViewColumn</span></span>  
 <span data-ttu-id="453fc-138">El esquema de la <xref:System.Windows.Forms.DataGridView> almacén de datos adjuntos del control se expresa en el <xref:System.Windows.Forms.DataGridView> columnas del control.</span><span class="sxs-lookup"><span data-stu-id="453fc-138">The schema of the <xref:System.Windows.Forms.DataGridView> control's attached data store is expressed in the <xref:System.Windows.Forms.DataGridView> control's columns.</span></span> <span data-ttu-id="453fc-139">Puede tener acceso a la <xref:System.Windows.Forms.DataGridView> columnas del control mediante el uso de la <xref:System.Windows.Forms.DataGridView.Columns%2A> colección.</span><span class="sxs-lookup"><span data-stu-id="453fc-139">You can access the <xref:System.Windows.Forms.DataGridView> control's columns by using the <xref:System.Windows.Forms.DataGridView.Columns%2A> collection.</span></span> <span data-ttu-id="453fc-140">Puede acceder a las columnas seleccionadas mediante la <xref:System.Windows.Forms.DataGridView.SelectedColumns%2A> colección.</span><span class="sxs-lookup"><span data-stu-id="453fc-140">You can access the selected columns by using the <xref:System.Windows.Forms.DataGridView.SelectedColumns%2A> collection.</span></span> <span data-ttu-id="453fc-141">El modelo de objetos siguiente muestra este uso y muestra el <xref:System.Windows.Forms.DataGridViewColumn> jerarquía de herencia.</span><span class="sxs-lookup"><span data-stu-id="453fc-141">The following object model illustrates this usage and shows the <xref:System.Windows.Forms.DataGridViewColumn> inheritance hierarchy.</span></span>  
  
 <span data-ttu-id="453fc-142">![Modelo de objetos DataGridViewColumn](./media/datagridviewcolumn.gif "DataGridViewColumn")</span><span class="sxs-lookup"><span data-stu-id="453fc-142">![DataGridViewColumn Object Model](./media/datagridviewcolumn.gif "DataGridViewColumn")</span></span>  
<span data-ttu-id="453fc-143">Modelo de objetos DataGridViewColumn</span><span class="sxs-lookup"><span data-stu-id="453fc-143">DataGridViewColumn object model</span></span>  
  
 <span data-ttu-id="453fc-144">Algunos de los tipos de celda clave tienen tipos de columna correspondientes.</span><span class="sxs-lookup"><span data-stu-id="453fc-144">Some of the key cell types have corresponding column types.</span></span> <span data-ttu-id="453fc-145">Estas se derivan los <xref:System.Windows.Forms.DataGridViewColumn> clase base.</span><span class="sxs-lookup"><span data-stu-id="453fc-145">These are derived from the <xref:System.Windows.Forms.DataGridViewColumn> base class.</span></span>  
  
 <span data-ttu-id="453fc-146">La siguiente lista muestra las clases derivadas de <xref:System.Windows.Forms.DataGridViewColumn>:</span><span class="sxs-lookup"><span data-stu-id="453fc-146">The following list shows the classes derived from <xref:System.Windows.Forms.DataGridViewColumn>:</span></span>  
  
-   <xref:System.Windows.Forms.DataGridViewButtonColumn>  
  
-   <xref:System.Windows.Forms.DataGridViewCheckBoxColumn>  
  
-   <xref:System.Windows.Forms.DataGridViewComboBoxColumn>  
  
-   <xref:System.Windows.Forms.DataGridViewImageColumn>  
  
-   <xref:System.Windows.Forms.DataGridViewTextBoxColumn>  
  
-   <xref:System.Windows.Forms.DataGridViewLinkColumn>  
  
-   <span data-ttu-id="453fc-147">Tipos de columna personalizada</span><span class="sxs-lookup"><span data-stu-id="453fc-147">Your custom column types</span></span>  
  
### <a name="datagridview-editing-controls"></a><span data-ttu-id="453fc-148">Controles de edición de DataGridView</span><span class="sxs-lookup"><span data-stu-id="453fc-148">DataGridView Editing Controls</span></span>  
 <span data-ttu-id="453fc-149">Las celdas que admiten funciones de edición avanzadas normalmente utilizan un control hospedado que se deriva de un control de Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="453fc-149">Cells that support advanced editing functionality typically use a hosted control that is derived from a Windows Forms control.</span></span> <span data-ttu-id="453fc-150">Estos controles también implementan la <xref:System.Windows.Forms.IDataGridViewEditingControl> interfaz.</span><span class="sxs-lookup"><span data-stu-id="453fc-150">These controls also implement the <xref:System.Windows.Forms.IDataGridViewEditingControl> interface.</span></span> <span data-ttu-id="453fc-151">El modelo de objetos siguiente muestra el uso de estos controles.</span><span class="sxs-lookup"><span data-stu-id="453fc-151">The following object model illustrates the usage of these controls.</span></span>  
  
 <span data-ttu-id="453fc-152">![Modelo de objetos de Control de edición de DataGridView](./media/datagridviewediting.gif "DataGridViewEditing")</span><span class="sxs-lookup"><span data-stu-id="453fc-152">![DataGridView Editing Control Object Model](./media/datagridviewediting.gif "DataGridViewEditing")</span></span>  
<span data-ttu-id="453fc-153">Modelo de objetos de control de edición de DataGridView</span><span class="sxs-lookup"><span data-stu-id="453fc-153">DataGridView editing control object model</span></span>  
  
 <span data-ttu-id="453fc-154">Los controles de edición siguientes se proporcionan con el <xref:System.Windows.Forms.DataGridView> control:</span><span class="sxs-lookup"><span data-stu-id="453fc-154">The following editing controls are provided with the <xref:System.Windows.Forms.DataGridView> control:</span></span>  
  
-   <xref:System.Windows.Forms.DataGridViewComboBoxEditingControl>  
  
-   <xref:System.Windows.Forms.DataGridViewTextBoxEditingControl>  
  
 <span data-ttu-id="453fc-155">Para obtener información acerca de cómo crear sus propios editar controles, vea [Cómo: Alojar controles en formularios de Windows las celdas de DataGridView](how-to-host-controls-in-windows-forms-datagridview-cells.md).</span><span class="sxs-lookup"><span data-stu-id="453fc-155">For information about creating your own editing controls, see [How to: Host Controls in Windows Forms DataGridView Cells](how-to-host-controls-in-windows-forms-datagridview-cells.md).</span></span>  
  
 <span data-ttu-id="453fc-156">En la tabla siguiente se ilustra la relación entre los tipos de celdas, tipos de columna y controles de edición.</span><span class="sxs-lookup"><span data-stu-id="453fc-156">The following table illustrates the relationship among cell types, column types, and editing controls.</span></span>  
  
|<span data-ttu-id="453fc-157">Tipo de celda</span><span class="sxs-lookup"><span data-stu-id="453fc-157">Cell type</span></span>|<span data-ttu-id="453fc-158">Control hospedado</span><span class="sxs-lookup"><span data-stu-id="453fc-158">Hosted control</span></span>|<span data-ttu-id="453fc-159">Tipo de columna</span><span class="sxs-lookup"><span data-stu-id="453fc-159">Column type</span></span>|  
|---------------|--------------------|-----------------|  
|<xref:System.Windows.Forms.DataGridViewButtonCell>|<span data-ttu-id="453fc-160">N/D</span><span class="sxs-lookup"><span data-stu-id="453fc-160">n/a</span></span>|<xref:System.Windows.Forms.DataGridViewButtonColumn>|  
|<xref:System.Windows.Forms.DataGridViewCheckBoxCell>|<span data-ttu-id="453fc-161">no disponible</span><span class="sxs-lookup"><span data-stu-id="453fc-161">n/a</span></span>|<xref:System.Windows.Forms.DataGridViewCheckBoxColumn>|  
|<xref:System.Windows.Forms.DataGridViewComboBoxCell>|<xref:System.Windows.Forms.DataGridViewComboBoxEditingControl>|<xref:System.Windows.Forms.DataGridViewComboBoxColumn>|  
|<xref:System.Windows.Forms.DataGridViewImageCell>|<span data-ttu-id="453fc-162">no disponible</span><span class="sxs-lookup"><span data-stu-id="453fc-162">n/a</span></span>|<xref:System.Windows.Forms.DataGridViewImageColumn>|  
|<xref:System.Windows.Forms.DataGridViewLinkCell>|<span data-ttu-id="453fc-163">N/D</span><span class="sxs-lookup"><span data-stu-id="453fc-163">n/a</span></span>|<xref:System.Windows.Forms.DataGridViewLinkColumn>|  
|<xref:System.Windows.Forms.DataGridViewTextBoxCell>|<xref:System.Windows.Forms.DataGridViewTextBoxEditingControl>|<xref:System.Windows.Forms.DataGridViewTextBoxColumn>|  
  
### <a name="datagridviewrow"></a><span data-ttu-id="453fc-164">DataGridViewRow</span><span class="sxs-lookup"><span data-stu-id="453fc-164">DataGridViewRow</span></span>  
 <span data-ttu-id="453fc-165">El <xref:System.Windows.Forms.DataGridViewRow> muestra clase campos de datos de un registro de los datos del almacén al que el <xref:System.Windows.Forms.DataGridView> está asociado el control.</span><span class="sxs-lookup"><span data-stu-id="453fc-165">The <xref:System.Windows.Forms.DataGridViewRow> class displays a record's data fields from the data store to which the <xref:System.Windows.Forms.DataGridView> control is attached.</span></span> <span data-ttu-id="453fc-166">Puede tener acceso a la <xref:System.Windows.Forms.DataGridView> filas del control mediante la <xref:System.Windows.Forms.DataGridView.Rows%2A> colección.</span><span class="sxs-lookup"><span data-stu-id="453fc-166">You can access the <xref:System.Windows.Forms.DataGridView> control's rows by using the <xref:System.Windows.Forms.DataGridView.Rows%2A> collection.</span></span> <span data-ttu-id="453fc-167">Puede acceder a las filas seleccionadas mediante la <xref:System.Windows.Forms.DataGridView.SelectedRows%2A> colección.</span><span class="sxs-lookup"><span data-stu-id="453fc-167">You can access the selected rows by using the <xref:System.Windows.Forms.DataGridView.SelectedRows%2A> collection.</span></span> <span data-ttu-id="453fc-168">El modelo de objetos siguiente muestra este uso y muestra el <xref:System.Windows.Forms.DataGridViewRow> jerarquía de herencia.</span><span class="sxs-lookup"><span data-stu-id="453fc-168">The following object model illustrates this usage and shows the <xref:System.Windows.Forms.DataGridViewRow> inheritance hierarchy.</span></span>  
  
 <span data-ttu-id="453fc-169">![Modelo de objetos DataGridViewRow](./media/datagridviewrow.gif "DataGridViewRow")</span><span class="sxs-lookup"><span data-stu-id="453fc-169">![DataGridViewRow Object Model](./media/datagridviewrow.gif "DataGridViewRow")</span></span>  
<span data-ttu-id="453fc-170">Modelo de objetos DataGridViewRow</span><span class="sxs-lookup"><span data-stu-id="453fc-170">DataGridViewRow object model</span></span>  
  
 <span data-ttu-id="453fc-171">Puede derivar sus propios tipos desde el <xref:System.Windows.Forms.DataGridViewRow> clase, aunque normalmente no será necesario.</span><span class="sxs-lookup"><span data-stu-id="453fc-171">You can derive your own types from the <xref:System.Windows.Forms.DataGridViewRow> class, although this will typically not be necessary.</span></span> <span data-ttu-id="453fc-172">El <xref:System.Windows.Forms.DataGridView> control tiene varios eventos relacionados con la fila y propiedades para personalizar el comportamiento de su <xref:System.Windows.Forms.DataGridViewRow> objetos.</span><span class="sxs-lookup"><span data-stu-id="453fc-172">The <xref:System.Windows.Forms.DataGridView> control has several row-related events and properties for customizing the behavior of its <xref:System.Windows.Forms.DataGridViewRow> objects.</span></span>  
  
 <span data-ttu-id="453fc-173">Si habilita la <xref:System.Windows.Forms.DataGridView> del control <xref:System.Windows.Forms.DataGridView.AllowUserToAddRows%2A> una fila especial para agregar nuevas filas de propiedad, aparece como la última fila.</span><span class="sxs-lookup"><span data-stu-id="453fc-173">If you enable the <xref:System.Windows.Forms.DataGridView> control's <xref:System.Windows.Forms.DataGridView.AllowUserToAddRows%2A> property, a special row for adding new rows appears as the last row.</span></span> <span data-ttu-id="453fc-174">Esta fila es parte de la <xref:System.Windows.Forms.DataGridView.Rows%2A> colección, pero tiene una funcionalidad especial que requiera su atención.</span><span class="sxs-lookup"><span data-stu-id="453fc-174">This row is part of the <xref:System.Windows.Forms.DataGridView.Rows%2A> collection, but it has special functionality that may require your attention.</span></span> <span data-ttu-id="453fc-175">Para obtener más información, consulte [utilizando la fila de nuevos registros en el DataGridView Control de Windows Forms](using-the-row-for-new-records-in-the-windows-forms-datagridview-control.md).</span><span class="sxs-lookup"><span data-stu-id="453fc-175">For more information, see [Using the Row for New Records in the Windows Forms DataGridView Control](using-the-row-for-new-records-in-the-windows-forms-datagridview-control.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="453fc-176">Vea también</span><span class="sxs-lookup"><span data-stu-id="453fc-176">See also</span></span>
- [<span data-ttu-id="453fc-177">Información general del control DataGridView</span><span class="sxs-lookup"><span data-stu-id="453fc-177">DataGridView Control Overview</span></span>](datagridview-control-overview-windows-forms.md)
- [<span data-ttu-id="453fc-178">Personalizar el control DataGridView de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="453fc-178">Customizing the Windows Forms DataGridView Control</span></span>](customizing-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="453fc-179">Utilizar la fila de nuevos registros en el control DataGridView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="453fc-179">Using the Row for New Records in the Windows Forms DataGridView Control</span></span>](using-the-row-for-new-records-in-the-windows-forms-datagridview-control.md)
