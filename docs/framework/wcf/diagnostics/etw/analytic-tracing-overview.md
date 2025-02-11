---
title: Información general de traza analítica
ms.date: 03/30/2017
helpviewer_keywords:
- analytic tracing [WCF], overview
ms.assetid: ae55e9cc-0809-442f-921f-d644290ebf15
ms.openlocfilehash: 6170accc01e837bba0afb446f67a6c6272e7dde7
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798204"
---
# <a name="analytic-tracing-overview"></a>Información general de traza analítica
La traza analítica en [!INCLUDE[netfx_current_long](../../../../../includes/netfx-current-long-md.md)] es una característica de traza de alto rendimiento y bajo nivel de detalle establecida en Seguimiento de eventos para Windows (ETW). ETW se ejecuta en el kernel para reducir en gran medida la sobrecarga de las operaciones de traza. Almacena en búfer eventos de usuario y en modo kernel, y permite una habilitación dinámica del registro sin requerir un reinicio del servicio. Los datos de la traza están disponibles en los registros de eventos una vez emitidos y recibidos.  
  
 Para obtener más información sobre ETW, vea [mejorar la depuración y el ajuste del rendimiento con ETW](https://go.microsoft.com/fwlink/?LinkId=164781).  
  
 Además de usar registros de eventos del sistema Windows, de seguridad y de la aplicación para analizar la aplicación, [!INCLUDE[wv](../../../../../includes/wv-md.md)] y [!INCLUDE[lserver](../../../../../includes/lserver-md.md)] introducen registros adicionales en el nodo superior de registros de servicios y aplicaciones. El propósito de estos nuevos registros es almacenar eventos para una aplicación determinada o un componente concreto en lugar de los eventos globales que tienen un impacto en todo el sistema (como el tipo de eventos que el registro de eventos de seguridad podría grabar). [!INCLUDE[netfx_current_short](../../../../../includes/netfx-current-short-md.md)]unifica y correlaciona el registro de eventos de seguimiento de WCF, los registros de mensajes de [!INCLUDE[wf1](../../../../../includes/wf1-md.md)] WCF y los registros de seguimiento en los registros de servicios y aplicaciones.  
  
## <a name="concepts-and-capabilities"></a>Conceptos y capacidades  
 Los siguientes conceptos y capacidades se aplican a la traza analítica de WCF.  
  
### <a name="enabling-wcf-diagnostics-settings"></a>Habilitar la configuración de diagnóstico de WCF  
 Los diagnósticos de WCF se \<habilitan en la\<sección configuración de System. ServiceModel > Diagnostics >.  
  
```xml  
<system.serviceModel>  
  <diagnostics>  
```  
  
 La configuración de diagnóstico de WCF para una aplicación virtual de IIS hospedada en web se habilita en el archivo Web.config. Otra opción es crear Web.config en un subdirectorio dentro de la aplicación.  Esta opción aplica la configuración a todos los servicios dentro de un subdirectorio.  Para asegurarse de que la configuración de diagnóstico se inicializa de forma coherente para todos los servicios dentro de la aplicación, la configuración debería estar dentro de Web.config en el directorio de aplicaciones, y no en uno de los subdirectorios individuales dentro de la aplicación.  
  
### <a name="channels"></a>Canales  
 ETW permite a los componentes de software dirigir eventos de traza a una audiencia determinada mediante el empleo de canales. Por ejemplo, puede enviar eventos para los administradores del sistema a un canal, y eventos importantes para los desarrolladores de aplicaciones a otro canal. Los canales se denominan y se registran con Windows para que los consumidores puedan ver los eventos de un canal mediante el visor de eventos.  
  
 La característica de seguimiento analítico para WCF [!INCLUDE[netfx_current_short](../../../../../includes/netfx-current-short-md.md)] en escribe en el canal Microsoft-Windows-Application-Server-Applications. Este canal está diseñado específicamente para los usuarios que desean supervisar el estado de los servicios WCF en producción. Define un pequeño conjunto de eventos que se puede usar en muchos casos de supervisión de estado y solución de problemas.  
  
 Para habilitar el manifiesto Seguimiento de eventos para Windows de modo que los mensajes se descodifiquen de forma apropiada en el registro de eventos, use la herramienta ServiceModelReg en la línea de comandos, como se indica a continuación:  
  
 `ServiceModelReg.exe -i -c:etw`  
  
### <a name="dynamic-configuration"></a>Configuración dinámica  
 La infraestructura de ETW permite habilitar la traza y configurarla de forma dinámica mediante herramientas Windows estándar. Para obtener más información, consulte [Habilitar dinámicamente la traza analítica](dynamically-enabling-analytic-tracing.md).  
  
### <a name="message-flow-tracing"></a>Traza de flujo de mensajes  
 Para obtener más información sobre cómo habilitar el seguimiento del flujo de mensajes, vea [configurar el seguimiento del flujo de mensajes](configuring-message-flow-tracing.md).  
  
### <a name="keywords"></a>Palabras clave  
 Las palabras clave se usan para filtrar los mensajes de seguimiento y definir qué componente de la .NET Framework emitió el evento. Para obtener más información, consulte [Habilitar dinámicamente la traza analítica](dynamically-enabling-analytic-tracing.md).
