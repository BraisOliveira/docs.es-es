---
title: directivas de caché basadas en la ubicación
ms.date: 03/30/2017
helpviewer_keywords:
- Cache If Available policy
- reload policy
- location-based cache policies
- Cache Only policy
- local cache
- intermediate cache
- No Cache No Store policy
- cache [.NET Framework], location-based policies
- Revalidate policy
- freshness of cached resources
- Cache Or Next Cache Only policy
- Refresh policy
ms.assetid: e41d7f1a-0a6a-4dee-97d1-c6a8b6a07fc2
ms.openlocfilehash: e6896452fce89f69b40f1d03332355df72d93211
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/17/2019
ms.locfileid: "71047665"
---
# <a name="location-based-cache-policies"></a>directivas de caché basadas en la ubicación
Una directiva de caché basada en la ubicación define la actualización de las entradas válidas almacenadas en caché en función de dónde se puede obtener el recurso solicitado. Un recurso almacenado en caché es válido si al usarlo no se infringen los requisitos de revalidación especificados por el servidor. Una directiva de caché basada en la ubicación se crea mediante programación con un constructor de clase <xref:System.Net.Cache.RequestCachePolicy> o <xref:System.Net.Cache.HttpRequestCachePolicy>. El tipo de la directiva basada en la ubicación se pasa al constructor con un valor de enumeración <xref:System.Net.Cache.RequestCacheLevel> o <xref:System.Net.Cache.HttpRequestCacheLevel>. Para obtener ejemplos de código en los que se crean directivas de caché basadas en ubicación, vea [Cómo: Establecer en una aplicación una directiva de caché basada en la ubicación](how-to-set-a-location-based-cache-policy-for-an-application.md). En las secciones siguientes se explica cada tipo de directiva de caché basada en la ubicación para recursos del Protocolo de transferencia de hipertexto (http y https).  
  
## <a name="cache-if-available-policy"></a>Directiva de caché si está disponible  
 Si un recurso solicitado válido se encuentra en la caché local, se usa el recurso almacenado en caché; en caso contrario, la solicitud del recurso se envía al servidor. Si el recurso solicitado está disponible en cualquier caché entre el cliente y el servidor, una caché intermedia puede atender a la solicitud.  
  
## <a name="cache-only-policy"></a>Directiva de solo caché  
 Si un recurso solicitado válido se encuentra en la caché local, se usa el recurso almacenado en caché. Cuando se especifica este nivel de directiva de caché, se produce una excepción <xref:System.Net.WebException> si el elemento no está en la caché local.  
  
## <a name="cache-or-next-cache-only-policy"></a>Directiva de caché o solo siguiente caché  
 Si un recurso solicitado válido se encuentra en la caché local o en una caché intermedia en la red de área local, se usa el recurso almacenado en caché. En caso contrario, se producirá una excepción <xref:System.Net.WebException>. En el protocolo de almacenamiento en caché HTTP, esto se logra mediante el uso de la directiva de control de caché "only-if-cached".  
  
## <a name="no-cache-no-store-policy"></a>Directiva de ninguna directiva ningún almacén  
 Un recurso solicitado no se usa nunca de una caché y no se coloca nunca en una caché. Si un recurso solicitado está presente en la caché local, se quita. Este nivel de directiva les indica a las memorias caché intermedias que también deben quitar el recurso. En el protocolo de almacenamiento en caché HTTP, esto se logra mediante el uso de la directiva de control de caché "no-store".  
  
## <a name="refresh-policy"></a>Actualizar directiva  
 Un recurso solicitado se puede usar si se obtiene del servidor o si se encuentra en una caché distinta de la caché local. Antes de que una caché intermedia pueda atender a la solicitud, esa caché debe revalidar su entrada almacenada en caché con el servidor. En el protocolo de almacenamiento en caché HTTP, esto se logra mediante el uso de la directiva de control de caché "max-age = 0" y el encabezado Pragma "no-cache".  
  
## <a name="reload-policy"></a>volver a cargar directiva  
 Los recursos solicitados deben obtenerse del servidor. La respuesta podría estar guardada en la caché local. En el protocolo de almacenamiento en caché HTTP, esto se logra mediante el uso de la directiva de control de caché "no-cache" y el encabezado Pragma "no-cache".  
  
## <a name="revalidate-policy"></a>Revalidar directiva  
 Compara la copia del recurso en la caché con la copia en el servidor. Si la copia en el servidor es más reciente, se usa para atender a la solicitud y reemplaza a la copia en la caché. Si la copia en la caché es la misma que la del servidor, se usa la copia almacenada en caché. En el protocolo de almacenamiento en caché HTTP, esto se logra mediante una solicitud condicional.  
  
## <a name="see-also"></a>Vea también

- [Administración de la memoria caché para aplicaciones de red](cache-management-for-network-applications.md)
- [Directiva de caché](cache-policy.md)
- [Time-Based Cache Policies](time-based-cache-policies.md) (Directivas de caché de duración definida)
- [Configurar el almacenamiento en caché de las aplicaciones de red](configuring-caching-in-network-applications.md)
- [Elemento \<requestCaching> (configuración de red)](../configure-apps/file-schema/network/requestcaching-element-network-settings.md)
