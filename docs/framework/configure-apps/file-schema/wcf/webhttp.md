---
title: <webHttp>
ms.date: 03/30/2017
ms.assetid: 1f9d0754-d41e-44ce-a298-e51cb3096c64
ms.openlocfilehash: 795e61b9054d2ea9276970988018c50099bcbe17
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61769803"
---
# <a name="webhttp"></a><span data-ttu-id="9b8a1-101">\<webHttp></span><span class="sxs-lookup"><span data-stu-id="9b8a1-101">\<webHttp></span></span>
<span data-ttu-id="9b8a1-102">Este elemento especifica <xref:System.ServiceModel.Description.WebHttpBehavior> en un punto de conexión a través de la configuración.</span><span class="sxs-lookup"><span data-stu-id="9b8a1-102">This element specifies the <xref:System.ServiceModel.Description.WebHttpBehavior> on an endpoint through configuration.</span></span> <span data-ttu-id="9b8a1-103">Este comportamiento, cuando se usa junto con el [ \<webHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttpbinding.md) enlace estándar, permite que el modelo de programación Web para un servicio de Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="9b8a1-103">This behavior, when used in conjunction with the [\<webHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttpbinding.md) standard binding, enables the Web programming model for a Windows Communication Foundation (WCF) service.</span></span>  
  
 <span data-ttu-id="9b8a1-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="9b8a1-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="9b8a1-105">\<comportamientos ></span><span class="sxs-lookup"><span data-stu-id="9b8a1-105">\<behaviors></span></span>  
<span data-ttu-id="9b8a1-106">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="9b8a1-106">\<endpointBehaviors></span></span>  
<span data-ttu-id="9b8a1-107">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="9b8a1-107">\<behavior></span></span>  
<span data-ttu-id="9b8a1-108">\<webHttp></span><span class="sxs-lookup"><span data-stu-id="9b8a1-108">\<webHttp></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9b8a1-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9b8a1-109">Syntax</span></span>  
  
