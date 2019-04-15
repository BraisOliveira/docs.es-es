---
title: 'Mitigación: Diseño de WPF'
ms.date: 03/30/2017
ms.assetid: 805ffd7f-8d1e-427e-a648-601ca8ec37a5
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f81af76ed305fb614202c240e449adc62b310933
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59189942"
---
# <a name="mitigation-wpf-layout"></a><span data-ttu-id="eb2e6-102">Mitigación: Diseño de WPF</span><span class="sxs-lookup"><span data-stu-id="eb2e6-102">Mitigation: WPF Layout</span></span>
<span data-ttu-id="eb2e6-103">El diseño de los controles WPF puede cambiar ligeramente.</span><span class="sxs-lookup"><span data-stu-id="eb2e6-103">The layout of WPF controls can change slightly.</span></span>  
  
## <a name="impact"></a><span data-ttu-id="eb2e6-104">Impacto</span><span class="sxs-lookup"><span data-stu-id="eb2e6-104">Impact</span></span>  
 <span data-ttu-id="eb2e6-105">Debido a este cambio:</span><span class="sxs-lookup"><span data-stu-id="eb2e6-105">As a result of this change:</span></span>  
  
-   <span data-ttu-id="eb2e6-106">El ancho o alto de los elementos puede aumentar o disminuir un píxel como máximo.</span><span class="sxs-lookup"><span data-stu-id="eb2e6-106">The width or height of elements may grow or shrink by at most one pixel.</span></span>  
  
-   <span data-ttu-id="eb2e6-107">La posición de un objeto se puede mover un píxel como máximo.</span><span class="sxs-lookup"><span data-stu-id="eb2e6-107">The placement of an object can move by at most one pixel.</span></span>  
  
-   <span data-ttu-id="eb2e6-108">Los elementos centrados pueden estar descentrados como máximo en un píxel en vertical o en horizontal.</span><span class="sxs-lookup"><span data-stu-id="eb2e6-108">Centered elements can be vertically or horizontally off center by at most one pixel.</span></span>  
  
 <span data-ttu-id="eb2e6-109">De forma predeterminada, este nuevo diseño solo está habilitado para las aplicaciones que tienen como destino .NET Framework 4.6.</span><span class="sxs-lookup"><span data-stu-id="eb2e6-109">By default, this new layout is enabled only for apps that target the .NET Framework 4.6.</span></span>  
  
## <a name="mitigation"></a><span data-ttu-id="eb2e6-110">Mitigación</span><span class="sxs-lookup"><span data-stu-id="eb2e6-110">Mitigation</span></span>  
 <span data-ttu-id="eb2e6-111">Dado que esta modificación tiende a eliminar el recorte de la parte derecha o inferior de los controles WPF en PPP altos, las aplicaciones destinadas a versiones anteriores de .NET Framework que se ejecutan en .NET Framework 4.6 pueden optar por este nuevo comportamiento agregando la siguiente línea a la sección `<runtime>` del archivo app.config:</span><span class="sxs-lookup"><span data-stu-id="eb2e6-111">Since this modification tends to eliminate clipping of the right or bottom of WPF controls at high DPIs, apps that target earlier versions of the .NET Framework but are running on the .NET Framework 4.6 can opt into this new behavior by adding the following line to the `<runtime>` section of the app.config file:</span></span>  
  
```xml  
<AppContextSwitchOverrides value="Switch.MS.Internal.DoNotApplyLayoutRoundingToMarginsAndBorderThickness=false" />  
```  
  
 <span data-ttu-id="eb2e6-112">Las aplicaciones que tienen como destino .NET Framework 4.6 y que desean que los controles WPF efectúen la representación con el algoritmo de diseño anterior pueden hacerlo agregando la siguiente línea a la sección `<runtime>` del archivo app.config:</span><span class="sxs-lookup"><span data-stu-id="eb2e6-112">Apps that target the .NET Framework 4.6 but want WPF controls to render using the previous layout algorithm can do so by adding the following line to the  `<runtime>` section of the app.config file:</span></span>  
  
```xml  
<AppContextSwitchOverrides value="Switch.MS.Internal.DoNotApplyLayoutRoundingToMarginsAndBorderThickness=true" />  
```  
  
## <a name="see-also"></a><span data-ttu-id="eb2e6-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="eb2e6-113">See also</span></span>

- [<span data-ttu-id="eb2e6-114">Cambios de redestinación</span><span class="sxs-lookup"><span data-stu-id="eb2e6-114">Retargeting Changes</span></span>](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-6.md)
