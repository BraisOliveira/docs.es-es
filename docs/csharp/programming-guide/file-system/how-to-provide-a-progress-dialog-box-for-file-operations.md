---
title: 'Procedimiento Proporcionar un cuadro de diálogo de progreso para operaciones de archivos: Guía de programación de C#'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- progress dialog [C#]
ms.assetid: 01b71fe7-8178-4dc8-aeb1-12053be7b51c
ms.openlocfilehash: 028e779f3cd8a17f162a79791b0c84abae14cf44
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/19/2019
ms.locfileid: "69590049"
---
# <a name="how-to-provide-a-progress-dialog-box-for-file-operations-c-programming-guide"></a>Procedimiento Proporcionar un cuadro de diálogo de progreso para operaciones de archivos (Guía de programación de C#)
Puede proporcionar un cuadro de diálogo estándar que muestra el progreso en las operaciones de archivo en Windows si usa el método <xref:Microsoft.VisualBasic.FileIO.FileSystem.CopyFile%28System.String%2CSystem.String%2CMicrosoft.VisualBasic.FileIO.UIOption%29> en el espacio de nombres <xref:Microsoft.VisualBasic?displayProperty=nameWithType>.  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-add-a-reference-in-visual-studio"></a>Para agregar una referencia en Visual Studio  
  
1. En la barra de menús, elija **Proyecto**, **Agregar referencia**.  
  
     Aparecerá el cuadro de diálogo **Administrador de referencias**.  
  
2. En el área **Ensamblados**, elija **Framework** si no está ya seleccionado.  
  
3. En la lista de nombres, seleccione la casilla **Microsoft.VisualBasic** y elija el botón **Aceptar** para cerrar el cuadro de diálogo.  
  
## <a name="example"></a>Ejemplo  
 El siguiente código copia el directorio que especifica `sourcePath` en el directorio que especifica `destinationPath`. Este código también proporciona un cuadro de diálogo estándar en el que se muestra el tiempo estimado restante antes de que finalice la operación.  
  
 [!code-csharp[csFilesandFolders#11](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csFilesAndFolders/CS/FileIteration.cs#11)]  
  
## <a name="see-also"></a>Vea también

- [Registro y sistema de archivos (Guía de programación de C#)](./index.md)
