---
title: <assert> (Elemento)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/assert
- http://schemas.microsoft.com/.NetConfiguration/v2.0#assert
helpviewer_keywords:
- <assert> element
- assert element
ms.assetid: ef4c3229-b151-4d85-8091-e6456af9b935
ms.openlocfilehash: 30ec24aefcf8c4d1e110238a2c60a958eded5545
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/01/2019
ms.locfileid: "71699387"
---
# <a name="assert-element"></a>\<assert >, elemento
Especifica si se muestra un cuadro de mensaje cuando se llama al método <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>; también indica el nombre del archivo para el que se van a escribir los mensajes.  
  
[ **\<configuration>** ](../configuration-element.md)  
&nbsp; @ no__t-1[ **\<System. diagnostics >** ](system-diagnostics-element.md)  
&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 **\<assert >**  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<assert assertuienabled="true|false" logfilename="file name"/>  
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|Descripción|  
|---------------|-----------------|  
|`assertuienabled`|Atributo opcional.<br /><br /> Especifica si se va a mostrar un cuadro de mensaje cuando el método **Debug. Assert** se evalúe como **false**.|  
|`logfilename`|Atributo opcional.<br /><br /> Especifica el nombre del archivo en el que se va a escribir el mensaje si **Debug. Assert** se evalúa como **false**.|  
  
## <a name="assertuienabled-attribute"></a>Atributo assertuienabled  
  
|Valor|Descripción|  
|-----------|-----------------|  
|`true`|Muestra el cuadro de mensaje. Este es el valor predeterminado.|  
|`false`|No muestra el cuadro de mensaje.|  
  
### <a name="child-elements"></a>Elementos secundarios  
 Ninguno.  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|`configuration`|Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.|  
|`system.diagnostics`|Especifica los agentes de escucha de seguimiento que recopilan, almacenan y enrutan mensajes, así como el nivel en el que está establecido un modificador de seguimiento.|  
  
## <a name="remarks"></a>Comentarios  
 Ambos atributos del elemento **> \<assert** son opcionales. Puede deshabilitar los cuadros de mensaje sin especificar un archivo en el que escribir los mensajes, o puede especificar un archivo en el que escribir los mensajes mientras se deshabilitan los cuadros de mensaje.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra cómo deshabilitar la visualización de cuadros de mensaje cuando se llama a **Debug. Assert** y se escriben los mensajes en `c:\log.txt`.  
  
```xml  
<configuration>  
   <system.diagnostics>  
      <assert assertuienabled="false" logfilename="c:\log.txt"/>  
   </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a>Vea también

- <xref:System.Diagnostics.Debug>
- [Esquema de la configuración de seguimiento y depuración](index.md)
