---
title: Procedimiento para personalizar una directiva de caché de duración definida
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- time-based cache policies
- customizing time-based cache policies
- cache [.NET Framework], time-based policies
ms.assetid: 8d84f936-2376-4356-9264-03162e0f9279
ms.openlocfilehash: d4a35882d99a87ca5bf22fb386a87158e3c2d664
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59154575"
---
# <a name="how-to-customize-a-time-based-cache-policy"></a><span data-ttu-id="5f733-102">Procedimiento para personalizar una directiva de caché de duración definida</span><span class="sxs-lookup"><span data-stu-id="5f733-102">How to: Customize a Time-Based Cache Policy</span></span>
<span data-ttu-id="5f733-103">Al crear una directiva de caché de duración definida, puede personalizar el comportamiento de almacenamiento en caché. Para ello, especifique valores de antigüedad máxima, actualización mínima, obsolescencia máxima o una fecha de sincronización de caché.</span><span class="sxs-lookup"><span data-stu-id="5f733-103">When creating a time-based cache policy, you can customize caching behavior by specifying values for maximum age, minimum freshness, maximum staleness, or cache synchronization date.</span></span> <span data-ttu-id="5f733-104">El objeto <xref:System.Net.Cache.HttpRequestCachePolicy> proporciona varios constructores que permiten especificar combinaciones válidas de estos valores.</span><span class="sxs-lookup"><span data-stu-id="5f733-104">The <xref:System.Net.Cache.HttpRequestCachePolicy> object provides several constructors that allow you to specify valid combinations of these values.</span></span>  
  
### <a name="to-create-a-time-based-cache-policy-that-uses-a-cache-synchronization-date"></a><span data-ttu-id="5f733-105">Para crear una directiva de caché de duración definida que use una fecha de sincronización de caché</span><span class="sxs-lookup"><span data-stu-id="5f733-105">To create a time-based cache policy that uses a cache synchronization date</span></span>  
  
-   <span data-ttu-id="5f733-106">Para crear una directiva de caché de duración definida que use una fecha de sincronización de caché, pase un objeto <xref:System.DateTime> al constructor <xref:System.Net.Cache.HttpRequestCachePolicy>.</span><span class="sxs-lookup"><span data-stu-id="5f733-106">Create a time-based cache policy that uses a cache synchronization date by passing a <xref:System.DateTime> object to the <xref:System.Net.Cache.HttpRequestCachePolicy> constructor.</span></span>  
  
    ```csharp  
    public static HttpRequestCachePolicy CreateLastSyncPolicy(DateTime when)  
    {  
        HttpRequestCachePolicy policy =   
            new HttpRequestCachePolicy(when);  
        Console.WriteLine("When: {0}", when);  
        Console.WriteLine(policy.ToString());  
        return policy;  
    }  
    ```  
  
    ```vb  
    Public Shared Function CreateLastSyncPolicy([when] As DateTime) As HttpRequestCachePolicy  
        Dim policy As New HttpRequestCachePolicy([when])  
        Console.WriteLine("When: {0}", [when])  
        Console.WriteLine(policy.ToString())  
        Return policy  
    End Function  
    ```  
  
 <span data-ttu-id="5f733-107">La salida será similar a la siguiente:</span><span class="sxs-lookup"><span data-stu-id="5f733-107">The output is similar to the following:</span></span>  
  
```  
When: 1/14/2004 8:07:30 AM  
Level:Default CacheSyncDate:1/14/2004 8:07:30 AM  
```  
  
### <a name="to-create-a-time-based-cache-policy-that-is-based-on-minimum-freshness"></a><span data-ttu-id="5f733-108">Para crear una directiva de caché de duración definida basada en la actualización mínima</span><span class="sxs-lookup"><span data-stu-id="5f733-108">To create a time-based cache policy that is based on minimum freshness</span></span>  
  
-   <span data-ttu-id="5f733-109">Para crear una directiva de caché de duración definida basada en la actualización mínima, especifique <xref:System.Net.Cache.HttpCacheAgeControl.MinFresh> como el valor del parámetro `cacheAgeControl` y pase un objeto <xref:System.TimeSpan> al constructor <xref:System.Net.Cache.HttpRequestCachePolicy>.</span><span class="sxs-lookup"><span data-stu-id="5f733-109">Create a time-based cache policy that is based on minimum freshness by specifying <xref:System.Net.Cache.HttpCacheAgeControl.MinFresh> as the `cacheAgeControl` parameter value and passing a <xref:System.TimeSpan> object to the <xref:System.Net.Cache.HttpRequestCachePolicy> constructor.</span></span>  
  
    ```csharp  
    public static HttpRequestCachePolicy CreateMinFreshPolicy(TimeSpan span)  
    {  
        HttpRequestCachePolicy policy =   
            new HttpRequestCachePolicy(HttpCacheAgeControl.MinFresh, span);  
        Console.WriteLine(policy.ToString());  
        return policy;  
    }  
    ```  
  
    ```vb  
    Public Shared Function CreateMinFreshPolicy(span As TimeSpan) As HttpRequestCachePolicy  
        Dim policy As New HttpRequestCachePolicy(HttpCacheAgeControl.MinFresh, span)  
        Console.WriteLine(policy.ToString())  
        Return policy  
    End Function  
    ```  
  
 <span data-ttu-id="5f733-110">Para la invocación siguiente:</span><span class="sxs-lookup"><span data-stu-id="5f733-110">For the following invocation:</span></span>  
  
