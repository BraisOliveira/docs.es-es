---
title: <findCriteria>
ms.date: 03/30/2017
ms.assetid: 5454cd19-6bf5-4ba8-94d1-f58d10dc1917
ms.openlocfilehash: eaa3998d3d0b1642c0c92380ec1228eea69d4da8
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59129563"
---
# <a name="findcriteria"></a><span data-ttu-id="9c187-101">\<findCriteria></span><span class="sxs-lookup"><span data-stu-id="9c187-101">\<findCriteria></span></span>
<span data-ttu-id="9c187-102">Elemento de configuración que proporciona un conjunto de criterios utilizado por una aplicación cliente para buscar un servicio de detección.</span><span class="sxs-lookup"><span data-stu-id="9c187-102">A configuration element that supplies a set of criteria used by a client application to search for a discovery service.</span></span> <span data-ttu-id="9c187-103">Los criterios pueden agruparse en criterios de búsqueda (que especifican qué servicios está buscando) y encuentra criterios de finalización (cuánto tiempo debe durar la búsqueda).</span><span class="sxs-lookup"><span data-stu-id="9c187-103">Criteria can be grouped into search criteria (specifying what services you’re looking for) and find termination criteria (how long the search should last).</span></span>  
  
 <span data-ttu-id="9c187-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="9c187-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="9c187-105">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="9c187-105">\<standardEndpoints></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9c187-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9c187-106">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <standardEndpoints>
    <dynamicEndpoint>
      <standardEndpoint>
        <discoveryClientSettings discoveryEndpoint="String">
          <findCriteria duration="TimeSpan"
                        maxResults="Integer"
                        scopeMatchBy="Uri">
            <contractTypeNames>
              <add name="String"
                   namespace="String" />
            </contractTypeNames>
            <extensions />
            <scopes>
              <add scope="URI" />
            </scopes>
          </findCriteria>
        </discoveryClientSettings>
      </standardEndpoint>
    </dynamicEndpoint>
  </standardEndpoints>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9c187-107">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="9c187-107">Attributes and Elements</span></span>  
 <span data-ttu-id="9c187-108">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="9c187-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9c187-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="9c187-109">Attributes</span></span>  
  
|<span data-ttu-id="9c187-110">Atributo</span><span class="sxs-lookup"><span data-stu-id="9c187-110">Attribute</span></span>|<span data-ttu-id="9c187-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="9c187-111">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="9c187-112">duration</span><span class="sxs-lookup"><span data-stu-id="9c187-112">duration</span></span>|<span data-ttu-id="9c187-113">Un valor Timespan que especifica el tiempo máximo para esperar respuestas de los servicios en la red.</span><span class="sxs-lookup"><span data-stu-id="9c187-113">A Timespan value that specifies the maximum time to wait for replies from services on the network.</span></span> <span data-ttu-id="9c187-114">La duración predeterminada es de 20 segundos.</span><span class="sxs-lookup"><span data-stu-id="9c187-114">The default duration is 20 seconds.</span></span>|  
|<span data-ttu-id="9c187-115">maxResults</span><span class="sxs-lookup"><span data-stu-id="9c187-115">maxResults</span></span>|<span data-ttu-id="9c187-116">Entero que especifica el número máximo de respuestas que se deben esperar, de los servicios en una red o de Internet.</span><span class="sxs-lookup"><span data-stu-id="9c187-116">An integer that specifies the maximum number of replies to wait for, from services on a network or the Internet.</span></span> <span data-ttu-id="9c187-117">Si se recibe el máximo de respuestas antes de que haya transcurrido el valor especificado en el atributo `duration`, finalizará la operación de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="9c187-117">If maximum replies are received before the value specified in the `duration` attribute has elapsed, the find operation ends.</span></span>|  
|<span data-ttu-id="9c187-118">scopeMatchBy</span><span class="sxs-lookup"><span data-stu-id="9c187-118">scopeMatchBy</span></span>|<span data-ttu-id="9c187-119">URI que especifica el algoritmo de coincidencia que se va a utilizar al establecer las coincidencias de los ámbitos del mensaje de sondeo con los del punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="9c187-119">A URI that specify the matching algorithm to use while matching the scopes in the Probe message with that of the endpoint.</span></span><br /><br /> <span data-ttu-id="9c187-120">Hay cinco reglas de coincidencia de ámbito admitidas.</span><span class="sxs-lookup"><span data-stu-id="9c187-120">There are five supported scope-matching rules.</span></span> <span data-ttu-id="9c187-121">Si no especifica ninguna regla de coincidencia de ámbito, se usa `ScopeMatchByPrefix`.</span><span class="sxs-lookup"><span data-stu-id="9c187-121">If you do not specify a scope-matching rule, `ScopeMatchByPrefix` is used.</span></span> <span data-ttu-id="9c187-122">Para obtener más información sobre este tema vea <xref:System.ServiceModel.Discovery.FindCriteria>.</span><span class="sxs-lookup"><span data-stu-id="9c187-122">For more information on this, see <xref:System.ServiceModel.Discovery.FindCriteria>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9c187-123">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="9c187-123">Child Elements</span></span>  
  
