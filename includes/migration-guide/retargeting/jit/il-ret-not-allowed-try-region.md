---
ms.openlocfilehash: 060da3ebc60057554fd572bd2569652afee6bd0f
ms.sourcegitcommit: d55e14eb63588830c0ba1ea95a24ce6c57ef8c8c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/11/2019
ms.locfileid: "67804473"
---
### <a name="il-ret-not-allowed-in-a-try-region"></a><span data-ttu-id="136d2-101">No se permite ret de IL en una región try</span><span class="sxs-lookup"><span data-stu-id="136d2-101">IL ret not allowed in a try region</span></span>

|   |   |
|---|---|
|<span data-ttu-id="136d2-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="136d2-102">Details</span></span>|<span data-ttu-id="136d2-103">A diferencia del compilador Just-In-Time JIT64, RyuJIT (que se usa en .NET Framework 4.6) no admite una instrucción ret de nivel de integridad en una región try.</span><span class="sxs-lookup"><span data-stu-id="136d2-103">Unlike the JIT64 just-in-time compiler, RyuJIT (used in .NET Framework 4.6) does not allow an IL ret instruction in a try region.</span></span> <span data-ttu-id="136d2-104">Devolver desde una región try no permite la especificación de ECMA-335 y ningún compilador administrado conocido genera tal IL.</span><span class="sxs-lookup"><span data-stu-id="136d2-104">Returning from a try region is disallowed by the ECMA-335 specification, and no known managed compiler generates such IL.</span></span> <span data-ttu-id="136d2-105">Sin embargo, el compilador JIT64 ejecutará dicho IL si se genera mediante la emisión de reflexión.</span><span class="sxs-lookup"><span data-stu-id="136d2-105">However, the JIT64 compiler will execute such IL if it is generated using reflection emit.</span></span>|
|<span data-ttu-id="136d2-106">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="136d2-106">Suggestion</span></span>|<span data-ttu-id="136d2-107">Si una aplicación genera un IL que incluye un código de operación de ret en una región try, la aplicación puede tener como destino .NET Framework 4.5 para usar el JIT antiguo y evitar esta interrupción.</span><span class="sxs-lookup"><span data-stu-id="136d2-107">If an app is generating IL that includes a ret opcode in a try region, the app may target .NET Framework 4.5 to use the old JIT and avoid this break.</span></span> <span data-ttu-id="136d2-108">Como alternativa, se puede actualizar el IL generado para que devuelva después de la región try.</span><span class="sxs-lookup"><span data-stu-id="136d2-108">Alternatively, the generated IL may be updated to return after the try region.</span></span>|
|<span data-ttu-id="136d2-109">Ámbito</span><span class="sxs-lookup"><span data-stu-id="136d2-109">Scope</span></span>|<span data-ttu-id="136d2-110">Borde</span><span class="sxs-lookup"><span data-stu-id="136d2-110">Edge</span></span>|
|<span data-ttu-id="136d2-111">Versión</span><span class="sxs-lookup"><span data-stu-id="136d2-111">Version</span></span>|<span data-ttu-id="136d2-112">4.6</span><span class="sxs-lookup"><span data-stu-id="136d2-112">4.6</span></span>|
|<span data-ttu-id="136d2-113">Tipo</span><span class="sxs-lookup"><span data-stu-id="136d2-113">Type</span></span>|<span data-ttu-id="136d2-114">Redestinación</span><span class="sxs-lookup"><span data-stu-id="136d2-114">Retargeting</span></span>|

