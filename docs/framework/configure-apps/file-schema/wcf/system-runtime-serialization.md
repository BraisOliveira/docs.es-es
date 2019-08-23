---
title: <system.runtime.serialization>
ms.date: 03/30/2017
ms.assetid: a8cebf4c-06d2-4667-8f5b-c3e1fc90df6f
ms.openlocfilehash: 4ec5cd19ccdc5c21a3caf426520d51442dc5ab3f
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69938925"
---
# <a name="systemruntimeserialization"></a><span data-ttu-id="97c37-102">\<system.runtime.serialization></span><span class="sxs-lookup"><span data-stu-id="97c37-102">\<system.runtime.serialization></span></span>
<span data-ttu-id="97c37-103">Representa el elemento raíz para la sección de espacio de nombres <xref:System.Runtime.Serialization> y contiene elementos para establecer opciones de <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="97c37-103">Represents the root element for the <xref:System.Runtime.Serialization> namespace section and contains elements for setting options of the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
 <span data-ttu-id="97c37-104">system.runtime.serialization</span><span class="sxs-lookup"><span data-stu-id="97c37-104">system.runtime.serialization</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="97c37-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="97c37-105">Syntax</span></span>  
  
```xml  
<configuration>
  <system.runtime.serialization>
    <dataContractSerializer ignoreExtensionDataObject="Boolean"
                            maxItemsInObjectGraph="Integer">
      <declaredTypes>
        <add type="String">
          <knownType type="String">
            <parameter index="Integer" />
          </knownType>
        </add>
      </declaredTypes>
    <dataContractSerializer>
  </system.runtime.serialization>
</configuration>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="97c37-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="97c37-106">Attributes and Elements</span></span>  
 <span data-ttu-id="97c37-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios</span><span class="sxs-lookup"><span data-stu-id="97c37-107">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="97c37-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="97c37-108">Attributes</span></span>  
 <span data-ttu-id="97c37-109">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="97c37-109">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="97c37-110">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="97c37-110">Child Elements</span></span>  
  
|<span data-ttu-id="97c37-111">Elemento</span><span class="sxs-lookup"><span data-stu-id="97c37-111">Element</span></span>|<span data-ttu-id="97c37-112">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="97c37-112">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="97c37-113">\<dataContractSerializer></span><span class="sxs-lookup"><span data-stu-id="97c37-113">\<dataContractSerializer></span></span>](datacontractserializer-of-system-runtime-serialization.md)|<span data-ttu-id="97c37-114">Permite agregar tipos conocidos que se van a usar al deserializar.</span><span class="sxs-lookup"><span data-stu-id="97c37-114">Enables addition of known types to be used when deserialization.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="97c37-115">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="97c37-115">Parent Elements</span></span>  
  
|<span data-ttu-id="97c37-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="97c37-116">Element</span></span>|<span data-ttu-id="97c37-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="97c37-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="97c37-118">Elemento \<configuration></span><span class="sxs-lookup"><span data-stu-id="97c37-118">\<configuration> Element</span></span>](../configuration-element.md)|<span data-ttu-id="97c37-119">El elemento de nivel superior para la configuración.</span><span class="sxs-lookup"><span data-stu-id="97c37-119">The top level element for configuration.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="97c37-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="97c37-120">See also</span></span>

- <xref:System.Runtime.Serialization>
- [<span data-ttu-id="97c37-121">Utilización de contratos de datos</span><span class="sxs-lookup"><span data-stu-id="97c37-121">Using Data Contracts</span></span>](../../../wcf/feature-details/using-data-contracts.md)
- [<span data-ttu-id="97c37-122">Tipos conocidos de contratos de datos</span><span class="sxs-lookup"><span data-stu-id="97c37-122">Data Contract Known Types</span></span>](../../../wcf/feature-details/data-contract-known-types.md)
