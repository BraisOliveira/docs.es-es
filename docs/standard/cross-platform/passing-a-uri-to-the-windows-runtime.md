---
title: Pasar un URI a Windows Runtime
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Windows Runtime, .NET Framework support for
- Windows Runtime, passing a URI to
ms.assetid: 3eb5ce6f-f304-4f87-8e81-0f25092f5ad4
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c5ce0d4ac2b95dc4d51e785e3a00026f56c13d2c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61921386"
---
# <a name="passing-a-uri-to-the-windows-runtime"></a><span data-ttu-id="25fdb-102">Pasar un URI a Windows Runtime</span><span class="sxs-lookup"><span data-stu-id="25fdb-102">Passing a URI to the Windows Runtime</span></span>
<span data-ttu-id="25fdb-103">Los métodos de Windows Runtime solo aceptan URI absolutos.</span><span class="sxs-lookup"><span data-stu-id="25fdb-103">Windows Runtime methods accept only absolute URIs.</span></span> <span data-ttu-id="25fdb-104">Si se pasa un URI relativo a un método [!INCLUDE[wrt](../../../includes/wrt-md.md)], se produce una excepción <xref:System.ArgumentException>.</span><span class="sxs-lookup"><span data-stu-id="25fdb-104">If you pass a relative URI to a [!INCLUDE[wrt](../../../includes/wrt-md.md)] method, an <xref:System.ArgumentException> exception is thrown.</span></span> <span data-ttu-id="25fdb-105">El motivo es el siguiente: Cuando se usa el [!INCLUDE[wrt](../../../includes/wrt-md.md)] en el código de .NET Framework, el <xref:Windows.Foundation.Uri?displayProperty=nameWithType> clase aparece como <xref:System.Uri?displayProperty=nameWithType> en Intellisense.</span><span class="sxs-lookup"><span data-stu-id="25fdb-105">Here's why: When you use the [!INCLUDE[wrt](../../../includes/wrt-md.md)] in .NET Framework code, the <xref:Windows.Foundation.Uri?displayProperty=nameWithType> class appears as <xref:System.Uri?displayProperty=nameWithType> in Intellisense.</span></span> <span data-ttu-id="25fdb-106">El <xref:System.Uri?displayProperty=nameWithType> clase permite URI relativos, pero la <xref:Windows.Foundation.Uri?displayProperty=nameWithType> clase no es así.</span><span class="sxs-lookup"><span data-stu-id="25fdb-106">The <xref:System.Uri?displayProperty=nameWithType> class allows relative URIs, but the <xref:Windows.Foundation.Uri?displayProperty=nameWithType> class does not.</span></span> <span data-ttu-id="25fdb-107">Esto también ocurre con los métodos que usted expone en componentes de [!INCLUDE[wrt](../../../includes/wrt-md.md)].</span><span class="sxs-lookup"><span data-stu-id="25fdb-107">This is also true for methods you expose in [!INCLUDE[wrt](../../../includes/wrt-md.md)] Components.</span></span> <span data-ttu-id="25fdb-108">Si su componente expone un método que toma un URI, la firma de su código incluye <xref:System.Uri?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="25fdb-108">If your component exposes a method that takes a URI, the signature in your code includes <xref:System.Uri?displayProperty=nameWithType>.</span></span> <span data-ttu-id="25fdb-109">Sin embargo, para los usuarios de su componente, la firma incluye <xref:Windows.Foundation.Uri?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="25fdb-109">However, to users of your component, the signature includes <xref:Windows.Foundation.Uri?displayProperty=nameWithType>.</span></span> <span data-ttu-id="25fdb-110">Un URI que se pase a su componente debe ser absoluto.</span><span class="sxs-lookup"><span data-stu-id="25fdb-110">A URI that is passed to your component must be an absolute URI.</span></span>  
  
<span data-ttu-id="25fdb-111">En este tema se muestra cómo detectar un URI absoluto y cómo crear uno al hacer referencia a un recurso del paquete de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="25fdb-111">This topic shows how to detect an absolute URI and how to create one when referring to a resource in the app package.</span></span>  
  
