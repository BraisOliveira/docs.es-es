---
title: Resumen del tipo de seguimiento
ms.date: 03/30/2017
ms.assetid: e639410b-d1d1-479c-b78e-a4701d4e4085
ms.openlocfilehash: 73777df2b58b14947c416ce409bcb42d439499ec
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61925156"
---
# <a name="trace-type-summary"></a><span data-ttu-id="7879c-102">Resumen del tipo de seguimiento</span><span class="sxs-lookup"><span data-stu-id="7879c-102">Trace Type Summary</span></span>
<span data-ttu-id="7879c-103">[Niveles de origen](https://go.microsoft.com/fwlink/?LinkID=94943) definen los distintos niveles de seguimiento: Crítico, Error, advertencia, información y detallado, así, proporciona una descripción de la `ActivityTracing` marca, que alterna el resultado de seguimiento de eventos de transferencia de actividad y el límite.</span><span class="sxs-lookup"><span data-stu-id="7879c-103">[Source Levels](https://go.microsoft.com/fwlink/?LinkID=94943) defines various trace levels: Critical, Error, Warning, Information, and Verbose, as well as provides description of the `ActivityTracing` flag, which toggles the output of trace boundary and activity transfer events.</span></span>  
  
 <span data-ttu-id="7879c-104">También puede revisar [TraceEventType](https://go.microsoft.com/fwlink/?LinkId=95169) para los tipos de seguimiento que se puede emitir desde <xref:System.Diagnostics>.</span><span class="sxs-lookup"><span data-stu-id="7879c-104">You can also review [TraceEventType](https://go.microsoft.com/fwlink/?LinkId=95169) for the types of traces which can be emitted from <xref:System.Diagnostics>.</span></span>  
  
 <span data-ttu-id="7879c-105">La tabla siguiente enumera los más importantes.</span><span class="sxs-lookup"><span data-stu-id="7879c-105">The following table lists the most important ones.</span></span>  
  
|<span data-ttu-id="7879c-106">Tipo de traza</span><span class="sxs-lookup"><span data-stu-id="7879c-106">Trace Type</span></span>|<span data-ttu-id="7879c-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="7879c-107">Description</span></span>|  
|----------------|-----------------|  
|<span data-ttu-id="7879c-108">Crítico</span><span class="sxs-lookup"><span data-stu-id="7879c-108">Critical</span></span>|<span data-ttu-id="7879c-109">Error irrecuperable o bloqueo de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="7879c-109">Fatal error or application crash.</span></span>|  
|<span data-ttu-id="7879c-110">Error</span><span class="sxs-lookup"><span data-stu-id="7879c-110">Error</span></span>|<span data-ttu-id="7879c-111">Error recuperable.</span><span class="sxs-lookup"><span data-stu-id="7879c-111">Recoverable error.</span></span>|  
|<span data-ttu-id="7879c-112">Advertencia</span><span class="sxs-lookup"><span data-stu-id="7879c-112">Warning</span></span>|<span data-ttu-id="7879c-113">Mensaje informativo.</span><span class="sxs-lookup"><span data-stu-id="7879c-113">Informational message.</span></span>|  
|<span data-ttu-id="7879c-114">Información</span><span class="sxs-lookup"><span data-stu-id="7879c-114">Information</span></span>|<span data-ttu-id="7879c-115">Problema no crítico.</span><span class="sxs-lookup"><span data-stu-id="7879c-115">Non-critical problem.</span></span>|  
|<span data-ttu-id="7879c-116">Detallado</span><span class="sxs-lookup"><span data-stu-id="7879c-116">Verbose</span></span>|<span data-ttu-id="7879c-117">Traza de depuración.</span><span class="sxs-lookup"><span data-stu-id="7879c-117">Debugging trace.</span></span>|  
|<span data-ttu-id="7879c-118">Iniciar</span><span class="sxs-lookup"><span data-stu-id="7879c-118">Start</span></span>|<span data-ttu-id="7879c-119">Inicio de una unidad lógica de procesamiento.</span><span class="sxs-lookup"><span data-stu-id="7879c-119">Starting of a logical unit of processing.</span></span>|  
|<span data-ttu-id="7879c-120">Suspender</span><span class="sxs-lookup"><span data-stu-id="7879c-120">Suspend</span></span>|<span data-ttu-id="7879c-121">Suspensión de una unidad lógica de procesamiento.</span><span class="sxs-lookup"><span data-stu-id="7879c-121">Suspension of a logical unit of processing.</span></span>|  
|<span data-ttu-id="7879c-122">Reanudar</span><span class="sxs-lookup"><span data-stu-id="7879c-122">Resume</span></span>|<span data-ttu-id="7879c-123">Reanudación de una unidad lógica de procesamiento.</span><span class="sxs-lookup"><span data-stu-id="7879c-123">Resumption of a logical unit of processing.</span></span>|  
|<span data-ttu-id="7879c-124">Detener</span><span class="sxs-lookup"><span data-stu-id="7879c-124">Stop</span></span>|<span data-ttu-id="7879c-125">Detención de una unidad lógica de procesamiento.</span><span class="sxs-lookup"><span data-stu-id="7879c-125">Stopping of a logical unit of processing.</span></span>|  
|<span data-ttu-id="7879c-126">Transferir</span><span class="sxs-lookup"><span data-stu-id="7879c-126">Transfer</span></span>|<span data-ttu-id="7879c-127">Cambio de la identidad de correlación.</span><span class="sxs-lookup"><span data-stu-id="7879c-127">Changing of correlation identity.</span></span>|  
  
 <span data-ttu-id="7879c-128">Una actividad se define como una combinación de los tipos de trazas anteriores.</span><span class="sxs-lookup"><span data-stu-id="7879c-128">An activity is defined as a combination of the trace types above.</span></span>  
  
 <span data-ttu-id="7879c-129">La siguiente expresión se utiliza habitualmente para definir una actividad ideal en un ámbito local (origen de la traza),</span><span class="sxs-lookup"><span data-stu-id="7879c-129">The following is a regular expression that defines an ideal activity in a local (trace source) scope,</span></span>  
  
 `R = Start (Critical | Error | Warning | Information | Verbose | Transfer | (Transfer Suspend Transfer Resume) )* Stop`  
  
 <span data-ttu-id="7879c-130">Esto significa que una actividad debe satisfacer las condiciones siguientes.</span><span class="sxs-lookup"><span data-stu-id="7879c-130">This means that an activity must satisfy the following conditions.</span></span>  
  
- <span data-ttu-id="7879c-131">Debe iniciarse y detenerse por trazas de inicio y detención, respectivamente</span><span class="sxs-lookup"><span data-stu-id="7879c-131">It must start and stop respectively by a Start and Stop traces</span></span>  
  
- <span data-ttu-id="7879c-132">Debe tener una traza de transferencia que preceda inmediatamente a una traza de suspensión o reanudación</span><span class="sxs-lookup"><span data-stu-id="7879c-132">It must have a Transfer trace immediately preceding a Suspend or Resume trace</span></span>  
  
- <span data-ttu-id="7879c-133">No debe presentar traza alguna entre las trazas de suspensión y reanudación, en caso de que éstas existan</span><span class="sxs-lookup"><span data-stu-id="7879c-133">It must not have any traces between the Suspend and Resume traces if such traces exist</span></span>  
  
- <span data-ttu-id="7879c-134">Puede tener cuantas trazas crítico/error/advertencia/información/detalles/transferencia, siempre y cuando se cumplan las condiciones anteriores</span><span class="sxs-lookup"><span data-stu-id="7879c-134">It can have any and as many of critical/Error/Warning/Information/Verbose/Transfer traces as long as the previous conditions are observed</span></span>  
  
 <span data-ttu-id="7879c-135">La siguiente expresión se utiliza habitualmente para definir una actividad ideal en el ámbito global,</span><span class="sxs-lookup"><span data-stu-id="7879c-135">The following is a regular expression that defines an ideal activity in the global scope,</span></span>  
  
```  
R+   
```  
  
 <span data-ttu-id="7879c-136">en la que R es la expresión regular para una actividad en el ámbito local.</span><span class="sxs-lookup"><span data-stu-id="7879c-136">with R being the regular expression for an activity in the local scope.</span></span> <span data-ttu-id="7879c-137">Esto se traduce en,</span><span class="sxs-lookup"><span data-stu-id="7879c-137">This translates to,</span></span>  
  
```  
[R+ = Start ( Critical | Error | Warning | Information | Verbose | Transfer | (Transfer Suspend Transfer Resume) )* Stop]+  
```
