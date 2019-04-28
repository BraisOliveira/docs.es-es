---
title: Elemento <remove> para <namedCaches>
ms.date: 03/30/2017
helpviewer_keywords:
- remove element for namedCaches
- <remove> element for namedCaches
ms.assetid: 24211ea5-163e-4fe5-aed8-004d8499760c
ms.openlocfilehash: 053e2776153489dfdd61547fdc039980646ae697
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61704731"
---
# <a name="remove-element-for-namedcaches"></a><span data-ttu-id="d6f09-102">\<Quitar > (elemento) para \<namedCaches ></span><span class="sxs-lookup"><span data-stu-id="d6f09-102">\<remove> Element for \<namedCaches></span></span>
<span data-ttu-id="d6f09-103">Quita una entrada de caché con nombre de la colección `namedCaches` de una caché en memoria.</span><span class="sxs-lookup"><span data-stu-id="d6f09-103">Removes a named cache entry from the `namedCaches` collection for a memory cache.</span></span>  
  
 <span data-ttu-id="d6f09-104">\<system.runtime.caching></span><span class="sxs-lookup"><span data-stu-id="d6f09-104">\<system.runtime.caching></span></span>  
<span data-ttu-id="d6f09-105">\<memoryCache></span><span class="sxs-lookup"><span data-stu-id="d6f09-105">\<memoryCache></span></span>  
<span data-ttu-id="d6f09-106">\<namedCaches></span><span class="sxs-lookup"><span data-stu-id="d6f09-106">\<namedCaches></span></span>  
<span data-ttu-id="d6f09-107">\<remove></span><span class="sxs-lookup"><span data-stu-id="d6f09-107">\<remove></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d6f09-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d6f09-108">Syntax</span></span>  
  
```xml  
<namedCaches>  
    <remove name="default" />  
    <!-- child elements -->  
 </namedCaches>  
```  
  
## <a name="type"></a><span data-ttu-id="d6f09-109">Tipo</span><span class="sxs-lookup"><span data-stu-id="d6f09-109">Type</span></span>  
 `None`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d6f09-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="d6f09-110">Attributes and Elements</span></span>  
 <span data-ttu-id="d6f09-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="d6f09-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d6f09-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="d6f09-112">Attributes</span></span>  
 `None`  
  
### <a name="child-elements"></a><span data-ttu-id="d6f09-113">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="d6f09-113">Child Elements</span></span>  
 `None`  
  
### <a name="parent-elements"></a><span data-ttu-id="d6f09-114">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="d6f09-114">Parent Elements</span></span>  
  
|<span data-ttu-id="d6f09-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="d6f09-115">Element</span></span>|<span data-ttu-id="d6f09-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="d6f09-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d6f09-117">\<namedCaches></span><span class="sxs-lookup"><span data-stu-id="d6f09-117">\<namedCaches></span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/namedcaches-element-cache-settings.md)|<span data-ttu-id="d6f09-118">Contiene una colección de valores de configuración para la instancia con nombre <xref:System.Runtime.Caching.MemoryCache> instancias.</span><span class="sxs-lookup"><span data-stu-id="d6f09-118">Contains a collection of configuration settings for the named <xref:System.Runtime.Caching.MemoryCache> instances.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d6f09-119">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d6f09-119">Remarks</span></span>  
 <span data-ttu-id="d6f09-120">El `remove` elemento quita un `namedCache` entrada de la colección de caché con nombre de una memoria caché.</span><span class="sxs-lookup"><span data-stu-id="d6f09-120">The `remove` element removes a `namedCache` entry from the named cache collection for a memory cache.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d6f09-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="d6f09-121">See also</span></span>

- [<span data-ttu-id="d6f09-122">\<namedCaches > elemento (configuración de caché)</span><span class="sxs-lookup"><span data-stu-id="d6f09-122">\<namedCaches> Element (Cache Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/namedcaches-element-cache-settings.md)