## <a name="detecting-and-using-an-absolute-uri"></a><span data-ttu-id="25fdb-112">Detectar y usar un URI absoluto</span><span class="sxs-lookup"><span data-stu-id="25fdb-112">Detecting and using an absolute URI</span></span>  
<span data-ttu-id="25fdb-113">Use la propiedad <xref:System.Uri.IsAbsoluteUri%2A?displayProperty=nameWithType> para asegurarse de que un URI sea absoluto antes de pasarlo a [!INCLUDE[wrt](../../../includes/wrt-md.md)].</span><span class="sxs-lookup"><span data-stu-id="25fdb-113">Use the <xref:System.Uri.IsAbsoluteUri%2A?displayProperty=nameWithType> property to ensure that a URI is absolute before passing it to the [!INCLUDE[wrt](../../../includes/wrt-md.md)].</span></span> <span data-ttu-id="25fdb-114">Utilizar esta propiedad es más eficaz que detectar y gestionar la excepción <xref:System.ArgumentException>.</span><span class="sxs-lookup"><span data-stu-id="25fdb-114">Using this property is more efficient than catching and handling the <xref:System.ArgumentException> exception.</span></span>  
  
## <a name="using-an-absolute-uri-for-a-resource-in-the-app-package"></a><span data-ttu-id="25fdb-115">Usar un URI absoluto para un recurso del paquete de la aplicación</span><span class="sxs-lookup"><span data-stu-id="25fdb-115">Using an absolute URI for a resource in the app package</span></span>  
<span data-ttu-id="25fdb-116">Si desea especificar un URI para un recurso incluido en el paquete de la aplicación, puede usar los esquemas `ms-appx` o `ms-appx-web` para crear un URI absoluto.</span><span class="sxs-lookup"><span data-stu-id="25fdb-116">If you want to specify a URI for a resource that your app package contains, you can use the `ms-appx` or `ms-appx-web` scheme to create an absolute URI.</span></span>  
  
<span data-ttu-id="25fdb-117">El ejemplo siguiente muestra cómo establecer el <xref:Windows.UI.Xaml.Controls.WebView.Source%2A> propiedad para un <xref:Windows.UI.Xaml.Controls.WebView> control y el <xref:Windows.UI.Xaml.Controls.Image.Source%2A> propiedad para un <xref:Windows.UI.Xaml.Controls.Image> control a los recursos que se encuentran en una carpeta denominada páginas, utilizando tanto XAML como código.</span><span class="sxs-lookup"><span data-stu-id="25fdb-117">The following example shows how to set the <xref:Windows.UI.Xaml.Controls.WebView.Source%2A> property for a <xref:Windows.UI.Xaml.Controls.WebView> control and the <xref:Windows.UI.Xaml.Controls.Image.Source%2A> property for an <xref:Windows.UI.Xaml.Controls.Image> control to resources that are contained in a folder named Pages, using both XAML and code.</span></span>  
  
[!code-xaml[System.URIToWindowsURI#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.uritowindowsuri/cs/mainpage.xaml#1)]  
[!code-csharp[System.URIToWindowsURI#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.uritowindowsuri/cs/mainpage.xaml.cs#2)]
[!code-vb[System.URIToWindowsURI#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.uritowindowsuri/vb/mainpage.xaml.vb#2)]  
  
<span data-ttu-id="25fdb-118">Para obtener más información sobre estos esquemas, vea [esquemas de URI](/windows/uwp/app-resources/uri-schemes) en el centro de desarrollo de Windows.</span><span class="sxs-lookup"><span data-stu-id="25fdb-118">For more information about these schemes, see [URI schemes](/windows/uwp/app-resources/uri-schemes) in the Windows Dev Center.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="25fdb-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="25fdb-119">See also</span></span>

- [<span data-ttu-id="25fdb-120">Compatibilidad de .NET Framework con las aplicaciones de la Tienda Windows y Windows Runtime</span><span class="sxs-lookup"><span data-stu-id="25fdb-120">.NET Framework Support for Windows Store Apps and Windows Runtime</span></span>](../../../docs/standard/cross-platform/support-for-windows-store-apps-and-windows-runtime.md)
