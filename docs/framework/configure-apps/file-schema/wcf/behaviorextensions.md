---
title: <behaviorExtensions>
ms.date: 03/30/2017
ms.assetid: 59f2791a-c78f-40d7-aa80-0d9cd10135d9
ms.openlocfilehash: bcf1f1dcdba50c3e7fba8eb170132d0cf47c4271
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69919814"
---
# <a name="behaviorextensions"></a>\<> behaviorExtensions
Las extensiones de comportamiento le permiten al usuario crear los elementos de comportamiento definidos por el usuario. Estos elementos se pueden utilizar junto a los elementos de comportamiento de Windows Communication Foundation (WCF) estándares. La sección `behaviorExtensions` define el elemento tal como se puede utilizar en configuración. Éste es un ejemplo de una extensión de comportamiento típica.  
  
```xml  
<system.serviceModel>
  <extensions>
    <behaviorExtensions>
      <add name="myBehavior"
           type="Microsoft.ServiceModel.Samples.MyBehaviorSection, MyBehavior,
                 Version=1.0.0.0, Culture=neutral, PublicKeyToken=null" />
    </behaviorExtensions>
  </extensions>
</system.serviceModel>
```  
  
 Para agregar capacidades de configuración al elemento, necesita escribir y registrar un elemento de configuración. Para obtener más información, consulte la documentación existente sobre <xref:System.Configuration>.  
  
 Después de la definición del elemento y de su tipo de configuración, se puede utilizar la extensión como se muestra en el ejemplo siguiente.  
  
```xml  
<behaviors>
  <behavior configurationName="testChannelBehavior">
    <myBehavior />
    <channelSecurity cacheCookies="false"
                     detectReplays="false"
                     maxCachedNonces="9"
                     maxClockSkew="00:00:03"
                     maxCookieCachingTime="00:07:24"
                     replayWindow="00:07:22.2190000" />
  </behavior>
</behaviors>
```  
  
## <a name="security"></a>Seguridad  
 Se recomienda fuertemente que utilice nombres de ensamblado completo al registrar los tipos en los archivos `machine.config` y `app.config`. Si no se define el tipo singularmente, el cargador de tipo CLR lo busca en las ubicaciones siguientes en el orden especificado:  
  
 Si se conoce el ensamblado del tipo, el cargador busca en las ubicaciones de la redirección del archivo de configuración GAC, el ensamblado actual utilizando información de configuración, y el directorio base de la aplicación. Si el ensamblado es desconocido, el cargador busca en el ensamblado actual, mscorlib y la ubicación devueltos por el controlador de eventos `TypeResolve`. Este orden de búsqueda de CLR se puede modificar con enlaces como el mecanismo de Tipo Reenvío y el evento AppDomain.TypeResolve.  
  
 Un atacante se puede aprovechar del orden de búsqueda de CLR y ejecutar un código desautorizado. Al utilizar los nombres completos (seguros) sólo se identifica un tipo y aumenta la seguridad de su sistema.  
  
 Para obtener más información, vea [cómo el motor en tiempo de ejecución ubica ensamblados](https://go.microsoft.com/fwlink/?LinkId=95336) y <xref:System.AppDomain.TypeResolve>.  
  
## <a name="see-also"></a>Vea también

- <xref:System.ServiceModel.Configuration.BehaviorExtensionElement>
- [Configuración y extensión del tiempo de ejecución con comportamientos](../../../wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md)
