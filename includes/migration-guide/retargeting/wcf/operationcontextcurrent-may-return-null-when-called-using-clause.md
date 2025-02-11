---
ms.openlocfilehash: 62ba525a28960d96c5458aa1481e1f319d5bc875
ms.sourcegitcommit: d55e14eb63588830c0ba1ea95a24ce6c57ef8c8c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/11/2019
ms.locfileid: "67859370"
---
### <a name="operationcontextcurrent-may-return-null-when-called-in-a-using-clause"></a>Es posible que OperationContext.Current devuelva NULL cuando se llama en una cláusula using.

|   |   |
|---|---|
|Detalles|Es posible que <xref:System.ServiceModel.OperationContext.Current?displayProperty=nameWithType> devuelva <code>null</code> y que se inicie una excepción <xref:System.NullReferenceException> si todas las condiciones siguientes son verdaderas:<ul><li>Se recupera el valor de la propiedad <xref:System.ServiceModel.OperationContext.Current?displayProperty=nameWithType> en un método que devuelve una <xref:System.Threading.Tasks.Task> o <xref:System.Threading.Tasks.Task%601>.</li><li>Se crea una instancia del objeto <xref:System.ServiceModel.OperationContextScope> en una cláusula <code>using</code>.</li><li>Se recupera el valor de la propiedad <xref:System.ServiceModel.OperationContext.Current?displayProperty=nameWithType> dentro de <code>using statement</code>. Por ejemplo:</li></ul><pre><code class="lang-csharp">using (new OperationContextScope(OperationContext.Current))&#13;&#10;{&#13;&#10;OperationContext context = OperationContext.Current;      // OperationContext.Current is null.&#13;&#10;// ...&#13;&#10;}&#13;&#10;</code></pre>|
|Sugerencia|Para solucionar este problema, puede seguir estos pasos:<ul><li>Modifique el código como se indica a continuación para crear una instancia de un objeto <xref:System.ServiceModel.OperationContext.Current%2A> que no sea <code>null</code>:</li></ul><pre><code class="lang-csharp">OperationContext ocx = OperationContext.Current;&#13;&#10;using (new OperationContextScope(OperationContext.Current))&#13;&#10;{&#13;&#10;OperationContext.Current = new OperationContext(ocx.Channel);&#13;&#10;// ...&#13;&#10;}&#13;&#10;</code></pre><ul><li>Instale la actualización más reciente de .NET Framework 4.6.2 o actualice a una versión posterior de .NET Framework. Esto deshabilita el flujo del <xref:System.Threading.ExecutionContext> en <xref:System.ServiceModel.OperationContext.Current?displayProperty=nameWithType> y restaura el comportamiento de las aplicaciones de WCF de .NET Framework 4.6.1 y versiones anteriores. Este comportamiento se puede configurar; equivale a agregar la configuración de aplicación siguiente al archivo de configuración:</li></ul><pre><code class="lang-xml">&lt;appSettings&gt;&#13;&#10;&lt;add key=&quot;Switch.System.ServiceModel.DisableOperationContextAsyncFlow&quot; value=&quot;true&quot; /&gt;&#13;&#10;&lt;/appSettings&gt;&#13;&#10;</code></pre>Si no quiere este cambio y la aplicación depende del flujo del contexto de ejecución entre los contextos de operación, puede habilitar su flujo de esta manera:<pre><code class="lang-xml">&lt;appSettings&gt;&#13;&#10;&lt;add key=&quot;Switch.System.ServiceModel.DisableOperationContextAsyncFlow&quot; value=&quot;false&quot; /&gt;&#13;&#10;&lt;/appSettings&gt;&#13;&#10;</code></pre>|
|Ámbito|Borde|
|Versión|4.6.2|
|Tipo|Redestinación|
|API afectadas|<ul><li><xref:System.ServiceModel.OperationContext.Current?displayProperty=nameWithType></li></ul>|

