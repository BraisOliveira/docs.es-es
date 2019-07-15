---
ms.openlocfilehash: d48519443aeee05617538cf2cc12bea49ad3e16d
ms.sourcegitcommit: d55e14eb63588830c0ba1ea95a24ce6c57ef8c8c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/11/2019
ms.locfileid: "67858541"
---
### <a name="x509certificate2tostringboolean-does-not-throw-now-when-net-cannot-handle-the-certificate"></a><span data-ttu-id="4d9ac-101">X509Certificate2.ToString(Boolean) ahora no se inicia cuando .NET no puede controlar el certificado</span><span class="sxs-lookup"><span data-stu-id="4d9ac-101">X509Certificate2.ToString(Boolean) does not throw now when .NET cannot handle the certificate</span></span>

|   |   |
|---|---|
|<span data-ttu-id="4d9ac-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="4d9ac-102">Details</span></span>|<span data-ttu-id="4d9ac-103">En .NET Framework 4.5.2 y versiones anteriores, este método iniciaba una excepción si se pasaba <code>true</code> para el parámetro detallado y había certificados instalados no admitidos por .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="4d9ac-103">In .NET Framework 4.5.2 and earlier versions, this method would throw if <code>true</code> was passed for the verbose parameter and there were certificates installed that weren't supported by the .NET Framework.</span></span> <span data-ttu-id="4d9ac-104">Ahora, el método se realizará correctamente y devolverá una cadena válida que omite las partes inaccesibles del certificado.</span><span class="sxs-lookup"><span data-stu-id="4d9ac-104">Now, the method will succeed and return a valid string that omits the inaccessible portions of the certificate.</span></span>|
|<span data-ttu-id="4d9ac-105">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="4d9ac-105">Suggestion</span></span>|<span data-ttu-id="4d9ac-106">Cualquier código que dependa de <xref:System.Security.Cryptography.X509Certificates.X509Certificate2.ToString(System.Boolean)?displayProperty=nameWithType> se debe actualizar para esperar que la cadena devuelta pueda excluir algunos datos del certificado (como la clave pública, la clave privada y las extensiones) en algunos casos en los que anteriormente se habría iniciado la API.</span><span class="sxs-lookup"><span data-stu-id="4d9ac-106">Any code depending on <xref:System.Security.Cryptography.X509Certificates.X509Certificate2.ToString(System.Boolean)?displayProperty=nameWithType> should be updated to expect that the returned string may exclude some certificate data (such as public key, private key, and extensions) in some cases in which the API would have previously thrown.</span></span>|
|<span data-ttu-id="4d9ac-107">Ámbito</span><span class="sxs-lookup"><span data-stu-id="4d9ac-107">Scope</span></span>|<span data-ttu-id="4d9ac-108">Borde</span><span class="sxs-lookup"><span data-stu-id="4d9ac-108">Edge</span></span>|
|<span data-ttu-id="4d9ac-109">Versión</span><span class="sxs-lookup"><span data-stu-id="4d9ac-109">Version</span></span>|<span data-ttu-id="4d9ac-110">4.6</span><span class="sxs-lookup"><span data-stu-id="4d9ac-110">4.6</span></span>|
|<span data-ttu-id="4d9ac-111">Tipo</span><span class="sxs-lookup"><span data-stu-id="4d9ac-111">Type</span></span>|<span data-ttu-id="4d9ac-112">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="4d9ac-112">Runtime</span></span>|
|<span data-ttu-id="4d9ac-113">API afectadas</span><span class="sxs-lookup"><span data-stu-id="4d9ac-113">Affected APIs</span></span>|<ul><li><xref:System.Security.Cryptography.X509Certificates.X509Certificate2.ToString(System.Boolean)?displayProperty=nameWithType></li></ul>|

