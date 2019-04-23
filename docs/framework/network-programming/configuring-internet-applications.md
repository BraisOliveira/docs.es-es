---
title: Configuración de aplicaciones de Internet
ms.date: 03/30/2017
helpviewer_keywords:
- downloading Internet resources, default proxy
- sending data, default proxy
- receiving data, default proxy
- downloading Internet resources, configuring Internet applications
- protocol-specific modules
- custom authentication modules
- receiving data, configuring Internet applications
- configuration settings [.NET Framework], Internet applications
- requesting data from Internet, configuring Internet applications
- requesting data from Internet, default proxy
- response to Internet request, default proxy
- Internet, configuring Internet applications
- response to Internet request, configuring Internet applications
- default proxy
- network resources, default proxy
- sending data, configuring Internet applications
- network resources, configuring Internet applications
- Internet, default proxy
ms.assetid: bb707c72-eed2-4a82-8800-c9e68df2fd4f
ms.openlocfilehash: ddc4717c873e65311a8502e66f3edaf39dd89ff9
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59133807"
---
# <a name="configuring-internet-applications"></a><span data-ttu-id="f3bce-102">Configuración de aplicaciones de Internet</span><span class="sxs-lookup"><span data-stu-id="f3bce-102">Configuring Internet Applications</span></span>
<span data-ttu-id="f3bce-103">El elemento de configuración [Elemento \<system.Net> (configuración de red)](../../../docs/framework/configure-apps/file-schema/network/system-net-element-network-settings.md) contiene información de configuración de red para las aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="f3bce-103">The [\<system.Net> Element (Network Settings)](../../../docs/framework/configure-apps/file-schema/network/system-net-element-network-settings.md) configuration element contains network configuration information for applications.</span></span> <span data-ttu-id="f3bce-104">Con el [Elemento \<system.Net> (configuración de red)](../../../docs/framework/configure-apps/file-schema/network/system-net-element-network-settings.md), puede establecer servidores proxy, establecer parámetros de administración de conexiones e incluir módulos personalizados de autenticación y solicitud en la aplicación.</span><span class="sxs-lookup"><span data-stu-id="f3bce-104">Using the [\<system.Net> Element (Network Settings)](../../../docs/framework/configure-apps/file-schema/network/system-net-element-network-settings.md) element, you can set proxy servers, set connection management parameters, and include custom authentication and request modules in your application.</span></span>  
  
 <span data-ttu-id="f3bce-105">El [Elemento \<defaultProxy> (configuración de red)](../../../docs/framework/configure-apps/file-schema/network/defaultproxy-element-network-settings.md) define el servidor proxy devuelto por la clase `GlobalProxySelection`.</span><span class="sxs-lookup"><span data-stu-id="f3bce-105">The [\<defaultProxy> Element (Network Settings)](../../../docs/framework/configure-apps/file-schema/network/defaultproxy-element-network-settings.md) element defines the proxy server returned by the `GlobalProxySelection` class.</span></span> <span data-ttu-id="f3bce-106">Cualquier elemento <xref:System.Net.HttpWebRequest> que no tenga su propia propiedad <xref:System.Net.HttpWebRequest.Proxy%2A> establecida en un valor específico, usa el proxy predeterminado.</span><span class="sxs-lookup"><span data-stu-id="f3bce-106">Any <xref:System.Net.HttpWebRequest> that does not have its own <xref:System.Net.HttpWebRequest.Proxy%2A> property set to a specific value uses the default proxy.</span></span> <span data-ttu-id="f3bce-107">Además de establecer la dirección de proxy, puede crear una lista de direcciones de servidor que no vayan a usar el proxy y puede indicar que no se debería usar el proxy para direcciones locales.</span><span class="sxs-lookup"><span data-stu-id="f3bce-107">In addition to setting the proxy address, you can create a list of server addresses that will not use the proxy, and you can indicate that the proxy should not be used for local addresses.</span></span>  
  
 <span data-ttu-id="f3bce-108">Es importante tener en cuenta que la configuración de Microsoft Internet Explorer se combina con los valores de configuración, que tienen preferencia.</span><span class="sxs-lookup"><span data-stu-id="f3bce-108">It is important to note that the Microsoft Internet Explorer settings are combined with the configuration settings, with the latter taking precedence.</span></span>  
  
 <span data-ttu-id="f3bce-109">En el siguiente ejemplo se establece la dirección del servidor proxy predeterminada en `http://proxyserver`, se indica que el proxy no debe usarse para las direcciones locales y se especifica que todas las solicitudes a servidores ubicados en el dominio contoso.com deben omitir el proxy.</span><span class="sxs-lookup"><span data-stu-id="f3bce-109">The following example sets the default proxy server address to `http://proxyserver`, indicates that the proxy should not be used for local addresses, and specifies that all requests to servers located in the contoso.com domain should bypass the proxy.</span></span>  
  
