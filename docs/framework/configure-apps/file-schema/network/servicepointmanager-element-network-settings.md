---
title: Elemento <servicePointManager> (configuración de red)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#servicePointManager
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/settings/servicePointManager
helpviewer_keywords:
- servicePointManager element
- <servicePointManager> element
ms.assetid: 6e5def51-3646-4ef6-a7bd-c69151321bec
ms.openlocfilehash: 95ad1880cbb832a17311e7e63e9203f53257f65f
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/01/2019
ms.locfileid: "71697716"
---
# <a name="servicepointmanager-element-network-settings"></a>\<servicePointManager (elemento >) (configuración de red)
Configura las conexiones a los recursos de red.  
  
[ **\<configuration>** ](../configuration-element.md)  
&nbsp; @ no__t-1[ **@no__t -4System. net >** ](system-net-element-network-settings.md)  
&nbsp; @ no__t-1 @ no__t-2 @ no__t-3[ **\<settings >** ](settings-element-network-settings.md)  
&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 @ no__t-4 @ no__t-5 **\<servicePointManager >**  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<servicePointManager  
  checkCertificateName="true|false"  
  checkCertificateRevocationList="true|false"  
  encryptionPolicy="AllowNoEncryption|NoEncryption|RequireEncryption"  
  expect100Continue="true|false"  
  useNagleAlgorithm="true|false"  
  enableDnsRoundRobin="true|false"  
  dnsRefreshTimeout="time"  
/>  
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|**Attribute**|**Descripción**|  
|-------------------|---------------------|  
|`checkCertificateName`|Especifica si el sistema debe comprobar que el nombre del certificado coincide con el nombre de host del servidor antes de usar el certificado. El valor predeterminado es `true`.|  
|`checkCertificateRevocationList`|Especifica si el sistema debe comprobar si el certificado se ha revocado antes de utilizar el certificado. El valor predeterminado es `false`.|  
|`dnsRefreshTimeout`|Especifica cuánto tiempo se almacenan en caché las resoluciones del servicio de nombres de dominio (DNS) junto con la opción Round Robin de DNS, en milisegundos. El valor predeterminado es 120.000 milisegundos (dos minutos).|  
|`enableDnsRoundRobin`|Especifica si las resoluciones DNS de los nombres de host con varias direcciones IP (Protocolo de Internet) devuelven todas las direcciones, o solo la primera. El valor predeterminado es `false`.|  
|`encryptionPolicy`|Especifica la Directiva de cifrado que se aplica a una sesión de SSL/TLS en una instancia de <xref:System.Net.ServicePointManager>. Los valores posibles son equivalentes a los valores de la enumeración <xref:System.Net.Security.EncryptionPolicy>. El uso de <xref:System.Security.Authentication.CipherAlgorithmType.Null> es necesario cuando la Directiva de cifrado se establece en `NoEncryption`. El valor predeterminado es `RequireEncryption`.|  
|`expect100Continue`|Especifica si los métodos POST deben esperar recibir una respuesta `100-continue` del servidor. El valor predeterminado es `true`.|  
|`useNagleAlgorithm`|Especifica si las conexiones controladas por el administrador de puntos de servicio usan el algoritmo de Nagle. El valor predeterminado es `true`.|  
  
### <a name="child-elements"></a>Elementos secundarios  
 Ninguno.  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|**Element**|**Descripción**|  
|-----------------|---------------------|  
|[Configuración](settings-element-network-settings.md)|Configura opciones de red básicas para el espacio de nombres <xref:System.Net>.|  
  
## <a name="remarks"></a>Comentarios  
  
## <a name="configuration-files"></a>Archivos de configuración  
 Este elemento se puede usar en el archivo de configuración de la aplicación o en el archivo de configuración del equipo (Machine.config).  
  
## <a name="see-also"></a>Vea también

- <xref:System.Net.ServicePointManager>
- <xref:System.Net.Security.EncryptionPolicy>
- [Esquema de la configuración de red](index.md)
