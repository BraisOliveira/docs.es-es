---
title: <remove>del <claimTypeRequirements> elemento
ms.date: 03/30/2017
ms.assetid: 8ef05bc4-1950-4ee4-95c5-1c6a394eff7e
ms.openlocfilehash: 84f4208d3f4581cf7e8c4455bf3f5d78f7e13b9f
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399999"
---
# <a name="remove-of-claimtyperequirements-element"></a><span data-ttu-id="fc996-102">\<quitar > del \<elemento de > claimTypeRequirements</span><span class="sxs-lookup"><span data-stu-id="fc996-102">\<remove> of \<claimTypeRequirements> element</span></span>
<span data-ttu-id="fc996-103">Especifica los tipos de notificaciones que se van a quitar en la credencial aliada.</span><span class="sxs-lookup"><span data-stu-id="fc996-103">Specifies the types of claims to be removed in the federated credential.</span></span>  
  
<span data-ttu-id="fc996-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="fc996-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="fc996-105">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="fc996-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="fc996-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> de enlaces**](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="fc996-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="fc996-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> wsFederationHttpBinding**](wsfederationhttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="fc996-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<wsFederationHttpBinding>**](wsfederationhttpbinding.md)</span></span>\
<span data-ttu-id="fc996-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> de enlace**</span><span class="sxs-lookup"><span data-stu-id="fc996-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="fc996-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> de seguridad**](security-of-wsfederationhttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="fc996-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-wsfederationhttpbinding.md)</span></span>\
<span data-ttu-id="fc996-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> de mensajes**](message-element-of-wsfederationhttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="fc996-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<message>**](message-element-of-wsfederationhttpbinding.md)</span></span>\
<span data-ttu-id="fc996-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> claimTypeRequirements**](claimtyperequirements-for-message.md)</span><span class="sxs-lookup"><span data-stu-id="fc996-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<claimTypeRequirements>**](claimtyperequirements-for-message.md)</span></span>\
<span data-ttu-id="fc996-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<quitar >**</span><span class="sxs-lookup"><span data-stu-id="fc996-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fc996-113">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="fc996-113">Syntax</span></span>  
  
```xml  
<claimTypeRequirements>
  <remove claimType="URI" />
</claimTypeRequirements>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fc996-114">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="fc996-114">Attributes and Elements</span></span>  
 <span data-ttu-id="fc996-115">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="fc996-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fc996-116">Atributos</span><span class="sxs-lookup"><span data-stu-id="fc996-116">Attributes</span></span>  
  
|<span data-ttu-id="fc996-117">Atributo</span><span class="sxs-lookup"><span data-stu-id="fc996-117">Attribute</span></span>|<span data-ttu-id="fc996-118">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="fc996-118">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="fc996-119">claimType</span><span class="sxs-lookup"><span data-stu-id="fc996-119">claimType</span></span>|<span data-ttu-id="fc996-120">URI que define el tipo de una notificación que se va a eliminar.</span><span class="sxs-lookup"><span data-stu-id="fc996-120">A URI that defines the type of a claim to be removed.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="fc996-121">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="fc996-121">Child Elements</span></span>  
 <span data-ttu-id="fc996-122">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="fc996-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="fc996-123">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="fc996-123">Parent Elements</span></span>  
  
|<span data-ttu-id="fc996-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="fc996-124">Element</span></span>|<span data-ttu-id="fc996-125">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="fc996-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="fc996-126">\<claimTypeRequirements></span><span class="sxs-lookup"><span data-stu-id="fc996-126">\<claimTypeRequirements></span></span>](claimtyperequirements-for-message.md)|<span data-ttu-id="fc996-127">Especifica una colección de tipos de notificación requeridos.</span><span class="sxs-lookup"><span data-stu-id="fc996-127">Specifies a collection of required claim types.</span></span> <span data-ttu-id="fc996-128">Cada elemento es del tipo <xref:System.ServiceModel.Configuration.ClaimTypeElement>.</span><span class="sxs-lookup"><span data-stu-id="fc996-128">Each element is of type <xref:System.ServiceModel.Configuration.ClaimTypeElement>.</span></span><br /><br /> <span data-ttu-id="fc996-129">En un escenario aliado, los servicios indican los requisitos de las credenciales de entrada.</span><span class="sxs-lookup"><span data-stu-id="fc996-129">In a federated scenario, services state the requirements on incoming credentials.</span></span> <span data-ttu-id="fc996-130">Por ejemplo, las credenciales de entrada deben poseer un determinado conjunto de tipos de notificación.</span><span class="sxs-lookup"><span data-stu-id="fc996-130">For example, the incoming credentials must possess a certain set of claim types.</span></span> <span data-ttu-id="fc996-131">Cada elemento de la colección especifica los tipos de notificaciones necesarias y opcionales que se espera que aparezcan en una credencial aliada.</span><span class="sxs-lookup"><span data-stu-id="fc996-131">Each element in this collection specifies the types of required and optional claims expected to appear in a federated credential.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="fc996-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="fc996-132">See also</span></span>

- <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.ClaimTypeRequirements%2A>
- <xref:System.ServiceModel.Security.Tokens.ClaimTypeRequirement>
- <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.ClaimTypeRequirements%2A>
- <xref:System.ServiceModel.Configuration.ClaimTypeElementCollection>
- <xref:System.ServiceModel.Configuration.ClaimTypeElement>
