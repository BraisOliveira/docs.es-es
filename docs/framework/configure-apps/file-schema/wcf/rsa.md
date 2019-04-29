---
title: <rsa>
ms.date: 03/30/2017
ms.assetid: ae1f2267-e40d-42ff-8abf-06ab7067bdb9
ms.openlocfilehash: 0e307069bd3a98153cc66147ba7bcf511cf13a8e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61670667"
---
# <a name="rsa"></a><span data-ttu-id="c869d-101">\<rsa></span><span class="sxs-lookup"><span data-stu-id="c869d-101">\<rsa></span></span>
<span data-ttu-id="c869d-102">Un cliente WCF seguro que se conecta a un punto de conexión con esta identidad comprueba que las notificaciones presentadas por el servidor contienen una notificación que incluye la clave pública RSA utilizada para construir esta identidad.</span><span class="sxs-lookup"><span data-stu-id="c869d-102">A secure WCF client that connects to an endpoint with this identity verifies that the claims presented by the server contain a claim that contains the RSA public key used to construct this identity.</span></span>  
  
 <span data-ttu-id="c869d-103">\<identity></span><span class="sxs-lookup"><span data-stu-id="c869d-103">\<identity></span></span>  
<span data-ttu-id="c869d-104">\<rsa></span><span class="sxs-lookup"><span data-stu-id="c869d-104">\<rsa></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c869d-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c869d-105">Syntax</span></span>  
  
```xml  
<rsa value="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c869d-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="c869d-106">Attributes and Elements</span></span>  
 <span data-ttu-id="c869d-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios</span><span class="sxs-lookup"><span data-stu-id="c869d-107">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c869d-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="c869d-108">Attributes</span></span>  
  
|<span data-ttu-id="c869d-109">Atributo</span><span class="sxs-lookup"><span data-stu-id="c869d-109">Attribute</span></span>|<span data-ttu-id="c869d-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="c869d-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c869d-111">value</span><span class="sxs-lookup"><span data-stu-id="c869d-111">value</span></span>|<span data-ttu-id="c869d-112">Cadena opcional.</span><span class="sxs-lookup"><span data-stu-id="c869d-112">Optional String.</span></span> <span data-ttu-id="c869d-113">El valor de clave pública de RSA con la que se va a comparar en el cliente.</span><span class="sxs-lookup"><span data-stu-id="c869d-113">The RSA public key value to be compared with on the client.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c869d-114">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="c869d-114">Child Elements</span></span>  
 <span data-ttu-id="c869d-115">Ninguna</span><span class="sxs-lookup"><span data-stu-id="c869d-115">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c869d-116">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="c869d-116">Parent Elements</span></span>  
  
|<span data-ttu-id="c869d-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="c869d-117">Element</span></span>|<span data-ttu-id="c869d-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="c869d-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c869d-119">\<identity></span><span class="sxs-lookup"><span data-stu-id="c869d-119">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|<span data-ttu-id="c869d-120">Especifica la identidad del servicio que va a autenticar el cliente.</span><span class="sxs-lookup"><span data-stu-id="c869d-120">Specifies the identity of the service to be authenticated by the client.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c869d-121">Comentarios</span><span class="sxs-lookup"><span data-stu-id="c869d-121">Remarks</span></span>  
 <span data-ttu-id="c869d-122">Una comprobación de RSA le permite restringir específicamente la autenticación a un certificado único basado en su clave RSA o que generó su propio valor de clave de RSA.</span><span class="sxs-lookup"><span data-stu-id="c869d-122">A RSA check enables you to specifically restrict authentication to a single certificate based upon its RSA key or generated your own RSA key value.</span></span> <span data-ttu-id="c869d-123">Esto habilita una autenticación más estricta de una clave RSA específica en el gasto del servicio que ya no trabaja con clientes existentes si se cambia el valor de clave de RSA.</span><span class="sxs-lookup"><span data-stu-id="c869d-123">This enables stricter authentication of a specific RSA key at the expense of the service no longer working with existing clients if the RSA key value is changed.</span></span>  
  
 <span data-ttu-id="c869d-124">Para obtener más información sobre el uso de identidad para validar un servicio a un cliente, consulte [autenticación e identidad de servicio](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="c869d-124">For more information about using identity to validate a service to a client, see [Service Identity and Authentication](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="c869d-125">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c869d-125">Example</span></span>  
 <span data-ttu-id="c869d-126">El código de configuración siguiente especifica el valor de clave pública de un certificado X.509 que se usa para autenticar un servidor.</span><span class="sxs-lookup"><span data-stu-id="c869d-126">The following configuration code specifies the public key value of an X.509 certificate that is used to authenticate a server.</span></span>  
  
```xml  
<identity>
  <rsa value="0000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000" />
</identity>
```  
  
## <a name="see-also"></a><span data-ttu-id="c869d-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="c869d-127">See also</span></span>

- <xref:System.ServiceModel.Configuration.IdentityElement>
- <xref:System.ServiceModel.EndpointAddress>
- <xref:System.ServiceModel.EndpointAddress.Identity%2A>
- <xref:System.ServiceModel.RsaEndpointIdentity>
- [<span data-ttu-id="c869d-128">Identidad del servicio y autenticación</span><span class="sxs-lookup"><span data-stu-id="c869d-128">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="c869d-129">\<identity></span><span class="sxs-lookup"><span data-stu-id="c869d-129">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)
