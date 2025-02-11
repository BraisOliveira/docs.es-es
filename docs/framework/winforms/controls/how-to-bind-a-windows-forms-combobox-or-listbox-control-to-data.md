---
title: Procedimiento para enlazar un control ComboBox o ListBox de formularios Windows Forms a datos
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data [Windows Forms], binding to controls
- list boxes [Windows Forms], data binding
- ComboBox control [Windows Forms], data binding
- data binding [Windows Forms], combo boxes
- ListBox control [Windows Forms], data binding
- combo boxes [Windows Forms], data binding
- bound controls [Windows Forms], combo boxes
- Windows Forms controls, data binding
- data-bound controls [Windows Forms], Windows Forms
ms.assetid: dfd7f081-8bea-4a41-86a3-86a1934828ef
ms.openlocfilehash: f361526c44f8fbb9ab282fe15ae109b67e8f01dd
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69922752"
---
# <a name="how-to-bind-a-windows-forms-combobox-or-listbox-control-to-data"></a>Procedimiento para enlazar un control ComboBox o ListBox de formularios Windows Forms a datos
Puede enlazar los <xref:System.Windows.Forms.ComboBox> datos <xref:System.Windows.Forms.ListBox> y a los datos para realizar tareas como la exploración de datos en una base de datos, la entrada de nuevos datos o la edición de datos existentes.  
  
### <a name="to-bind-a-combobox-or-listbox-control"></a>Para enlazar un control ComboBox o ListBox  
  
1. Establezca la `DataSource` propiedad en un objeto de origen de datos. Entre los orígenes de datos <xref:System.Windows.Forms.BindingSource> posibles se incluyen un enlazado a datos, una tabla de datos, una vista de datos, un conjunto de datos, un administrador de vistas de datos <xref:System.Collections.IList> , una matriz o cualquier clase que implemente la interfaz. Para obtener más información, vea [orígenes de datos compatibles con Windows Forms](../data-sources-supported-by-windows-forms.md).  
  
2. Si va a enlazar a una tabla, establezca `DisplayMember` la propiedad en el nombre de una columna del origen de datos.  
  
     \- o -  
  
     Si va a enlazar a <xref:System.Collections.IList>, establezca el miembro de presentación en una propiedad pública del tipo en la lista.  
  
    ```vb  
    Private Sub BindComboBox()  
      ComboBox1.DataSource = DataSet1.Tables("Suppliers")  
      ComboBox1.DisplayMember = "ProductName"  
    End Sub  
    ```  
  
    ```csharp  
    private void BindComboBox()  
    {  
      comboBox1.DataSource = dataSet1.Tables["Suppliers"];  
      comboBox1.DisplayMember = "ProductName";  
    }  
    ```  
  
    > [!NOTE]
    > Si está enlazado a un origen de datos que no implementa la <xref:System.ComponentModel.IBindingList> interfaz, como <xref:System.Collections.ArrayList>, los datos del control enlazado no se actualizarán cuando se actualice el origen de datos. Por ejemplo, si tiene un cuadro combinado enlazado a un <xref:System.Collections.ArrayList> y los <xref:System.Collections.ArrayList>datos se agregan a, estos nuevos elementos no aparecerán en el cuadro combinado. Sin embargo, puede forzar que el cuadro combinado se actualice llamando a <xref:System.Windows.Forms.BindingManagerBase.SuspendBinding%2A> los <xref:System.Windows.Forms.BindingManagerBase.ResumeBinding%2A> métodos y en la instancia de <xref:System.Windows.Forms.BindingContext> la clase a la que está enlazado el control.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.ComboBox>
- <xref:System.Windows.Forms.ListBox>
- [Enlace de datos en Windows Forms](../windows-forms-data-binding.md)
- [Enlace de datos y Windows Forms](../data-binding-and-windows-forms.md)
- [Controles de formularios Windows Forms usados para mostrar opciones](windows-forms-controls-used-to-list-options.md)
