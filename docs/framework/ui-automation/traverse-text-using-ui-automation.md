---
title: Recorrer texto mediante usando UI Automation
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- UI Automation, traversing text
- text, traversing
- traversing text
ms.assetid: 3ddb3b7b-1d6b-4dba-8678-5a68e868aadb
ms.openlocfilehash: d73ae4ca11d6f5417bb5cb768eae4e586538bd92
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61982792"
---
# <a name="traverse-text-using-ui-automation"></a><span data-ttu-id="79426-102">Recorrer texto mediante usando UI Automation</span><span class="sxs-lookup"><span data-stu-id="79426-102">Traverse Text Using UI Automation</span></span>
> [!NOTE]
>  <span data-ttu-id="79426-103">Esta documentación está dirigida a los desarrolladores de .NET Framework que quieran usar las clases [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] administradas definidas en el espacio de nombres <xref:System.Windows.Automation>.</span><span class="sxs-lookup"><span data-stu-id="79426-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="79426-104">Para obtener información más reciente sobre [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], consulte [Windows Automation API: Automatización de interfaz de usuario](https://go.microsoft.com/fwlink/?LinkID=156746).</span><span class="sxs-lookup"><span data-stu-id="79426-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](https://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="79426-105">En este tema se muestra cómo usar [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] para recorrer el contenido textual de un documento en incrementos <xref:System.Windows.Automation.Text.TextUnit> .</span><span class="sxs-lookup"><span data-stu-id="79426-105">This topic shows how to use [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] to traverse the textual content of a document by <xref:System.Windows.Automation.Text.TextUnit> increments.</span></span>  
  
## <a name="example"></a><span data-ttu-id="79426-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="79426-106">Example</span></span>  
 <span data-ttu-id="79426-107">En el ejemplo de código siguiente se muestra cómo recorrer el contenido de un proveedor de texto de automatización de la interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="79426-107">The following code example demonstrates how to traverse the content of a UI Automation text provider.</span></span> <span data-ttu-id="79426-108">El método <xref:System.Windows.Automation.Text.TextPatternRange.Move%2A> mueve <xref:System.Windows.Automation.Text.TextPatternRangeEndpoint.Start> y los extremos <xref:System.Windows.Automation.Text.TextPatternRangeEndpoint.End> de un <xref:System.Windows.Automation.Text.TextPatternRange>.</span><span class="sxs-lookup"><span data-stu-id="79426-108">The <xref:System.Windows.Automation.Text.TextPatternRange.Move%2A> method moves the <xref:System.Windows.Automation.Text.TextPatternRangeEndpoint.Start> and <xref:System.Windows.Automation.Text.TextPatternRangeEndpoint.End> endpoints of a <xref:System.Windows.Automation.Text.TextPatternRange>.</span></span> <span data-ttu-id="79426-109">Este intervalo de texto suele ser un intervalo degenerado que representa el punto de inserción de texto.</span><span class="sxs-lookup"><span data-stu-id="79426-109">This text range is typically a degenerate range representing the text insertion point.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="79426-110">Puesto que solo se consideran parte de la secuencia de texto los objetos incrustados basados en texto, los objetos incrustados como imágenes no afectan a `Move` o su valor devuelto.</span><span class="sxs-lookup"><span data-stu-id="79426-110">Since only text-based embedded objects are considered part of the text stream, embedded objects such as images do not affect `Move` or its return value.</span></span>  
  
[!code-csharp[FindText#StartApp](../../../samples/snippets/csharp/VS_Snippets_Wpf/FindText/CSharp/SearchWindow.cs#startapp)]
[!code-vb[FindText#StartApp](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FindText/VisualBasic/SearchWindow.vb#startapp)]  
[!code-csharp[FindText#FindTextProvider](../../../samples/snippets/csharp/VS_Snippets_Wpf/FindText/CSharp/SearchWindow.cs#findtextprovider)]
[!code-vb[FindText#FindTextProvider](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FindText/VisualBasic/SearchWindow.vb#findtextprovider)]  
[!code-csharp[FindText#Navigate](../../../samples/snippets/csharp/VS_Snippets_Wpf/FindText/CSharp/SearchWindow.cs#navigate)]
[!code-vb[FindText#Navigate](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FindText/VisualBasic/SearchWindow.vb#navigate)]  
  
 <span data-ttu-id="79426-111">Cualquier método que use <xref:System.Windows.Automation.Text.TextUnit> aplazará al siguiente <xref:System.Windows.Automation.Text.TextUnit> de mayor tamaño si el control no admite el <xref:System.Windows.Automation.Text.TextUnit> determinado.</span><span class="sxs-lookup"><span data-stu-id="79426-111">Any method using <xref:System.Windows.Automation.Text.TextUnit> will defer to the next largest <xref:System.Windows.Automation.Text.TextUnit> supported if the given <xref:System.Windows.Automation.Text.TextUnit> is not supported by the control.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="79426-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="79426-112">See also</span></span>

- [<span data-ttu-id="79426-113">Información general sobre TextPattern en Automatización de la interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="79426-113">UI Automation TextPattern Overview</span></span>](../../../docs/framework/ui-automation/ui-automation-textpattern-overview.md)
- [<span data-ttu-id="79426-114">Adición de contenido a un cuadro de texto mediante Automatización de la interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="79426-114">Add Content to a Text Box Using UI Automation</span></span>](../../../docs/framework/ui-automation/add-content-to-a-text-box-using-ui-automation.md)
- [<span data-ttu-id="79426-115">Búsqueda y resaltado de texto mediante Automatización de la interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="79426-115">Find and Highlight Text Using UI Automation</span></span>](../../../docs/framework/ui-automation/find-and-highlight-text-using-ui-automation.md)
- [<span data-ttu-id="79426-116">Información general sobre los patrones de control de la Automatización de la interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="79426-116">UI Automation Control Patterns Overview</span></span>](../../../docs/framework/ui-automation/ui-automation-control-patterns-overview.md)
- [<span data-ttu-id="79426-117">Patrones de control de Automatización de la interfaz de usuario para clientes</span><span class="sxs-lookup"><span data-stu-id="79426-117">UI Automation Control Patterns for Clients</span></span>](../../../docs/framework/ui-automation/ui-automation-control-patterns-for-clients.md)
