---
title: <issuerChannelBehaviors> (Elemento)
ms.date: 03/30/2017
ms.assetid: f7378673-8e9b-45b2-98d1-cf5dccdd8c40
ms.openlocfilehash: 3386a287d577681b67bd3ad54a75b0276e29da1f
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2019
ms.locfileid: "57357253"
---
# <a name="issuerchannelbehaviors-element"></a><span data-ttu-id="26ba5-102">\<issuerChannelBehaviors > elemento</span><span class="sxs-lookup"><span data-stu-id="26ba5-102">\<issuerChannelBehaviors> Element</span></span>

<span data-ttu-id="26ba5-103">Contiene una colección de comportamientos de punto de conexión de cliente de Windows Communication Foundation (WCF) (definido en la configuración) que se usará al comunicarse con los servicios de Token de servicio especificado.</span><span class="sxs-lookup"><span data-stu-id="26ba5-103">Contains a collection of Windows Communication Foundation (WCF) client endpoint behaviors (defined in the configuration) to be used when communicating with the specified Service Token Services.</span></span> <span data-ttu-id="26ba5-104">Los comportamientos definidos no pueden contener ninguno [ \<clientCredentials >](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md) elementos.</span><span class="sxs-lookup"><span data-stu-id="26ba5-104">The defined behaviors cannot include any [\<clientCredentials>](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md) elements.</span></span>

<span data-ttu-id="26ba5-105">\<system.ServiceModel>\\</span><span class="sxs-lookup"><span data-stu-id="26ba5-105">\<system.ServiceModel>\\</span></span>
<span data-ttu-id="26ba5-106">\<comportamientos > \\</span><span class="sxs-lookup"><span data-stu-id="26ba5-106">\<behaviors>\\</span></span>
<span data-ttu-id="26ba5-107">section\ endpointBehaviors</span><span class="sxs-lookup"><span data-stu-id="26ba5-107">endpointBehaviors section\\</span></span>
<span data-ttu-id="26ba5-108">\<comportamiento > \\</span><span class="sxs-lookup"><span data-stu-id="26ba5-108">\<behavior>\\</span></span>
<span data-ttu-id="26ba5-109">\<clientCredentials>\\</span><span class="sxs-lookup"><span data-stu-id="26ba5-109">\<clientCredentials>\\</span></span>
<span data-ttu-id="26ba5-110">\<issuedToken>\\</span><span class="sxs-lookup"><span data-stu-id="26ba5-110">\<issuedToken>\\</span></span>
<span data-ttu-id="26ba5-111">\<issuerChannelBehaviors></span><span class="sxs-lookup"><span data-stu-id="26ba5-111">\<issuerChannelBehaviors></span></span>

## <a name="syntax"></a><span data-ttu-id="26ba5-112">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="26ba5-112">Syntax</span></span>

```xml
<issuerChannelBehaviors>
  <add behaviorConfiguration="string"
       issuerAddress="string" />
</issuerChannelBehaviors>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="26ba5-113">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="26ba5-113">Attributes and Elements</span></span>

<span data-ttu-id="26ba5-114">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="26ba5-114">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="26ba5-115">Atributos</span><span class="sxs-lookup"><span data-stu-id="26ba5-115">Attributes</span></span>

<span data-ttu-id="26ba5-116">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="26ba5-116">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="26ba5-117">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="26ba5-117">Child Elements</span></span>

|<span data-ttu-id="26ba5-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="26ba5-118">Element</span></span>|<span data-ttu-id="26ba5-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="26ba5-119">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="26ba5-120">\<add></span><span class="sxs-lookup"><span data-stu-id="26ba5-120">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-issuerchannelbehaviors.md)|<span data-ttu-id="26ba5-121">Agrega un comportamiento a la colección.</span><span class="sxs-lookup"><span data-stu-id="26ba5-121">Adds a behavior to the collection.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="26ba5-122">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="26ba5-122">Parent Elements</span></span>

|<span data-ttu-id="26ba5-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="26ba5-123">Element</span></span>|<span data-ttu-id="26ba5-124">Descripción</span><span class="sxs-lookup"><span data-stu-id="26ba5-124">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="26ba5-125">\<issuedToken></span><span class="sxs-lookup"><span data-stu-id="26ba5-125">\<issuedToken></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtoken.md)|<span data-ttu-id="26ba5-126">Especifica un token personalizado usado para autenticar un cliente en un servicio.</span><span class="sxs-lookup"><span data-stu-id="26ba5-126">Specifies a custom token used to authenticate a client to a service.</span></span>|

## <a name="remarks"></a><span data-ttu-id="26ba5-127">Comentarios</span><span class="sxs-lookup"><span data-stu-id="26ba5-127">Remarks</span></span>

<span data-ttu-id="26ba5-128">Use este elemento cuando se deba utilizar un comportamiento (excepto los comportamientos que incluyen elementos `<clientCredentials>`) para comunicar con un servicio.</span><span class="sxs-lookup"><span data-stu-id="26ba5-128">Use this element when any behaviors (other than behaviors that include `<clientCredentials>` elements) must be used to communicate with a service.</span></span> <span data-ttu-id="26ba5-129">Por ejemplo, si un [ \<dataContractSerializer >](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md) debe incluirse el elemento de comportamiento.</span><span class="sxs-lookup"><span data-stu-id="26ba5-129">For example, if a [\<dataContractSerializer>](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md) behavior element must be included.</span></span>

## <a name="see-also"></a><span data-ttu-id="26ba5-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="26ba5-130">See also</span></span>

- <xref:System.ServiceModel.Configuration.IssuedTokenClientElement.IssuerChannelBehaviors%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenClientBehaviorsElement>
- <xref:System.ServiceModel.Configuration.IssuedTokenClientBehaviorsElementCollection>
- <xref:System.ServiceModel.Security.IssuedTokenClientCredential.IssuerChannelBehaviors%2A>
- [<span data-ttu-id="26ba5-131">Identidad del servicio y autenticación</span><span class="sxs-lookup"><span data-stu-id="26ba5-131">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="26ba5-132">Comportamientos de seguridad</span><span class="sxs-lookup"><span data-stu-id="26ba5-132">Security Behaviors</span></span>](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="26ba5-133">Federación y tokens emitidos</span><span class="sxs-lookup"><span data-stu-id="26ba5-133">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="26ba5-134">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="26ba5-134">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="26ba5-135">Protección de clientes</span><span class="sxs-lookup"><span data-stu-id="26ba5-135">Securing Clients</span></span>](../../../../../docs/framework/wcf/securing-clients.md)
- [<span data-ttu-id="26ba5-136">Cómo: Crear a un cliente federado</span><span class="sxs-lookup"><span data-stu-id="26ba5-136">How to: Create a Federated Client</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-create-a-federated-client.md)
- [<span data-ttu-id="26ba5-137">Cómo: Configurar a un emisor Local</span><span class="sxs-lookup"><span data-stu-id="26ba5-137">How to: Configure a Local Issuer</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-configure-a-local-issuer.md)
- [<span data-ttu-id="26ba5-138">Federación y tokens emitidos</span><span class="sxs-lookup"><span data-stu-id="26ba5-138">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
