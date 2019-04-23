---
title: Procedimiento para obtener acceso a elementos específicos de un control ComboBox, ListBox o CheckedListBox de formularios Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- ComboBox control [Windows Forms], accessing items
- ListBox control [Windows Forms], returning item information
- list boxes [Windows Forms], accessing items
- ListBox control [Windows Forms], accessing items
- combo boxes [Windows Forms], accessing items
- CheckedListBox control [Windows Forms], accessing items
ms.assetid: 1216742f-bcf9-4ff8-8a62-d7c9053c2b96
ms.openlocfilehash: fbdd9168fe286823db7cf066ae0f821b8db88ecb
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59324531"
---
# <a name="how-to-access-specific-items-in-a-windows-forms-combobox-listbox-or-checkedlistbox-control"></a><span data-ttu-id="ee6cd-102">Procedimiento para obtener acceso a elementos específicos de un control ComboBox, ListBox o CheckedListBox de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="ee6cd-102">How to: Access Specific Items in a Windows Forms ComboBox, ListBox, or CheckedListBox Control</span></span>
<span data-ttu-id="ee6cd-103">Obtener acceso a elementos específicos en un cuadro combinado de Windows Forms, cuadro de lista o cuadro de lista activado es una tarea esencial.</span><span class="sxs-lookup"><span data-stu-id="ee6cd-103">Accessing specific items in a Windows Forms combo box, list box, or checked list box is an essential task.</span></span> <span data-ttu-id="ee6cd-104">Permite determinar mediante programación qué hay en una lista, en cualquier posición dada.</span><span class="sxs-lookup"><span data-stu-id="ee6cd-104">It enables you to programmatically determine what is in a list, at any given position.</span></span>  
  
### <a name="to-access-a-specific-item"></a><span data-ttu-id="ee6cd-105">Para obtener acceso a un elemento específico</span><span class="sxs-lookup"><span data-stu-id="ee6cd-105">To access a specific item</span></span>  
  
1. <span data-ttu-id="ee6cd-106">Consulta el `Items` colección utilizando el índice del elemento específico:</span><span class="sxs-lookup"><span data-stu-id="ee6cd-106">Query the `Items` collection using the index of the specific item:</span></span>  
  
    ```vb  
    Private Function GetItemText(i As Integer) As String  
       ' Return the text of the item using the index:  
       Return ComboBox1.Items(i).ToString  
    End Function  
    ```  
  
    ```csharp  
    private string GetItemText(int i)  
    {  
       // Return the text of the item using the index:  
       return (comboBox1.Items[i].ToString());  
    }  
    ```  
  
    ```cpp  
    private:  
       String^ GetItemText(int i)  
       {  
          // Return the text of the item using the index:  
          return (comboBox1->Items->Item[i]->ToString());  
       }  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="ee6cd-107">Vea también</span><span class="sxs-lookup"><span data-stu-id="ee6cd-107">See also</span></span>

- <xref:System.Windows.Forms.ComboBox>
- <xref:System.Windows.Forms.ListBox>
- <xref:System.Windows.Forms.CheckedListBox>
- [<span data-ttu-id="ee6cd-108">Controles de formularios Windows Forms usados para mostrar opciones</span><span class="sxs-lookup"><span data-stu-id="ee6cd-108">Windows Forms Controls Used to List Options</span></span>](windows-forms-controls-used-to-list-options.md)
