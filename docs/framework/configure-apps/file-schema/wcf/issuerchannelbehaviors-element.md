---
title: <issuerChannelBehaviors> Elemento
ms.date: 03/30/2017
ms.assetid: f7378673-8e9b-45b2-98d1-cf5dccdd8c40
ms.openlocfilehash: 7cbd50daa82b0ca937a1bba93786545898b03c8b
ms.sourcegitcommit: 5c2176883dc3107445702724a7caa7ac2f6cb0d3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/03/2019
ms.locfileid: "58890480"
---
# <a name="issuerchannelbehaviors-element"></a><span data-ttu-id="b736f-102">\<issuerChannelBehaviors > elemento</span><span class="sxs-lookup"><span data-stu-id="b736f-102">\<issuerChannelBehaviors> Element</span></span>

<span data-ttu-id="b736f-103">Contiene una colección de comportamientos de punto de conexión de cliente de Windows Communication Foundation (WCF) (definido en la configuración) que se usará al comunicarse con los servicios de Token de servicio especificado.</span><span class="sxs-lookup"><span data-stu-id="b736f-103">Contains a collection of Windows Communication Foundation (WCF) client endpoint behaviors (defined in the configuration) to be used when communicating with the specified Service Token Services.</span></span> <span data-ttu-id="b736f-104">Los comportamientos definidos no pueden contener ninguno [ \<clientCredentials >](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md) elementos.</span><span class="sxs-lookup"><span data-stu-id="b736f-104">The defined behaviors cannot include any [\<clientCredentials>](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md) elements.</span></span>

```xml
<system.ServiceModel>
  <behaviors>
    <endpointBehaviors>
      <behavior>
        <clientCredentials>
          <issuedToken>
            <issuerChannelBehaviors>
```

## <a name="syntax"></a><span data-ttu-id="b736f-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b736f-105">Syntax</span></span>

```xml
<issuerChannelBehaviors>
  <add behaviorConfiguration="string"
       issuerAddress="string" />
</issuerChannelBehaviors>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="b736f-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="b736f-106">Attributes and Elements</span></span>

<span data-ttu-id="b736f-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="b736f-107">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="b736f-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="b736f-108">Attributes</span></span>

<span data-ttu-id="b736f-109">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="b736f-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="b736f-110">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="b736f-110">Child Elements</span></span>

|<span data-ttu-id="b736f-111">Elemento</span><span class="sxs-lookup"><span data-stu-id="b736f-111">Element</span></span>|<span data-ttu-id="b736f-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="b736f-112">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="b736f-113">\<add></span><span class="sxs-lookup"><span data-stu-id="b736f-113">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-issuerchannelbehaviors.md)|<span data-ttu-id="b736f-114">Agrega un comportamiento a la colección.</span><span class="sxs-lookup"><span data-stu-id="b736f-114">Adds a behavior to the collection.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="b736f-115">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="b736f-115">Parent Elements</span></span>

|<span data-ttu-id="b736f-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="b736f-116">Element</span></span>|<span data-ttu-id="b736f-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="b736f-117">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="b736f-118">\<issuedToken></span><span class="sxs-lookup"><span data-stu-id="b736f-118">\<issuedToken></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtoken.md)|<span data-ttu-id="b736f-119">Especifica un token personalizado usado para autenticar un cliente en un servicio.</span><span class="sxs-lookup"><span data-stu-id="b736f-119">Specifies a custom token used to authenticate a client to a service.</span></span>|

## <a name="remarks"></a><span data-ttu-id="b736f-120">Comentarios</span><span class="sxs-lookup"><span data-stu-id="b736f-120">Remarks</span></span>

<span data-ttu-id="b736f-121">Use este elemento cuando se deba utilizar un comportamiento (excepto los comportamientos que incluyen elementos `<clientCredentials>`) para comunicar con un servicio.</span><span class="sxs-lookup"><span data-stu-id="b736f-121">Use this element when any behaviors (other than behaviors that include `<clientCredentials>` elements) must be used to communicate with a service.</span></span> <span data-ttu-id="b736f-122">Por ejemplo, si un [ \<dataContractSerializer >](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md) debe incluirse el elemento de comportamiento.</span><span class="sxs-lookup"><span data-stu-id="b736f-122">For example, if a [\<dataContractSerializer>](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md) behavior element must be included.</span></span>

## <a name="see-also"></a><span data-ttu-id="b736f-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="b736f-123">See also</span></span>

- <xref:System.ServiceModel.Configuration.IssuedTokenClientElement.IssuerChannelBehaviors%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenClientBehaviorsElement>
- <xref:System.ServiceModel.Configuration.IssuedTokenClientBehaviorsElementCollection>
- <xref:System.ServiceModel.Security.IssuedTokenClientCredential.IssuerChannelBehaviors%2A>
- [<span data-ttu-id="b736f-124">Identidad del servicio y autenticación</span><span class="sxs-lookup"><span data-stu-id="b736f-124">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="b736f-125">Comportamientos de seguridad</span><span class="sxs-lookup"><span data-stu-id="b736f-125">Security Behaviors</span></span>](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="b736f-126">Federación y tokens emitidos</span><span class="sxs-lookup"><span data-stu-id="b736f-126">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="b736f-127">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="b736f-127">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="b736f-128">Protección de clientes</span><span class="sxs-lookup"><span data-stu-id="b736f-128">Securing Clients</span></span>](../../../../../docs/framework/wcf/securing-clients.md)
- [<span data-ttu-id="b736f-129">Filtrar para crear un cliente federado</span><span class="sxs-lookup"><span data-stu-id="b736f-129">How to: Create a Federated Client</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-create-a-federated-client.md)
- [<span data-ttu-id="b736f-130">Filtrar para configurar un emisor local</span><span class="sxs-lookup"><span data-stu-id="b736f-130">How to: Configure a Local Issuer</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-configure-a-local-issuer.md)
- [<span data-ttu-id="b736f-131">Federación y tokens emitidos</span><span class="sxs-lookup"><span data-stu-id="b736f-131">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
