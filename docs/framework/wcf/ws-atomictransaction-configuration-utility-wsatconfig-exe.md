---
title: Utilidad de configuración de WS-AtomicTransaction (wsatConfig.exe)
ms.date: 03/30/2017
ms.assetid: 1c56cf98-3963-46d5-a4e1-482deae58c58
ms.openlocfilehash: 161ac59e64e1a933049ed36ebb7140901686929c
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/01/2019
ms.locfileid: "73425268"
---
# <a name="ws-atomictransaction-configuration-utility-wsatconfigexe"></a>Utilidad de configuración de WS-AtomicTransaction (wsatConfig.exe)
La utilidad de configuración de WS-AtomicTransaction se utiliza para configurar valores básicos de compatibilidad de WS-AtomicTransaction.  
  
## <a name="syntax"></a>Sintaxis  
  
```console  
wsatConfig [Options]  
```  
  
## <a name="remarks"></a>Comentarios  
 Esta herramienta de línea de comandos se puede utilizar para configurar sólo los valores WS-AT básicos en un equipo local. Si tiene que configurar los valores en los equipos locales y remotos, debe usar el complemento MMC como se describe en configuración de la [compatibilidad con transacciones WS-Atomic](./feature-details/configuring-ws-atomic-transaction-support.md).  
  
 Puede encontrar la herramienta de línea de comandos en la ubicación de instalación de Windows SDK, específicamente  
  
 %SystemRoot%\Microsoft.Net\Framework\v3.0\Windows Communication Foundation\wsatConfig.exe  
  
 Si está ejecutando [!INCLUDE[wxp](../../../includes/wxp-md.md)] o [!INCLUDE[ws2003](../../../includes/ws2003-md.md)], debe descargar una actualización antes de ejecutar WsatConfig.exe. Para obtener más información acerca de esta actualización, consulte la [actualización de Commerce Server 2007 (KB912817)](https://go.microsoft.com/fwlink/?LinkId=95340) y la [disponibilidad del paquete acumulativo de revisiones de Windows XP com+ 13](https://go.microsoft.com/fwlink/?LinkId=95341).  
  
 La tabla siguiente muestra las opciones que se pueden utilizar con la utilidad de configuración de WS-AtomicTransaction (wsatConfig.exe).  
  
> [!NOTE]
> Al establecer un certificado SSL para un puerto seleccionado, sobrescribe el certificado SSL original asociado a ese puerto, si existe.  
  
|Opciones|Descripción|  
|-------------|-----------------|  
|-accounts: \<account, >|Especifica una lista separada por comas de cuentas que pueden participar en WS-AtomicTransaction. No se comprueba la validez de estas cuentas.|  
|-accountsCerts: \<thumb >&#124;"issuer\subjectname." >|Especifica una lista separada por comas de certificados que pueden participar en WS-AtomicTransaction. Los certificados se indican por huella digital o por el par de Issuer\SubjectName. Utilice {EMPTY} como nombre de sujeto si está vacío.|  
|-endpointCert: < Machine&#124;\<thumb >&#124;"issuer\subjectname." >|Utiliza el certificado de equipo u otro certificado del extremo local especificado por huella digital o par de Issuer\SubjectName. Utiliza {EMPTY} como nombre de sujeto si está vacío.|  
|-maxTimeout: \<sec >|Especifica el tiempo de espera máximo en segundos. Los valores válidos son de 0 a 3600.|  
|-Network: \<enable&#124;deshabilitar >|Habilita o deshabilita la compatibilidad para red de WS-AtomicTransaction.|  
|-Port: \<portNum >|Establece los puertos HTTPS para WS-AtomicTransaction.<br /><br /> Si ya ha habilitado el firewall antes de ejecutar esta herramienta, el puerto se registra automáticamente en la lista de excepciones. Si el firewall está deshabilitado antes de ejecutar esta herramienta, no se configura nada adicional con respecto al firewall.<br /><br /> Si habilita el firewall después de configurar WS-AT, tiene que ejecutar de nuevo esta herramienta y proporcionar el número de puerto mediante este parámetro. Si deshabilita el firewall después de configurar, WS-AT continúa funcionando sin entrada adicional.|  
|-timeout: \<sec >|Especifica el tiempo de espera predeterminado en segundos. Los valores válidos están comprendidos entre 1 y 3600.|  
|-traceActivity: \<enable&#124;deshabilitar >|Habilita o deshabilita el seguimiento de eventos de actividad.|  
|-traceLevel: \<Off&#124;información&#124;&#124; de&#124;ADVERTENCIA&#124;crítica de error&#124;detallado todos los >}|Especifica el nivel de seguimiento.|  
|-tracePII: \<enable&#124;deshabilitar >|Habilita o deshabilita el seguimiento de información de identificación personal.|  
|-traceProp: \<enable&#124;deshabilitar >|Habilita o deshabilita el seguimiento de eventos de propagación.|  
|-restart|Reinicia MSDTC para activar cambios inmediatamente. Si no se especifica esto, los cambios tienen efecto cuando se reinicia MSDTC.|  
|-show|Muestra los valores de protocolo actuales de WS-AtomicTransaction.|  
|-servidorVirtual: \<virtualServer >|Especifica el nombre del clúster de recursos de DTC.|  
  
## <a name="see-also"></a>Vea también

- [Utilización de WS-AtomicTransaction](./feature-details/using-ws-atomictransaction.md)
- [Configuración de la compatibilidad con WS-Atomic Transaction](./feature-details/configuring-ws-atomic-transaction-support.md)