```xml  
<configuration>  
    <system.net>  
        <defaultProxy>  
            <proxy  
                usesystemdefault = "false"  
                proxyaddress = "http://proxyserver:80"  
                bypassonlocal = "true"  
            />  
            <bypasslist>  
                <add address="http://[a-z]+\.contoso\.com/" />  
            </bypasslist>  
        </defaultProxy>  
    </system.net>  
</configuration>  
```  
  
 <span data-ttu-id="f3bce-110">Use el [Elemento \<connectionManagement> (configuración de red)](../../../docs/framework/configure-apps/file-schema/network/connectionmanagement-element-network-settings.md) para configurar el número de conexiones persistentes que pueden realizarse a un servidor concreto o a todos los demás servidores.</span><span class="sxs-lookup"><span data-stu-id="f3bce-110">Use the [\<connectionManagement> Element (Network Settings)](../../../docs/framework/configure-apps/file-schema/network/connectionmanagement-element-network-settings.md) element to configure the number of persistent connections that can be made to a specific server or to all other servers.</span></span> <span data-ttu-id="f3bce-111">En el ejemplo siguiente se configura la aplicación para que use dos conexiones persistentes al servidor `www.contoso.com`, cuatro conexiones persistentes al servidor con la dirección IP 192.168.1.2 y una conexión persistente a todos los demás servidores.</span><span class="sxs-lookup"><span data-stu-id="f3bce-111">The following example configures the application to use two persistent connections to the server `www.contoso.com`, four persistent connections to the server with the IP address 192.168.1.2, and one persistent connection to all other servers.</span></span>  
  
```xml  
<configuration>  
    <system.net>  
        <connectionManagement>  
            <add address="http://www.contoso.com" maxconnection="2" />  
            <add address="192.168.1.2" maxconnection="4" />  
            <add address="*" maxconnection="1" />  
        </connectionManagement>  
    </system.net>  
</configuration>  
```  
  
 <span data-ttu-id="f3bce-112">Los módulos de autenticación personalizados se configuran con el [Elemento \<authenticationModules> (configuración de red)](../../../docs/framework/configure-apps/file-schema/network/authenticationmodules-element-network-settings.md).</span><span class="sxs-lookup"><span data-stu-id="f3bce-112">Custom authentication modules are configured with the [\<authenticationModules> Element (Network Settings)](../../../docs/framework/configure-apps/file-schema/network/authenticationmodules-element-network-settings.md) element.</span></span> <span data-ttu-id="f3bce-113">Los módulos de autenticación personalizados deben implementar la interfaz <xref:System.Net.IAuthenticationModule>.</span><span class="sxs-lookup"><span data-stu-id="f3bce-113">Custom authentication modules must implement the <xref:System.Net.IAuthenticationModule> interface.</span></span>  
  
 <span data-ttu-id="f3bce-114">En el ejemplo siguiente se configura un módulo de autenticación personalizado.</span><span class="sxs-lookup"><span data-stu-id="f3bce-114">The following example configures a custom authentication module.</span></span>  
  
```xml  
<configuration>  
    <system.net>  
        <authenticationModules>  
            <add type="MyAuthModule, MyAuthModule.dll" />  
        </authenticationModules>  
    </system.net>  
</configuration>  
```  
  
 <span data-ttu-id="f3bce-115">Puede usar el [Elemento \<webRequestModules> (configuración de red)](../../../docs/framework/configure-apps/file-schema/network/webrequestmodules-element-network-settings.md) para configurar la aplicación de modo que use módulos personalizados específicos del protocolo para solicitar información de recursos de Internet.</span><span class="sxs-lookup"><span data-stu-id="f3bce-115">You can use the [\<webRequestModules> Element (Network Settings)](../../../docs/framework/configure-apps/file-schema/network/webrequestmodules-element-network-settings.md) element to configure your application to use custom protocol-specific modules to request information from Internet resources.</span></span> <span data-ttu-id="f3bce-116">Los módulos especificados deben implementar la interfaz <xref:System.Net.IWebRequestCreate>.</span><span class="sxs-lookup"><span data-stu-id="f3bce-116">The specified modules must implement the <xref:System.Net.IWebRequestCreate> interface.</span></span> <span data-ttu-id="f3bce-117">Puede invalidar los módulos predeterminados HTTP, HTTPS y de solicitud de archivos si especifica el módulo personalizado en el archivo de configuración, como en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="f3bce-117">You can override the default HTTP, HTTPS, and file request modules by specifying your custom module in the configuration file, as in the following example.</span></span>  
  
```xml  
<configuration>  
    <system.net>  
        <webRequestModules>  
            <add  
                prefix="HTTP"  
                type = "MyHttpRequest.dll, MyHttpRequestCreator"  
            />  
        </webRequestModules>  
    </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="f3bce-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="f3bce-118">See also</span></span>

- [<span data-ttu-id="f3bce-119">Programación para redes en .NET Framework</span><span class="sxs-lookup"><span data-stu-id="f3bce-119">Network Programming in the .NET Framework</span></span>](../../../docs/framework/network-programming/index.md)
- [<span data-ttu-id="f3bce-120">Esquema de la configuración de red</span><span class="sxs-lookup"><span data-stu-id="f3bce-120">Network Settings Schema</span></span>](../../../docs/framework/configure-apps/file-schema/network/index.md)
- [<span data-ttu-id="f3bce-121">Elemento \<system.Net> (configuración de red)</span><span class="sxs-lookup"><span data-stu-id="f3bce-121">\<system.Net> Element (Network Settings)</span></span>](../../../docs/framework/configure-apps/file-schema/network/system-net-element-network-settings.md)