```  
CreateMinFreshPolicy(new TimeSpan(1,0,0));  
```  
  
```  
Level:Default MinFresh:3600  
```  
  
### <a name="to-create-a-time-based-cache-policy-that-is-based-on-minimum-freshness-and-maximum-age"></a><span data-ttu-id="5f733-111">Para crear una directiva de caché de duración definida basada en la actualización mínima y la antigüedad máxima</span><span class="sxs-lookup"><span data-stu-id="5f733-111">To create a time-based cache policy that is based on minimum freshness and maximum age</span></span>  
  
-   <span data-ttu-id="5f733-112">Para crear una directiva de caché de duración definida basada en la actualización mínima y la antigüedad máxima, especifique <xref:System.Net.Cache.HttpCacheAgeControl.MaxAgeAndMinFresh> como el valor del parámetro `cacheAgeControl` y pase dos objetos <xref:System.TimeSpan> al constructor <xref:System.Net.Cache.HttpRequestCachePolicy>, uno para especificar la antigüedad máxima de los recursos y otro para especificar la actualización mínima permitida para un objeto devuelto desde la memoria caché.</span><span class="sxs-lookup"><span data-stu-id="5f733-112">Create a time-based cache policy that is based on minimum freshness and maximum age by specifying <xref:System.Net.Cache.HttpCacheAgeControl.MaxAgeAndMinFresh> as the `cacheAgeControl` parameter value and passing two <xref:System.TimeSpan> objects to the <xref:System.Net.Cache.HttpRequestCachePolicy> constructor, one to specify the maximum age for resources and a second to specify the minimum freshness permitted for an object returned from the cache.</span></span>  
  
    ```csharp  
    public static HttpRequestCachePolicy CreateFreshAndAgePolicy(TimeSpan freshMinimum, TimeSpan ageMaximum)  
    {  
        HttpRequestCachePolicy policy =   
        new HttpRequestCachePolicy(HttpCacheAgeControl.MaxAgeAndMinFresh, ageMaximum, freshMinimum);  
        Console.WriteLine(policy.ToString());  
        return policy;  
    }  
    ```  
  
    ```vb  
    Public Shared Function CreateFreshAndAgePolicy(freshMinimum As TimeSpan, ageMaximum As TimeSpan) As HttpRequestCachePolicy  
        Dim policy As New HttpRequestCachePolicy(HttpCacheAgeControl.MaxAgeAndMinFresh, ageMaximum, freshMinimum)  
        Console.WriteLine(policy.ToString())  
        Return policy  
    End Function  
    ```  
  
 <span data-ttu-id="5f733-113">Para la invocación siguiente:</span><span class="sxs-lookup"><span data-stu-id="5f733-113">For the following invocation:</span></span>  
  
```  
CreateFreshAndAgePolicy(new TimeSpan(5,0,0), new TimeSpan(10,0,0));  
```  
  
```  
Level:Default MaxAge:36000 MinFresh:18000  
```  
  
## <a name="see-also"></a><span data-ttu-id="5f733-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="5f733-114">See also</span></span>

- [<span data-ttu-id="5f733-115">Administración de la memoria caché para aplicaciones de red</span><span class="sxs-lookup"><span data-stu-id="5f733-115">Cache Management for Network Applications</span></span>](../../../docs/framework/network-programming/cache-management-for-network-applications.md)
- [<span data-ttu-id="5f733-116">Directiva de caché</span><span class="sxs-lookup"><span data-stu-id="5f733-116">Cache Policy</span></span>](../../../docs/framework/network-programming/cache-policy.md)
- [<span data-ttu-id="5f733-117">Location-Based Cache Policies (Directivas de caché basadas en la ubicación)</span><span class="sxs-lookup"><span data-stu-id="5f733-117">Location-Based Cache Policies</span></span>](../../../docs/framework/network-programming/location-based-cache-policies.md)
- <span data-ttu-id="5f733-118">[Time-Based Cache Policies](../../../docs/framework/network-programming/time-based-cache-policies.md) (Directivas de caché de duración definida)</span><span class="sxs-lookup"><span data-stu-id="5f733-118">[Time-Based Cache Policies](../../../docs/framework/network-programming/time-based-cache-policies.md)</span></span>
- [<span data-ttu-id="5f733-119">Elemento \<requestCaching> (configuración de red)</span><span class="sxs-lookup"><span data-stu-id="5f733-119">\<requestCaching> Element (Network Settings)</span></span>](../../../docs/framework/configure-apps/file-schema/network/requestcaching-element-network-settings.md)
