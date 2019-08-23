---
title: <add> de <protocolMapping>
ms.date: 03/30/2017
ms.assetid: 08e62249-1641-41d1-91b1-66d7b46244e4
ms.openlocfilehash: df69b5f8a79489b722c1074f118b9c6f6e8e363d
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69926673"
---
# <a name="add-of-protocolmapping"></a><span data-ttu-id="9ea69-102">\<Agregar > de \<protocolMapping ></span><span class="sxs-lookup"><span data-stu-id="9ea69-102">\<add> of \<protocolMapping></span></span>
<span data-ttu-id="9ea69-103">Representa una asignación de protocolo predeterminada entre un esquema de protocolo de transporte (por ejemplo, http, net. TCP, net. Pipe, etc.) y un enlace Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="9ea69-103">Represents a default protocol mapping between a transport protocol scheme (e.g., http, net.tcp, net.pipe, etc.) and a Windows Communication Foundation (WCF) binding.</span></span> <span data-ttu-id="9ea69-104">Al crear puntos de conexión predeterminados en tiempo de ejecución, WCF examina las asignaciones configuradas y decide qué enlace usar para una dirección base determinada.</span><span class="sxs-lookup"><span data-stu-id="9ea69-104">When creating default endpoints at runtime, WCF looks at the configured mappings and decides on which binding to use for a particular based address.</span></span>  
  
 <span data-ttu-id="9ea69-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="9ea69-105">\<system.serviceModel></span></span>  
<span data-ttu-id="9ea69-106">\<> protocolMapping</span><span class="sxs-lookup"><span data-stu-id="9ea69-106">\<protocolMapping></span></span>  
<span data-ttu-id="9ea69-107">\<add></span><span class="sxs-lookup"><span data-stu-id="9ea69-107">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9ea69-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9ea69-108">Syntax</span></span>  
  
```xml  
<protocolMapping>
  <add binding="String"
       bindingConfiguration="String"
       scheme="http/net.msmq/net.pipe/net.tcp" />
</protocolMapping>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9ea69-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="9ea69-109">Attributes and Elements</span></span>  
 <span data-ttu-id="9ea69-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="9ea69-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9ea69-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="9ea69-111">Attributes</span></span>  
  
|<span data-ttu-id="9ea69-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="9ea69-112">Element</span></span>|<span data-ttu-id="9ea69-113">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="9ea69-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="9ea69-114">enlace</span><span class="sxs-lookup"><span data-stu-id="9ea69-114">binding</span></span>|<span data-ttu-id="9ea69-115">Cadena que especifica el tipo de enlace que se va a usar para un extremo durante la creación del extremo predeterminado.</span><span class="sxs-lookup"><span data-stu-id="9ea69-115">A string that specifies the type of binding to be used for an endpoint during default endpoint creation.</span></span>|  
|<span data-ttu-id="9ea69-116">bindingConfiguration</span><span class="sxs-lookup"><span data-stu-id="9ea69-116">bindingConfiguration</span></span>|<span data-ttu-id="9ea69-117">Cadena que especifica el nombre de la sección de configuración de enlace a la que se va a hacer referencia.</span><span class="sxs-lookup"><span data-stu-id="9ea69-117">A string that specifies the name of the binding configuration section to be referenced.</span></span>|  
|<span data-ttu-id="9ea69-118">scheme</span><span class="sxs-lookup"><span data-stu-id="9ea69-118">scheme</span></span>|<span data-ttu-id="9ea69-119">Esquema de protocolos de transporte que se va a utilizar para el extremo predeterminado.</span><span class="sxs-lookup"><span data-stu-id="9ea69-119">The transport protocol scheme to be used for the default endpoint.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9ea69-120">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="9ea69-120">Child Elements</span></span>  
 <span data-ttu-id="9ea69-121">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="9ea69-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="9ea69-122">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="9ea69-122">Parent Elements</span></span>  
  
|<span data-ttu-id="9ea69-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="9ea69-123">Element</span></span>|<span data-ttu-id="9ea69-124">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="9ea69-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9ea69-125">\<protocolMapping></span><span class="sxs-lookup"><span data-stu-id="9ea69-125">\<protocolMapping></span></span>](protocolmapping.md)|<span data-ttu-id="9ea69-126">Representa una sección de configuración para definir las asignaciones de protocolo predeterminadas entre los esquemas de protocolo de transporte (por ejemplo, http, net. TCP, net. Pipe, etc.) y los enlaces de Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="9ea69-126">Represents a configuration section for defining default protocol mappings between transport protocol schemes (e.g., http, net.tcp, net.pipe, etc.) and Windows Communication Foundation (WCF) bindings.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="9ea69-127">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="9ea69-127">Example</span></span>  
 <span data-ttu-id="9ea69-128">En el siguiente ejemplo de configuración se muestra la asignación de protocolo predeterminado en el archivo machine.config.</span><span class="sxs-lookup"><span data-stu-id="9ea69-128">The following configuration example shows the default protocol mapping in the machine.config file.</span></span> <span data-ttu-id="9ea69-129">Puede invalidar esta asignación predeterminada en el nivel del equipo modificando el archivo machine.config.</span><span class="sxs-lookup"><span data-stu-id="9ea69-129">You can override this default mapping at the machine level by modifying the machine.config file.</span></span> <span data-ttu-id="9ea69-130">O bien, si solo deseara invalidarlo dentro del ámbito de una aplicación, puede invalidar esta sección dentro del archivo de configuración de la aplicación y cambiar la asignación para los esquemas de protocolos individuales.</span><span class="sxs-lookup"><span data-stu-id="9ea69-130">Or if you would only like to override it within the scope of an application, you can override this section within your application configuration file and change the mapping for individual protocol schemes.</span></span>  
  
```xml  
<protocolMapping>
  <add scheme="http"
       binding="basicHttpBinding" />
  <add scheme="net.tcp"
       binding="netTcpBinding" />
  <add scheme="net.pipe"
       binding="netNamedPipeBinding" />
  <add scheme="net.msmq"
       binding="netMsmqBinding" />
</protocolMapping>
```  
  
## <a name="see-also"></a><span data-ttu-id="9ea69-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="9ea69-131">See also</span></span>

- <xref:System.ServiceModel.Configuration.ProtocolMappingSection?displayProperty=nameWithType>
- <xref:System.ServiceModel.Configuration.ProtocolMappingElement?displayProperty=nameWithType>
