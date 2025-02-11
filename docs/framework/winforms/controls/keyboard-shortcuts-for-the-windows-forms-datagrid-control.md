---
title: Métodos abreviados de teclado para el control DataGrid de formularios Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- keyboard shortcuts [Windows Forms], DataGrid control
- DataGrid control [Windows Forms], navigation keys
ms.assetid: a01780f9-20d5-4f5f-808f-c790c9a007a5
ms.openlocfilehash: 6b4d566d377a3cda73bf8422caa798134d356f63
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69962570"
---
# <a name="keyboard-shortcuts-for-the-windows-forms-datagrid-control"></a>Métodos abreviados de teclado para el control DataGrid de formularios Windows Forms
> [!NOTE]
> El control <xref:System.Windows.Forms.DataGridView> reemplaza y agrega funcionalidad al control <xref:System.Windows.Forms.DataGrid>; sin embargo, el control <xref:System.Windows.Forms.DataGrid> se conserva a efectos de compatibilidad con versiones anteriores y uso futuro, en su caso. Para obtener más información, consulte [Differences Between the Windows Forms DataGridView and DataGrid Controls](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md) (Diferencias entre los controles DataGridView y DataGrid de formularios Windows Forms).  
  
 En la tabla siguiente se enumeran los métodos abreviados de teclado que se pueden usar <xref:System.Windows.Forms.DataGrid> para la navegación dentro del control Windows Forms:  
  
|.|Método abreviado|  
|------------|--------------|  
|Complete una entrada de celda y desplácese hacia abajo hasta la celda siguiente.<br /><br /> Si el foco está en un vínculo de tabla secundaria, vaya a esa tabla.|ENTRAR|  
|Cancela la edición de celdas si está en modo de edición de celda.<br /><br /> Si está en la selección de marquesina, cancele la edición en la fila.|ESC|  
|Elimine el carácter situado delante del punto de inserción al editar una celda.|RETROCESO|  
|Elimine el carácter situado después del punto de inserción al editar una celda.|SUPRIMIR|  
|Moverse a la primera celda de la fila actual.|INICIO|  
|Moverse a la última celda de la fila actual.|FIN|  
|Resaltar caracteres en la celda actual y colocar el punto de inserción al final de la línea. El mismo comportamiento que si se hace doble clic en una celda.|F2|  
|Si el foco está en una celda, desplazarse a la siguiente celda de la fila.<br /><br /> Si el foco está en la última celda de una fila, desplácese hasta el primer vínculo de tabla secundaria de la fila y expándalo.<br /><br /> Si el foco está en un vínculo secundario, desplácese al siguiente vínculo secundario.<br /><br /> Si el foco está en el último vínculo secundario, desplazarse a la primera celda de la fila siguiente.|TAB|  
|Si el foco está en una celda, desplazarse a la celda anterior de la fila.<br /><br /> Si el foco está en la primera celda de una fila, desplazarse hasta el último vínculo de tabla secundaria expandida de la fila anterior o desplazarse a la última celda de la fila anterior.<br /><br /> Si el foco está en un vínculo secundario, desplácese al vínculo secundario anterior.<br /><br /> Si el foco está en el primer vínculo secundario, desplazarse a la última celda de la fila anterior.|MAYÚS+TAB|  
|Moverse al siguiente control en el orden de tabulación.|CTRL+TAB|  
|Moverse al control anterior en el orden de tabulación.|CTRL+MAYÚS+TAB|  
|Subir a la tabla primaria si se trata de una tabla secundaria. El mismo comportamiento que al hacer clic en el botón atrás.|ALT+FLECHA IZQUIERDA|  
|Expanda vínculos de tabla secundaria. ALT + Flecha abajo expande todos los vínculos, no solo los seleccionados.|ALT + Flecha abajo o CTRL + signo más|  
|Contraer vínculos de tablas secundarias. ALT + Flecha arriba contrae todos los vínculos, no solo los seleccionados.|ALT + Flecha arriba o CTRL + signo menos|  
|Desplácese a la celda en blanco más alejada en la dirección de la flecha.|CTRL + FLECHA|  
|Extiende la selección una fila en la dirección de la flecha (excluyendo los vínculos de la tabla secundaria).|MAYÚS + FLECHA ARRIBA/ABAJO|  
|Extienda la selección hasta la fila que no esté en blanco más lejos en la dirección de la flecha (excepto los vínculos de tabla secundaria).|CTRL + MAYÚS + FLECHA ARRIBA/ABAJO|  
|Desplácese a la celda superior izquierda.|CTRL + INICIO|  
|Desplácese a la celda inferior derecha.|CTRL + FIN|  
|Extiende la selección a la fila superior.|CTRL + MAYÚS + INICIO|  
|Extiende la selección a la fila inferior.|CTRL + MAYÚS + FIN|  
|Seleccione la fila actual (excluyendo los vínculos de tabla secundaria).|MAYÚS + BARRA ESPACIADORA|  
|Seleccione toda la cuadrícula (excluyendo los vínculos de tabla secundaria).|CTRL+A|  
|Mostrar la fila primaria cuando se está en una tabla secundaria.|CTRL+AV PÁG|  
|Oculte la fila primaria en una tabla secundaria.|CTRL+RE PÁG|  
|Ampliar la selección una pantalla (excepto los vínculos de tabla secundaria).|MAYÚS+AV PÁG|  
|Extender la selección una pantalla hacia arriba (excepto los vínculos de tabla secundaria).|MAYÚS+RE PÁG|  
|Llame al <xref:System.Windows.Forms.DataGrid.EndEdit%2A> método para la fila actual.|CTRL+ENTRAR|  
|Escriba un <xref:System.DBNull.Value?displayProperty=nameWithType> valor en una celda en el modo de edición.|CTRL+0|  
  
## <a name="see-also"></a>Vea también

- [Información general del control DataGrid](datagrid-control-overview-windows-forms.md)
- [DataGrid (control)](datagrid-control-windows-forms.md)
