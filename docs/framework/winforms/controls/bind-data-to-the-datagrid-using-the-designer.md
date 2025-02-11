---
title: Procedimiento para enlazar datos al control DataGridView de formularios Windows Forms mediante el diseñador
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms controls, binding to a data source
- data sources [Windows Forms], binding to Windows Forms controls
- DataGridView control [Windows Forms], data binding
ms.assetid: f4f46009-cec2-441b-8668-6b5af057558b
ms.openlocfilehash: 609878416be26786ce865168c996c78e18b1897f
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69917875"
---
# <a name="how-to-bind-data-to-the-windows-forms-datagridview-control-using-the-designer"></a>Procedimiento para enlazar datos al control DataGridView de formularios Windows Forms mediante el diseñador
Puede usar el diseñador para conectar un <xref:System.Windows.Forms.DataGridView> control a orígenes de datos de varias variedades diferentes, como bases de datos, objetos comerciales o servicios Web. Al enlazar el control a un origen de datos mediante el diseñador, el control se enlaza automáticamente a <xref:System.Windows.Forms.BindingSource> un componente que representa el origen de datos. Además, las columnas se generan automáticamente en el control para coincidir con la información del esquema proporcionada por el origen de datos.

 Después de generar las columnas, puede modificarlas para satisfacer sus necesidades. Por ejemplo, puede quitar u ocultar aquellas columnas que no desee mostrar, puede reorganizar las columnas o puede modificar los tipos de columna. Para más información sobre la modificación de columnas, consulte los temas mostrados en la sección Vea también.

 También puede enlazar varios <xref:System.Windows.Forms.DataGridView> controles a las tablas relacionadas para crear relaciones principal-detalle. En esta configuración, un control muestra una tabla primaria y otro control muestra solo aquellas filas de una tabla secundaria que están relacionadas con la fila actual de la tabla primaria. Para obtener más información, consulte [Cómo Mostrar datos relacionados en una aplicación](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/57tx3hhe(v=vs.120))Windows Forms.

 El procedimiento siguiente requiere un proyecto de **aplicación Windows** con un formulario que contenga un <xref:System.Windows.Forms.DataGridView> control o dos controles para una relación principal-detalle. Para obtener información sobre cómo iniciar este tipo de [proyecto, vea cómo: Cree un proyecto](/visualstudio/ide/step-1-create-a-windows-forms-application-project) de aplicación de [Windows Forms y cómo: Agregue controles a Windows Forms](how-to-add-controls-to-windows-forms.md).

## <a name="to-bind-the-control-to-a-data-source"></a>Para enlazar el control a un origen de datos

1. Haga clic en el glifo de etiqueta inteligente (![glifo de etiqueta inteligente](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) en la <xref:System.Windows.Forms.DataGridView> esquina superior derecha del control.

2. Haga clic en la flecha de lista desplegable de la opción **Elegir origen de datos**.

3. Si su proyecto aún no tiene un origen de datos, haga clic en **Agregar origen de datos del proyecto** y siga los pasos indicados por el asistente.

     Para más información, consulte [Asistente para la configuración de orígenes de datos](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/w4dd7z6t(v=vs.120)). El nuevo origen de datos aparecerá en la ventana desplegable **Elegir origen de datos**. Si el nuevo origen de datos contiene solo un miembro, como una única tabla de base de datos, el control se enlazará automáticamente a dicho miembro. De lo contrario, vaya al paso siguiente.

4. Expanda los nodos **Otros orígenes de datos** y **Orígenes de datos del proyecto** si aún no están expandidos y, después, seleccione el origen datos al que desea enlazar el control.

5. Si el origen de datos contiene más de un miembro, por ejemplo, si ha creado <xref:System.Data.DataSet?displayProperty=nameWithType> un que contiene varias tablas, expanda el origen de datos y, a continuación, seleccione el miembro específico al que se va a enlazar.

6. Para crear una relación principal-detalle, en la ventana desplegable **elegir origen de datos** para un segundo <xref:System.Windows.Forms.DataGridView> control, expanda <xref:System.Windows.Forms.BindingSource> el objeto creado para la tabla primaria y, a continuación, seleccione la tabla secundaria relacionada en la lista que se muestra.

    > [!NOTE]
    > Si el proyecto ya tiene un origen de datos, también puede usar la ventaja **Orígenes de datos** para crear un formulario de datos. Para más información, consulte [Orígenes de datos (ventana)](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/6ckyxa83(v=vs.120)).

## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.BindingSource>
- <xref:System.Windows.Forms.DataGridView.DataMember%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.DataSource%2A?displayProperty=nameWithType>
- [Cómo: Conectarse a los datos de una base de datos](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/fxk9yw1t(v=vs.120))
- [Procedimientos: Agregar y quitar columnas en el control DataGridView Windows Forms mediante el diseñador](add-and-remove-columns-in-the-datagrid-using-the-designer.md)
- [Procedimientos: Cambiar el orden de las columnas en el control DataGridView Windows Forms mediante el diseñador](change-the-order-of-columns-in-the-datagrid-using-the-designer.md)
- [Cómo: Cambiar el tipo de una Windows Forms columna DataGridView mediante el diseñador](change-the-type-of-a-wf-datagridview-column-using-the-designer.md)
- [Cómo: Inmovilizar columnas en el control DataGridView Windows Forms mediante el diseñador](freeze-columns-in-the-datagrid-using-the-designer.md)
- [Procedimientos: Ocultar columnas en el control DataGridView Windows Forms mediante el diseñador](hide-columns-in-the-datagrid-using-the-designer.md)
- [Cómo: Crear columnas de solo lectura en el control DataGridView Windows Forms mediante el diseñador](make-columns-read-only-in-the-datagrid-using-the-designer.md)
- [Procedimientos: Crear un proyecto de aplicación de Windows Forms](/visualstudio/ide/step-1-create-a-windows-forms-application-project)
- [Procedimientos: Agregar controles a Windows Forms](how-to-add-controls-to-windows-forms.md)
- [Ventana orígenes de datos](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/6ckyxa83(v=vs.120))
- [Cómo: Mostrar datos relacionados en una aplicación Windows Forms](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/57tx3hhe(v=vs.120))
