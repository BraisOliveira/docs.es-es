---
title: -win32manifest (Visual Basic)
ms.date: 03/13/2018
helpviewer_keywords:
- /win32manifest compiler option [Visual Basic]
- win32manifest compiler option [Visual Basic]
- -win32manifest compiler option [Visual Basic]
ms.assetid: 9e3191b4-90db-41c8-966a-28036fd20005
ms.openlocfilehash: cae6b34aadf6698a337e52aa1ea1ce44206836ac
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/07/2019
ms.locfileid: "72004628"
---
# <a name="-win32manifest-visual-basic"></a>-win32manifest (Visual Basic)
Identifica un archivo de manifiesto de la aplicación Win32 definido por el usuario que se va a insertar en un archivo ejecutable portable (PE) del proyecto.  
  
## <a name="syntax"></a>Sintaxis  
  
```console  
-win32manifest: fileName  
```  
  
## <a name="arguments"></a>Argumentos  
  
|Término|Definición|  
|---|---|  
|`fileName`|Ruta de acceso del archivo de manifiesto personalizado.|  
  
## <a name="remarks"></a>Comentarios  
 De forma predeterminada, el compilador Visual Basic inserta un manifiesto de aplicación que especifica un nivel de ejecución solicitado de AsInvoker. Crea el manifiesto en la misma carpeta en la que se compila el archivo ejecutable, normalmente la carpeta bin\Debug o bin\Release cuando se usa Visual Studio. Si desea proporcionar un manifiesto personalizado, por ejemplo, para especificar un nivel de ejecución solicitado de highestAvailable o requireAdministrator, use esta opción para especificar el nombre del archivo.  
  
> [!NOTE]
> Esta opción y la opción [-Win32Resource](../../../visual-basic/reference/command-line-compiler/win32resource.md) son mutuamente excluyentes. Si intenta usar ambas opciones en la misma línea de comandos, obtendrá un error de compilación.  
  
 Una aplicación sin manifiesto de aplicación que especifique un nivel de ejecución solicitado estará sujeta a virtualización de archivos y Registro conforme a la característica Control de cuentas de usuario de Windows Vista. Para más información sobre la virtualización, vea [Implementación de ClickOnce en Windows Vista](/visualstudio/deployment/clickonce-deployment-on-windows-vista).  
  
 La aplicación estará sujeta a la virtualización si se cumple alguna de las siguientes condiciones:  
  
1. Use la opción `-nowin32manifest` y no proporcione un manifiesto en un paso de compilación posterior o como parte de un archivo de recursos de Windows (. res) mediante la opción `-win32resource`.  
  
2. Se proporciona un manifiesto personalizado que no especifica un nivel de ejecución solicitado.  
  
 Visual Studio crea un archivo de manifiesto predeterminado y lo almacena en los directorios de depuración y versión junto con el archivo ejecutable. Para ver o editar el archivo app. manifest predeterminado, haga clic en **Ver configuración de UAC** en la pestaña **aplicación** del diseñador de proyectos. Para obtener más información, consulte [Application Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic).  
  
 Puede proporcionar el manifiesto de aplicación como un paso personalizado posterior a la compilación o como parte de un archivo de recursos de Win32 mediante la opción `-nowin32manifest`. Use esa misma opción si quiere que la aplicación esté sujeta a virtualización de archivos y Registro en Windows Vista. Esto impedirá que el compilador cree e inserte un manifiesto predeterminado en el archivo PE.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra el manifiesto predeterminado que el compilador Visual Basic inserta en un PE.  
  
> [!NOTE]
> El compilador inserta un nombre de aplicación estándar, la aplicación en el XML de manifiesto. Se trata de una solución alternativa para permitir que las aplicaciones se ejecuten en Windows Server 2003 Service Pack 3.  
  
```xml  
<?xml version="1.0" encoding="utf-8" standalone="yes"?>  
<assembly xmlns="urn:schemas-microsoft-com:asm.v1" manifestVersion="1.0">  
  <assemblyIdentity version="1.0.0.0" name="MyApplication.app"/>  
  <trustInfo xmlns="urn:schemas-microsoft-com:asm.v2">  
    <security>  
      <requestedPrivileges xmlns="urn:schemas-microsoft-com:asm.v3">  
        <requestedExecutionLevel level="asInvoker"/>  
      </requestedPrivileges>  
    </security>  
  </trustInfo>  
</assembly>  
```  
  
## <a name="see-also"></a>Vea también

- [Compilador de línea de comandos de Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)
- [-nowin32manifest (Visual Basic)](../../../visual-basic/reference/command-line-compiler/nowin32manifest.md)
