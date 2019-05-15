---
title: Usar la capa de sockets seguros
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Networking
- SSL
- Secure Sockets Layer
- requesting data from Internet, Secure Sockets Layer
- sending data, Secure Sockets Layer
- Network Resources
- data requests, Secure Sockets Layer
- receiving data, Secure Sockets Layer
- Internet, Secure Sockets Layer
ms.assetid: 6e4289e6-d1b7-4e82-ab0d-e83e3b6063ed
ms.openlocfilehash: 9cfa8d6a71898a1d1ea91825ffc9a37f4654ebd5
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64583531"
---
# <a name="using-secure-sockets-layer"></a><span data-ttu-id="c14d8-102">Usar la capa de sockets seguros</span><span class="sxs-lookup"><span data-stu-id="c14d8-102">Using Secure Sockets Layer</span></span>
<span data-ttu-id="c14d8-103">Las clases <xref:System.Net> usan la Capa de sockets seguros (SSL) para cifrar la conexión de varios protocolos de red.</span><span class="sxs-lookup"><span data-stu-id="c14d8-103">The <xref:System.Net> classes use the Secure Sockets Layer (SSL) to encrypt the connection for several network protocols.</span></span>  
  
 <span data-ttu-id="c14d8-104">Para las conexiones http, las clases <xref:System.Net.WebRequest> y <xref:System.Net.WebResponse> usan SSL para comunicarse con hosts web que admiten SSL.</span><span class="sxs-lookup"><span data-stu-id="c14d8-104">For http connections, the <xref:System.Net.WebRequest> and <xref:System.Net.WebResponse> classes use SSL to communicate with web hosts that support SSL.</span></span> <span data-ttu-id="c14d8-105">Es la clase <xref:System.Net.WebRequest> la que toma la decisión de usar SSL, según el URI que se le proporcione.</span><span class="sxs-lookup"><span data-stu-id="c14d8-105">The decision to use SSL is made by the <xref:System.Net.WebRequest> class, based on the URI it is given.</span></span> <span data-ttu-id="c14d8-106">Si el URI comienza con "https:", se usa SSL; si el URI comienza con "http:", se usa una conexión no cifrada.</span><span class="sxs-lookup"><span data-stu-id="c14d8-106">If the URI begins with "https:", SSL is used; if the URI begins with "http:", an unencrypted connection is used.</span></span>  
  
 <span data-ttu-id="c14d8-107">Para usar SSL con el protocolo de transferencia de archivos (FTP), establezca la propiedad <xref:System.Net.FtpWebRequest.EnableSsl> en true antes de llamar a <xref:System.Net.FtpWebRequest.GetResponse>.</span><span class="sxs-lookup"><span data-stu-id="c14d8-107">To use SSL with File Transfer Protocol (FTP), set the <xref:System.Net.FtpWebRequest.EnableSsl> property to true prior to calling <xref:System.Net.FtpWebRequest.GetResponse>.</span></span> <span data-ttu-id="c14d8-108">Del mismo modo, para usar SSL con el Protocolo simple de transferencia de correo (SMTP), establezca la propiedad <xref:System.Net.Mail.SmtpClient.EnableSsl> en true antes de enviar el correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="c14d8-108">Similarly, to use SSL with Simple Mail Transport Protocol (SMTP), set the <xref:System.Net.Mail.SmtpClient.EnableSsl> property to true prior to sending the email.</span></span>  
  
 <span data-ttu-id="c14d8-109">La clase <xref:System.Net.Security.SslStream> proporciona una abstracción basada en flujos para SSL y ofrece varias maneras de configurar el protocolo de enlace SSL.</span><span class="sxs-lookup"><span data-stu-id="c14d8-109">The <xref:System.Net.Security.SslStream> class provides a stream-based abstraction for SSL, and offers many ways to configure the SSL handshake.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c14d8-110">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c14d8-110">Example</span></span>  
  
### <a name="code"></a><span data-ttu-id="c14d8-111">Código</span><span class="sxs-lookup"><span data-stu-id="c14d8-111">Code</span></span>  
  
```vb  
Dim MyURI As String = "https://www.contoso.com/"  
Dim Wreq As WebRequest = WebRequest.Create(MyURI)  
  
Dim serverUri As String = "ftp://ftp.contoso.com/file.txt"  
Dim request As FtpWebRequest = CType(WebRequest.Create(serverUri), FtpWebRequest)  
request.Method = WebRequestMethods.Ftp.DeleteFile  
request.EnableSsl = True  
Dim response As FtpWebResponse = CType(request.GetResponse(), FtpWebResponse)  
```  
  
```csharp  
String MyURI = "https://www.contoso.com/";  
WebRequest WReq = WebRequest.Create(MyURI);  
  
String serverUri = "ftp://ftp.contoso.com/file.txt"  
FtpWebRequest request = (FtpWebRequest)WebRequest.Create(serverUri);  
request.EnableSsl = true;  
request.Method = WebRequestMethods.Ftp.DeleteFile;  
FtpWebResponse response = (FtpWebResponse)request.GetResponse();  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="c14d8-112">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="c14d8-112">Compiling the Code</span></span>  
 <span data-ttu-id="c14d8-113">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="c14d8-113">This example requires:</span></span>  
  
- <span data-ttu-id="c14d8-114">Referencias al espacio de nombres **System.Net**.</span><span class="sxs-lookup"><span data-stu-id="c14d8-114">References to the **System.Net** namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c14d8-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="c14d8-115">See also</span></span>

- [<span data-ttu-id="c14d8-116">Seguridad en la programación para redes</span><span class="sxs-lookup"><span data-stu-id="c14d8-116">Security in Network Programming</span></span>](../../../docs/framework/network-programming/security-in-network-programming.md)
- [<span data-ttu-id="c14d8-117">Programación para redes en .NET Framework</span><span class="sxs-lookup"><span data-stu-id="c14d8-117">Network Programming in the .NET Framework</span></span>](../../../docs/framework/network-programming/index.md)
- [<span data-ttu-id="c14d8-118">Selección y validación de certificados</span><span class="sxs-lookup"><span data-stu-id="c14d8-118">Certificate Selection and Validation</span></span>](../../../docs/framework/network-programming/certificate-selection-and-validation.md)
