---
title: <serviceActivations>
ms.date: 03/30/2017
ms.assetid: 97e665b6-1c51-410b-928a-9bb42c954ddb
ms.openlocfilehash: fb7c699612ef12aae39aaeadaf170d0e8f2553cd
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69936440"
---
# <a name="serviceactivations"></a><span data-ttu-id="eefb8-101">\<serviceActivations></span><span class="sxs-lookup"><span data-stu-id="eefb8-101">\<serviceActivations></span></span>

<span data-ttu-id="eefb8-102">Un elemento de configuración que le permite agregar valores que definen la configuración de activación de servicio virtual que se asignan a los tipos de servicio Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="eefb8-102">A configuration element that allows you to add settings that define virtual service activation settings that map to your Windows Communication Foundation (WCF) service types.</span></span> <span data-ttu-id="eefb8-103">Esto hace posible activar servicios hospedados en WAS/IIS sin un archivo .svc.</span><span class="sxs-lookup"><span data-stu-id="eefb8-103">This makes it possible to activate services hosted in WAS/IIS without an .svc file.</span></span>

<span data-ttu-id="eefb8-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="eefb8-104">\<system.ServiceModel></span></span>\
<span data-ttu-id="eefb8-105">\<serviceHostingEnvironment></span><span class="sxs-lookup"><span data-stu-id="eefb8-105">\<serviceHostingEnvironment></span></span>\
<span data-ttu-id="eefb8-106">\<serviceActivations></span><span class="sxs-lookup"><span data-stu-id="eefb8-106">\<serviceActivations></span></span>

## <a name="syntax"></a><span data-ttu-id="eefb8-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="eefb8-107">Syntax</span></span>

```xml
<serviceHostingEnvironment>
  <serviceActivations>
    <add factory="String"
         service="String" />
  </serviceActivations>
</serviceHostingEnvironment>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="eefb8-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="eefb8-108">Attributes and Elements</span></span>

<span data-ttu-id="eefb8-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="eefb8-109">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="eefb8-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="eefb8-110">Attributes</span></span>

<span data-ttu-id="eefb8-111">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="eefb8-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="eefb8-112">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="eefb8-112">Child Elements</span></span>

|<span data-ttu-id="eefb8-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="eefb8-113">Element</span></span>|<span data-ttu-id="eefb8-114">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="eefb8-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="eefb8-115">\<add></span><span class="sxs-lookup"><span data-stu-id="eefb8-115">\<add></span></span>](add-of-serviceactivations.md)|<span data-ttu-id="eefb8-116">Agrega un elemento de configuración que especifica la activación de una aplicación de servicio.</span><span class="sxs-lookup"><span data-stu-id="eefb8-116">Adds a configuration element that specifies the activation of a service application.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="eefb8-117">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="eefb8-117">Parent Elements</span></span>

|<span data-ttu-id="eefb8-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="eefb8-118">Element</span></span>|<span data-ttu-id="eefb8-119">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="eefb8-119">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="eefb8-120">\<serviceHostingEnvironment></span><span class="sxs-lookup"><span data-stu-id="eefb8-120">\<serviceHostingEnvironment></span></span>](servicehostingenvironment.md)|<span data-ttu-id="eefb8-121">Define el tipo del que el entorno host del servicio crea instancias para un transporte determinado.</span><span class="sxs-lookup"><span data-stu-id="eefb8-121">Defines the type the service hosting environment instantiates for a particular transport.</span></span>|

## <a name="remarks"></a><span data-ttu-id="eefb8-122">Comentarios</span><span class="sxs-lookup"><span data-stu-id="eefb8-122">Remarks</span></span>

<span data-ttu-id="eefb8-123">En el siguiente ejemplo se muestra cómo configurar los valores de activación dentro del archivo web.config.</span><span class="sxs-lookup"><span data-stu-id="eefb8-123">The following example shows how to configure activation settings within your web.config file.</span></span>

```xml
<configuration>
  <system.serviceModel>
    <serviceHostingEnvironment>
      <serviceActivations>
        <add service="GreetingService" />
      </serviceActivations>
    </serviceHostingEnvironment>
  </system.serviceModel>
</configuration>
```

<span data-ttu-id="eefb8-124">Con esta configuración, puede activar GreetingService sin usar un archivo .svc.</span><span class="sxs-lookup"><span data-stu-id="eefb8-124">Using this configuration, you can activate the GreetingService without using an .svc file.</span></span>

<span data-ttu-id="eefb8-125">Observe que `<serviceHostingEnvironment>` es una configuración de nivel de aplicación.</span><span class="sxs-lookup"><span data-stu-id="eefb8-125">Note that `<serviceHostingEnvironment>` is an application level configuration.</span></span> <span data-ttu-id="eefb8-126">Tiene que colocar el archivo `web.config` que contiene la configuración en la raíz de la aplicación virtual.</span><span class="sxs-lookup"><span data-stu-id="eefb8-126">You have to place the `web.config` containing the configuration under the root of the virtual Application.</span></span> <span data-ttu-id="eefb8-127">Además, `serviceHostingEnvironment` es una sección machineToApplication heredable.</span><span class="sxs-lookup"><span data-stu-id="eefb8-127">In addition, `serviceHostingEnvironment` is a machineToApplication inheritable section.</span></span> <span data-ttu-id="eefb8-128">Si registra un solo servicio en la raíz del equipo, cada servicio de la aplicación heredará este servicio.</span><span class="sxs-lookup"><span data-stu-id="eefb8-128">If you register a single service in the root of the machine, every service in the application will inherit this service.</span></span>

<span data-ttu-id="eefb8-129">La activación basada en la configuración admite la activación a través de protocolos http y distintos de http.</span><span class="sxs-lookup"><span data-stu-id="eefb8-129">Configuration-based activation supports activation over both http and non-http protocol.</span></span> <span data-ttu-id="eefb8-130">Requiere extensiones en relativeAddress, es decir,. SVC,. xoml o. xamlx.</span><span class="sxs-lookup"><span data-stu-id="eefb8-130">It requires extensions in the relativeAddress i.e. .svc, .xoml or .xamlx.</span></span> <span data-ttu-id="eefb8-131">Puede asignar sus propias extensiones al buildProviders conocido, que le permitirá activar el servicio a través de cualquier extensión.</span><span class="sxs-lookup"><span data-stu-id="eefb8-131">You can map your own extensions to the know buildProviders, which will then enable you to activate service over any extension.</span></span> <span data-ttu-id="eefb8-132">Si existe conflicto, la sección `<serviceActivations>` invalida los registros de .svc.</span><span class="sxs-lookup"><span data-stu-id="eefb8-132">Upon conflict, the `<serviceActivations>` section overrides .svc registrations.</span></span>

## <a name="see-also"></a><span data-ttu-id="eefb8-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="eefb8-133">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceActivationElementCollection>
- <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection>
- <xref:System.ServiceModel.ServiceHostingEnvironment>
