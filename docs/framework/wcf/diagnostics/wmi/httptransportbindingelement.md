---
title: HttpTransportBindingElement
ms.date: 03/30/2017
ms.assetid: 088a7bce-6bb2-4839-ad74-f68d4b1aa0f9
ms.openlocfilehash: 5e23342d57621554aaec67c5c568bb75202a9454
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59073746"
---
# <a name="httptransportbindingelement"></a><span data-ttu-id="6216e-102">HttpTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="6216e-102">HttpTransportBindingElement</span></span>
<span data-ttu-id="6216e-103">HttpTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="6216e-103">HttpTransportBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6216e-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6216e-104">Syntax</span></span>  
  
```csharp
class HttpTransportBindingElement : TransportBindingElement  
{  
  boolean AllowCookies;  
  string AuthenticationScheme;  
  boolean BypassProxyOnLocal;  
  string HostNameComparisonMode;  
  boolean KeepAliveEnabled;  
  sint32 MaxBufferSize;  
  string ProxyAddress;  
  string ProxyAuthenticationScheme;  
  string Realm;  
  string TransferMode;  
  boolean UnsafeConnectionNtlmAuthentication;  
  boolean UseDefaultWebProxy;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="6216e-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="6216e-105">Methods</span></span>  
 <span data-ttu-id="6216e-106">La clase HttpTransportBindingElement no define ningún método.</span><span class="sxs-lookup"><span data-stu-id="6216e-106">The HttpTransportBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="6216e-107">Propiedades</span><span class="sxs-lookup"><span data-stu-id="6216e-107">Properties</span></span>  
 <span data-ttu-id="6216e-108">La clase HttpTransportBindingElement tiene las propiedades siguientes:</span><span class="sxs-lookup"><span data-stu-id="6216e-108">The HttpTransportBindingElement class has the following properties:</span></span>  
  
### <a name="allowcookies"></a><span data-ttu-id="6216e-109">AllowCookies</span><span class="sxs-lookup"><span data-stu-id="6216e-109">AllowCookies</span></span>  
 <span data-ttu-id="6216e-110">Tipo de datos: booleano</span><span class="sxs-lookup"><span data-stu-id="6216e-110">Data type: boolean</span></span>  
  
 <span data-ttu-id="6216e-111">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="6216e-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="6216e-112">Un valor que indica si el cliente acepta las cookies y las propaga en solicitudes futuras.</span><span class="sxs-lookup"><span data-stu-id="6216e-112">A value that indicates whether the client accepts cookies and propagates them on future requests.</span></span>  
  
### <a name="authenticationscheme"></a><span data-ttu-id="6216e-113">AuthenticationScheme</span><span class="sxs-lookup"><span data-stu-id="6216e-113">AuthenticationScheme</span></span>  
 <span data-ttu-id="6216e-114">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="6216e-114">Data type: string</span></span>  
  
 <span data-ttu-id="6216e-115">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="6216e-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="6216e-116">El esquema de autenticación usado para autenticar las solicitudes del cliente que está procesando un agente de escucha HTTP.</span><span class="sxs-lookup"><span data-stu-id="6216e-116">The authentication scheme used to authenticate client requests being processed by an HTTP listener.</span></span>  
  
### <a name="bypassproxyonlocal"></a><span data-ttu-id="6216e-117">BypassProxyOnLocal</span><span class="sxs-lookup"><span data-stu-id="6216e-117">BypassProxyOnLocal</span></span>  
 <span data-ttu-id="6216e-118">Tipo de datos: booleano</span><span class="sxs-lookup"><span data-stu-id="6216e-118">Data type: boolean</span></span>  
  
 <span data-ttu-id="6216e-119">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="6216e-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="6216e-120">Un valor que indica si se omiten servidores proxy para direcciones locales.</span><span class="sxs-lookup"><span data-stu-id="6216e-120">A value that indicates whether proxies are ignored for local addresses.</span></span>  
  
### <a name="hostnamecomparisonmode"></a><span data-ttu-id="6216e-121">HostNameComparisonMode</span><span class="sxs-lookup"><span data-stu-id="6216e-121">HostNameComparisonMode</span></span>  
 <span data-ttu-id="6216e-122">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="6216e-122">Data type: string</span></span>  
  
 <span data-ttu-id="6216e-123">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="6216e-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="6216e-124">Un valor que indica si el nombre del host se usa para alcanzar el servicio al coincidir con el URI.</span><span class="sxs-lookup"><span data-stu-id="6216e-124">A value that indicates whether the hostname is used to reach the service when matching on the URI.</span></span>  
  
### <a name="keepaliveenabled"></a><span data-ttu-id="6216e-125">KeepAliveEnabled</span><span class="sxs-lookup"><span data-stu-id="6216e-125">KeepAliveEnabled</span></span>  
 <span data-ttu-id="6216e-126">Tipo de datos: booleano</span><span class="sxs-lookup"><span data-stu-id="6216e-126">Data type: boolean</span></span>  
  
 <span data-ttu-id="6216e-127">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="6216e-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="6216e-128">Cuando se habilita, las conexiones HTTP se mantienen vivas sin tener en cuenta el nivel de actividad.</span><span class="sxs-lookup"><span data-stu-id="6216e-128">When enabled, HTTP connections are kept alive regardless of activity level.</span></span>  
  
### <a name="maxbuffersize"></a><span data-ttu-id="6216e-129">MaxBufferSize</span><span class="sxs-lookup"><span data-stu-id="6216e-129">MaxBufferSize</span></span>  
 <span data-ttu-id="6216e-130">Tipo de datos: sint32</span><span class="sxs-lookup"><span data-stu-id="6216e-130">Data type: sint32</span></span>  
  
 <span data-ttu-id="6216e-131">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="6216e-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="6216e-132">El tamaño máximo del grupo de búferes.</span><span class="sxs-lookup"><span data-stu-id="6216e-132">The maximum size of the buffer pool.</span></span>  
  
### <a name="proxyaddress"></a><span data-ttu-id="6216e-133">ProxyAddress</span><span class="sxs-lookup"><span data-stu-id="6216e-133">ProxyAddress</span></span>  
 <span data-ttu-id="6216e-134">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="6216e-134">Data type: string</span></span>  
  
 <span data-ttu-id="6216e-135">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="6216e-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="6216e-136">Un URI que contiene la dirección del proxy que utilizar para las solicitudes HTTP.</span><span class="sxs-lookup"><span data-stu-id="6216e-136">A URI that contains the address of the proxy to use for HTTP requests.</span></span>  
  
### <a name="proxyauthenticationscheme"></a><span data-ttu-id="6216e-137">ProxyAuthenticationScheme</span><span class="sxs-lookup"><span data-stu-id="6216e-137">ProxyAuthenticationScheme</span></span>  
 <span data-ttu-id="6216e-138">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="6216e-138">Data type: string</span></span>  
  
 <span data-ttu-id="6216e-139">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="6216e-139">Access type: Read-only</span></span>  
  
 <span data-ttu-id="6216e-140">El esquema de autenticación usado para autenticar las solicitudes del cliente que un proxy HTTP está procesando.</span><span class="sxs-lookup"><span data-stu-id="6216e-140">The authentication scheme used to authenticate client requests being processed by an HTTP proxy.</span></span>  
  
### <a name="realm"></a><span data-ttu-id="6216e-141">Dominio kerberos</span><span class="sxs-lookup"><span data-stu-id="6216e-141">Realm</span></span>  
 <span data-ttu-id="6216e-142">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="6216e-142">Data type: string</span></span>  
  
 <span data-ttu-id="6216e-143">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="6216e-143">Access type: Read-only</span></span>  
  
 <span data-ttu-id="6216e-144">El dominio kerberos de autenticación.</span><span class="sxs-lookup"><span data-stu-id="6216e-144">The authentication realm.</span></span>  
  
### <a name="transfermode"></a><span data-ttu-id="6216e-145">TransferMode</span><span class="sxs-lookup"><span data-stu-id="6216e-145">TransferMode</span></span>  
 <span data-ttu-id="6216e-146">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="6216e-146">Data type: string</span></span>  
  
 <span data-ttu-id="6216e-147">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="6216e-147">Access type: Read-only</span></span>  
  
 <span data-ttu-id="6216e-148">Un valor que especifica si los mensajes se almacenan en búfer, se transmiten o si son una solicitud o una respuesta.</span><span class="sxs-lookup"><span data-stu-id="6216e-148">A value that specifies whether messages are buffered or streamed or a request or response.</span></span>  
  
### <a name="unsafeconnectionntlmauthentication"></a><span data-ttu-id="6216e-149">UnsafeConnectionNtlmAuthentication</span><span class="sxs-lookup"><span data-stu-id="6216e-149">UnsafeConnectionNtlmAuthentication</span></span>  
 <span data-ttu-id="6216e-150">Tipo de datos: booleano</span><span class="sxs-lookup"><span data-stu-id="6216e-150">Data type: boolean</span></span>  
  
 <span data-ttu-id="6216e-151">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="6216e-151">Access type: Read-only</span></span>  
  
 <span data-ttu-id="6216e-152">Un valor que indica si la conexión compartida no segura está habilitada en el servidor.</span><span class="sxs-lookup"><span data-stu-id="6216e-152">A value that indicates whether Unsafe Connection Sharing is enabled on the server.</span></span>  
  
### <a name="usedefaultwebproxy"></a><span data-ttu-id="6216e-153">UseDefaultWebProxy</span><span class="sxs-lookup"><span data-stu-id="6216e-153">UseDefaultWebProxy</span></span>  
 <span data-ttu-id="6216e-154">Tipo de datos: booleano</span><span class="sxs-lookup"><span data-stu-id="6216e-154">Data type: boolean</span></span>  
  
 <span data-ttu-id="6216e-155">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="6216e-155">Access type: Read-only</span></span>  
  
 <span data-ttu-id="6216e-156">Un valor que indica si se utiliza la configuración de proxy del equipo en lugar de la configuración específica del usuario.</span><span class="sxs-lookup"><span data-stu-id="6216e-156">A value that indicates whether the machine-wide proxy settings are used rather than the user specific settings.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6216e-157">Requisitos</span><span class="sxs-lookup"><span data-stu-id="6216e-157">Requirements</span></span>  
  
|<span data-ttu-id="6216e-158">MOF</span><span class="sxs-lookup"><span data-stu-id="6216e-158">MOF</span></span>|<span data-ttu-id="6216e-159">Se declara en Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="6216e-159">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="6216e-160">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="6216e-160">Namespace</span></span>|<span data-ttu-id="6216e-161">Se define en root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="6216e-161">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6216e-162">Vea también</span><span class="sxs-lookup"><span data-stu-id="6216e-162">See also</span></span>

- <xref:System.ServiceModel.Channels.HttpTransportBindingElement>
