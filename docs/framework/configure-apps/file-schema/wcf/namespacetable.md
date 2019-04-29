---
title: <namespaceTable>
ms.date: 03/30/2017
ms.assetid: 64801766-01b7-4c65-9ce6-70ad5af67689
ms.openlocfilehash: ee7a0c23adca883af279addf9d1f221bd4056d00
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61772416"
---
# <a name="namespacetable"></a><span data-ttu-id="69ed0-101">\<namespaceTable></span><span class="sxs-lookup"><span data-stu-id="69ed0-101">\<namespaceTable></span></span>

<span data-ttu-id="69ed0-102">Representa una sección de configuración para definir un conjunto de elementos que contienen el espacio de nombres para prefijar asignaciones que se pueden utilizar a continuación en filtros XPath para el enrutamiento.</span><span class="sxs-lookup"><span data-stu-id="69ed0-102">Represents a configuration section for defining a set of elements that contain namespace to prefix mappings that can then be used in XPath filters for routing.</span></span>

<span data-ttu-id="69ed0-103">**\<system.serviceModel>** </span><span class="sxs-lookup"><span data-stu-id="69ed0-103">**\<system.serviceModel>** </span></span>  
<span data-ttu-id="69ed0-104">&nbsp;&nbsp;**\<enrutamiento >** </span><span class="sxs-lookup"><span data-stu-id="69ed0-104">&nbsp;&nbsp;**\<routing>** </span></span>  
<span data-ttu-id="69ed0-105">&nbsp;&nbsp;&nbsp;&nbsp;**\<namespaceTable>**</span><span class="sxs-lookup"><span data-stu-id="69ed0-105">&nbsp;&nbsp;&nbsp;&nbsp;**\<namespaceTable>**</span></span>
  
## <a name="syntax"></a><span data-ttu-id="69ed0-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="69ed0-106">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <routing>
    <namespaceTable>
      <add namespace="String"
           prefix="String" />
    </namespaceTable>
  </routing>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="69ed0-107">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="69ed0-107">Attributes and elements</span></span>

<span data-ttu-id="69ed0-108">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="69ed0-108">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="69ed0-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="69ed0-109">Attributes</span></span>

<span data-ttu-id="69ed0-110">Ninguna</span><span class="sxs-lookup"><span data-stu-id="69ed0-110">None</span></span>

### <a name="child-elements"></a><span data-ttu-id="69ed0-111">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="69ed0-111">Child elements</span></span>

|     | <span data-ttu-id="69ed0-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="69ed0-112">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="69ed0-113">**\<filter>**</span><span class="sxs-lookup"><span data-stu-id="69ed0-113">**\<filter>**</span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/filter.md) | <span data-ttu-id="69ed0-114">Define una asignación de prefijo de espacio de nombres usado para expresiones XPath.</span><span class="sxs-lookup"><span data-stu-id="69ed0-114">Defines a namespace prefix mapping used for XPath expressions.</span></span> |

### <a name="parent-elements"></a><span data-ttu-id="69ed0-115">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="69ed0-115">Parent elements</span></span>

|     | <span data-ttu-id="69ed0-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="69ed0-116">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="69ed0-117">**\<enrutamiento >**</span><span class="sxs-lookup"><span data-stu-id="69ed0-117">**\<routing>**</span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md) | <span data-ttu-id="69ed0-118">Representa una sección de configuración para definir un conjunto de filtros de enrutamiento, que determinan el tipo de Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> que se usará al evaluar los mensajes entrantes, así como el enrutamiento de las tablas que definen los extremos de destino enviar mensajes cuando coincida un filtro.</span><span class="sxs-lookup"><span data-stu-id="69ed0-118">Represents a configuration section for defining a set of routing filters, which determine the type of Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages, as well as routing tables that define the target endpoints to send messages to when a filter matches.</span></span> |

## <a name="see-also"></a><span data-ttu-id="69ed0-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="69ed0-119">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.NamespaceElementCollection?displayProperty=nameWithType>