|<span data-ttu-id="9c187-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="9c187-124">Element</span></span>|<span data-ttu-id="9c187-125">Descripción</span><span class="sxs-lookup"><span data-stu-id="9c187-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9c187-126">\<contractTypeNames></span><span class="sxs-lookup"><span data-stu-id="9c187-126">\<contractTypeNames></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/contracttypenames.md)|<span data-ttu-id="9c187-127">Una colección de elementos de configuración que contienen los nombres de tipos de contrato de servicio de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="9c187-127">A collection of configuration elements that contain the names of workflow service contract types.</span></span>|  
|<span data-ttu-id="9c187-128">\<Extensiones > de \<findCriteria ></span><span class="sxs-lookup"><span data-stu-id="9c187-128">\<extensions> of \<findCriteria></span></span>|<span data-ttu-id="9c187-129">Colección de objetos de elementos XML que proporcionan las extensiones.</span><span class="sxs-lookup"><span data-stu-id="9c187-129">A collection of XML element objects that provide extensions.</span></span>|  
|[<span data-ttu-id="9c187-130">\<scopes></span><span class="sxs-lookup"><span data-stu-id="9c187-130">\<scopes></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/scopes.md)|<span data-ttu-id="9c187-131">Colección de objetos que contienen URI absolutos que se usan durante una operación de búsqueda para localizar un servicio o servicios concretos.</span><span class="sxs-lookup"><span data-stu-id="9c187-131">A collection of objects that contain absolute URIs that are used during a find operation to locate a specific service or services.</span></span><br /><br /> <span data-ttu-id="9c187-132">Si se encuentra el servicio concreto, se ha establecido una coincidencia correcta entre el URI del servicio y el URI del ámbito, en ocasiones con la ayuda de las reglas de ámbito que se ocupan de las complicaciones relativas a las coincidencias.</span><span class="sxs-lookup"><span data-stu-id="9c187-132">If the specific service is found, a successful match has been made between the service URI and the Scope URI, sometimes with the help of scope rules that handle complications of matching.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="9c187-133">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="9c187-133">Parent Elements</span></span>  
  
|<span data-ttu-id="9c187-134">Elemento</span><span class="sxs-lookup"><span data-stu-id="9c187-134">Element</span></span>|<span data-ttu-id="9c187-135">Descripción</span><span class="sxs-lookup"><span data-stu-id="9c187-135">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9c187-136">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="9c187-136">\<standardEndpoints></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/standardendpoints.md)|<span data-ttu-id="9c187-137">Contiene la configuración que necesita una aplicación para participar en el proceso de detección del servicio como un cliente.</span><span class="sxs-lookup"><span data-stu-id="9c187-137">Contains the settings needed by an application to participate in the service discovery process as a client.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9c187-138">Vea también</span><span class="sxs-lookup"><span data-stu-id="9c187-138">See also</span></span>

- <xref:System.ServiceModel.Discovery.FindCriteria>
- <xref:System.ServiceModel.Discovery.Configuration.FindCriteriaElement>
