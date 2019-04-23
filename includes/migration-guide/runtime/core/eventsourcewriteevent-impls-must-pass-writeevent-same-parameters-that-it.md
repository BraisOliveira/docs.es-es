---
ms.openlocfilehash: 47d0aa554d88726caca35fa6bebe4d863fdc0695
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59235801"
---
### <a name="eventsourcewriteevent-impls-must-pass-writeevent-the-same-parameters-that-it-received-plus-id"></a><span data-ttu-id="21fdd-101">Las implementaciones EventSource.WriteEvent deben pasar a WriteEvent los mismos parámetros que recibió (además del identificador)</span><span class="sxs-lookup"><span data-stu-id="21fdd-101">EventSource.WriteEvent impls must pass WriteEvent the same parameters that it received (plus ID)</span></span>

|   |   |
|---|---|
|<span data-ttu-id="21fdd-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="21fdd-102">Details</span></span>|<span data-ttu-id="21fdd-103">El runtime ahora aplica el contrato que especifica lo siguiente: una clase derivada de <xref:System.Diagnostics.Tracing.EventSource?displayProperty=name> que define un método de evento ETW debe llamar al método <code>EventSource.WriteEvent</code> de la clase base con el identificador de evento, seguido de los mismos argumentos que se pasaron al método de evento ETW.</span><span class="sxs-lookup"><span data-stu-id="21fdd-103">The runtime now enforces the contract that specifies the following: A class derived from <xref:System.Diagnostics.Tracing.EventSource?displayProperty=name> that defines an ETW event method must call the base class <code>EventSource.WriteEvent</code> method with the event ID followed by the same arguments that the ETW event method was passed.</span></span>|
|<span data-ttu-id="21fdd-104">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="21fdd-104">Suggestion</span></span>|<span data-ttu-id="21fdd-105">Se produce una excepción <xref:System.IndexOutOfRangeException?displayProperty=name> si un objeto <xref:System.Diagnostics.Tracing.EventListener?displayProperty=name> lee datos <xref:System.Diagnostics.Tracing.EventSource?displayProperty=name> en proceso para un origen de eventos que infringe este contrato.</span><span class="sxs-lookup"><span data-stu-id="21fdd-105">An <xref:System.IndexOutOfRangeException?displayProperty=name> exception is thrown if an <xref:System.Diagnostics.Tracing.EventListener?displayProperty=name> reads <xref:System.Diagnostics.Tracing.EventSource?displayProperty=name> data in process for an event source that violates this contract.</span></span>|
|<span data-ttu-id="21fdd-106">Ámbito</span><span class="sxs-lookup"><span data-stu-id="21fdd-106">Scope</span></span>|<span data-ttu-id="21fdd-107">Secundaria</span><span class="sxs-lookup"><span data-stu-id="21fdd-107">Minor</span></span>|
|<span data-ttu-id="21fdd-108">Versión</span><span class="sxs-lookup"><span data-stu-id="21fdd-108">Version</span></span>|<span data-ttu-id="21fdd-109">4.5.1</span><span class="sxs-lookup"><span data-stu-id="21fdd-109">4.5.1</span></span>|
|<span data-ttu-id="21fdd-110">Tipo</span><span class="sxs-lookup"><span data-stu-id="21fdd-110">Type</span></span>|<span data-ttu-id="21fdd-111">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="21fdd-111">Runtime</span></span>|