```xml  
<webHttp />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9b8a1-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="9b8a1-110">Attributes and Elements</span></span>  
 <span data-ttu-id="9b8a1-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="9b8a1-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9b8a1-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="9b8a1-112">Attributes</span></span>  
  
|<span data-ttu-id="9b8a1-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="9b8a1-113">Attribute</span></span>|<span data-ttu-id="9b8a1-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="9b8a1-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="9b8a1-115">automaticFormatSelectionEnabled</span><span class="sxs-lookup"><span data-stu-id="9b8a1-115">automaticFormatSelectionEnabled</span></span>|<span data-ttu-id="9b8a1-116">Cuando esta propiedad está establecida en `true`, la infraestructura de WCF determina el mejor formato que se debe usar.</span><span class="sxs-lookup"><span data-stu-id="9b8a1-116">When this property is set to `true`, the WCF infrastructure determines the best format to use.</span></span> <span data-ttu-id="9b8a1-117">La selección de formato automática está deshabilitada de forma predeterminada para la compatibilidad con versiones anteriores.</span><span class="sxs-lookup"><span data-stu-id="9b8a1-117">Automatic format selection is disabled by default for backwards compatibility.</span></span> <span data-ttu-id="9b8a1-118">La selección de formato automática puede habilitarse mediante programación o a través de la configuración.</span><span class="sxs-lookup"><span data-stu-id="9b8a1-118">Automatic format selection can be enabled programmatically or through configuration.</span></span>|  
|<span data-ttu-id="9b8a1-119">defaultBodyStyle</span><span class="sxs-lookup"><span data-stu-id="9b8a1-119">defaultBodyStyle</span></span>|<span data-ttu-id="9b8a1-120">Especifica el estilo de cuerpo predeterminado de los mensajes devueltos.</span><span class="sxs-lookup"><span data-stu-id="9b8a1-120">Specifies the default body style of returned messages.</span></span> <span data-ttu-id="9b8a1-121">Para obtener más información, consulte <xref:System.ServiceModel.Web.WebMessageBodyStyle> y [WCF Web HTTP formato](../../../../../docs/framework/wcf/feature-details/wcf-web-http-formatting.md).</span><span class="sxs-lookup"><span data-stu-id="9b8a1-121">For more information, see <xref:System.ServiceModel.Web.WebMessageBodyStyle> and [WCF Web HTTP Formatting](../../../../../docs/framework/wcf/feature-details/wcf-web-http-formatting.md).</span></span>|  
|<span data-ttu-id="9b8a1-122">defaultOutgoingResponseFormat</span><span class="sxs-lookup"><span data-stu-id="9b8a1-122">defaultOutgoingResponseFormat</span></span>|<span data-ttu-id="9b8a1-123">Especifica el formato de respuesta de salida predeterminado de los mensajes.</span><span class="sxs-lookup"><span data-stu-id="9b8a1-123">Specifies the default outgoing response format for messages.</span></span> <span data-ttu-id="9b8a1-124">Para obtener más información, consulte [WCF Web HTTP formato](../../../../../docs/framework/wcf/feature-details/wcf-web-http-formatting.md).</span><span class="sxs-lookup"><span data-stu-id="9b8a1-124">For more information, see [WCF Web HTTP Formatting](../../../../../docs/framework/wcf/feature-details/wcf-web-http-formatting.md).</span></span>|  
|<span data-ttu-id="9b8a1-125">faultExceptionEnabled</span><span class="sxs-lookup"><span data-stu-id="9b8a1-125">faultExceptionEnabled</span></span>|<span data-ttu-id="9b8a1-126">Obtiene o establece la marca que especifica si se genera FaultException cuando se produce un error de servidor interno (código de estado HTTP: 500).</span><span class="sxs-lookup"><span data-stu-id="9b8a1-126">Gets or sets the flag that specifies whether a FaultException is generated when an internal server error (HTTP status code: 500) occurs.</span></span>|  
|<span data-ttu-id="9b8a1-127">helpEnabled</span><span class="sxs-lookup"><span data-stu-id="9b8a1-127">helpEnabled</span></span>|<span data-ttu-id="9b8a1-128">Obtiene o establece un valor que determina si la página de Ayuda está habilitada.</span><span class="sxs-lookup"><span data-stu-id="9b8a1-128">Gets or sets a value that determines if the Help page is enabled.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9b8a1-129">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="9b8a1-129">Child Elements</span></span>  
 <span data-ttu-id="9b8a1-130">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="9b8a1-130">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="9b8a1-131">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="9b8a1-131">Parent Elements</span></span>  
  
|<span data-ttu-id="9b8a1-132">Elemento</span><span class="sxs-lookup"><span data-stu-id="9b8a1-132">Element</span></span>|<span data-ttu-id="9b8a1-133">Descripción</span><span class="sxs-lookup"><span data-stu-id="9b8a1-133">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9b8a1-134">\<behavior></span><span class="sxs-lookup"><span data-stu-id="9b8a1-134">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="9b8a1-135">Especifica el conjunto de comportamientos del punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="9b8a1-135">Specifies the set of endpoint behaviors.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9b8a1-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="9b8a1-136">See also</span></span>

- <xref:System.ServiceModel.Configuration.WebHttpElement>
- <xref:System.ServiceModel.Description.WebHttpBehavior>
- [<span data-ttu-id="9b8a1-137">Integración de AJAX y compatibilidad de JSON</span><span class="sxs-lookup"><span data-stu-id="9b8a1-137">AJAX Integration and JSON Support</span></span>](../../../../../docs/framework/wcf/feature-details/ajax-integration-and-json-support.md)
- [<span data-ttu-id="9b8a1-138">\<webHttpBinding></span><span class="sxs-lookup"><span data-stu-id="9b8a1-138">\<webHttpBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttpbinding.md)
