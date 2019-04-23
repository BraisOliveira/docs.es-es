---
title: Cómo agregar una ubicación personalizada a un cuadro de diálogo de archivos
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Custom Place to dialog box
- adding Custom Place to dialog box
- CustomPlaces collection
ms.assetid: 63f6469b-59cd-40f6-9e61-8b5831856780
ms.openlocfilehash: 79836dd260cb13912ccba43cfb4a0a3e0ad195fd
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59087695"
---
# <a name="how-to-add-a-custom-place-to-a-file-dialog-box"></a><span data-ttu-id="a46f3-102">Cómo agregar una ubicación personalizada a un cuadro de diálogo de archivos</span><span class="sxs-lookup"><span data-stu-id="a46f3-102">How To: Add a Custom Place to a File Dialog Box</span></span>
<span data-ttu-id="a46f3-103">Los cuadros de diálogo para abrir y guardar predeterminados en [!INCLUDE[wiprlhext](../../../../includes/wiprlhext-md.md)] tienen un área en el lado izquierdo titulada **Vínculos favoritos**.</span><span class="sxs-lookup"><span data-stu-id="a46f3-103">The default open and save dialog boxes on [!INCLUDE[wiprlhext](../../../../includes/wiprlhext-md.md)] have an area on the left side of the dialog box titled **Favorite Links**.</span></span> <span data-ttu-id="a46f3-104">Esta área se denomina ubicaciones personalizadas.</span><span class="sxs-lookup"><span data-stu-id="a46f3-104">This area is called custom places.</span></span> <span data-ttu-id="a46f3-105">El <xref:System.Windows.Forms.OpenFileDialog> y <xref:System.Windows.Forms.SaveFileDialog> clases le permiten agregar carpetas a la <xref:System.Windows.Forms.FileDialog.CustomPlaces%2A> colección.</span><span class="sxs-lookup"><span data-stu-id="a46f3-105">The <xref:System.Windows.Forms.OpenFileDialog> and <xref:System.Windows.Forms.SaveFileDialog> classes allow you to add folders to the <xref:System.Windows.Forms.FileDialog.CustomPlaces%2A> collection.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a46f3-106">En el orden de una ubicación personalizada aparezca en el <xref:System.Windows.Forms.OpenFileDialog> o <xref:System.Windows.Forms.SaveFileDialog>, el <xref:System.Windows.Forms.FileDialog.AutoUpgradeEnabled%2A> propiedad debe establecerse en `true` (valor predeterminado).</span><span class="sxs-lookup"><span data-stu-id="a46f3-106">In order for a custom place to appear in the <xref:System.Windows.Forms.OpenFileDialog> or <xref:System.Windows.Forms.SaveFileDialog>, the <xref:System.Windows.Forms.FileDialog.AutoUpgradeEnabled%2A> property must be set to `true` (the default).</span></span>  
  
### <a name="to-add-a-custom-place-to-a-file-dialog-box"></a><span data-ttu-id="a46f3-107">Para agregar una ubicación personalizada a un cuadro de diálogo de archivos</span><span class="sxs-lookup"><span data-stu-id="a46f3-107">To add a custom place to a file dialog box</span></span>  
  
-   <span data-ttu-id="a46f3-108">Agregar una ruta de acceso, un GUID de carpetas conocidas, o un <xref:System.Windows.Forms.FileDialogCustomPlace> de objeto para el <xref:System.Windows.Forms.FileDialog.CustomPlaces%2A> colección del cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="a46f3-108">Add a path, a Known Folder GUID, or a <xref:System.Windows.Forms.FileDialogCustomPlace> object to the <xref:System.Windows.Forms.FileDialog.CustomPlaces%2A> collection of the dialog box.</span></span>  
  
     <span data-ttu-id="a46f3-109">En el siguiente ejemplo de código se muestra cómo agregar una ruta de acceso:</span><span class="sxs-lookup"><span data-stu-id="a46f3-109">The following code example shows how to add a path:</span></span>  
  
    ```vb  
    OpenFileDialog1.CustomPlaces.Add("C:\MyCustomPlace")  
    ```  
  
    ```csharp  
    openFileDialog1.CustomPlaces.Add("C:\\MyCustomPlace");  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="a46f3-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="a46f3-110">See also</span></span>

- <xref:System.Windows.Forms.FileDialog>
- <xref:System.Windows.Forms.FileDialogCustomPlacesCollection.Add%2A?displayProperty=nameWithType>
- [<span data-ttu-id="a46f3-111">GUID de carpeta conocidos para lugares comunes de cuadros de diálogo de archivos</span><span class="sxs-lookup"><span data-stu-id="a46f3-111">Known Folder GUIDs for File Dialog Custom Places</span></span>](known-folder-guids-for-file-dialog-custom-places.md)
