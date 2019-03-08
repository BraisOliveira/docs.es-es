---
title: Buscar y resaltar texto mediante UI Automation
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- text, highlighting
- finding text
- text, finding
- UI automation, highlighting text
- UI automation, finding text
- highlighting text
ms.assetid: b77693f5-87bb-4b29-a297-05ff882e2044
ms.openlocfilehash: a0df93b153f16dd09dfcc6da5d690dc69141435a
ms.sourcegitcommit: 58fc0e6564a37fa1b9b1b140a637e864c4cf696e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/08/2019
ms.locfileid: "57673709"
---
# <a name="find-and-highlight-text-using-ui-automation"></a><span data-ttu-id="8b4d1-102">Buscar y resaltar texto mediante UI Automation</span><span class="sxs-lookup"><span data-stu-id="8b4d1-102">Find and Highlight Text Using UI Automation</span></span>
> [!NOTE]
>  <span data-ttu-id="8b4d1-103">Esta documentación está dirigida a los desarrolladores de .NET Framework que quieran usar las clases [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] administradas definidas en el espacio de nombres <xref:System.Windows.Automation>.</span><span class="sxs-lookup"><span data-stu-id="8b4d1-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="8b4d1-104">Para obtener información más reciente sobre [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], consulte [Windows Automation API: Automatización de interfaz de usuario](https://go.microsoft.com/fwlink/?LinkID=156746).</span><span class="sxs-lookup"><span data-stu-id="8b4d1-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](https://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="8b4d1-105">En este tema se muestra cómo buscar secuencialmente y resaltar cada aparición de una cadena dentro del contenido de un control de texto mediante [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8b4d1-105">This topic demonstrates how to sequentially search for and highlight each occurrence of a string within the content of a text control using [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)].</span></span>  
  
## <a name="example"></a><span data-ttu-id="8b4d1-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="8b4d1-106">Example</span></span>  
 <span data-ttu-id="8b4d1-107">En el ejemplo siguiente se obtiene un <xref:System.Windows.Automation.TextPattern> objeto a partir de un control de texto.</span><span class="sxs-lookup"><span data-stu-id="8b4d1-107">The following example obtains a <xref:System.Windows.Automation.TextPattern> object from a text control.</span></span> <span data-ttu-id="8b4d1-108">Un <xref:System.Windows.Automation.Text.TextPatternRange> objeto que representa el contenido textual de todo el documento, a continuación, se crea mediante la <xref:System.Windows.Automation.TextPattern.DocumentRange%2A> propiedad de este <xref:System.Windows.Automation.TextPattern>.</span><span class="sxs-lookup"><span data-stu-id="8b4d1-108">A <xref:System.Windows.Automation.Text.TextPatternRange> object, representing the textual content of the entire document, is then created using the <xref:System.Windows.Automation.TextPattern.DocumentRange%2A> property of this <xref:System.Windows.Automation.TextPattern>.</span></span> <span data-ttu-id="8b4d1-109">Dos adicionales <xref:System.Windows.Automation.Text.TextPatternRange> objetos, a continuación, se crean para la búsqueda secuencial y resaltar la funcionalidad.</span><span class="sxs-lookup"><span data-stu-id="8b4d1-109">Two additional <xref:System.Windows.Automation.Text.TextPatternRange> objects are then created for the sequential search and highlight functionality.</span></span>  
  
[!code-csharp[FindText#StartApp](../../../samples/snippets/csharp/VS_Snippets_Wpf/FindText/CSharp/SearchWindow.cs#startapp)]
[!code-vb[FindText#StartApp](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FindText/VisualBasic/SearchWindow.vb#startapp)]  
[!code-csharp[FindText#FindTextProvider](../../../samples/snippets/csharp/VS_Snippets_Wpf/FindText/CSharp/SearchWindow.cs#findtextprovider)]
[!code-vb[FindText#FindTextProvider](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FindText/VisualBasic/SearchWindow.vb#findtextprovider)]  
[!code-csharp[FindText#SearchTarget](../../../samples/snippets/csharp/VS_Snippets_Wpf/FindText/CSharp/SearchWindow.cs#searchtarget)]
[!code-vb[FindText#SearchTarget](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FindText/VisualBasic/SearchWindow.vb#searchtarget)]  
  
## <a name="see-also"></a><span data-ttu-id="8b4d1-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="8b4d1-110">See also</span></span>
- [<span data-ttu-id="8b4d1-111">Búsqueda y resaltado de texto mediante Automatización de la interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="8b4d1-111">Find and Highlight Text Using UI Automation</span></span>](../../../docs/framework/ui-automation/find-and-highlight-text-using-ui-automation.md)
