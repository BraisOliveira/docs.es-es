---
title: 'Mitigación: serialización de caracteres de control con DataContractJsonSerializer'
ms.date: 04/07/2017
helpviewer_keywords:
- .NET Framework 4.7 retargeting changes
- retargeting changes
- DataContractJsonSerializer changes
- serialization changes
ms.assetid: e065d458-a128-44f2-9f17-66af9d5be954
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 12b26c8cc01b7af1c3b345d2f274a1d25a19d689
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70789845"
---
# <a name="mitigation-serialization-of-control-characters-with-the-datacontractjsonserializer"></a><span data-ttu-id="89469-102">Mitigación: serialización de caracteres de control con DataContractJsonSerializer</span><span class="sxs-lookup"><span data-stu-id="89469-102">Mitigation: Serialization of Control Characters with the DataContractJsonSerializer</span></span>

<span data-ttu-id="89469-103">A partir de NET Framework 4.7, ha cambiado la forma en la que se serializan los caracteres de control con <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> para que sean conformes con ECMAScript V6 y V8.</span><span class="sxs-lookup"><span data-stu-id="89469-103">Starting with the .NET Framework 4.7, the way in which control characters are serialized with the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> has changed to conform to ECMAScript V6 and V8.</span></span> 
 
## <a name="impact"></a><span data-ttu-id="89469-104">Impacto</span><span class="sxs-lookup"><span data-stu-id="89469-104">Impact</span></span>

<span data-ttu-id="89469-105">En .NET Framework 4.6.2 y versiones anteriores, el elemento <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> no serializaba algunos caracteres de control especiales, como `\b`, `\f` y `\t`, de forma que era compatible con los estándares de ECMAScript V6 y V8.</span><span class="sxs-lookup"><span data-stu-id="89469-105">In the .NET framework 4.6.2 and earlier versions, the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> did not serialize some special control characters, such as `\b`, `\f`, and `\t`, in a way that was compatible with the ECMAScript V6 and V8 standards.</span></span>

<span data-ttu-id="89469-106">Para las aplicaciones destinadas a versiones de .NET Framework a partir de .NET Framework 4.7, la serialización de estos caracteres de control es compatible con ECMAScript V6 y V8.</span><span class="sxs-lookup"><span data-stu-id="89469-106">For apps that target versions of the .NET Framework starting with the .NET Framework 4.7, serialization of these control characters is compatible with ECMAScript V6 and V8.</span></span> <span data-ttu-id="89469-107">Afecta a las siguientes API:</span><span class="sxs-lookup"><span data-stu-id="89469-107">The following APIs are affected:</span></span>

- <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.WriteObject%2A> 

## <a name="mitigation"></a><span data-ttu-id="89469-108">Mitigación</span><span class="sxs-lookup"><span data-stu-id="89469-108">Mitigation</span></span>

<span data-ttu-id="89469-109">Para aplicaciones destinadas a versiones de .NET Framework a partir de .NET Framework 4.7, este comportamiento está habilitado de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="89469-109">For apps that target versions of the .NET Framework starting with the .NET Framework 4.7, this behavior is enabled by default.</span></span>

<span data-ttu-id="89469-110">Si no desea este compartimiento, puede rechazar esta característica agregando la siguiente línea a la sección `<runtime>` del archivo app.config o web.config:</span><span class="sxs-lookup"><span data-stu-id="89469-110">If this behavior is not desirable, you can opt out of this feature by adding the following line to the `<runtime>` section of the app.config or web.config file:</span></span>

```xml
<runtime>
   <AppContextSwitchOverrides value="Switch.System.Runtime.Serialization.DoNotUseECMAScriptV6EscapeControlCharacter=false" />
</runtime>
```
 
## <a name="see-also"></a><span data-ttu-id="89469-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="89469-111">See also</span></span>

- [<span data-ttu-id="89469-112">Cambios de redestinación en .NET Framework 4.7</span><span class="sxs-lookup"><span data-stu-id="89469-112">Retargeting Changes in the .NET Framework 4.7</span></span>](retargeting-changes-in-the-net-framework-4-7.md)
