---
title: 'Mitigación: marcos PNG en objetos de icono'
ms.date: 03/30/2017
ms.assetid: ca87fefb-7144-4b4e-8832-5a939adbb4b2
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 85a76681cf6efd649fe366a68d956246334975fe
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70789975"
---
# <a name="mitigation-png-frames-in-icon-objects"></a><span data-ttu-id="9bb59-102">Mitigación: marcos PNG en objetos de icono</span><span class="sxs-lookup"><span data-stu-id="9bb59-102">Mitigation: PNG Frames in Icon Objects</span></span>
<span data-ttu-id="9bb59-103">A partir de .NET Framework 4.6, el método <xref:System.Drawing.Icon.ToBitmap%2A?displayProperty=nameWithType> convierte correctamente iconos con marcos PNG en objetos <xref:System.Drawing.Bitmap> .</span><span class="sxs-lookup"><span data-stu-id="9bb59-103">Starting with the .NET Framework 4.6, the <xref:System.Drawing.Icon.ToBitmap%2A?displayProperty=nameWithType> method successfully converts icons with PNG frames into <xref:System.Drawing.Bitmap> objects.</span></span>  
  
 <span data-ttu-id="9bb59-104">En aplicaciones destinadas a .NET Framework 4.5.2 y versiones anteriores, el método <xref:System.Drawing.Icon.ToBitmap%2A?displayProperty=nameWithType> genera una excepción <xref:System.ArgumentOutOfRangeException> si el objeto <xref:System.Drawing.Icon> tiene marcos PNG.</span><span class="sxs-lookup"><span data-stu-id="9bb59-104">In apps that target the .NET Framework 4.5.2 and earlier versions, the <xref:System.Drawing.Icon.ToBitmap%2A?displayProperty=nameWithType> method throws an <xref:System.ArgumentOutOfRangeException> exception if the <xref:System.Drawing.Icon> object has PNG frames.</span></span>  
  
## <a name="impact"></a><span data-ttu-id="9bb59-105">Impacto</span><span class="sxs-lookup"><span data-stu-id="9bb59-105">Impact</span></span>  
 <span data-ttu-id="9bb59-106">Este cambio afecta a las aplicaciones que se vuelven a compilar para tener como destino .NET Framework 4.6 y que implementan un control especial para <xref:System.ArgumentOutOfRangeException> que se genera cuando un objeto <xref:System.Drawing.Icon> tiene marcos PNG.</span><span class="sxs-lookup"><span data-stu-id="9bb59-106">This change affects apps that are recompiled to target the .NET Framework 4.6 and that implement special handling for the <xref:System.ArgumentOutOfRangeException> that is thrown when an <xref:System.Drawing.Icon> object has PNG frames.</span></span> <span data-ttu-id="9bb59-107">Cuando se ejecuta en .NET Framework 4.6, la conversión es correcta, ya no se genera un <xref:System.ArgumentOutOfRangeException> y, por tanto, ya no se invoca el controlador de excepciones.</span><span class="sxs-lookup"><span data-stu-id="9bb59-107">When running under the .NET Framework 4.6, the conversion is successful, an <xref:System.ArgumentOutOfRangeException> is no longer thrown, and therefore the exception handler is no longer invoked.</span></span>  
  
### <a name="mitigation"></a><span data-ttu-id="9bb59-108">Mitigación</span><span class="sxs-lookup"><span data-stu-id="9bb59-108">Mitigation</span></span>  
 <span data-ttu-id="9bb59-109">Si no desea este comportamiento, puede conservar el comportamiento anterior agregando el siguiente elemento en la sección [\<runtime>](../configure-apps/file-schema/runtime/runtime-element.md) del archivo app.config:</span><span class="sxs-lookup"><span data-stu-id="9bb59-109">If this behavior is undesirable, you can retain the previous behavior by adding the following element to the [\<runtime>](../configure-apps/file-schema/runtime/runtime-element.md) section of your app.config file:</span></span>  
  
```xml  
<AppContextSwitchOverrides   
      value="Switch.System.Drawing.DontSupportPngFramesInIcons=true" />  
```  
  
 <span data-ttu-id="9bb59-110">Si el archivo app.config ya contiene el elemento `AppContextSwitchOverrides` , el nuevo valor se debe combinar con el atributo `value` como este:</span><span class="sxs-lookup"><span data-stu-id="9bb59-110">If the app.config file already contains the `AppContextSwitchOverrides` element, the new value should be merged with the `value` attribute like this:</span></span>  
  
```xml  
<AppContextSwitchOverrides   
      value="Switch.System.Drawing.DontSupportPngFramesInIcons=true;<previous key>=<previous value>" />  
```  
  
## <a name="see-also"></a><span data-ttu-id="9bb59-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="9bb59-111">See also</span></span>

- [<span data-ttu-id="9bb59-112">Cambios de redestinación</span><span class="sxs-lookup"><span data-stu-id="9bb59-112">Retargeting Changes</span></span>](retargeting-changes-in-the-net-framework-4-6.md)
