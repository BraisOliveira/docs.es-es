---
ms.openlocfilehash: 47d0aa554d88726caca35fa6bebe4d863fdc0695
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59805104"
---
### <a name="eventsourcewriteevent-impls-must-pass-writeevent-the-same-parameters-that-it-received-plus-id"></a><span data-ttu-id="0f9cf-101">Las implementaciones EventSource.WriteEvent deben pasar a WriteEvent los mismos parámetros que recibió (además del identificador)</span><span class="sxs-lookup"><span data-stu-id="0f9cf-101">EventSource.WriteEvent impls must pass WriteEvent the same parameters that it received (plus ID)</span></span>

|   |   |
|---|---|
|<span data-ttu-id="0f9cf-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="0f9cf-102">Details</span></span>|<span data-ttu-id="0f9cf-103">El runtime ahora aplica el contrato que especifica lo siguiente: una clase derivada de <xref:System.Diagnostics.Tracing.EventSource?displayProperty=name> que define un método de evento ETW debe llamar al método <code>EventSource.WriteEvent</code> de la clase base con el identificador de evento, seguido de los mismos argumentos que se pasaron al método de evento ETW.</span><span class="sxs-lookup"><span data-stu-id="0f9cf-103">The runtime now enforces the contract that specifies the following: A class derived from <xref:System.Diagnostics.Tracing.EventSource?displayProperty=name> that defines an ETW event method must call the base class <code>EventSource.WriteEvent</code> method with the event ID followed by the same arguments that the ETW event method was passed.</span></span>|
|<span data-ttu-id="0f9cf-104">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="0f9cf-104">Suggestion</span></span>|<span data-ttu-id="0f9cf-105">Se produce una excepción <xref:System.IndexOutOfRangeException?displayProperty=name> si un objeto <xref:System.Diagnostics.Tracing.EventListener?displayProperty=name> lee datos <xref:System.Diagnostics.Tracing.EventSource?displayProperty=name> en proceso para un origen de eventos que infringe este contrato.</span><span class="sxs-lookup"><span data-stu-id="0f9cf-105">An <xref:System.IndexOutOfRangeException?displayProperty=name> exception is thrown if an <xref:System.Diagnostics.Tracing.EventListener?displayProperty=name> reads <xref:System.Diagnostics.Tracing.EventSource?displayProperty=name> data in process for an event source that violates this contract.</span></span>|
|<span data-ttu-id="0f9cf-106">Ámbito</span><span class="sxs-lookup"><span data-stu-id="0f9cf-106">Scope</span></span>|<span data-ttu-id="0f9cf-107">Secundaria</span><span class="sxs-lookup"><span data-stu-id="0f9cf-107">Minor</span></span>|
|<span data-ttu-id="0f9cf-108">Versión</span><span class="sxs-lookup"><span data-stu-id="0f9cf-108">Version</span></span>|<span data-ttu-id="0f9cf-109">4.5.1</span><span class="sxs-lookup"><span data-stu-id="0f9cf-109">4.5.1</span></span>|
|<span data-ttu-id="0f9cf-110">Tipo</span><span class="sxs-lookup"><span data-stu-id="0f9cf-110">Type</span></span>|<span data-ttu-id="0f9cf-111">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="0f9cf-111">Runtime</span></span>|
